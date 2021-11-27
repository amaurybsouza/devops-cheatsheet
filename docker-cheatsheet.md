## Docker cheatsheet for DevOps community

### `Basic commands`

```
git config --global user.name "[username]" - Configura seu username do Git
git config --global user.email "[email]" - Configura seu email do Git
git config --global color.ui auto - Configura cores que apareceram no terminal
git config --global alias.[alias_nome] [comando_git] - Configura um alias para comandos Git
git config --system core.editor [editor_de_texto] - Configura o editor de texto desejado
git config --global --edit - Abre o arquivo de configuração do Git
```

### `Branch Managing`

```
git branch - Lista todas as branchs locais do repositório
git branch -aa - Lista todas as branchs remotas do repositório
git branch [nome_branch] - Cria uma nova branch
git checkout [nome_branch] - Muda para a branch desejada, caso não exista o Git irá criar
git branch -d [nome_branch] - Deleta a branch desejada
git branch -m [nome_novo] - Muda o nome da branch atual
git merge [branch] - Faz o merge da branch atual para a branch desejada
```
