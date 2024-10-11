1. Baixar imagens:
https://craftpix.net
https://opengameart.org
2. Baixar sons
https://freesound.org/

---
# Virtual environment (venv)
- Eles permitem a criação de um ambiente isolados que pode conter suas próprias versões dos pacotes Python instalados, sem interferir com o sistema global ou com outros projetos.
- 

### - Diferença entre vm,container e venv\
![[Pasted image 20240922225515.png]]
# Passos para :
1. Criando um projeto vazio do Pycharm
2. Criando a venv(esse comando é para Vscode, no pychaim cria o arquivo ja com evenv)
```
virtualenv env
```
3. ativando a venv(tanto para VsCode como para Pychaim)
``` shell
.venv/Scripts/activate
  # se não tiver oculto não use o p[onto]
```
4. Desativando a venv
```
deactivate
```
----
# Pygame
- Ferramentas criada para interfaces para games
1. Instalar o pygame
```shell
pip install pygame
```
2. Para testar se o pygame foi realmente instalado:
```shell
py -m pygame.examples.aliens
```
---
## Boa pratica e criar um txt para dependência dos projetos para que o usuário saiba o que tem que instalar para rodar o projeto:

1. ver as dependências do projeto:
```shell
pip freeze
```
2. Enviar as dependências do projeto para um .txt
```shell
pip freeze > requirements.txt
```

---
