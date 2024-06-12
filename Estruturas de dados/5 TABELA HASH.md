>[!ATENÇÃO]
>![[Pasted image 20240609221505.png|500]]
# TABELA HASH

![[Pasted image 20240609221756.png]]
![[Pasted image 20240609221832.png]]
# FUNÇÃO DO EMPREGO DE UMA FUNÇÃO HASH
## <span style="color:orange">■ Array</span>
- Acesso ao dado na memória do array: O(1)
- Busca de um dado no array: depende do algoritmo de busca, pesquisa sequencial O(n)  e pesquisa binária O(logn)

## <span style="color:orange">■ Tabela hash</span>
- Acesso ao dado na memória na tabela: O(1), pois é implementada como um array sequencial
- Busca de um dado na tabela hash: O(1), pois acessa o índice por meio de uma função hash
- Deixamos de precisae fazer uma varredura no array e tornamos o acesso ao dado independente do tamanho conjunto de dados

# IMPLEMENTAÇÕES EM LINGUAGENS DE PROGRAMAÇÃO

- C++, Container associativo Map
- Java, classe HashMap
- Python, dicionário (dict)

## <span style="color: #1E90FF">■ Relebrando Dicionário em python</span> (relembrando)

```python
#Cria o dicionário
caderno = dict()
#atribui dados ao dicionário
caderno['kiwi'] = 3.12
caderno['abacaxi'] = 1.97
caderno['banana'] = 2.65
caderno['uva'] = 6.99

#imprime o dicionário mapeado: chaves:valores
print(caderno)

#imprime somente o valor da chave banana
print(caderno['banana'])

#imprime todas a chaves
for fruta in caderno.keys():
    print(fruta)
```
![[Pasted image 20240609223040.png]]
## <span style="color:orange">OBS:</span> Não iremos trabalhar com estruturas de hash prontas igual acima na linguagem de programação, iremos apreender a construir uma do zero

## <span style="color:brown">■ Aplicação  de Hash</span>
- Podemos manter um rastreamento de jogadas efetuadas por jogadores em jogos como xarez, damas ou diversos outros jogos com alta quantidade de possibilidades
- Aplicações voltadas para segurança, como criptografia  e autenticação de mensagens e assinatura digital, empregam hashs
- A estrutura de dados-base que permite as populares criptomoedas, como bitcoin, operarem são hashs.
- Elas trabalham com cadeias de hashs altamente complexas para manipular transações, oferecendo segurança e descentralização das operações
---
---
# FUNÇÃO HASH
- Conhecido como algoritmo de hash
- É uma expressão aritmética e/ou lógica específica para resolver uma determinada aplicação
- A função hash não apresenta uma forma definida
- Deve ser projetada levando-se em consideração o tamanho do conjunto de dados, seu comportamento e os tipos de dados-chave utilizados
![[Pasted image 20240610221715.png]]

## <span style="color:yellow">■ Uma boa função hash</span>
☐ Fácil de ser calculada
- De nada valeria termos uma função com cálculos tão complexos e lentos que todo o tempo que seria ganho no acesso à informação com complexidade O(1), seria perdido calculando uma custosa função do array.
☐ Capaz de distribuir palavras-chaves o mais uniformemente possível dentro da estrutura do array

##  <span style="color:#32CD32">■ Método da divisão</span> 
![[Pasted image 20240610222254.png|300]]
- Em que K é uma chave qualquer, n é o tamanho do array, e MOD representa o resto de uma divisão.
![[Pasted image 20240610222455.png|500]]
---
# Hash universal

![[Pasted image 20240610222925.png|500]]
- O uso de uma única função hash pode resultar em uma situação em que todas as chaves precisam ser inseridas na mesma posição, gerando colisão e, consequentemente, piorando o desempenho do algoritmo.
- Para minimizar esse problema, adotamos um conjunto H de funções hash. Sorteamos uma função dentro da classe de funções disponíveis para fazer a inserção do dado.
![[Pasted image 20240610223349.png]]
---
---
# IMPLEMENTANDO UMA TABELA HASH
![[Pasted image 20240610223622.png]]

![[Pasted image 20240610223752.png]]

## <span style="color:salmon">■ Velocidade de busca</span> 
![[Pasted image 20240610223930.png|500]]

