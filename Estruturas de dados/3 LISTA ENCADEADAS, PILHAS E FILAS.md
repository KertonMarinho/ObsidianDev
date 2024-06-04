# ARRAYS E LISTAS ENCADEADAS

## <span style="color:#BDB76B">Arraus ou vetores</span>
São estruturas de dados que trabalham com alocação de dados sequenciais na memória

# <span style="color:yellow">Array estático</span>
É um conjunto de espaços sequencial na memória que é previamente reservado, mas que em hipótese alguma pode ter o seu tamanho alterado
![[Pasted image 20240602215527.png]]
![[Pasted image 20240602220457.png]]
``O computador não guarda todos os endereços do array, ele pega o primeiro endereço e acrescenta o índice correspondente multiplicado pela tamanho da variável 

>[!info]
> - Não importa o tamanho do conjunto de dados vc consegue acessar qualquer informação dentro do array com o mesmo tempo, existe independência dos tamanhos de dados


# # <span style="color:yellow">Array Dinâmico</span>
Armazena dados sequencialmente, porém agora, à medida que surgem novos dados, podemos realocar o conjunto em outro espaço de memória em que caibam todos os dados.

![[Pasted image 20240602215929.png]]
# <span style="color:#BDB76B">Listas encadeadas</span>
Arranjo de dados sem necessidade de estarem sequencialmente alocados
- Alocação não sequencial
- Dados esparsos na memória do programa
![[Pasted image 20240602220318.png]]

----
### <span style="color:orange">Se os dados estão esparsos na memória, como a estrutura de lsita encadeada locakliza seusu elementos?</span>
- Cada elemento da lista encadeada armazena na memória não só seus dados, como também o endereço onde está localizado o próximo elemento na memória.
![[Pasted image 20240602221924.png]]
- Em uma lista encadeada, cada elemento conhece somente o próximo elemento, pois armazena somente o endereço deste

---

>[!info]
>![[Pasted image 20240602221253.png|200]]
>lista em python é um arrray dinâmico e não uma lista encadeada

---
![[Pasted image 20240602222332.png]]

----
---
# CONSTRUINDO LISTAS ENCADEADAS
- Também conhecida como
	- lista ligada
	- Linked lsit
- Cada elemento de uma lista:
	- Nó ou nodo
- Cada elemento da lista é composto, portanto, minimamente de duas informações: o(s) dado(s) a ser(em) armazenado(s) e um endereço(s) na memória do próximo elemento da lista encadeada.
 ![[Pasted image 20240602222833.png|400]]

## <span style="color: #1E90FF">■ Características das listas encadeadas </span>
 - Sucessivamente elementos conectados por ponteiros
 - O último elemento aponta para um endereço nulo, o que caracteriza o final da lista
 - Funciona dinamicamente, aumentando e diminuindo de tamanho conforme necessita
- Pode utilizar toda a memória destinada ao programa, uma vez que cada dado pode ficar isolado na memória
- Não desperdiça memória, alocando somente o que precisa
- Apresenta tempos de leitura Big-O de dados inferior aos arrays

