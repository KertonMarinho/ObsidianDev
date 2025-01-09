1. importa pygame
```shell
import pygame
```
2. inicia o pygame
```shell
pygame.init()
```
3. inicia uma variável com set mode do py game informando o tamanho da jenela do jogo:
```shell
window = pygame.display.set_mode(size = (600, 480))
```
> [!SUMMARY] pep 8
> Para que o código siga as boas práticas de fabricação do código seguindo a norma PEP 8(regras e boas práticas para escrever um código legível em Python) use a tecla de atalho ``crtl+alt+L``,ela organiza todo o código de acordo com a PEP 8

4. cria um loop para que a janela não fechar na incialização do programa:
```
while True:
	pass
```
5.  Para ter certeza que esta funcionado colque alguns prints:
![[Pasted image 20240925212446.png]]

6. colocar um evento e ficar checando de eventos em uma variável
```python
while True:
	#check for all events
	for event in pygame.event.get():
		if event.type == pygame.QUIT:
			pygame.quit() #Close window
			quit() # end pygame
```

7. Cria o arquivo git ignore,
- pega no site www.gitignore.io , o arquivo gitignore padrão do python(pesquisando python)
----
criando um pacote package

---
A4 (00:00:41)
- criar o mediator (7:47)
- tiros e colisões(26:57)
-  criar os tiros dos players
- criar tios dos enemies(52:35)
A5(parte 1)
- Implementar colisões e tiros(00:02;02)
- HUD(00:45:24)
- Score
A5(parte 2)
- inserir uma fase
- level em nosso jogo

A6(parte1)
- Apresentar o score na tela = 3;07
- Implementar as conexÕes com o banco de dados para gravar o score25:02
