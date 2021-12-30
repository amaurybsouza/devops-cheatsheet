## Linux cheatsheet for DevOps community

### `Basic commands`

```
pwd (Mostra em qual diretorio você está)
cd [caminho_ou_nome_diretorio] (Vai para o diretório desejado)
cd .. (Vai para o diretório anterior)
cd ~ (Vai para o diretório home do usúario)
cd / (Vai para o diretório raiz)
cd - (Volta para o último diretório que o usúario estava)
ls -a (arquivos ocultos)
ls -ld (lista detalhadamente o diretório sem mostrar o conteudo)
ls -l (lista de forma de lista os arquivos e diretórios)
ls -h (lista de forma mais ligível mostrando o formato do arquivo ou diretório) 
ls -lR (lista de forma recursiva cada diretório e todo o conteudo)
ls -l aula1* (mostra tudo depois de asterisco)
mkdir [nome_do_diretorio_desejado] (Cria um diretório com o nome desejado)
mkdir ~/[nome_do_diretorio_desejado] (Irá criar o diretório desejado na home)
rmdir [nome_diretório] (Deleta APENAS diretório vazio)
cat [arquivo_ou_caminho_arquivo] (Mostra o conteúdo do arquivo)
cat [arquivo] > [arquivo2] (Faz uma cópia do arquivo)
cat [arquivo] >> [arquivo2] (Acrescenta um arquivo ao outro)
more [nome_arquivo] (Mostra o conteúdo de um arquivo)
less [nome_arquivo] (Abre um páginador de arquivo navegável)
cp -i [arquivo_origem] [arquivo_destino] (Pergunta antes de copiar cada arquivo)
cp -R [diretorio_origem] [diretorio_destino] (Copia o diretório recursivamente)
mv [arquivo] [diretório_destino] (Move um arquivo)
mv [arquivo_antigo] [arquivo_novo] (Renomeia um arquivo)
```

### `Package management (RHEL based)`
```
rpm  (é o equivalente ao dpkg do Debian, ele que faz a base de instalação e remoção dos pacotes)
MODOS (O rpm trabalha em modos, COM 3 MODOS PRINCIPAIS (modeo de consulta, instalacao e remocao)
rpm -qa (mostra todos os pacotes instalados no sistema)
rpm -qa bash (mostra informações do que tiver o nome "bash")
rpm -qi bash (a opção i mostra informações, detalhes  do aplicativo mencionado, no caso o "bash")
rpm -ql bash (lista os arquivos que pertecem a essa instalação)
rpm -qc bash (mostra apenas os arquivos de configuração do pacote)
rpm -qd (mostra arquivos de documentação do pacote)
rpm -qf /etc/skel/.bashrc (mostra qual aplicação instalou esse pacote, esse arquivo)
rpm -qlp adobe-release-x86_64-1.0-1.noarch.rpm (lista os arquivos que estão dentro do pacote adobe)
rpm -i adobe-release-x86_64-1.0-1.noarch.rpm (instala essa aplicação, esse pacote)
rpm -U adobe-release-x86_64-1.0-1.noarch.rpm (faz o update, atualiza a versão do pacote)
principais opções usadas com o -i (v e h) (verbose e hash - cerquilhas)
rpm -ivh skypeforlinux-64.rpm (instala o pacote, mostra os detalhes da instalação e mostra os hash (cerquilhas durante a instalação))
rpm -qa skypeforlinux (lista o pacote)
rpm -ivh gcc-8.1.1-1.fc29.aarch64.rpm (esse pacote precisa de dependência para ser instalado)
rpm -ivh --nodeps gcc-8.1.1-1.fc29.aarch64.rpm (força a instalação do pacote sem verificar as dependências)
rpm -ivh --test skypeforlinux-64.rpm (essa opção testa e não faz a instalação de fato)
rpm -e ksh (remove o pacote ksh)
rpm -evh ksh (remove o pacote ksh, usando o verbose e o hash, mostrando melhor o resultado da remoção)
rpm -evh --teste gcc (simula a remoção do pacote gcc, mas não remove de fato)
rpm2cpio (ele transforma um arquivo rpm em cpio, de agrupamento de arquivos)
rpm2cpio gcc-8.1.1-1.fc29.aarch64.rpm > gcc.cpio (é uma forma de extrair o que tem dentro do pacote rpm)
/etc/yum.conf (principal arquivo de configuração do yum)
/etc/yum.repos.d/ (diretório que contém as fontes de pacotes, repositório, que o yum vai consultar)
yum (comando equivalente ao apt-get do Debian, ele faz download, instalação, verificação de dependências dos pacotes)
yum install gcc (instala o pacote gcc e suas dependências)
yum update (atualiza todos os pacotes do sistema, fontes novas)
yum upgrade (atualiza os pacotes e ainda, remove pacotes obsoletos do sistema)
yum check-update (checa todos os pacotes e verifica qual precisa de update, em relação a base de origem)
yum list (lista todos os pacotes que estão instalados no sistema)
yum search samba (mostra todos os pacotes que são relacionados ao samba)
yum remove ksh (remove o pacote ksh)
yumdownloader (é uma ferramenta do yum, normalmente não vem instalado como padrão no sistema)
yumdownloader csh (faz o download do pacote csh)
```

