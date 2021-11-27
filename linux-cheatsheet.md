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