---
## <span style="color:#00FA9A">listas encadeadas simples</span>
```python
#Cria cada elemento da lista
class ElementoDaListaSimples:
# construtor de inicialização da classe
    def __init__(self, dado):
        self.dado = dado
        self.proximo = None
#__repr__ é um método especial do Python
#use-o para criar a maneira como objeto

    def __repr__(self): #é mostrado fora da função print
        return self.dado
        
#Cria a lista encadeada simples
class ListaEncadeadaSimples:
  def __init__(self, nodos=None):
    self.head = None
    if nodos is not None:
        nodo = ElementoDaListaSimples(dado=nodos.pop(0))
        self.head = nodo
        for elem in nodos:
            nodo.proximo = ElementoDaListaSimples(dado=elem)
            nodo = nodo.proximo
  def __repr__(self):
      nodo = self.head
      nodos = []
      while nodo is not None:
          nodos.append(nodo.dado)
          nodo = nodo.proximo
      nodos.append("None")
      return " -> ".join(nodos)

#Varre a lista
  def __iter__(self):
    nodo = self.head
    while nodo is not None:
        yield nodo
        nodo = nodo.proximo
        
  def inserirNoInicio(self, nodo):
    nodo.proximo = self.head
    self.head = nodo

  def inserirNoFinal(self, nodo):
    if self.head is None:
        self.head = nodo
        return
	nodo_atual = self.head
	
    while nodo_atual.proximo != None:
        nodo_atual = nodo_atual.proximo
    nodo_atual.proximo = nodo
    return

  def deletar(self, dado):
    if self.head is None:
        raise Exception("A lista está vazia!")

    if self.head.dado == dado:
        self.head = self.head.proximo
        return

    nodo_anterior = self.head
    for nodo in self:
        if nodo.dado == dado:
            nodo_anterior.proximo = nodo.proximo
            return

        nodo_anterior = nodo

    raise Exception("Nó com o dado '%s' não foi econtrado." % dado)
    #insere dados:
Teste = ListaEncadeadaSimples()
Teste.inserirNoInicio(ElementoDaListaSimples('40'))
Teste.inserirNoInicio(ElementoDaListaSimples('4'))
Teste.inserirNoInicio(ElementoDaListaSimples('15'))
Teste.inserirNoInicio(ElementoDaListaSimples('7'))
Teste.inserirNoFinal(ElementoDaListaSimples('12'))
Teste.inserirNoFinal(ElementoDaListaSimples('24'))

# print na tela para inserir ->:
for nodo in Teste:
  print(nodo, end=' -> ')
print('None')

Teste.deletar('4')

for nodo in Teste:
  print(nodo, end=' -> ')
print('None')
```
![[Pasted image 20240602224806.png]]
>[!info]
>Para acrescentar um elemento da lista encadeada se coloca o elemento antes do elemento que se dominou `HEAT` e este passa a ser o ``Head``
>![[Pasted image 20240602225156.png|400]]

>[!info]
>Para inserir no final da lsita, vc varre elemento por elemento até localizar o último elemento(vazio) e faço apontar para este elemento
>![[Pasted image 20240602225713.png|400]]

---
![[Pasted image 20240602225943.png|500]]
- Lista encadeada simples : cada elemento aponta para o próximo
-Lista encadeada dupla: existe dois ponteiros por elemento, e ela é uma via de mão dupla, um elemento conhece o seu sucessor e o seu antecessor.
![[Pasted image 20240602230513.png]]

Circular simples: não tem ponteiros vazios, o final da lista fecha a lista e volta para o início
Circular dupla: são dois circulos o final aponta para o início e o ponteiro anterior do HEAT aponta para o final

---
---
# PILHAS[STACKS]
- Uma estrutura de dados é uma pilha quando só conseguimos manipular o que está no seu topo
- O primeiro que entra é o último que sai(First in last out-FILO)

## <span style="color:aquamarine">■ Exemplos de aplicações </span>
- Recursividade
- Cálculo de expressões matemáticas
- Jogo FreeCell

## <span style="color:brown">■ Construindo e manipulando uma pilha</span>
- O top é a única posição que conseguimos manipular
- Podemos implementar uma pilha com listas encadeadas ou com arrays
![[Pasted image 20240603203349.png|400]]
![[Pasted image 20240603203416.png|400]]
![[Pasted image 20240603203502.png|400]]
![[Pasted image 20240603203601.png|400]]

---
---
# FILAS (QUEUES)
- Uma estrutura de dados é uma fila quando inserimos somente no final dela e removemos somente do seu início
- O primeiro que entra é o primeiro que sai
- First in first out (FIFO)

## <span style="color:aquamarine">■ Exemplos de aplicações </span>
- Fila de impressão
- Lista de reprodução de música
- Jogo snake
## <span style="color:brown">■ Construindo e manipulando uma pilha</span>
- Inserimos no final(tail) e removemos do início(head)
- Podemos implementar uma fila com listas encadeadas ou com arrays

![[Pasted image 20240603204356.png]]

---
---
# Implementação pilhas e filas
- Implementação com arrays dinâmicos(listas em python)

## <span style="color:yellow">■ Código da pilha</span>
```python
#VERSÃO SIMPLIFICADO DO PYTHON

pilha = []
tam = 5

while True:
  print('1 - Inserir na pilha')
  print('2 - Remover da pilha')
  print('3 - Listar a pilha')
  print('4 - Sair')

  op = int(input("Escolha uma opção:"))
  if op ==1:
    dado = int(input('Qual número deseja inserir?'))
    if len(pilha) < 5:
      pilha.append(dado)
    else:
      print('Pilha cheia! Impossível inserir. ')
  elif op == 2:
    if len(pilha) > 0:
      pilha.pop()
    else:
      print('Pilha vazia! Impossível remover. ')
  elif op == 3:
    pilha.reverse()
    for item in pilha:
      print(item)
  elif op == 4:
    print('Encerrando...')
    break
  else:
    print("Selecione outra opção!\n")
    
```

