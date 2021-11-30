## Ansible cheatsheet for DevOps community

### `Basic commands`

```
ansible [all_servers] -m ping - Verifica se todos os servidores estão funcionando
ansible [all_servers] -a hostname - Printa todos os hostnames dos servidores
ansible [all_servers] -a uptime - Confere a quanto tempo os servers estão em pé
ansible [server] -a free - Verifica o espaço em disco do servidor
ansible [all_servers] -f 1 -a "free" - Roda um comando um servidor por vez
```

### `Ad-hoc [File Transfer]`

```
ansible [server] -m copy -a "src=/etc/hosts dest=/tmp/hosts" -
Copia o arquivo para outro servidor desejado
ansible [server] -m file -a "dest=/srv/foo/a.txt mode=600" -
Para mudar as permissões de um arquivo no servidor remoto
ansible [server] -m file -a "dest=/srv/foo/b.txt mode=600 owner=example group=example" -
Para mudar as permissões e o dono/grupo de um arquivo no servidor remoto
ansible [server] -m file -a "dest=/path/to/c mode=755 owner=example group=example state=directory"
Cria um diretório no servidor remoto
ansible [server] -m file -a "dest=/path/to/c state=absent" -
Para desinstalar um pacote no servidor remoto

```
