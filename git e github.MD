###Git - Hackerhank

O que � reposit�rio de c�digo fonte?

Sistema voltado para trabalho em equipe que visa resolver o problema de trabalho em arquivos compartilhados.

Podemos imaginar uma equipe de duas pessoas alterando o mesmo arquivo. O �ltimo que salvar, substituir� o primeiro que foi salvo, sem se quer avisar. Trabalhando com reposit�rio, o sistema avisa quando houver esse tipo conflito al�m de oferecer recursos para que possamos tratar esses tipos de erros sem perder qualquer informa��o.

O que � o Git?

� um sistema de controle de vers�o. 
Com o git instalado o computador passa a funcionar como se fosse um servidor individual para gerenciamento dos arquivos, tamb�m, de forma individual.


Github

Funciona como outro servidor em dom�nio geral, onde funciona online.

Imagina que cada computador com o git instalado; um projeto onde tr�s pessoas ir�o trabalhar nele; Agora, cada um ter� seu papel atribu�do dentro do projeto; Cada qual come�a a desenvolver suas atividades de forma espec�fica.

Com isso em mente, teremos que centralizar todas essas altera��es forma a manter o projeto atualizado com todas as altera��es em um s� lugar.

� a� que entra o gerenciador externo de reposit�rios, o Github.


1. Criando um resposit�rio de projeto no github
- github.com
- criar ou logar com uma conta
- criar um resposit�rio (nome, descri��o e inicar com readme)
- Copiar o HTTPS com o endere�o do projeto. (para clonar)
- No nosso computador, com o git instalado, criar ou abrir uma pasta onde ser�o colocados todos os projetos
- Clicar com o bot�o direito e clicar em Git Bash Here 

2. Comandos:

- GIT CLONE
Na linha de comando, digite: git clone e cole o endere�o do projeto do github:
	git clone https://github.com/emersonps/teste_comandos.git

no final, veremos uma pasta do projeto do github no nosso local.

3. Criando arquivos e alterando dentro do projeto local
- Cria um arquido de texto dentro da pasta do projeto que copiamos.
- Com isso, temos em nosso local, a c�pia do projeto que est� do gihub e agora uma altera��o, onde adicionamos um arquivo nesse projeto. Por hora, essa altera��o est� apenas dentro da c�pia do projeto em nosso computador.

3.1 - GIT STATUS
- Na linha de comandos (git bash) digite git status
- Os novos arquivos ou arquivos alterados, ser�o exibidos em destaque (vermelho), indicando que h� altera��es que precisam ser enviadas para o projeto remoto. 

3.2 - GIT ADD * [OU NOME DO ARQUIVO ESPEC�FICO]
- Com o comando 'git add' seguido de asterisco (* - tudo), estamos adicionado todos os arquivos alterados e novos, para serem submetidos ao projeto remoto.
- Novamente damos GIT STATUS, e veremos que a cor do(s) arquivo(s) muda de cor (verde), indicando que os mesmos foram adicionados (agora os arquivos est�o tracked - monitorados), ou seja, podemos envi�-los para o projeto remoto. Sempre devemos adicionar os arquivos antes de enviar para o remote.
- Ent�o digite: GIT ADD
- Depois digite: GIT STATUS

3.3 - GIT COMMIT [mensagem]
- O Commit � o comando que permite adicionar um texto descrevendo o que fora feito nos arquivos. Uma breve descri��o � o suficiente.
- Ent�o digite: GIT COMMIT -m "texto descreve as altera��es que eu fiz nos arquivos" 
- Uma mensagem indicando o mode 10064 (n�mero do commit)
- Indicando quantos arquivos foram modificados e quantas inser��es foram feitas nesse arquivo.
- Nesse momento, suas altera��es at� esse commit, ficam salvas localmente, ou seja, elas ainda n�o surtir�o efeito no projeto atual.
- Ent�o digite: GIT STAUS 
- Veja que agora n�o tem nada na listagem.
- Mas tudo ainda est� localmente.

3.4 - GIT PUSH (falso cognato com o nosso portugu�s - empurrar)
- Com esse comando, "empurrado", ou seja, enviamos aqueles arquivos adicionados e commitados para o servidor remoto.
- Ent�o digite: GIT PUSH 
- Note que no final ele lista algumas informa��es, mas note principalmente a �ltima linha (master->master)
- No github, d� um refresh na p�gina (F5), o arquivo e as altera��es poder�o ser vistas.

- Master: � o branch (ramo) no projeto remoto, ent�o a representa��o ficaria assim:

computador (local)
  |
  |_nome do projeto
	|
	|_master
	    |
	    |_arquivos_do_projeto (alterado)
	    |
	    |_arquivos_do_projeto (novo)


github (remote)
  |
  |_nome do projeto
	|
	|_master
	    |
	    |_arquivos_do_projeto (alterado)
	    |
	    |_arquivos_do_projeto (novo)


Obs: Ao dar um push, voc� precisar� estar logado com o nome de usu�rio e a senha, ent�o, pode ser que o gerenciador pe�a essas informa��es sempre que for subir algo para o branch remoto.

4. CONFIGURAR LOGIN E SENHA (LOCAL)
Para fixar o nome de usu�rio e a senha, fa�a o seguinte:
- Acesse o local: C:\Users\user
- Abra no notepad o arquivo: .gitconfig:
[user]
	name = adicione um nome
	email = adicione o email cadastrado no github
	password = adicione a senha da conta no github

