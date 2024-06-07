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
# ÁRVORE AVL
- Também conhecida como:
	- Árvore AVL
	- Árovere binária de busca balanceada
![[Pasted image 20240606205442.png|500]]

# <span style="color:yellow">Árvore AVL</span>
- Tem como objetivo melhorar o desempenho de busca/varredura, balanceada uma árvore binária, evitando ramos longos e gerando o maior número de ramificações binárias possíveis.![[Pasted image 20240606205731.png|500]]

## <span style="color:pink">■ Caracterísitca da árvore AVL</span> 
- Mesmas características da BST
- Uma propriedade a mais
	- A diferença de altura entre a subárvore da direita e da subárvore da esquerda será sempre 0,1 ou -1.

## <span style="color:green">O balanceamento</span> 
- <u> Passo 1</u> : Calcula -se a altura relativa daquele elemento para o lado direito da árvore. Nesse caso, pegamos o nível mais alto do lado direito daquele elemento e subtraímos do nível do elemento desejado.
- <u> Passo 2</U>: Calcula-se a altura relativa daquele elemento para o lado esquerdo da árvore. Nesse caso, pegamos o nível mais alto do lado esquerdo daquele elemento e subtraímos do nível do elemento desejado.
- <u>Passo 3</u>: Tendo a altura direita e a esquerda calculada, fazemos  a diferença entre elas (direita menos esquerda, sempre). Se o cálculo resultar em 2 ou -2, existe um desbalanceamento e uma rotação será necessária na árvore.
![[Pasted image 20240606211043.png]]
![[Pasted image 20240606211210.png]]

----
----
# ROTAÇÃO DA ÁRVORE AVL
![[Pasted image 20240606211347.png]]
![[Pasted image 20240606211437.png]]
![[Pasted image 20240606211558.png]]
![[Pasted image 20240606211611.png]]
![[Pasted image 20240606211619.png]]
![[Pasted image 20240606211656.png]]