## <span style="color:red">Implementação em linguagem Python</span> 
```python
def hashFunc (k, n):
    return k % n

def hashFuncSigla (k, n):
    k = list(k)
    return (ord(k[0]) + ord(k[1])) % n 
    
#Programa principal
n = 10
tabelaHash = [None] * n
while True:
  print('1 - Inserir na tabela hash')
  print('2 - Remover na tabela hash')
  print('3 - Listar a tabela hash')
  print('4 - Sair')

  op = int(input("Escolha uma opção:"))
  if op == 1:
    chave = input('Digite a sigla de um estado: ')
    pos = hashFuncSigla(chave, n)
    if tabelaHash[pos] == None:
        tabelaHash[pos] = chave
    else:
        print('Já existe um dado neste lugar!')
  elif op == 2:
    chave = int(input('Digite o que deseja remover: '))
    pos = hashFuncSigla(chave, n)
    if tabelaHash[pos] == chave:
        tabelaHash[pos] = None
    else:
        print('Valor não localizado para a remoção!')
  elif op == 3:
      print(tabelaHash)
  elif op == 4:
    print('Encerrando...')
    break
  else:
    print("Selecione outra opção!\n")
```
![[Pasted image 20240610224512.png]]

Claro, vou explicar os códigos fornecidos com comentários:

### Função de Hashing com números

```python
def hashFunc(k, n):
    return k % n
```
Esta função `hashFunc` recebe dois parâmetros:
- `k`: a chave que será inserida na tabela hash.
- `n`: o tamanho da tabela hash.

Ela retorna o resto da divisão de `k` por `n`. Esse resto é a posição onde a chave será armazenada na tabela hash.

### Função de Hashing com Siglas

```python
def hashFuncSigla(k, n):
    k = list(k)  # Converte a string `k` em uma lista de caracteres.
    return (ord(k[0]) + ord(k[1])) % n
```
Esta função `hashFuncSigla` também recebe dois parâmetros:
- `k`: a chave, que neste caso é uma sigla de dois caracteres.
- `n`: o tamanho da tabela hash.

Ela converte a string `k` em uma lista de caracteres e calcula a soma dos valores ASCII dos dois primeiros caracteres da lista. Em seguida, retorna o resto da divisão dessa soma por `n`. Esse valor é a posição onde a sigla será armazenada na tabela hash.

### Programa Principal

```python
# Define o tamanho da tabela hash
n = 10
# Cria a tabela hash com `n` posições, inicialmente vazias (`None`)
tabelaHash = [None] * n

while True:
    # Menu de opções para o usuário
    print('1 - Inserir na tabela hash')
    print('2 - Remover na tabela hash')
    print('3 - Listar a tabela hash')
    print('4 - Sair')

    # Lê a opção escolhida pelo usuário
    op = int(input("Escolha uma opção:"))
    
    if op == 1:
        # Opção 1: Inserir uma nova sigla na tabela hash
        chave = input('Digite a sigla de um estado: ')
        pos = hashFuncSigla(chave, n)  # Calcula a posição usando a função de hash
        if tabelaHash[pos] == None:
            tabelaHash[pos] = chave  # Insere a sigla na posição calculada
        else:
            print('Já existe um dado neste lugar!')
    
    elif op == 2:
        # Opção 2: Remover uma sigla da tabela hash
        chave = input('Digite a sigla que deseja remover: ')
        pos = hashFuncSigla(chave, n)  # Calcula a posição usando a função de hash
        if tabelaHash[pos] == chave:
            tabelaHash[pos] = None  # Remove a sigla da posição calculada
        else:
            print('Valor não localizado para a remoção!')
    
    elif op == 3:
        # Opção 3: Listar todos os elementos da tabela hash
        print(tabelaHash)
    
    elif op == 4:
        # Opção 4: Sair do programa
        print('Encerrando...')
        break  # Sai do loop `while`
    
    else:
        # Opção inválida
        print("Selecione outra opção!\n")
```

### Explicação do Programa Principal:

1. **Inicialização**:
   - `n` é definido como 10, o que significa que a tabela hash terá 10 posições.
   - `tabelaHash` é inicializada com 10 elementos `None`.

2. **Loop Principal**:
   - Um loop `while` é usado para exibir um menu de opções até que o usuário escolha sair.
   