5. USANDO O CONSOLE NO VISUAL STUDIO
- Execute o VS Code Studio
- Abra a pasta do projeto (File-> Open Folde / Ctrl +(k+o))
- Clique em terminal, em seguida, clique em Novo terminal ou (Ctrl+Shift+')
- Use os comandos git no novo terminal
-Obs.: Fique atendo se vc está dentro da pasta do projeto.

6. BRANCH
- É como ramificações que seguem desde o MASTER
- Então podemos ter vários branchs à partir do master ou até mesmo de outros branchs, para que cada usuário possa ter uma cópia do projeto original e com isso fazer suas atualizações em branchs separados. 
- Por fim, podemos mergear (fundir/juntar) todos os branchs num só, ou seja, naquele que será o projeto final disponível para acesso aos usuários finais.

7. CRIANDO NOVO BRANCH À PARTIR DO MASTER
- Quando criamos um projeto e o clonamos para a nossa máquina local, vimos que podemos adicionar e commitar as alterações feitas no projeto local.
- Quando damos um push, enviamos todas essas alterações para o servidor remoto no github, ou seja, para o branch MASTER.
- Agora imagina o seguinte cenário: um novo mebro entrará na equipe. Então, é importante que todos as alterações precisas estejam atualizadas no branch master, pois é à partir dali que ele irá fazer seu clone para o seu local.

7.1 GIT CHECKOUT <nome do branch>
- Para que possamos criar um novo branch, é preciso ter certeza que estamos no branch de onde queremos fazer nossa cópia.
- Use os seguintes comandos: GIT CHECKOUT MASTER (para termos certeza que estamos no branch correto):
Switched to branch 'master' <- branch atual - você está aqui
M       git e github.txt    <- commits 'M'ergeados
Your branch is up to date with 'origin/master'. 
- Agora digite GIT STATUS, para verificar se há alguma alteração que tenhamos que adicionar, commitar e dar push.
- Se tiver, execute esses comandos: 
GIT ADD * 
GIT COMMIT -M "MENSAGEM"
GIT PUSH

7.2 GIT CHECKOUT -B <nome do novo branch>
- Como estamos no branch master e com tudo atualizado, agora podemos criar um novo branch à partir dele.
- GIT CHECKOUT -B novo_branch
- Agora temos um novo branch idêntico ao master.
- Faça uma alteração em qualquer arquivo, enquanto estiver nesse novo branch, e salve.
- Digite:
GIT STATUS
GIT ADD
GIT COMMIT -M "ALTERAÇÃO"

7.4 GIT PUSH --SET-UPSTREAM ORIGIN <NOME_NOVO_BRANCH>: 
- Para que possamos enviar o nosso branch local para o servidor remoto (github), damos o push da seguinte forma:
- As seguintes informações serão exibidas:
remote: This repository moved. Please use the new location:  
remote:   https://github.com/emersonps/comandos_git.git <- o novo branch será adicionado nesse projeto
remote:
remote: Create a pull request for 'coolaborador1' on GitHub by visiting: <- comando será executado criando o novo branch no servidor remoto (projeto no github)
remote:      https://github.com/emersonps/comandos_git/pull/new/coolaborador1 
remote:
To https://github.com/emersonps/teste_comandos.git
 * [new branch]      coolaborador1 -> coolaborador1 <- como o novo branch aparecerá no github
Branch 'coolaborador1' set up to track remote branch 'coolaborador1' from 'origin'. <- à partir de agora, o novo branch será monitorado/rastreado

- Por fim, podemos conferir no github se o novo branch aparece lá.

Obs.: 
	- agora podemos commitar e dar pull de coisas em qualquer um dos dois branchs, não esquecendo de manter sempre atualizado antes de mergeá-los.
	- Depois do GIT PUSH --SET-UPSTREAM ORIGIN <NOME_BRANCH>, para dar push nas novas alterações, basta apenas usar o GIT PUSH estando no branch
	- Quando estiver em um branch use o GIT PUSH --SET-UPSTREAM ORIGIN <NOME_BRANCH> apenas para empurrar as coisas para outro branch no projeto.
	- Para o mesmo branch, use apenas GIT PUSH

8. ESTRATÉGIA DE CONTROLE DE VERSÃO

	TRUNK   (Master/Default)
	[ 1 ]
	 |  \
	 |   \
     |    \
	 |	  [ 2 ]	
	 |	    |   (Brancher)
	 |	  [ 3 ]
	 |	  /
	 | 	 / (Merge)
	 |  /
	[ 4 ]
   / | \  \
  /	 |  \   \ 
 /	 |	 \     \
[T1] |	  \    [ 5 ]
Tags |	   \      |
	 |	    \     |
	 |	  [ 6 ]   |
	 |	    |     |
	 | 		|	  |
	 |	  [ 7 ]   |
	 |	  /	    [ 8 ]
	 |	/         |
	 |/           |
    [ 9 ]         |
     /            |
	/			[ 10 ] (Descontinued development branch)
   /
 [T2] 
 (Tags)

9. MERGE 
- Uma vez concluídas as alterações no branch, devemos levar essas alterações para o Master.
- Chamamos esse recurso de merge (fundir/unir)
- Então, quando concluídas as alterações no branch, devemos adicinonar, commitar e dar um push:

git status  				- visualiza os arquivos que faltam ser adicionados
git add * 					- adiciona todos os arquivos para serem enviados para o servidor remoto (github)
git commit -m "mensagem" 	- adiciona a mensagem aos arquivos 
git push 					- envia as alterações para o servidor (master ou branch) remoto
git status 					- verifica se há algum arquivo para ser adicionado, commitado ou para dar push.

- Feito isso, devemos mudar para o branch master:
git checkout master 		- note que os arquivos no master mudarão, pois as últimas alterações estão no 								branch que acabamos de dar push.
- Agora queremos pegar os arquivos ou alterações do branch anterior e atualizar no master:
git merge <nome_do_branch>	- puxa os arquivos do outro branch para o master (podemos ser feito de branch 								  pra branch, ou do master pra branch também).


