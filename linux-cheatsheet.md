## Linux cheatsheet for DevOps community

### `File managing`

```
pwd - Mostra em qual diretorio você está
cd [caminho_ou_nome_diretorio] - Vai para o diretório desejado
cd .. - Vai para o diretório anterior
cd ~ - Vai para o diretório home do usúario
cd / - Vai para o diretório raiz
cd - - Volta para o último diretório que o usúario estava
```

### `Linux installation`

```
#/ (root) filesystem
#/var filesystem (sempre separado numa partição especifica, fila de impressão, de e-mail, logs pode ocupar muito espaço e é bom separar esse diretório)
#/home filesystem (diretório que ficam os arquivos dos usuários, tem que isolar essa partição, para que ele fique separado, não impactando outras partições e aplicações)
#/boot filesystem (diretório que tem o kernel, initrd, carregados pelo GRUB, )
#swap space (é usado no windows, linux, espaço no hd que serve para uma ram temporária caso a ram principal fique completamente cheia)
```

### `Partitions`

```
- partições comuns:
  /home  (arquivos dos usuários, isolar numa partição, para que os dados dos usuários não cause impactos na aplicação)
  /var   (arquivos temporários, filas de impressão, de e-mail)
  /tmp   (arquivos temporários)
  /boot  (bootloader, kernel, initrd, carregados pelo grub)
  /usr   (aplicação, arquivos de aplicação, programas)

- partições que podem estar fora do /
  /etc   (arquivos de configuração do sistema, fstab)
  /bin   (ficam os comandos, scripts, para ver as partições, ver os diretórios, processos do sistema)
  /sbin  (ficam os comandos, scripts, para ver as partições, ver os diretórios, processos do sistema)
  /dev
  /proc
  /sys
```

### `Systems variables`

```
HISTFILE=/root/.bash_history   (caminho que armazena os comandos feitos no terminal)
HISTFILESIZE=2000  (tamanho maximo que o arquivo terá)
HISTSIZE=1000   (limite maximo de linhas "comandos" no arquivo)
HOME=/root (mostra o home do usuário atual)
HOSTNAME=souza  (hostiname da máquina)
LOGNAME=root (mostra o nome do usuario que fez login no sistema)
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin (mostra todos os caminhos de programas do sistema)
PWD=/home/borges/Downloads    (mostra o diretório atual)
SHELL=/bin/bash (mostra o shell que está sendo usado)
TERM=xterm-256color (mostra qual terminal estamos usando)
USER=root (mostra o nome do usuário atual)
```
