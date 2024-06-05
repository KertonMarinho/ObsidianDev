# ÁRVORE BINÁRIA
#### Árvore binária quando cada elemento (nó/nodo) da árvore contém, no máximo, dois (bi) filhos.
![[Pasted image 20240604210034.png]]


>[!ÁRVORE]
>UMA ESTRUTURA DE DADOS É DENOMINADA DE ÁRVORE QUANDO SEUS ELEMENTOS CRIAM RAMIFICA;CÕES NA ESTRUTURA, GERANDO SUBÁRVORES.

## <span style="color:pink">■ Estrutura de árvore</span> 
- Organização não linear
- Diferente de uma lista encadeada, que é linear

![[Pasted image 20240604205227.png|400]]

## <span style="color:#00BFFF">■ Nomenclatura</span>
- <u>Nó raiz(root)</u> - nó original da árvore. Todos derivam dele.
- <u>Nó pai</u> - nó que da origem (está acima) a pelo menos um outro nó.
- <u>Nó filho</u> - nó que deriva de um nó pai
- <u>Nó folha/terminal</u> - nó que não contém filhos.

![[Pasted image 20240604210208.png]]

## <span style="color:#FF4500">Profundidade na árvore</span>
- É a diferença entre o nível do nó e o nível da raiz.

## <span style="color:yellow">■ Altura da árvore</span>
- Diferença entre dois níveis quaisquer
- Altura é importante para balanceamento de árvore

![[Pasted image 20240604210607.png|500]]

![[Pasted image 20240604210657.png]]

---
# <span style="color: #00FF00">■ TIPOS DE ÁRVORES BINÁRIAS</span> 
## <span style="color:yellow">➪ Árvore estritamente binária</span>
- É aquela em que cada nó contém, sempre, exatamente dois filhos, ou nenhum

## <span style="color:yellow">➪Árvore binária completa</span>
- É aquela em que todos os nós contendo menos de dois filhos estão colocados somente no último ou no penúltimo nível da árvore.

## <span style="color:yellow">➪ Árvore binária cheia</span>
. É assim denominada quando cada nó tem exatamente dois filhos, e os nós folhas estão sempre no mesmo nível. Ou seja, é quando a árvore é estritamente binária e completa ao mesmo tempo.
![[Pasted image 20240604211800.png]]

---
---
# ÁRVORE BINÁRIA DE BUSCA
- Binary Search tree (BST)
- Caso o valor a ser inserido seja menor do que o seu nó pai, inserimos o dado na subárvore esquerda
- Caso o valor a ser inserido seja maior do que o seu nó pai, inserimos o dado na subárvore direita.
- ![[Pasted image 20240604212237.png]]
<span style="color:orange">Exemplo</span>
- Inserimos o valor 7 na árvore:
![[Pasted image 20240604212412.png|500]]
---
---
# PERCURSO EM BST
## <span style="color:#FF7F50">■ Percurso em Largura</span>
- Level Order
- Percorremos horizontalmente a árvore
- De cima para baixo, da esquerda para direita
- Resultado: 6,2,8,1,4,
![[Pasted image 20240604213927.png|500]]
## <span style="color:#FF4500">■ Percurso em profundidade</span>
- É definida um caminho (galho da árvore), e vamos até o fim dele antes de retornarmos para escolher outro.
- Contém três tipos:
### <span style="color:#8A2BE2">1. Percurso em ordem</span>
- Esquerda, raiz, direita
- mais comum
- Resultado: 1,2,3,4,6,8
![[Pasted image 20240604214514.png|500]]
### <span style="color:#8A2BE2">2. Percurso em pré-ordem</span>
- Raiz, esquerda, direita
- Resultado: 6,2,1,4,3,8
![[Pasted image 20240604214944.png|500]]
### <span style="color:#8A2BE2">3. Percurso em pós-ordem</span>
- Esquerda, direita, raiz
- Resultado: 1,3,4,2,8,6
![[Pasted image 20240604215246.png|500]]

## <span style="color:red">■ Implementação em Python</span> 
```python
# Progrma principal
Teste = BST()

Teste.inserir(7)
Teste.inserir(4)
Teste.inserir(9)
Teste.inserir(0)
Teste.inserir(5)
Teste.inserir(8)
Teste.inserir(13)
#          7

#        /  \

#      /     \

#     4        9

#    / \      /  \

#   0   5    8    13

print('Em ordem: ', Teste.emOrdem([]))
print('Em pré-ordem: ', Teste.preOrdem([]))
print('Em pós-ordem: ', Teste.posOrdem([]))
print('Em nível: ', Teste.emNivel())
# funções
class BST:

    def __init__(self, dado=None): # innicialização dos dados
        self.dado = dado
        self.esquerda = None
        self.direita = None

    def inserir(self, dado): # Metodo de inserir dados(recursiva)
        if (self.dado == None):
            self.dado = dado
        else:
            if (dado < self.dado): # caminho da esquerda
                if (self.esquerda): #self.esquerda == None:
                    self.esquerda.inserir(dado)
                else:
                    self.esquerda = BST(dado)
            else:
                if(self.direita): #self.direita == None: ## caminho da direita
                    self.direita.inserir(dado)
                else:
                    self.direita = BST(dado)

    def emOrdem(self, lst): # percurso em ordem #
        if (self.esquerda): # esquerda
            self.esquerda.emOrdem(lst)
        lst.append(self.dado) #root  # raiz
        if (self.direita):
            self.direita.emOrdem(lst) # direita
        return lst

    def preOrdem(self, lst): # percurso em pre-ordem
        lst.append(self.dado) #root #raiz
        if (self.esquerda):
            self.esquerda.preOrdem(lst) #esquerda
        if (self.direita):
            self.direita.preOrdem(lst) #direita
        return lst

    def posOrdem(self, lst): # percuso pos-ordem
        if (self.esquerda): # esquerda
            self.esquerda.posOrdem(lst)
        if (self.direita): # direita
            self.direita.posOrdem(lst) # raiz
        lst.append(self.dado) #root
        return lst

    def emNivel(self):
        nodoAtual = self
        lst = []
        fila = []
        fila.insert(0,nodoAtual)
        
        while(len(fila) > 0):
            nodoAtual = fila.pop()
            lst.append(nodoAtual.dado)
            if(nodoAtual.esquerda):
                fila.insert(0,nodoAtual.esquerda)
            if(nodoAtual.direita):
                fila.insert(0,nodoAtual.direita)
        return lst
```

---
---
