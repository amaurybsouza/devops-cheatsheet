## Ansible Ad-hoc commands

### `Basic commands`

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

### `Ad-hoc [File Transfer]`

```
ansible [server] -m copy -a "src=/etc/hosts dest=/tmp/hosts" - Copia o arquivo para outro servidor desejado
ansible [server] -m file -a "dest=/srv/foo/a.txt mode=600" - Para mudar as permissões de um arquivo no servidor remoto
ansible [server] -m file -a "dest=/srv/foo/b.txt mode=600 owner=example group=example" - Para mudar as permissões e o dono/grupo de um arquivo no servidor remoto
ansible [server] -m file -a "dest=/path/to/c mode=755 owner=example group=example state=directory" - Cria um diretório no servidor remoto
ansible [server] -m file -a "dest=/path/to/c state=absent" - Para desinstalar um pacote no servidor remoto
```

### `Ad-hoc [Manage services]`

```
ansible [server] -m service -a "name=httpd state=started" - Inicia o service desejado.
ansible [server] -m service -a "name=httpd state=restarted" - Restarta o service desejado.
ansible [server] -m service -a "name=httpd state=stopped" - Pausa o service desejado.
```

### `Ad-hoc [Manage packages]`

```
ansible [server] -m apt -a "name=giropops state=present" - Instala o pacote desejado no servidor
ansible [server] -m apt -a "name=giropops-1.2 state=present" - Instala o pacote com a versão desejada
ansible [server] -m apt -a "name=giropops state=latest" - Instala a última versão do pacote desejado
ansible [server] -m apt -a "name=giropops state=absent" - Desinstala o pacote desejado no servidor
```

### `Ad-hoc [Rebooting servers]`

```
ansible atlanta -a "/sbin/reboot" - To reboot all the servers in the [atlanta] group
ansible atlanta -a "/sbin/reboot" -f 10 - To reboot the [atlanta] servers with 10 parallel forks:
ansible atlanta -a "/sbin/reboot" -f 10 -u username - To connect as a different user
```

### `Ad-hoc [Create user and groups]`

```
ansible [server] -s -m group -a "name=admin state=present" - Cria um grupo no servidor remoto
ansible [server] -s -m user -a "name=giropops group=admin createhome=yes" - Cria um usuário do grupo no servidor remoto
ansible [server] -m user -a "name=giropops password=strigus" - Cria um usuário com senha no servidor remoto
ansible [server] -a "id giropops" - Confirma a criação no servidor
ansible [server] -s -m user -a "name=giropops state=absent" - Deleta um usuário no servidor remoto
```

## Ansible Playbooks

### `Ansible playbooks [Verifying playbooks]`

```
ansible-playbook playbook.yml --list-hosts - lista todos os hosts afetados nesse playbook
ansible-playbook playbook.yml --check - executa o playbook em modo de check sem dar apply 
ansible-playbook playbook.yml --list-tasks - lista as tarefas do playbook
ansible-playbook playbook.yml --syntax-check - executa uma verifcacao da sintaxe do YML para do playbook
ansible-playbook --tags=cps playbooks/systems/priority.yml -i inventory.yml
```
