![[Pasted image 20240512212310.png|500]]
- ramificaçoes gitflow

![[Pasted image 20240512213410.png]]
![[Pasted image 20240512213446.png]]
![[Pasted image 20240512213509.png]]
## Exemplificação da criação de ramificações do gitflow

1. Abre o gitbash(ou cmd)
2. Entre na pasta do projeto pelo gitbash
3. Pode configurar o usuário do projeto
```bash
git config --global user.name "alex"
git config --global user.email "kerton@gmail.com"
```
4. Inicia o gitflow
```bash
git flow init
```
- ELE vai iniciar um fluxo de trabalho,aparece umas perguntas para serem configuradas se achar necessário
- por exemplo:
	- nome das ramificações(master, por exemplo)
	- devolp
	- soportar as features,etc
- indica que estamos no develop
![[Pasted image 20240512214641.png]]
- para criar uma nova feature:
```bahs
git flow feature <<start nome da feature>>
```
- Indica que estamos na ramificação feature
![[Pasted image 20240512214846.png]]
- Agora pode densevolver o projeto com esta ramificação do projeto
- O commit é igual ao padrão para upload da feature
- Para que ela seja colocada na develop (em vez do comando push), finaliza a `feature`
```bash
git flow feature finish (nome da feature)
```
![[Pasted image 20240512215500.png]]
- Agora ella precisa passar pelo processo de emologação
- vai enviar do develop para pro realise
```bash
git flow release start 0.0.1(controle de versÀo)
```
- agora ele entrar para realise
![[Pasted image 20240512215857.png]]
- Agora que todos os testes foram homologados  e testados mande para master,antes finaliza a realise
```bahs
git flow realise finish 0.0.1
```
- AParce um janela que vc pode colocar um texto explicativo
- Para fechar a janela user `:q`(salvar)
