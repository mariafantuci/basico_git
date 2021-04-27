Repositório com os comandos básico do git

# Atualiza com seu repositório
$ git fetch origin


# Mudar de repositório
$ git checkout nome_branch

# Criar uma nova branch e acessa a branch criada
$ git checkout -b nome_da_branch

# acessando a branch
git checkout -b pdf

# Atualizar meu repositório local
git checkout master
git pull origin master --rebase


# Manda os arquivos da branch para a master
git push origin nome da branch

# observação: toda vez que um commit é realizado ele gera uma chave, com vários valores, mais pode-se utilizar os 7 primiros números, que funciona assim como todos os valores.

# comandos git
git branch => mostra todas as branchs criadas e qual é a branch atual identificada pelo asterisco(*) 

git commit -m "comenta o que foi feito no codigo"

git init => é para iniciar o git dentro do projeto/repositório;

git add -A => atualiza o repositório local com os arquios que foram alterados.

git status => mostra as mudanças que foram feitas (o que precisa rastrear, e os arquivos modificados/inseridos/removidos)

git commit -am "ele comita e coloca o comentario sem precisar fazer dois comandos."

git log -> mostra so commits e as movimentações do repositorio, o autor, a data e o que foi alterado. 

para sair desse comando basta apertar a letra q

git reset --soft codigo do commit =>ele volta para o estado antes do commit, ele não remove só volta para o projeto antes 
do ultimo (da versão selecionada);

git reset --mixed codigo do commit =>

git reset --hard codigo do commit => volta para o antigo commit, e exclui tudo que tinha sido commitado. 

git diff => mostra todos os arquivos foram aterados dentro da branch, antes do commit

git diff +codigo do commit => mostra os itens que foram alterados entra a branch atual e o código do commite que eu informei

git diff +codigo do commit (espaço) +codigo do commit => mostra os itens que foram alterados entre as duas branchs informadas

git diff --name-only => mostra somente os nomes dos arquivos que foram alterados

git diff nome do arquivo => mostra o que foi alterado dentro desse arquivo

git checkout nome da branch => troca a branch atual para outra branch

git checkout HEAD -- nome do arquivo => o HEAD é um curinga que substitui o nome da branch atual que estamos. esse comando faz com que se um arquivo foi alterado e eu não quero salvar ele, só os outros, eu faço esse comando, ele volta do jeito que estava no ultimo commit

git branch -D noma da branch para remover => remove a branch local do repositório

git pull origin nome da branch => atualiza a branch local com pelo repositório remoto.

git clone url => clona um repositório e remoto para o local.

git reflog => mostras os commits e os códigos de cada commit

git commit --amend --no-edit -> primeiro tem que adicionar o todos os arquivos que foram esquercisdoa dentro do commit, depois que vem esse comado. Ele basicamente inclui arquinos em um commit que eu já fiz. Ou seja, eu comitei e não dei o git add -a ou o nome do arquivo e ele só comitou mas não incluiu os arquivos.

git show --pretty="" --name-only codigo do commit que eu quero verificar. 

git restore --staged nome do arquivo -> quando um arquivo foi acidentalmente adicionado e não era para ter sido, para remover esse arquivo basta digitar esse comando.


			comandos para github

git remote add origin link do projeto do github => faz o ligamento entre o repositório local e o remoto.
git remote => mostra que se conectou ou não ao github
git remote -v => mostra em detalhes do repositório remoto está 

*******************
fetch é a capacidade de puxar o repositorio remoto para o meu local
push é levar as coisas do meu repositório local para o repositório remoto

git push -u origin nome da branch => envia os arquivos do repositorio local para o remoto (somente a primeira vez que for fazer o primeiro push, pois na primeira vez ele não sabe qual é o repositório remoto, e precisa preencher os dados.)

git push origin master =>manda os arquivos para o repositorio remoto

git revert --no-edit + codigo do commit => ele cria um novo commit com base no ultimo commit feito, entitulado reverse, mas não perde as utlimas alterações que foi feita.
ou seja, ele cria um commit com base da penultima alteração, começando dela.

git push origin :branch remove a branch remota

/******/

1º Eu adiciono git add -A || git add --all
2º commitar git commit -am "comentario";
3º mandar para a branch do repositório remoto.

No Git versão 1.x:
+---------------+-------+-------------+-----------+------------------------------------------------------------------------+
|               |       |   Arquivos  |           |                                                                        |
+---------------+-------+-------------+-----------+------------------------------------------------------------------------+
| Comando       | Novos | Modificados | Removidos |                                                                        |
+---------------+-------+-------------+-----------+------------------------------------------------------------------------+
| git add --all |   X   |      X      |     X     | Coloca todos arquivos (novos, modificados e removidos) no index/stage  |
+---------------+-------+-------------+-----------+------------------------------------------------------------------------+
| git add .     |   X   |      X      |           | Coloca no Stage apenas arquivos novos e modificados                    |
+---------------+-------+-------------+-----------+------------------------------------------------------------------------+
| git add -u    |       |      X      |     X     | Coloca no Stage apenas arquivos modificados e removidos                |
+---------------+-------+-------------+-----------+------------------------------------------------------------------------+

No Git versão 2.x:
+---------------+-------+-------------+-----------+-----------------------------------------------------------------------+
|               |       |   Arquivos  |           |                                                                       |
+---------------+-------+-------------+-----------+-----------------------------------------------------------------------+
| Comando       | Novos | Modificados | Removidos |                                                                       |
+---------------+-------+-------------+-----------+-----------------------------------------------------------------------+
| git add --all |   X   |      X      |     X     | Coloca todos arquivos (novos, modificados e removidos) no index/stage |
+---------------+-------+-------------+-----------+-----------------------------------------------------------------------+
| git add .     |   X   |      X      |     X     | Coloca todos arquivos (novos, modificados e removidos) no index/stage¹|
+---------------+-------+-------------+-----------+-----------------------------------------------------------------------+
| git add -u    |       |      X      |     X     | Coloca no Stage apenas arquivos modificados e removidos               |
+---------------+-------+-------------+-----------+-----------------------------------------------------------------------+

git add --all: adiciona ao staging arquivos desde a raiz do repositório passando por todos os subdiretórios, e aqui está a diferença, não importa se você está na raiz ou no sub-diretório.

git add .: usando o ponto, será adicionado ao stagging somente os arquivos a partir do diretório que você está, e os sub-diretórios deste.

/******************************************/
para ignorar algum arquivo é só criar um arquivo no repositório chamado .gitignore
e dentro dele colocar o nome do arquivo que eu quero que seja ignorado ou, colocar o as extensões
exemplo *.sql ignora todas as extensões .sql
ex.     *.txt ignora todas as extensões .txt
ex.     nome da pasta/*  ignora todos os arquivos dentro dessa pasta
ex.     nome da pasta/   ignora todos os arquivos dentro dessa pasta e a pasta (nem a pasta aparace)