## Linux cheatsheet for DevOps community

### `Basic commands`

```bash
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

### `Miscelanious commands`
```bash
$ echo Hello There | tr [:lower:] [:upper:]
HELLO THERE
```

### `Linux installation`

``` bash
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
