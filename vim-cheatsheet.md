### `Basic navegation`

```
h - Move o cursor pra esquerda
j - Move o cursor pra baixo
k - Move o cursor pra cima
l (L minúsculo) - Move o cursor pra direita
H - Move o cursor para o topo da tela
M - Move o cursor para o meio da tela
L - Move o cursor para o final da tela
w - Navega entre a primeira letra de cada palavra
e - Navega entre a última letra de cada palavra
b - Navega em reverso entre a primeira letra de cada palavra
ge - Navega em reverso entre a última letra de cada palavra
0 (zero) - Volta para o começo da linha
$ - Vai para o final da linha
gg - Vai para a primeira linha do arquivo
G - Vai para a última linha do arquivo
10G ou 10gg - Vai para a linha desejada (nesse caso a décima linha)
} - Vai para o próximo parágrafo
{ - Vai para o parágrafo anterior
zz - Centraliza o cursor na tela
f(letra) - Vai para a próxima aparição da letra desejada
ctrl + u - Page Up
ctrl + d - Page Down
```

### `Basic commands`

```
yy - Copia a linha toda
5yy - Copia o número de linhas desejado (cinco nesse caso)
yw - Copia a palavra
y$ - Copia de onde o cursor está até o final da linha
p - Cola o que foi copiado
dd - Deleta a linha toda
5dd - Deleta o número de linhas desejado (cinco nesse caso)
dw - Deleta uma palavra a frente do cursor
D - Deleta de onde o cursor está até o final da linha
d$ - Deleta de onde o cursor está até o final da linha
x - Deleta um caractere
```

### `Saved and exit commands`

```
:w - Salva o arquivo
:q - Sai do arquivo se já está salvo
:wq ou :x - Salva o arquivo e sai
:q! ou ZQ - Sai do arquivo sem salvar
:w !sudo tee % - Salva o arquivo como sudo
ZZ - Zalva e zai
```