![[Pasted image 20240603205217.png]]

---
## <span style="color:yellow">■ Código da Fila</span>
```python
def queue(pilha, fim, tam, dado):
  if len(fila) == tam:
    print('Fila cheia! Impossível inserir. ')
  else:
    if fim < tam:
      fila.insert(fim, dado)
      fim += 1
    else:
      fim = 0
      fila.insert(fim, dado)
  return fila, fim

def dequeue(fila, inicio):
  if len(fila) == 0:
    print('Fila vazia! Impossível remover. ')
  else:
    fila[iicio] = None
    inicio += 1
  return fila, inicio

#Programa principal
inicio = 0
fim = 0
fila = []
tam = 5

while True:
  print('1 - Inserir na fila')
  print('2 - Remover da fila')
  print('3 - Listar a fila')
  print('4 - Sair')

  op = int(input("Escolha uma opção:"))
  if op ==1:
    dado = int(input('Qual número deseja inserir?'))
    fila, fim = queue(fila, fim, tam, dado)
  elif op == 2:
    fila, inicio = dequeue(fila, inicio)
  elif op == 3:
    for item in fila:
      print(item, end=" ")
    print()
  elif op == 4:
    print('Encerrando...')
    break
  else:
    print("Selecione outra opção!\n")
```

---
---
# AULA PLÁTICA

## <span style="color:orange">■ LISTA ENCADEADA</span>

```PYTHON
#Cria cada elemento da lista
class ElementoDaListaSimples:
# construtor de inicialização da classe
    def __init__(self, dado):
        self.dado = dado
        self.proximo = None
#__repr__ é um método especial do Python
#use-o para criar a maneira como objeto
#é mostrado fora da função print
    def __repr__(self):
        return self.dado

#Cria a lista encadeada simples
class ListaEncadeadaSimples:
  def __init__(self, nodos=None):
    self.head = None
    if nodos is not None:
        nodo = ElementoDaListaSimples(dado=nodos.pop(0))
        self.head = nodo
        for elem in nodos:
            nodo.proximo = ElementoDaListaSimples(dado=elem)
            nodo = nodo.proximo

  def __repr__(self):
      nodo = self.head
      nodos = []
      while nodo is not None:
          nodos.append(nodo.dado)
          nodo = nodo.proximo
      nodos.append("None")
      return " -> ".join(nodos)

#Varre a lista
  def __iter__(self):
    nodo = self.head
    while nodo is not None:
        yield nodo
        nodo = nodo.proximo

  def inserirNoInicio(self, nodo):
    nodo.proximo = self.head
    self.head = nodo

  def inserirNoFinal(self, nodo):
    if self.head is None:
        self.head = nodo
        return

    nodo_atual = self.head
    while nodo_atual.proximo != None:
        nodo_atual = nodo_atual.proximo

    nodo_atual.proximo = nodo
    return

  def deletar(self, dado):
    if self.head is None:
        raise Exception("A lista está vazia!")

    if self.head.dado == dado:
        self.head = self.head.proximo
        return

    nodo_anterior = self.head
    for nodo in self:
        if nodo.dado == dado:
            nodo_anterior.proximo = nodo.proximo
            return
        nodo_anterior = nodo
        
    raise Exception("Nó com o dado '%s' não foi econtrado." % dado)
    
Teste = ListaEncadeadaSimples[]

while True:
  print('1 - Inserir na início da lista encadeada')
  print('2 - Inserir na final da lista encadeada')
  print('3 - Remover da lista encadeada')
  print('4 - Imprimir a lista encadeada')
  print('5 - Sair')
  
  op = int(input("Escolha uma opção:"))
  if op == 1:
    dado = input('Qual número deseja inserir?')
    Teste.inserirNoInicio(ElementoDaListaSimples(dado))

  if op == 2:
    dado = input('Qual número deseja inserir?')
    Teste.inserirNoFinal(ElementoDaListaSimples(dado))

  elif op == 3:
    dado = input('Qual número deseja remover?')
    Teste.deletar(dado)

  elif op == 4:
    for nodo in Teste:
      print(nodo, end=' -> ')
    print('None')

  elif op == 5:
    print('Encerrando...')
    break

  else:
    print("Selecione outra opção!\n")
```
![[Pasted image 20240603210625.png]]
![[Pasted image 20240603210820.png]]

