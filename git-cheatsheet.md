## The Git cheatsheet for DevOps community

### Git Basic commands

```
git config --global user.name "[username]" - Configura seu username do Git
git config --global user.email "[email]" - Configura seu email do Git
git config --global color.ui auto - Configura cores que apareceram no terminal
git config --global alias.c "commit -ma" - Configura um alias para comandos Git
git config --system core.editor vim - Configura o editor de texto padrao
git config --global --edit - Abre o arquivo  que contem usuario e email setados
```

### Git Branch Managing

```
git branch - Lista todas as branchs locais do repositório
git branch -aa - Lista todas as branchs remotas do repositório
git branch [nome_branch] - Cria uma nova branch
git checkout [nome_branch] - Muda para a branch desejada, caso não exista o Git irá criar
git branch -d [nome_branch] - Deleta a branch desejada
git branch -m [nome_novo] - Muda o nome da branch atual
git merge [branch] - Faz o merge da branch atual para a branch desejada
```

### Git Repository Setup

```
git init [diretório] - Cria um novo repositório Git apartir de um diretório existente
git clone [URL/repo] - Clona um repositório
git clone [URL/repo] [diretório] - Clona um repositório dentro de um diretório específico na máquina
git pull origin main - Atualiza o repositório local com os dados do repositório remoto
git add . - Adiciona todas as novas mudanças do diretório atual
git add [arquivo] - Adiciona o arquivo desejado
git commit -m "[mensagem]" -a - Commita todas as novas mudanças
git commit --amend - Adiciona novas mudanças ao commit anterior
git push origin main - Atualiza o repositório remoto com os dados do repositório local
git reset [commit] - Desfaz todos os commits apartir do commit especificado
git reset --hard [commit] - Discarta todo histórico e mudanças para o commit especificado
```

### Git File Managing

```
git status - Mostra o status do diretório atual
git log - Lista os logs da branch em que você está
git log --all - Lista os logs de todas as branchs
git log [branch1]..[branch2] - Compara logs das branchs desejadas
git diff - Mostra todas mudanças que não foram commitadas
git diff [commit1] [commit2] - Mostra a diferença entre dois commits
git diff [branch1] [branch2] - Mostra a diferença entre duas branchs
git diff [arquivo1] [arquivo2] - Mostra a diferença entre dois arquivos
git show [objeto] -Mostra o conteúdo do objeto desejado
```
