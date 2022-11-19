# Sumário

[Iniciando um repositório novo](#iniciando-um-repositório-novo)

[Remover arquivos da área de stage](#remover-arquivos-da-área-de-stage)

[Desfazer modificações não salvas](#desfazer-modificações-não-salvas)

[Desfazer o último commit](#desfazer-o-último-commit)

[Deletar commits e também modificações nos arquivos](#deletar-commits-e-também-modificações-nos-arquivos)

[Atualizar o repositório local em relação ao remoto](#atualizar-o-repositório-local-em-relação-ao-remoto)

[Resolver push rejeitado](#resolver-push-rejeitado)

[Resolvendo conflito](#resolvendo-conflito)

[Sobrescrever um histórico no Github](#sobrescrever-um-histórico-no-github)

[Apontar o projeto para outro repositório remoto](#apontar-o-projeto-para-outro-repositório-remoto)

[Manipulando branches localmente](#manipulando-branches-localmente)

[Procedimento pull request](#procedimento-pull-request)

[Resolução de conflito](#resolução-de-conflito)

[Procedimento fork + pull request](#procedimento-fork--pull-request)

#
# Iniciando um repositório novo
```
git init
```
```
git add .
```
```
git commit -m "Mensagem explicativa"
```
```
git branch -M main
```
```
git remote add origin git@github.com:seuusuario/seurepositorio.git
```
```
git push -u origin main
```
#
# Remover arquivos da área de stage

```
git status

git reset
```
#
# Desfazer modificações não salvas
```
git status

git reset

git clean -df

git checkout -- .
```
#
# Desfazer o último commit
Desfazer último commit sem desfazer as modificações nos arquivos:

```
git status

git reset --soft HEAD~1
```
#
# Deletar commits e também modificações nos arquivos

Voltar o projeto ao estado de um dado commit (deletar commits e alterações
posteriores a esse commit)

```
git status

git reset --hard <código do commit>
```
Voltar o projeto ao estado do penúltimo commit:

```
git status

git reset --hard HEAD~1
```
<font color="red">ATENÇÃO: ação destrutiva!</font>

#
# Atualizar o repositório local em relação ao remoto

```
git status

git pull <nome do remote> <nome do branch>
```
#
# Resolver push rejeitado

Não é permitido enviar um push se seu repositório local está atrasado em
relação ao histórico do repositório remoto!

Você tem que atualizar o repositório local:
```
git pull <nome do remote> <nome do branch>
```
#
# Resolvendo conflito

• Analise o código fonte

• Faça as edições necessárias

• Faça um novo commit
#
# Sobrescrever um histórico no Github

```
git push -f <nome do remote> <nome do branch>
```

<font color="red">ATENÇÃO: ação destrutiva!</font>

#
# Apontar o projeto para outro repositório remoto

```
git remote set-url origin git@github.com:seuusuario/seurepositorio.git
```

#
# Manipulando branches localmente

Listar branches
```
git branch
```
Criar branch
```
git branch nome-do-branch
```
Deletar branch <font color="red">(ação destrutiva)</font>
```
git branch -d nome-do-branch
```
Deletar branch mesmo sem ter feito merge dele ainda <font color="red">(ação destrutiva)</font>
```
git branch -D nome-do-branch
```
#
# Procedimento pull request
1) Atualize o branch main local e faça o merge do main para o branch de feature. Depois salve o branch de
feature no repositório remoto.

```
(main) git pull origin main
(main) git checkout ft-login
(ft-login) git merge main
(ft-login) git push -u origin ft-login
```
2) No repositório remoto, abra um pull request da feature enviada.
3) Depois de passar pelo processo de homologação, aprove a pull request.
4) Opcional: delete o branch de feature no repositório remoto.
#
# Resolução de conflito
A resolução de conflito é uma operação manual, que exige
habilidade do desenvolvedor.
1. Edite o código fonte, resolvendo o conflito
2. Faça um novo commit
#
# Procedimento fork + pull request
Mesmo que você não tenha permissão de escrita em um repositório do Github,
você pode enviar contribuições para este repositório.
Este procedimento é a base para colaboração em projetos de código aberto.
Passos:
1. Faça um fork do repositório original para o seu Github
2. Clone seu repositório "forkado" para seu computador
3. Crie um novo branch e faça as alterações nesse branch
4. Envie as alterações para seu repositório "forkado"
5. Crie uma pull request para o repositório original