---
---
# AULA PLÁTICA
- Árvore binária de busca:
```PYTHON
class BST:
    def __init__(self, dado=None):
        self.dado = dado
        self.esquerda = None
        self.direita = None

    def inserir(self, dado):
        if (self.dado == None):
            self.dado = dado
        else:
            if (dado < self.dado):
                if (self.esquerda): #self.esquerda == None:
                    self.esquerda.inserir(dado)
                else:
                    self.esquerda = BST(dado)
            else:
                if(self.direita): #self.direita == None:
                    self.direita.inserir(dado)
                else
                    self.direita = BST(dado)

    def emOrdem(self, lst):
        if (self.esquerda):
            self.esquerda.emOrdem(lst)
        lst.append(self.dado) #root
        if (self.direita):
            self.direita.emOrdem(lst)
        return lst


    def preOrdem(self, lst):
        lst.append(self.dado) #root
        if (self.esquerda):
            self.esquerda.preOrdem(lst)
        if (self.direita):
            self.direita.preOrdem(lst)
        return lst

    def posOrdem(self, lst):
        if (self.esquerda):
            self.esquerda.posOrdem(lst)
        if (self.direita):
            self.direita.posOrdem(lst)
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
#            Jader

#        /           \

#      /              \

#   Camila           Maria

#    / \             /     \

#  Ana   Eduardo   Leonardo   Yago

Teste = BST()

while True:
  print('1 - Inserir na árvore binária')
  print('2 - Remover da árvore binária')
  print('3 - Imprimir a árvore binária')
  print('4 - Sair')

  op = int(input("Escolha uma opção:"))
  if op == 1:
    dado = input('Qual nome deseja inserir?')
    Teste.inserir(dado)
  #elif op == 2:
    # dado = input('Qual nome deseja remover?')
    # Teste.deletar(dado)
  elif op == 3:
    print('Em ordem: ', Teste.emOrdem([]))
  elif op == 4:
    print('Encerrando...')
    break
  else:
    print("Selecione outra opção!\n")
```
- Árvore AVL
```python
class BST(object):
    def __init__(self, dado):
        self.dado = dado
        self.esquerda = None
        self.direita = None
        self.altura = 1

class AVL(object):
    def inserir(self, root, dado):
        # Passo 1 - BST convencional
        if not root:
            return BST(dado)
        elif dado < root.dado:
            root.esquerda = self.inserir(root.esquerda, dado)
        else:
            root.direita = self.inserir(root.direita, dado)
        # Passo 2 - Atualiza a altura do nó pai
        root.altura = 1 + max(self.getAltura(root.esquerda),
                              self.getAltura(root.direita))

        # Passo 3 - Balanceamento
        balanceamento = self.getBalanceamento(root)

        # Passo 4 - se o nó estiver desbalanceado,
        # tenta uma das rotações abaixo
        # Direita

        if balanceamento > 1 and dado < root.esquerda.dado:
            return self.direitaRotacao(root)
        # Esquerda
        if balanceamento < -1 and dado > root.direita.dado:
            return self.esquerdaRotacao(root)

        # Dupla - Esquerda Direita
        if balanceamento > 1 and dado > root.esquerda.dado:
            root.esquerda = self.esquerdaRotacao(root.esquerda)
            return self.direitaRotacao(root)

        # Dupla - Direita Esquerda
        if balanceamento < -1 and dado < root.direita.dado:
            root.direita = self.direitaRotacao(root.direita)
            return self.esquerdaRotacao(root)
        return root

    def esquerdaRotacao(self, z):

        y = z.direita
        T2 = y.esquerda
        # Rotacionando
        y.esquerda = z
        z.direita = T2

        # Atualiza os valores das alturas
        z.altura = 1 + max(self.getAltura(z.esquerda),
                           self.getAltura(z.direita))
        y.altura = 1 + max(self.getAltura(y.esquerda),
                          self.getAltura(y.direita))

        # retorna novo root
        return y
    def direitaRotacao(self, z):
        y = z.esquerda
        T3 = y.direita

        #Rotacionando
        y.direita = z
        z.esquerda = T3
        # Atualiza os valores das alturas
        z.altura = 1 + max(self.getAltura(z.esquerda),
                           self.getAltura(z.direita))
        y.altura = 1 + max(self.getAltura(y.esquerda),
                           self.getAltura(y.direita))
        # retorna novo root
        return y

    def getAltura(self, root):
        if not root:
            return 0
        return root.altura

    def getBalanceamento(self, root):
        if not root:
            return 0

        return self.getAltura(root.esquerda) - self.getAltura(root.direita)

    def emOrdem(self, root):
        if not root:
            return
        self.emOrdem(root.esquerda)
        print("{0} ".format(root.dado), end="")
        self.emOrdem(root.direita)
# Programa principal
"""         30

           /  \

         20   40

        /  \     \

       10  25    50"""

Teste = AVL()
root = None
root = Teste.inserir(root, 10)
root = Teste.inserir(root, 20)
root = Teste.inserir(root, 30)
root = Teste.inserir(root, 40)
root = Teste.inserir(root, 50)
root = Teste.inserir(root, 25)

Teste.emOrdem(root)
print()
```
![[Pasted image 20240606213421.png]]

### CÓDIGO EXPLICADO:

O código que você forneceu implementa uma árvore AVL em Python. Árvores AVL são uma variação de árvores binárias de busca que se mantêm balanceadas para garantir que a complexidade de inserção, exclusão e busca seja \(O(\log n)\). Vamos comentar o código passo a passo:

### Classe BST (Árvore Binária de Busca)

```python
class BST(object):
    def __init__(self, dado):
        self.dado = dado
        self.esquerda = None
        self.direita = None
        self.altura = 1
```

- A classe `BST` representa um nó em uma árvore binária de busca.
- `dado`: Valor armazenado no nó.
- `esquerda`: Referência ao nó filho à esquerda.
- `direita`: Referência ao nó filho à direita.
- `altura`: Altura do nó, usada para balanceamento na árvore AVL.

### Classe AVL (Árvore AVL)

```python
class AVL(object):
```

A classe `AVL` contém métodos para inserir nós na árvore e manter o balanceamento.

#### Método `inserir`

```python
    def inserir(self, root, dado):
```

- `root`: Raiz da subárvore onde o novo nó será inserido.
- `dado`: Valor a ser inserido na árvore.

