# Ansible Cycle Tool
Ansible is an open-source configuration management and automation tool that allows users to manage and deploy software applications and infrastructure at scale. It was created by Michael DeHaan in 2012 and is now maintained by Red Hat.

## Ansible Hosts
The hosts file typically contains the IP addresses or hostnames of the remote machines, along with some configuration information, such as the username and password required for authentication. Ansible uses the information in the hosts file to connect to the remote machines, run commands, and apply configurations.

- Below you can check a basic way to set the localhost into the Ansible hosts file
```bash
[local]
#ensure you have your own machine to manage with Ansible
127.0.0.1 ansible_connection=local
```

- Below you can check a basic way to set your `homelab` into the file:
```bash
[devops-lab]
192.168.1.110 ansible_ssh_user=devopslab ansible_password=password
```

- Below you can check a basic way to set your AWS EC2 instances into the file:
```
[aws]
target1 ansible_ssh_user=ubuntu ansible_ssh_host=18.213.245.111  ansible_ssh_private_key_file=aws-key
```

Please feel free to ge the Ansible Hosts file [here](https://github.com/ansible/ansible/blob/devel/examples/hosts.yaml).

## Ad-hoc Basics
In Ansible, an ad-hoc command is a one-time, on-demand command that you can run on one or more remote hosts without having to write a playbook. It allows you to perform quick, simple tasks such as checking the uptime of a host, installing a package, or copying a file, without the need for a full-blown playbook.

```
ansible [all_servers] -m ping - Verifica se todos os servidores estão funcionando
ansible [all_servers] -a hostname - Printa todos os hostnames dos servidores
ansible [all_servers] -a uptime - Confere a quanto tempo os servers estão em pé
ansible [server] -a free - Verifica o espaço em disco do servidor
ansible [all_servers] -f 1 -a "free" - Roda um comando um servidor por vez
ansible prod -b -m shell -a "df -h /var" -i inventory.yml - executa o comando df -h no host remoto
ansible prod -b -m shell -a "find /var -mount -size +100M -exec du -sh {} \;" -i inventory.yml - executa o comando find no host remoto
ansible prod -b -m shell -a "rm -rf /var/cache/yum/" -i inventory.yml - remove o cche do yum no host remoto
ansible prod -b -m shell -a "ls -l /var/log/audit | tail -n 15" -i inventory.yml - executa o comando de listar arquivos no host remoto
```

### Ad-hoc File Transfer
```
ansible [server] -m copy -a "src=/etc/hosts dest=/tmp/hosts" - Copia o arquivo para outro servidor desejado
ansible [server] -m file -a "dest=/srv/foo/a.txt mode=600" - Para mudar as permissões de um arquivo no servidor remoto
ansible [server] -m file -a "dest=/srv/foo/b.txt mode=600 owner=example group=example" - Para mudar as permissões e o dono/grupo de um arquivo no servidor remoto
ansible [server] -m file -a "dest=/path/to/c mode=755 owner=example group=example state=directory" - Cria um diretório no servidor remoto
ansible [server] -m file -a "dest=/path/to/c state=absent" - Para desinstalar um pacote no servidor remoto
```

### Ad-hoc Manage services
```
ansible [server] -m service -a "name=httpd state=started" - Inicia o service desejado.
ansible [server] -m service -a "name=httpd state=restarted" - Restarta o service desejado.
ansible [server] -m service -a "name=httpd state=stopped" - Pausa o service desejado.
```

### Ad-hoc Manage packages
```
ansible [server] -m apt -a "name=giropops state=present" - Instala o pacote desejado no servidor
ansible [server] -m apt -a "name=giropops-1.2 state=present" - Instala o pacote com a versão desejada
ansible [server] -m apt -a "name=giropops state=latest" - Instala a última versão do pacote desejado
ansible [server] -m apt -a "name=giropops state=absent" - Desinstala o pacote desejado no servidor
```

### Ad-hoc Rebooting servers
```
ansible atlanta -a "/sbin/reboot" - To reboot all the servers in the [atlanta] group
ansible atlanta -a "/sbin/reboot" -f 10 - To reboot the [atlanta] servers with 10 parallel forks:
ansible atlanta -a "/sbin/reboot" -f 10 -u username - To connect as a different user
```

### Ad-hoc Create user and groups
```
ansible [server] -s -m group -a "name=admin state=present" - Cria um grupo no servidor remoto
ansible [server] -s -m user -a "name=giropops group=admin createhome=yes" - Cria um usuário do grupo no servidor remoto
ansible [server] -m user -a "name=giropops password=strigus" - Cria um usuário com senha no servidor remoto
ansible [server] -a "id giropops" - Confirma a criação no servidor
ansible [server] -s -m user -a "name=giropops state=absent" - Deleta um usuário no servidor remoto
```

## Ansible Playbooks

### Ansible playbooks Verifying playbooks
```
ansible-playbook playbook.yml --list-hosts - lista todos os hosts afetados nesse playbook
ansible-playbook playbook.yml --check - executa o playbook em modo de check sem dar apply 
ansible-playbook playbook.yml --list-tasks - lista as tarefas do playbook
ansible-playbook playbook.yml --syntax-check - executa uma verifcacao da sintaxe do YML para do playbook
ansible-playbook --tags=cps playbooks/systems/priority.yml -i inventory.yml
```