3. **Opções do Menu**:
   - **Opção 1**: Permite ao usuário inserir uma sigla na tabela hash.
     - A função `hashFuncSigla` calcula a posição na tabela onde a sigla será armazenada.
     - Se a posição estiver vazia (`None`), a sigla é inserida. Caso contrário, uma mensagem de erro é exibida.
   
   - **Opção 2**: Permite ao usuário remover uma sigla da tabela hash.
     - A função `hashFuncSigla` calcula a posição da tabela onde a sigla deveria estar armazenada.
     - Se a sigla na posição correspondente for a mesma que o usuário deseja remover, ela é removida (definida como `None`). Caso contrário, uma mensagem de erro é exibida.
   
   - **Opção 3**: Exibe o conteúdo da tabela hash.
   
   - **Opção 4**: Sai do programa.
   
   - Se uma opção inválida for escolhida, uma mensagem de erro é exibida.

Esse programa é uma implementação básica de uma tabela hash, utilizando siglas de estados como chaves e uma função de hashing simples para calcular as posições na tabela.

---
---
# Colisões em tabelas hash
- É impossível escrevermos uma função hash que seja livre de colisões
- Ocorrem quando uma chave precisa ser posicionada em uma posição em que já existe outra chave
### Existe três tipos de soluções para colisões:

## <span style="color:yellow">■ Endereçamento aberto</span>(duas)
- Quando todas as posições são conhecidas e se tem cada uma, no máximo, uma chave
![[Pasted image 20240611222709.png|500]]
![[Pasted image 20240611222840.png|500]]
![[Pasted image 20240611223207.png|500]]
## <span style="color:yellow">■ Endereçamento em cadeia</span>
- Cada posição poderá conter diversas chaves encadeadas
- A forma de implementar é utilizando uma lista encadeada simples
![[Pasted image 20240611223612.png|500]]
![[Pasted image 20240611223721.png|500]]

---
---
# IMPLEMENTANDO COLISÕES E DESEMPENHO HASH
## Endereçamento aberto e tentativa linear
## <span style="color:orange">■ Vamos implementar em Python</span>
- mesmo código básico anterior acrescido do tratamento das colisões:
```python
#Tentativa linear
def tentativaLinear(k, n, pos, tabelaHash):
  tentativa = pos
  while (tabelaHash[tentativa] != None):
    tentativa += 1
    if tentativa == n:
      tentativa = 0
    if tentativa == pos:
      tentativa = -1
      break
  return tentativa
  
  #Tentativa linear
def tentativaLinear(k, n, pos, tabelaHash):
  tentativa = pos
  
  while (tabelaHash[tentativa] != None):
    tentativa += 1
    if tentativa == n:
      tentativa = 0
    if tentativa == pos:
      tentativa = -1
      break
  return tentativa

#Tentativa linear Remover
def tentativaLinearDel(k, n, pos, tabelaHash):
  tentativa = pos
  while (tabelaHash[tentativa] != k):
    tentativa += 1
    if tentativa == n:
      tentativa = 0
    if tentativa == pos:
      tentativa = -1
      break
  return tentativa

#Programa principal
n = 10
tabelaHash = [None] * n
while True:
  print('1 - Inserir na tabela hash')
  print('2 - Remover na tabela hash')
  print('3 - Listar a tabela hash')
  print('4 - Sair')
  op = int(input("Escolha uma opção:"))
  if op == 1:
    chave = input('Digite a sigla de um estado: ')
    pos = hashFuncSigla(chave, n)
    if tabelaHash[pos] == None:
        tabelaHash[pos] = chave

    else: #Colisão!
        pos = tentativaLinear(chave, n, pos, tabelaHash)
        if pos != -1:
          tabelaHash[pos] = chave
        else:
          print('Tabela hash cheia. Impossível inserir!')

  elif op == 2:
    chave = input('Digite o que deseja remover: ')
    pos = hashFuncSigla(chave, n)
    if tabelaHash[pos] == chave:
        tabelaHash[pos] = None

    else: #Colisão
        pos = tentativaLinearDel(chave, n, pos, tabelaHash)
        if pos != -1:
          tabelaHash[pos] = None
        else:
            print('Valor não localizado para a remoção!')
  elif op == 3:
      print(tabelaHash)
  elif op == 4:
    print('Encerrando...')
    break
  else:
    print("Selecione outra opção!\n")
```

