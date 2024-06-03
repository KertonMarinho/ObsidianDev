# ✅BUBLE SORT
☻ Também conhecido como:
- Ordenação bolha
- Método bolha
- Ordenação por troca
## <span style="color:salmon">☻ A lógica de funcionamento</span> 
- Independentemente da linguagem, a lógica é a mesma.

■ Vamos ordenar um conjunto de dados de cinco elementos 
![[Pasted image 20240531143757.png]]
■ A ordenação deverá ser crescente, resultando em
![[Pasted image 20240531143840.png]]
■ O que é Buble Sort
- O algoritmo varre o conjunto de dados do inicio ao fim, comparando os dados de dois em dois e efetuando a troca, ser necessário.
- A varredura ocorrerá uma quantidade de vezes igual ao tamanho do conjunto de dados
![[Pasted image 20240531144624.png|400]]
- O que é Buble Sort faz:
	- Dois laços de repetiçao
	- uma condicional
	- a troca
vejamos:
```python
def bubbleSort(dados):
  #tamanho do conjunto de dados
  tam = len(dados)
  #laço que ocorre quantidade de vezes igual ao
  #tamanho do conjunto de dados
  for v in range(0, tam, 1): //Dois laços
    #laço interno que pega os valores em pares
    for i in range(0, tam-1, 1):
      #comparação
      if dados[i] > dados[i+1]: //uma condiconal
        #troca os dados usando variável auxiliar
        aux = dados[i] //troca
        dados[i] = dados[i+1] 
        dados[i+1] = aux
#Programa Principal
dados = [5, 4, 2, 1, 8]
bubbleSort(dados)
print(dados)
```
## <span style="color:#BDB76B">Complexidade Big-O</span>
![[Pasted image 20240531145240.png]]
## <span style="color:#FF4500">■ Buble Sort: algortimo melhorado</span>
```python
def bubbleSort(dados):
  tam = len(dados)
  for v in range(0, tam, 1):
    #flag começa em 0
    troca = 0
    for i in range(0, tam-1, 1):
      if dados[i] > dados[i+1]:
        aux = dados[i]
        dados[i] = dados[i+1]
        dados[i+1] = aux
        #se houve uma troca, mantém a flag em 1
        troca = 1
    if troca == 0:
      return
```
---
# 🤖MERGE SORT
- Também conhecido:
	- Ordenação por intercalação
	- Ordenação por mesclagem
## <span style="color:#BDB76B">☻ Logica de funcionamento</span>
```
Estratégia de dividr para conquistar
```
## ■ Dividimos o conjunto de dados sempre ao meio, até não ser mais possível dividir(caso base)
![[Pasted image 20240531151234.png|400]]
<span style="color:orange">Exemplo</span>
![[Pasted image 20240531151302.png]]
![[Pasted image 20240531151341.png]]
![[Pasted image 20240531151356.png]]
![[Pasted image 20240531151413.png]]
![[Pasted image 20240531151425.png]]
![[Pasted image 20240531151544.png]]
```python
def mergeSort(dados):
  #Condiçao que indica se os dados ainda precisam ser divididos
  if len(dados) > 1:
    #divide recursivamente
    meio = len(dados)//2
    esquerda = dados[:meio]
    direita = dados[meio:]
	mergeSort(esquerda)  #chama recursivamente
    mergeSort(direita)    #chama recursivamente
    # Qaundo ele para de chamar margesort ele avança para o próximo código:
    #intercala/mescla os dados
    i = j = k = 0
    while i<len(esquerda) and j<len(direita):
      if esquerda[i]<direita[j]:
        dados[k]=esquerda[i]
        i=i+1
      else:
        dados[k]=direita[j]
        j=j+1
      k=k+1
    while i<len(esquerda):
      dados[k]=esquerda[i]
      i=i+1
      k=k+1
    while j<len(direita):
      dados[k]=direita[j]
      j=j+1
      k=k+1
#Programa Principal
dados = [54, 26, 93, 17, 77, 31, 44, 55]
mergeSort(dados)
print(dados)
```
![[Pasted image 20240531152142.png]]
![[Pasted image 20240531152221.png]]

---
---
# ✅MARGE SORT: O ALGORITMO
```python
def mergeSort(dados):
  #Condiçao que indica se os dados ainda precisam ser divididos
  if len(dados) > 1:
    #divide recursivamente
    meio = len(dados)//2 #PONTO CENTRAL
    esquerda = dados[:meio] # DIVIDIR AO MEIO,LADO ESQUERDO
    direita = dados[meio:] # DIVIDIR AO MEIO, LADO DIREITO
	mergeSort(esquerda)  #chama recursivamente PARA O LAOD ESQUERDO
    mergeSort(direita)    #chama recursivamente PARA O LAOD DIREITO
    # ele VOLTA PARA O INÍCIO DA FUNÇAO ATÉ NÃO TER O MAIS QUE DIVIDIR
    # Qaundo ele para de chamar margesort ele avança para o próximo código:
    #intercala/mescla os dados
    i = j = k = 0
    while i<len(esquerda) and j<len(direita):
    #eLE COPIA OS DADOS PARA LOCAIS DE ORDENAÇãO CERTA
      if esquerda[i]<direita[j]:
        dados[k]=esquerda[i]
        i=i+1
      else:
        dados[k]=direita[j]
        j=j+1
      k=k+1
    while i<len(esquerda):
      dados[k]=esquerda[i]
      i=i+1
      k=k+1
    while j<len(direita):
      dados[k]=direita[j]
      j=j+1
      k=k+1
#Programa Principal
dados = [54, 26, 93, 17, 77, 31, 44, 55]
mergeSort(dados)
print(dados)
```
## <span style="color:#BDB76B">Complexidade Big-O</span>
![[Pasted image 20240531153337.png]]

---
---
# ✅QUICK SORT
- Estratégia de dividir para conquistar
- Opera diferentemente do Merge Sort
![[Pasted image 20240601114108.png]]
```python
#Versão clássica

def quickSort(dados,inicio,fim):

  if inicio < fim:
    posicao_de_particionamento = partition(dados,inicio,fim)
    quickSort(dados,inicio,posicao_de_particionamento - 1)
    quickSort(dados,posicao_de_particionamento + 1,fim)

def partition(dados,inicio,fim):
  pivo = dados[inicio]
  esq = inicio + 1
  dir = fim
  flag = False

  while not flag:
    while esq <= dir and dados[esq] <= pivo:
      esq = esq + 1

    while dir >= esq and dados[dir] >= pivo:
      dir = dir -1

    if dir < esq:
      flag = True
    else:

      temp = dados[esq]
      dados[esq] = dados[dir]
      dados[dir] = temp

  temp = dados[inicio]
  dados[inicio] = dados[dir]
  dados[dir] = temp
  return dir
#Programa Principal

dados = [50,25,92,16,76,30,43,54,19]
quickSort(dados,0,len(dados)-1)
print(dados)
```
## <span style="color:#BDB76B">■ Complexidade do Quick Sort</span>
![[Pasted image 20240601120351.png|400]]

---
![[Pasted image 20240601120527.png]]
```PYTHON
#Versão simplificada usando as característica do Python

def quickSort(dados):

  if len(dados) < 2:
    return dados

  else:
    pivo = dados[0]
    menores = [i for i in dados[1:] if i <= pivo]
    maiores = [i for i in dados[1:] if i >  pivo]

    return quickSort(menores) + [pivo] + quickSort(maiores)

#Programa Principal
dados = [50, 25, 92, 16, 76, 30, 43, 54, 19]
dados = quickSort(dados)
print(dados)
```
---
# 