Passo 1: Inserção convencional em uma árvore binária de busca

```python
        if not root:
            return BST(dado)
        elif dado < root.dado:
            root.esquerda = self.inserir(root.esquerda, dado)
        else:
            root.direita = self.inserir(root.direita, dado)
```

- Se `root` é `None`, cria e retorna um novo nó BST com o `dado`.
- Caso contrário, insere o `dado` recursivamente na subárvore esquerda ou direita, dependendo do valor.

Passo 2: Atualiza a altura do nó pai

```python
        root.altura = 1 + max(self.getAltura(root.esquerda),
                              self.getAltura(root.direita))
```

- Atualiza a altura do nó pai após a inserção do novo nó.

Passo 3: Calcula o fator de balanceamento

```python
        balanceamento = self.getBalanceamento(root)
```

- O fator de balanceamento é a diferença entre as alturas das subárvores esquerda e direita.

Passo 4: Realiza rotações se necessário para manter a árvore balanceada

```python
        if balanceamento > 1 and dado < root.esquerda.dado:
            return self.direitaRotacao(root)
        if balanceamento < -1 and dado > root.direita.dado:
            return self.esquerdaRotacao(root)
        if balanceamento > 1 and dado > root.esquerda.dado:
            root.esquerda = self.esquerdaRotacao(root.esquerda)
            return self.direitaRotacao(root)
        if balanceamento < -1 and dado < root.direita.dado:
            root.direita = self.direitaRotacao(root.direita)
            return self.esquerdaRotacao(root)
        return root
```

- Dependendo do fator de balanceamento e do valor do `dado`, são realizadas rotações simples ou duplas para manter a árvore balanceada.

#### Rotação Esquerda

```python
    def esquerdaRotacao(self, z):
        y = z.direita
        T2 = y.esquerda

        y.esquerda = z
        z.direita = T2

        z.altura = 1 + max(self.getAltura(z.esquerda),
                           self.getAltura(z.direita))
        y.altura = 1 + max(self.getAltura(y.esquerda),
                           self.getAltura(y.direita))

        return y
```

- Realiza uma rotação à esquerda em torno do nó `z`.
- Atualiza as alturas dos nós `z` e `y`.
- Retorna o novo nó raiz após a rotação.

#### Rotação Direita

```python
    def direitaRotacao(self, z):
        y = z.esquerda
        T3 = y.direita

        y.direita = z
        z.esquerda = T3

        z.altura = 1 + max(self.getAltura(z.esquerda),
                           self.getAltura(z.direita))
        y.altura = 1 + max(self.getAltura(y.esquerda),
                           self.getAltura(y.direita))

        return y
```

- Realiza uma rotação à direita em torno do nó `z`.
- Atualiza as alturas dos nós `z` e `y`.
- Retorna o novo nó raiz após a rotação.

#### Métodos Auxiliares

```python
    def getAltura(self, root):
        if not root:
            return 0
        return root.altura

    def getBalanceamento(self, root):
        if not root:
            return 0
        return self.getAltura(root.esquerda) - self.getAltura(root.direita)
```

- `getAltura`: Retorna a altura do nó.
- `getBalanceamento`: Calcula e retorna o fator de balanceamento do nó.

#### Percurso em Ordem

```python
    def emOrdem(self, root):
        if not root:
            return
        self.emOrdem(root.esquerda)
        print("{0} ".format(root.dado), end="")
        self.emOrdem(root.direita)
```

- `emOrdem`: Realiza um percurso em ordem (esquerda, raiz, direita) na árvore e imprime os valores dos nós.

### Programa Principal

```python
Teste = AVL()
root = None
root = Teste.inserir(root, 10)
root = Teste.inserir(root, 20)
root = Teste.inserir(root, 30)
root = Teste.inserir(root, 40)
root = Teste.inserir(root, 50)
root = Teste.inserir(root, 25)

Teste.emOrdem(root)
print()
```

- Cria uma instância da árvore AVL (`Teste`).
- Insere vários valores na árvore.
- Realiza um percurso em ordem na árvore e imprime os valores dos nós.

O resultado do percurso em ordem será uma sequência de valores ordenados: `10 20 25 30 40 50`.