## <span style="color:aquamarine">■ Fator de carga</span> 
- Ajuda a definir se o tamanho da tabela hash é suficiente para uma determinada aplicação
![[Pasted image 20240611225018.png]]
<span style="color:orange">Exemplo:</span>
![[Pasted image 20240611225046.png|500]]
- Fator de carga acima de 1.0 indica a necessidade de redimensionar o array
- Redimensionar o tempo todo tem um alto custo computacional
---
# Comparativo de desempenho
![[Pasted image 20240611225334.png|500]]

---
---
# Aula plática

## <span style="color:#BDB76B">Tabela hash com tratamento linear</span>
```python
def hashFunc (k, n):
    return k % n
def hashFuncSigla (k, n):
    k = list(k)
    return (ord(k[0]) + ord(k[1])) % n
    
#Tentativa linear
def tentativaLinear(k, n, pos, tabelaHash):
  tentativa = pos
  while (tabelaHash[tentativa] != None):
    tentativa += 1
    if tentativa == n:
      tentativa = 0
    if tentativa == pos:
      tentativa = -1
      break
  return tentativa

#Tentativa linear Remover
def tentativaLinearDel(k, n, pos, tabelaHash):
  tentativa = pos
  while (tabelaHash[tentativa] != k):
    tentativa += 1
    if tentativa == n:
      tentativa = 0
    if tentativa == pos:
      tentativa = -1
      break
  return tentativa

#Programa principal
n = 10
tabelaHash = [None] * n

while True:
  print('1 - Inserir na tabela hash')
  print('2 - Remover na tabela hash')
  print('3 - Listar a tabela hash')
  print('4 - Sair')
  op = int(input("Escolha uma opção:"))
  if op == 1:
    chave = input('Digite a sigla de um estado: ')
    pos = hashFuncSigla(chave, n)
    if tabelaHash[pos] == None:
        tabelaHash[pos] = chave
    else: #Colisão!
        pos = tentativaLinear(chave, n, pos, tabelaHash)
        if pos != -1:
          tabelaHash[pos] = chave
        else:
          print('Tabela hash cheia. Impossível inserir!')
  elif op == 2:
    chave = input('Digite o que deseja remover: ')
    pos = hashFuncSigla(chave, n)
    if tabelaHash[pos] == chave:
        tabelaHash[pos] = None
    else: #Colisão
        pos = tentativaLinearDel(chave, n, pos, tabelaHash)
        if pos != -1:
          tabelaHash[pos] = None
        else:
            print('Valor não localizado para a remoção!')
  elif op == 3:
      print(tabelaHash)
  elif op == 4:
    print('Encerrando...')
    break
  else:
    print("Selecione outra opção!\n")
```

## <span style="color:#BDB76B">TABELA HASH COM ENDEREÇAMENTO EM CADEIA</span>
```python
class ElementoDaListaSimples:
    def __init__(self, chave=None, dado=None):
        self.chave = chave
        self.dado = dado
        self.proximo = None

class ListaEncadeadaSimples:
    def __init__(self):
        self.head = None
    def inserir(self, chave, dado):
        nodo = ElementoDaListaSimples(chave, dado)
        if self.head == None:
            self.head = nodo
            return 0
        else:
            nodo.proximo = self.head
            self.head = nodo
            return 0

    def imprimir(self):
        temp = self.head
        while temp:
            print(f"{temp.chave}\t{temp.dado}")
            temp = temp.proximo

class TabelaHash:
    def __init__(self):
        self.tam = 10
        self.length = 0
        self.h = [ListaEncadeadaSimples() for i in range(0, self.tam)]

    def hashFunc(self, k):
        k = list(k)
        return (ord(k[0]) + ord(k[1])) % self.tam

    def inserir(self, chave, dado):
        pos = self.hashFunc(chave)
        add = self.h[pos].inserir(chave, dado)

    def imprimir(self):
        for i in range(0, self.tam):
            self.h[i].imprimir()

#Programa principal
Teste = TabelaHash()
while True:
  print('1 - Inserir na tabela hash')
  print('2 - Remover na tabela hash')
  print('3 - Listar a tabela hash')
  print('4 - Sair')

  op = int(input("Escolha uma opção:"))
  if op == 1:
    chave = input('Digite a sigla de um estado: ')
    dado = input('Digite o nome do estado: ')
    Teste.inserir(chave, dado)
  elif op == 2:
    chave = input('Digite o que deseja remover: ')
    
#IMPLEMENTAR
  elif op == 3:
      Teste.imprimir()
  elif op == 4:
    print('Encerrando...')
    break
  else:
    print("Selecione outra opção!\n")
```