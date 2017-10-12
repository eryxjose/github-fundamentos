
# Comandos Git básicos no Linux Ubuntu 16.04

$ sudo apt-get install git git-extras

git-extras habilita recursos adicionais para personalizar comandos e operações git.

Utilize o comando abaixo para definir um repositório para pasta ativa no terminal

$ git init

Crie o repositório em seu perfil no site github.com e então utilize o comando abaixo para vincular a pasta local com o repositório github.

$ git remote add origin https://github.com/eryxjose/linux-ubuntu-tutorial.git

Para definir informações de sua conta de usuário git localmente utilize os comandos abaixo.

$ git config --global user.name "nomeusuariogit"
$ git config --global user.email emailusuariogit@mail.com

Depois de definir a pasta local, criar o repositório no site github.com e relacionar o diretório local com o repositório, é necessário utilizar o comando git pull para obter o arquivo readme.md concluindo a configuração inicial. Você utilizará este comando sempre que quiser obter os arquivos do repositório.

$ git pull origin master

Em seguida, utilize o comando git branch para definir o branch ativo que receberá os arquivos do repositório.

$ git branch --set-upstream-to=origin/master

A mensagem abaixo indica que o branch master foi definido com sucesso.

"Branch master set up to track remote branch master from origin."

Em seguida, podemos adicionar individualmente cada arquivo que será atualizado pelo controle de versão utilizando o comando git add seguido pelo nome do arquivo.

$ git add README.md

Ou utilizar o parâmetro -A para adicionar todos os arquivos.

$ git add -A

Em seguida, utilize o comando git commit para preparar os arquivos alterados para o envio e definir um comentário sobre as alterações. Comentários podem conter no máximo 140 caracteres.

$ git commit -m "Este é um comentário deste commit"

E então utilize o comando git push para enviar os arquivos para o repositório no branch configurado previamente através do do git origin. 

$ git push

Caso você não tenha definido anteriormente o branch utilizando o git origin, você pode passar como parâmetro  junto com o comando git push. Serão solicitados usuário e senha.

$ git push origin master

Se os arquivos forem enviados com sucesso, um resumo será exibido, por exemplo:

Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 405 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/eryxjose/linux-ubuntu-tutorial.git
   f7e460f..de607db  master -> master

Utilize o comando git rm para remover uma pasta do repositório.

$ git rm -r nomedapasta

Depois de fazer esta alteração, será necessário atualizar o repositório github semelhante ao que foi feito quando modificamos arquivos.

$ git add -A
$ git commit -m "Diretório removido do controle de versão"
$ git push

Caso haja alguma mensagem informando que não foi possível remover algum arquivo por ter sido modificado localmente, acrescente o parâmetro -f (force).

$ git rm -r -f nomedapasta

E então repetir os passos para atualizar o repositório.

O comando git-ignore pode ser utilizado para definir uma lista de arquivos que não serão atualizados no controle de versão.

$ git-ignore ./nomedapasta

O arquivo gitignore contém a relação de arquivos e pastas a serem ignorados.