---
## <span style="color:orange">■ Pilhas(stacks)</span>
```python
#VERSÃO SIMPLIFICADO DO PYTHON
pilha = []
tam = 5

while True:
  print('1 - Inserir na pilha')
  print('2 - Remover da pilha')
  print('3 - Listar a pilha')
  print('4 - Sair')

  op = int(input("Escolha uma opção:"))
  if op ==1:
    dado = int(input('Qual número deseja inserir?'))
    if len(pilha) < 5:
      pilha.append(dado)
    else:
      print('Pilha cheia! Impossível inserir. ')
  elif op == 2:
    if len(pilha) > 0:
      pilha.pop()
    else:
      print('Pilha vazia! Impossível remover. ')
  elif op == 3:
    pilha.reverse()
    for item in pilha:
      print(item)
  elif op == 4:
    print('Encerrando...')
    break
  else:
    print("Selecione outra opção!\n")

def push(pilha, top, tam, dado):
  if len(pilha) == tam:
    print('Pilha cheia! Impossível inserir. ')
  else:
    pilha.insert(top, dado)
    top += 1
    return pilha, top

def pop(pilha, top):
  if len(pilha) == 0:
    print('Pilha vazia! Impossível remover. ')
  else:
    del pilha[top]
    top -= 1
    return pilha, top
###############################################################################   
#Programa principal
top = 0
pilha = []
tam = 5

while True:
  print('1 - Inserir na pilha')
  print('2 - Remover da pilha')
  print('3 - Listar a pilha')
  print('4 - Sair')

  op = int(input("Escolha uma opção:"))
  if op ==1:
    dado = int(input('Qual número deseja inserir?'))
    push(pilha, top, tam, dado)

  elif op == 2:
    pop(pilha, top)
  elif op == 3:
    for item in pilha:
      print(item)

  elif op == 4:
    print('Encerrando...')
    break
  else:
    print("Selecione outra opção!\n")
```
![[Pasted image 20240603212030.png]]

---
## <span style="color:orange">■ Filas(queues)</span>
```python
#VERSÃO SIMPLIFICADO DO PYTHON
fila = []
tam = 5

while True:
  print('1 - Inserir na fila')
  print('2 - Remover da fila')
  print('3 - Listar a fila')
  print('4 - Sair')

  op = int(input("Escolha uma opção:"))
  if op == 1:
    dado = int(input('Qual número deseja inserir?'))
    if len(fila) < 5:
      fila.append(dado)
    else:
      print('Fila cheia! Impossível inserir. ')
  elif op == 2:
    if len(fila) > 0:
      fila.pop(0)
    else:
      print('Fila vazia! Impossível remover. ')
  elif op == 3:
    for item in fila:
      print(item, end=' ')
    print('\n')
  elif op == 4:
    print('Encerrando...')
    break
  else:
  
    print("Selecione outra opção!\n")
def queue(pilha, fim, tam, dado):
  if len(fila) == tam:
    print('Fila cheia! Impossível inserir. ')
  else:
    if fim < tam:
      fila.insert(fim, dado)
      fim += 1
    else:
      fim = 0
      fila.insert(fim, dado)
  return fila, fim

def dequeue(fila, inicio):
  if len(fila) == 0:
    print('Fila vazia! Impossível remover. ')
  else:
    fila[inicio] = None
    inicio += 1
  return fila, inicio
##############################################################################
#Programa principal
inicio = 0
fim = 0
fila = []
tam = 5

while True:
  print('1 - Inserir na fila')
  print('2 - Remover da fila')
  print('3 - Listar a fila')
  print('4 - Sair')

  op = int(input("Escolha uma opção:"))
  if op ==1:
    dado = int(input('Qual número deseja inserir?'))
    fila, fim = queue(fila, fim, tam, dado)
  elif op == 2:
    fila, inicio = dequeue(fila, inicio)
  elif op == 3:
    for item in fila:
      print(item, end=" ")
    print()
  elif op == 4:
    print('Encerrando...')
    break
  else:
    print("Selecione outra opção!\n")
```