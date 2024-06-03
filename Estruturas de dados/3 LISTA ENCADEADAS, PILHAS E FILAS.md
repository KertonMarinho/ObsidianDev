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