### `Package management (Debian based)`
```
/etc/apt/sources.list (é nesse arquivo que contem todas as fontes, é daqui que o apt-get faz o download da versão correta dos programas)
dpkg (instala e manipula arquivos .deb. Ele também faz operações de consultas em pacotes já instalados)
Opções:
-i : instala um pacote.
-x : extrai conteúdo de um pacote.
-r : remove um pacote, mas mantem os arquivos de configuração do pacote.
-P : --purge - remove completamente o pacote e arquivos de configuração.
-l : lista pacotes instalados.
-c : exibe o conteúdo de um arquivo de pacote .deb. ou --contents (não instalado)
-L : lista os arquivos que pertencem a tal pacote.
-S : exibe quais arquivos foram copiados para o sistema após a instalação do pacote.
-s : exibe o status do pacote.(instalado no sistema)
-p : exibe informações detalhadas sobre pacote já instalado.
--get-selections : lista todos os pacotes instalados.
-I : mostra informações sobre um pacote não instalado.
dpkg -i ldap-utils_2.4.21-0ubuntu5.2_i386.deb (Instala o pacote 'ldap-utils' através de um arquivo de pacote .deb.)
dpkg -r samba (Remove o pacote samba sem remover seus arquivos)
dpkg -c ldap-utils_2.4.21-0ubuntu5.2_i386.deb (Mostra o conteúdo do arquivo de pacote)
dpkg -p samba (Mostra detalhes sobre o pacote samba, que já está instalado)
dpkg-reconfigure (é usado para imprimir pacotes que exigem uma interação de configuração com o usuário)
dselect (é uma interface gráfica do apt, em modo texto, seleciona os pacotes para remover, instalar)
apt-get (os comandos do apt tem um repositório, um conjunto de URL, onde ele consulta os pacotes e softwares que se pretende instalar ou remover)
apt-get update (obtém informações atualizadas das fontes)
apt-get upgrade (realiza a atualização de todos os pacotes)
apt-get dist-upgrade (realiza a atualização de todos os pacotes, desde que não haja quebra de dependências)
apt-get install (Instala um pacote e suas dependências a partir de repositórios que estão listados dentro de /etc/apt/sources.list)
apt-get install zsh (instala esse pacote, verifica a versão mais atual, a origem, de onde ele vai fazer download e quais os pacotes dependentes).
Opções:
-s : simula a instalação do pacote.
-d: apenas faz o download dos pacotes para o diretório /var/cache/apt/archives/.
-y : assume como “Yes” todas as respostas de instalação.
--reinstall : reinstala um pacote
apt-get purge (remove o pacote e os arquivos de configuração)
apt-get check (verifica as consistencias checa a base de dados do gerenciador de pacotes)
apt-get clean (remove algum arquivo temporário e faz uma limpeza na base de dados)
apt-get --download-only install zsh (faz o download do pacote, não instala)
apt-cache (comando utilizado para mostrar as informações que ele tem na base de dados dele, na base de pacotes debian dele)
apt-cache pkgnames (lista de pacotes instalados no sistema)
apt-cache show vim (mostra as informações do vim, dependencias, descriçao dele, e outras informações)
aptitude (ele tbm tem uma interface gráfica através de menus, mais complexa que o dselect)
alien (ele converte e instala pacotes binários alien)
aptitude purge csh (remove o pacote csh e todos os arquivos de configuração)
aptitude search csh (pesquisa todos os pacotes que tem csh no nome dos pacotes, é bom que vc verifica qual o pacote ideal para se instalar)
alien -r zsh_5.1.1-3_amd64.deb  (transforma esse pacote .deb em um pacote rpm para Red Hat)
alien -i zsh-5.1.1-4.x86_64.rpm (instala o pacote, o sistema debian instala o pacote rpm, executa o dpkg)
```

### `Miscelanious commands`

```
$ echo Hello There | tr [:lower:] [:upper:]
HELLO THERE
```

### `Linux installation`

``` 
/ (root) filesystem
/var filesystem (sempre separado numa partição especifica, fila de impressão, de e-mail, logs pode ocupar muito espaço e é bom separar esse diretório)
/home filesystem (diretório que ficam os arquivos dos usuários, tem que isolar essa partição, para que ele fique separado, não impactando outras partições e aplicações)
/boot filesystem (diretório que tem o kernel, initrd, carregados pelo GRUB, )
swap space (é usado no windows, linux, espaço no hd que serve para uma ram temporária caso a ram principal fique completamente cheia)
```

### `Partitions`

```
- partições comuns:
  /home  (arquivos dos usuários, isolar numa partição, para que os dados dos usuários não cause impactos na aplicação)
  /var   (arquivos temporários, filas de impressão, de e-mail)
  /tmp   (arquivos temporários)
  /boot  (bootloader, kernel, initrd, carregados pelo grub)
  /usr   (aplicação, arquivos de aplicação, programas)

- partições que podem estar fora do diretorio /
  /etc   (arquivos de configuração do sistema, fstab)
  /bin   (ficam os comandos, scripts, para ver as partições, ver os diretórios, processos do sistema)
  /sbin  (ficam os comandos, scripts, para ver as partições, ver os diretórios, processos do sistema)
```

### `Systems variables`

```
HISTFILE=/root/.bash_history  (caminho que armazena os comandos feitos no terminal)
HISTFILESIZE=2000  (tamanho maximo que o arquivo terá)
HISTSIZE=1000   (limite maximo de linhas "comandos" no arquivo)
HOME=/root (mostra o home do usuário atual)
HOSTNAME=souza  (hostname da máquina)
LOGNAME=root (mostra o nome do usuario que fez login no sistema)
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin (mostra todos os caminhos de programas do sistema)
PWD=/home/borges/Downloads    (mostra o diretório atual)
SHELL=/bin/bash (mostra o shell que está sendo usado)
TERM=xterm-256color (mostra qual terminal estamos usando)
USER=root (mostra o nome do usuário atual)
```
