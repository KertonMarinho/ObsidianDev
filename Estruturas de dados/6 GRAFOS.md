# CONCEITOS DE GRAFOS
## <span style="color:yellow">Grafos G</span> é um conjunto de vértices conectados através de arestas sem uma distribuição fixa ou padronizada.

## <span style="color:yellow">Vértices V</span> de um grafo são seus pontos. Cada ponto poderá ser um ponto de encontro entre caminhos (rotas)  de um grafo, por exemplo

## <span style="color:yellow">Arestas E</span> São as linhas de conexão entre vértices. Cada arestas conecta dois vértices

![[Pasted image 20240616215529.png|500]]

---
# CONCEITOS
## <span style="color:#FF00FF">Grafos completos</span> 
- Quando existe uma, e somente uma, aresta para cada distinto de vértices 
## <span style="color:#FF69B4">Grafos trivial</span>
- É um grafo com unicamente um vértice.

![[Pasted image 20240616215938.png|500]]
![[Pasted image 20240616220112.png|500]]
![[Pasted image 20240616220224.png|500]]

---
---
# REPRESENTAÇÃO DE GRAFOS
## <span style="color:#FF7F50">■ Matriz de adjacências</span>
- Matriz de dimensão V, onde V é o número de vértices. E preenchida com:
![[Pasted image 20240616220926.png]]
![[Pasted image 20240616221923.png|500]]
![[Pasted image 20240616222015.png|500]]
## <span style="color:#FF7F50">■ Lista de adjacências</span>
- Criamos listas encadeadas de vizinhos de cada vértice
- Vizinhos de um vértice são todos os outros vértices que estão conectados a ele
![[Pasted image 20240616222409.png|500]]

![[Pasted image 20240616222443.png|500]]
## <span style="color:#FF8C00"> ■ Comparativo</span>
- Em uma matriz de adjacência, sempre utilizaremos |V|² de espaço na memória, ou seja, se tivermos um grafo com 10 mil vértices, teríamos 100.000.000 bytes de uso de memórir
- Portanto, uma desvantagem dessa representação é o excesso de uso de memória, especialmente para grafos grandes.
- Em termos de complexidade de tempo de execução, a matriz é mais rápida que a lista de adjacência para grafos densos |E| = |V|², pois acessa qualquer dado com o mesmo tempo
- Por fim, essa representação é mais simples de ser aplicada para grafos ponderados
- Uma lista de adjacência é mais rápido, e emprega menos espaço de memória para grafos esparsos |E| = |V|
- Em contrapartida, para grafos bastante densos, são mais lentas do que a verão matricial, isso porque grafos densos tendem a formar grandes listas de vizinhos, que, quando representadas por listas encadeadas, geram um tempo de acesso ao dado bastante elevado.
---
---
# BUSCA EM PROFUNDIDADE
- Conhecida como
	- depth-first Search(DFS)
- Usamos para descobrir um grafo, ou fazer uma varredura, passando por todos os vértices uma única vez.
- Agora, queremos andar por cada vértice do grafo, sem repetir nenhum, partindo de um vértice de origem. Cada vértice visitado é marcado para que não seja revisitado. O algoritmo é encerrado quando o último vértice é visitado
- Podemos entender que cada quadradinho do labirinto pode ser considerado um vértice. Se houver conexão entre dois quadradinhos, ou seja, se eles se encostam, existe, portanto, uma aresta de conexão entre eles.

Não existe aresta nos quadradinhos marcados em cinza. Esses quadrados são considerados paredes em nosso labirinto. Podemos representar o labirinto como um grafo quadrado de 7x7 vértices, conforme Figura 11 (a) a seguir
![[Pasted image 20240617214947.png|500]]
![[Pasted image 20240617215947.png]]

----
### Desejamos iniciar a descoberta de nosso grafo pelo vértice zero. Na Figura 15 a seguir, vemos que esse vértice é então marcado como já visitado (cor azul). Assim, não é possível mais revisitá-lo. Em nossa pilha, que estava vazia, colocamos nosso vértice inicial zero.
![[Pasted image 20240617221234.png]]
- Como esse vértice V<sub>0</sub>está no topo da pilha, vamos acessar sua respectiva lista de vizinhos. Acessamos, então, o primeiro elemento da lista encadeada de vizinhos de V<sub>0</sub>, que é o V <sub>1</sub>. Imediatamente, colocamos esse vértice como já visitado (cor azul) no grafo e inserimos ele no topo da pilha, acima de V<sub>0</sub> Agora, temos dois quatros vértices já visitados.
![[Pasted image 20240617221317.png]]
- O próximo vértice a ser visitado será o primeiro vizinho da lista encadeada do vértice V<sub>1</sub>. É importante perceber que nem terminamos de varrer toda a lista encadeada de V<sub>0</sub>, mas já pulamos para a lista de outro vértice. O primeiro vizinho de V<sub>1 </sub> é o próprio V<sub>0</sub>, que na verdade já foi visitado. Nesse caso, passamos para o próximo elemento da lista encadeada, que é o vértice V<sub>2</sub>. Este, ainda não visitado (em laranja), é então marcado como visitado e colocado no topo da pilha, que agora contém três elementos. Vejamos a etapa 4 a seguir.
![[Pasted image 20240617221346.png]]
- Nesse momento, estamos na lista encadeada do vértice V<sub>2</sub>. Na Figura logo abaixo, a seguir, vemos que precisamos acessar o primeiro vizinho do vértice V<sub>2</sub>(em laranja); esse vizinho é o vértice V<sub>1</sub>, que já foi visitado. Ainda, toda a lista de vizinhos do vértice V<sub>2</sub> já foi verificada, não havendo mais nenhum vizinho de V<sub>2</sub>.
- Desempilhamos o vértice atual V<sup>2</sup> e voltamos para o elemento abaixo dele na pilha (V<sub>1</sub>), que já teve todos os seus vizinhos visitados. Desempilhamos ele, voltamos para V<sub>0</sub> e acessamos o segundo elemento da lista encadeada, pois o primeiro havia sido visitado anteriormente. Encontramos, assim, o último vértice não visitado, o V<sub>3</sub>. Marcamos ele e colocamos no topo da pilha.
![[Pasted image 20240617221431.png]]
- Todos os vértices já haviam sidos visitados na etapa anterior. Porém, ainda precisamos encerrar nosso algoritmo. Na Figura abaixo a seguir, no vértice V<sub>3</sub>, verificamos o primeiro vizinho dele na lista encadeada, o vértice  V<sub>0</sub>, anteriormente marcado. Chegamos ao final da lista; desempilhamos V<sub>3</sub> , restando somente V<sub>0</sub>
![[Pasted image 20240617221519.png]]
- Embora V<sub>0</sub> já tenha sido visitado, faltava desempilhá-lo (Figura abaixo). Fazendo isso, temos nossa pilha vazia e todos os quatro vértices visitados, encerrando nosso algoritmo de busca por profundidade.
![[Pasted image 20240617221546.png]]

---
---
# Busca de Largura
- Conhecida como:
	- Breath-First Search (BFS)
- Usamos para descobrir um grafo, ou fazer uma varredura, passando por todos os vértices uma única vez.
-  A busca em largura anda em todos os lados ao mesmo tempo
- A busca de profundidade anda em pilha enquanto a busca de largura anda em fila
![[Pasted image 20240617223012.png|500]]
![[Pasted image 20240617223043.png|500]]
- Na Figura abaixo, a seguir, está ilustrado o grafo que será trabalhado. É interessante perceber que temos agora um _array_ de distâncias, que manterá armazenada a distância de cada vértice em relação ao vértice de origem, ajudando na decisão de qual será o próximo vértice a ser visitado.
- ![[Pasted image 20240617223436.png]]
- A proposta desse algoritmo é a de partir de um vértice de origem e acessar a lista de adjacências daquele vértice, ou seja, seus vizinhos. Partindo da lista de vizinhos, calcula-se a distância deles para o vértice de origem e salva-se em um vetor de distâncias. Os elementos vão sendo enfileirados à medida que vão sendo acessados nas listas encadeadas.
- Iniciamos nossa análise no vértice V<sub>0</sub> novamente. Nesse modo, podemos imediatamente marcá-lo como já visitado (cor azul). Colocamos também esse vértice na fila. Lembre-se de que, em uma fila, a inserção acontece sempre no final dela (Fifo). Como a fila estava vazia, o inserimos na primeira posição. A distância do vértice de origem para ele mesmo será sempre zero (Figura abaixo).
![[Pasted image 20240617223655.png]]
- Na Figura abaixo, a seguir, encontramos o primeiro vizinho de V<sub>0</sub> , que é V<sub>1</sub>. Colocamos V<sub>1</sub> na fila e calculamos a distância dele para a origem. O cálculo da distância é feito usando o valor da distância do vértice atual (valor zero) e acrescentando uma unidade, resultando em distância um (<sub>0+1=1</sub>), conforme Figura abaixo, a seguir.
![[Pasted image 20240617224127.png]]
- Na Figura abaixo, a seguir, passamos para o próximo vizinho do vértice  V<sub>0</sub>. O vértice V<sub>3</sub> recebe o mesmo tratamento que V<sub>1</sub> : sua distância é de valor um <sup>0+1=1</sup>, pois está a um salto de distância da origem, e ele é colocado no final da fila, após o vértice V<sub>1</sub>. Assim, encerramos a varredura dos vizinhos do vértice V<sub>0</sub> e calculamos as distâncias, mas ainda não visitamos eles.
![[Pasted image 20240617224450.png]]
- Na Figura abaixo, a seguir, com V<sub>0</sub> encerrado (cor verde), vamos para o próximo vértice da fila, o vértice V<sub>1</sub>0. Marcamos ele, o removemos da fila e acessamos sua lista encadeada de vizinhos. O primeiro vizinho é o vértice V<sub>0</sub>, que já foi visitado, portanto, seguimos para o próximo vértice, que é V<sub>2</sub>Esse vértice ainda não foi visitado, então colocamos ele ao final da fila e calculamos uma distância. Como ele está a dois vértices de distância da origem, sua distância é dois (<sup>1+1=2</sup>).
![[Pasted image 20240617224539.png]]
- Na etapa 4, já encerramos os cálculos de todas as distâncias possíveis e enfileiramos todos os vértices restantes, V<sub>3</sub> e V<sub>2</sub>. Assim, na etapa 5 (Figura abaixo), removemos da fila o próximo vértice V<sub>3</sub>e marcamos ele (cor azul). Acessamos, então, a sua lista de vizinhos. Nela, só existe o vértice V<sub>0</sub>, já acessado. Portanto, nada mais fazemos nessa etapa e podemos passar para o próximo elemento da nossa fila.
![[Pasted image 20240617224606.png]]
- Na Figura abaixo, a seguir, acessamos o vértice V<sub>2</sub>, último ainda não descoberto, e vemos que ele tem como vizinho somente o vértice V<sub>1</sub>. Como o vértice 1 já é conhecido, nada mais fazemos nessa etapa.
![[Pasted image 20240617224641.png]]
- Por fim, na etapa 7 (Figura abaixo), estamos com todos nossos elementos já visitados e todas as listas encadeadas varridas. Nosso algoritmo se encerra aqui.
![[Pasted image 20240617224710.png]]

---
## ■ <span style="color:yellow">DFS x BFS</span>
- DFS funciona com uma pilha
- BFS funciona como uma filha
- Complexidade de ambas
	- O ( |V| + |E| )
---
---
# ☐ Caminho Mínimo(algoritmo de Dijkstra)
- Encontra a melhor rota/caminho entre dois vértices em um grafo ponderado
- Métrica aditiva
	- Menor rota considerando o menor peso somado entre os caminhos
### Na Figura abaixo, a seguir, temos o estado inicial da lista de adjacências ponderadas. Os valores que estão entre parênteses são os pesos das arestas. Por exemplo, na lista encadeada do vértice V<sub>1</sub>, temos como primeiro elemento V<sub>0</sub>e o peso da aresta entre eles está indicado pelo valor 2 entre parênteses.
![[Pasted image 20240617230121.png|500]]
O algoritmo do caminho mínimo precisa calcular as menores rotas de um vértice em relação a todos os outros. Portanto, um vetor com distâncias fica armazenado. O estado inicial desse vetor é que todas as rotas iniciam com um valor infinito, ou seja, como se o caminho de um vértice até o outro não fosse conhecido. À medida que os trajetos vão sendo calculados, os pesos das rotas vão sendo alterados.
Vamos explicar o funcionamento do algoritmo iniciando no vértice V<sub>1</sub>. Assim, encontraremos a rota de V<sub>1</sub> para todos os outros vértices existentes no grafo ponderado.
Na Figura abaixo, a seguir, iniciamos a primeira etapa de operação do método. Como partiremos de V<sub>1</sub>, já iniciaremos acessando a lista de vizinhos desse vértice e calculando as rotas para eles. Iniciamos encontrando a rota de V<sub>1</sub>para ele mesmo. Nesse caso, o vértice de origem para ele mesmo terá sempre peso zero, conforme apresentado no vetor de distâncias.

Em seguida, acessamos o _head_ da lista encadeada de V<sub>1</sub>, que é V<sub>0</sub>, com um peso de aresta de 2. Assim, o cálculo da distância entre eles será o peso em <sup>V<sub>1</sub>=0</sup> acrescido do peso dessa aresta, resultando no valor 2. Esse valor, por ser menor do que infinito, é colocado no vetor na posição de V<sub>0</sub>. O cálculo está apresentado no canto inferior direito da Figura abaixo.
![[Pasted image 20240617231502.png]]
seguimos na figura abaixo, 4, a seguir, acessando o segundo elemento da lista de vizinhos de 𝑉0. Em 𝑉2, fazemos o peso de 𝑉0 = 0 acrescido da aresta para 𝑉2, resultando no valor 4, que por ser menor do que infinito é colocado como rota válida entre 𝑉1 e 𝑉2.
![[Pasted image 20240618215602.png]]
A etapa 3 está na Figura abaixo, a seguir. De forma semelhante às duas etapas anteriores, calculamos a distância entre 𝑉1 e 𝑉3, resultando em 5, e colocamos no vetor de distâncias na posição de 𝑉3
![[Pasted image 20240618215653.png]]
Todos os vizinhos do vértice 𝑉1 têm suas rotas calculadas. Um panorama geral é apresentado na Figura 36, a seguir, indicando que todos os vizinhos foram calculados (cor verde)
![[Pasted image 20240618215725.png]]
Precisamos passar para o próximo vértice e calcular as rotas partindo de 𝑉1 e passando por este vértice intermediário. O vértice que vamos assumir agora é o de menor caminho no vetor distâncias e que ainda não tinha sido marcado. Será, portanto, o vértice 𝑉0, com distância para 𝑉1 sendo 2. Seu primeiro vizinho é o próprio vértice de origem 𝑉0, na Figura 37, a seguir. Como esse vértice já foi visitado, podemos pulá-lo nessa análise.
![[Pasted image 20240618215758.png]]Na Figura 38 adiante, seguimos para o próximo vizinho de 𝑉0, o 𝑉3. Isso significa que calcularemos uma rota 𝑉1 → 𝑉0 → 𝑉3. O peso dessa rota será o peso até 𝑉0, já calculado e de valor 2, somado com o peso da aresta 𝑉0 e 𝑉3, que é 2 também. Assim 2 + 2 = 4. Observemos agora algo interessante. O peso da rota de 𝑉1 até 𝑉3, passando por 𝑉0, resultou em peso 4. Anteriormente, tínhamos calculado o peso da rota direta entre 𝑉1 e 𝑉3, cujo valor resultou em 5. Portanto, a rota passando por 𝑉0 tem um peso menor (4 < 5), resultando em uma nova rota até 𝑉3. Notemos que uma rota com peso menor, mesmo passando por um vértice a mais, acaba resultando em um caminho menor que o outro. 

``Figura 38 – Algoritmo de Dijkstra, partindo de 𝑉1: etapa 6
![[Pasted image 20240618215843.png]]
Na Figura 39 adiante, já encerramos nossos cálculos passando pelo vértice 𝑉0 . Seguimos então para o próximo vértice não visitado e de menor distância no vetor, o vértice 𝑉2. O único vizinho de 𝑉2 é vértice origem 𝑉1, já visitado. Portanto, não existirá uma nova rota aqui. 29 
``
``Figura 39 – Algoritmo de Dijkstra, partindo de 𝑉1: etapa 7
![[Pasted image 20240618215916.png]]
Na Figura 40 adiante, seguimos para o próximo, e último, vértice não visitado e de menor distância no vetor, o vértice 𝑉3. O primeiro vizinho de 𝑉3 é 𝑉0, assim faremos o trajeto 𝑉1 → 𝑉3 → 𝑉0. O custo até 𝑉3 é 4 e o peso de 𝑉3 até 𝑉0 é 2, resultando em 6, custo superior a atualmente a rota de 4. 

``Figura 40 – Algoritmo de Dijkstra, partindo de 𝑉1: etapa 8
![[Pasted image 20240618215945.png]]
Na Figura 41, a seguir, temos o segundo vizinho de 𝑉3, o 𝑉1, que é a própria origem. Portanto, não precisamos analisar. 

``Figura 41 – Algoritmo de Dijkstra, partindo de 𝑉1: etapa 9
![[Pasted image 20240618220008.png]]Na Figura 42, a seguir, já percorremos todos os vizinhos de todos os vértices e calculamos todas as rotas possíveis. Desse modo, as distâncias resultantes estão colocadas no vetor de distâncias, e abaixo de cada valor está a sequência de vértices para aquela rota. Por exemplo, para atingirmos o vértice 𝑉3, a melhor rota encontrada foi 𝑉1 → 𝑉0 → 𝑉3, e não 𝑉1 → 𝑉3 diretamente. 

``Figura 42 – Algoritmo de Dijkstra, partindo de 𝑉1: etapa 10
![[Pasted image 20240618220038.png]]

---
---
# 🌚AULA PLÁTICA
## <span style="color:aquamarine">■ Criando Grafos</span>
Aqui está a implementação do grafo com lista de adjacência comentada, explicando cada função:

```python
# Implementação com lista de adjacência
class Vertice:
    def __init__(self, n):
        # Inicializa o vértice com um nome e uma lista vazia de vizinhos
        self.nome = n
        self.vizinhos = list()

    def addVizinho(self, v):
        # Adiciona um vizinho ao vértice, se ainda não estiver presente
        if v not in self.vizinhos:
            self.vizinhos.append(v)
            # Mantém a lista de vizinhos ordenada
            self.vizinhos.sort()

class Grafo:
    # Dicionário de vértices, onde a chave é o nome do vértice e o valor é o objeto Vértice
    vertices = {}

    def addVertice(self, vertice):
        # Verifica se o objeto é de fato um objeto de vértice e se ele ainda não existe no grafo
        if isinstance(vertice, Vertice) and vertice.nome not in self.vertices:
            # Adiciona o vértice no dicionário de vértices
            self.vertices[vertice.nome] = vertice
            return True
        else:
            return False

    def addAresta(self, u, v):
        # Verifica se ambos vértices de fato existem no grafo para criar a aresta
        if u in self.vertices and v in self.vertices:
            # Percorre todos os vértices no grafo
            for key, valor in self.vertices.items():
                # Adiciona v na lista de vizinhos de u
                if key == u:
                    valor.addVizinho(v)
                # Adiciona u na lista de vizinhos de v
                if key == v:
                    valor.addVizinho(u)
            return True
        else:
            return False

    # Imprime a lista de adjacências do grafo
    def printGrafo(self):
        # Percorre todos os vértices ordenados pelo nome
        for key in sorted(list(self.vertices.keys())):
            # Imprime o nome do vértice e sua lista de vizinhos
            print(key + str(self.vertices[key].vizinhos))

# Programa principal:
G = Grafo()
# Adiciona vértices ao grafo, de 'A' a 'F'
for i in range(ord('A'), ord('G')):
    G.addVertice(Vertice(chr(i)))

# Define as arestas a serem adicionadas no formato 'UV'
arestas = ['AB', 'AD', 'BC', 'CD', 'CE', 'CF']
# Adiciona cada aresta ao grafo
for aresta in arestas:
    G.addAresta(aresta[:1], aresta[1:])

# Imprime a lista de adjacências do grafo
G.printGrafo()
```

### Explicação dos principais componentes:

1. **Classe `Vertice`**:
    - `__init__`: Inicializa um vértice com um nome (`n`) e uma lista vazia de vizinhos.
    - `addVizinho`: Adiciona um vizinho à lista de vizinhos, se ainda não estiver presente, e mantém a lista ordenada.

2. **Classe `Grafo`**:
    - `vertices`: Um dicionário onde as chaves são os nomes dos vértices e os valores são os objetos `Vertice`.
    - `addVertice`: Adiciona um vértice ao grafo, verificando se é uma instância de `Vertice` e se ainda não está presente.
    - `addAresta`: Adiciona uma aresta entre dois vértices, verificando se ambos os vértices existem no grafo. Adiciona cada vértice à lista de vizinhos do outro.
    - `printGrafo`: Imprime a lista de adjacência de todos os vértices no grafo.

3. **Programa Principal**:
    - Cria uma instância do grafo.
    - Adiciona vértices com os nomes de 'A' a 'F'.
    - Adiciona arestas entre os vértices especificados na lista `arestas`.
    - Imprime a lista de adjacência do grafo.

---
---
# Aqui está a implementação do grafo com lista de adjacência comentada, explicando cada função:

```python
# Implementação com lista de adjacência
class Vertice:
    def __init__(self, n):
        # Inicializa o vértice com um nome e uma lista vazia de vizinhos
        self.nome = n
        self.vizinhos = list()

    def addVizinho(self, v):
        # Adiciona um vizinho ao vértice, se ainda não estiver presente
        if v not in self.vizinhos:
            self.vizinhos.append(v)
            # Mantém a lista de vizinhos ordenada
            self.vizinhos.sort()

class Grafo:
    # Dicionário de vértices, onde a chave é o nome do vértice e o valor é o objeto Vértice
    vertices = {}

    def addVertice(self, vertice):
        # Verifica se o objeto é de fato um objeto de vértice e se ele ainda não existe no grafo
        if isinstance(vertice, Vertice) and vertice.nome not in self.vertices:
            # Adiciona o vértice no dicionário de vértices
            self.vertices[vertice.nome] = vertice
            return True
        else:
            return False

    def addAresta(self, u, v):
        # Verifica se ambos vértices de fato existem no grafo para criar a aresta
        if u in self.vertices and v in self.vertices:
            # Percorre todos os vértices no grafo
            for key, valor in self.vertices.items():
                # Adiciona v na lista de vizinhos de u
                if key == u:
                    valor.addVizinho(v)
                # Adiciona u na lista de vizinhos de v
                if key == v:
                    valor.addVizinho(u)
            return True
        else:
            return False

    # Imprime a lista de adjacências do grafo
    def printGrafo(self):
        # Percorre todos os vértices ordenados pelo nome
        for key in sorted(list(self.vertices.keys())):
            # Imprime o nome do vértice e sua lista de vizinhos
            print(key + str(self.vertices[key].vizinhos))

# Programa principal:
G = Grafo()
# Adiciona vértices ao grafo, de 'A' a 'F'
for i in range(ord('A'), ord('G')):
    G.addVertice(Vertice(chr(i)))

# Define as arestas a serem adicionadas no formato 'UV'
arestas = ['AB', 'AD', 'BC', 'CD', 'CE', 'CF']
# Adiciona cada aresta ao grafo
for aresta in arestas:
    G.addAresta(aresta[:1], aresta[1:])

# Imprime a lista de adjacências do grafo
G.printGrafo()
```

### Explicação dos principais componentes:

1. **Classe `Vertice`**:
    - `__init__`: Inicializa um vértice com um nome (`n`) e uma lista vazia de vizinhos.
    - `addVizinho`: Adiciona um vizinho à lista de vizinhos, se ainda não estiver presente, e mantém a lista ordenada.

2. **Classe `Grafo`**:
    - `vertices`: Um dicionário onde as chaves são os nomes dos vértices e os valores são os objetos `Vertice`.
    - `addVertice`: Adiciona um vértice ao grafo, verificando se é uma instância de `Vertice` e se ainda não está presente.
    - `addAresta`: Adiciona uma aresta entre dois vértices, verificando se ambos os vértices existem no grafo. Adiciona cada vértice à lista de vizinhos do outro.
    - `printGrafo`: Imprime a lista de adjacência de todos os vértices no grafo.

3. **Programa Principal**:
    - Cria uma instância do grafo.
    - Adiciona vértices com os nomes de 'A' a 'F'.
    - Adiciona arestas entre os vértices especificados na lista `arestas`.
    - Imprime a lista de adjacência do grafo.
![[Pasted image 20240618221546.png]]

---
## <span style="color:brown">■ DFS</span>
Aqui está a implementação do grafo com lista de adjacência comentada, explicando cada função:

```python
# Implementação com lista de adjacência
class Vertice:
    def __init__(self, n):
        # Inicializa o vértice com um nome e uma lista vazia de vizinhos
        self.nome = n
        self.vizinhos = list()
        
        # Inicializa a ordem de descoberta e a flag de visitado
        self.ordemDescoberta = 0
        self.visitado = 0

    def addVizinho(self, v):
        # Adiciona um vizinho ao vértice, se ainda não estiver presente
        if v not in self.vizinhos:
            self.vizinhos.append(v)
            # Mantém a lista de vizinhos ordenada
            self.vizinhos.sort()

class Grafo:
    # Dicionário de vértices, onde a chave é o nome do vértice e o valor é o objeto Vertice
    vertices = {}
    # Variável global para controlar a ordem de descoberta dos vértices na DFS
    ordem = 0

    def addVertice(self, vertice):
        # Verifica se o objeto é de fato um objeto de vértice e se ele ainda não existe no grafo
        if isinstance(vertice, Vertice) and vertice.nome not in self.vertices:
            # Adiciona o vértice no dicionário de vértices
            self.vertices[vertice.nome] = vertice
            return True
        else:
            return False

    def addAresta(self, u, v):
        # Verifica se ambos vértices de fato existem no grafo para criar a aresta
        if u in self.vertices and v in self.vertices:
            # Adiciona v na lista de vizinhos de u e u na lista de vizinhos de v
            for key, valor in self.vertices.items():
                if key == u:
                    valor.addVizinho(v)
                if key == v:
                    valor.addVizinho(u)
            return True
        else:
            return False

    # Imprime a lista de adjacências do grafo
    def printGrafo(self):
        # Percorre todos os vértices ordenados pelo nome
        for key in sorted(list(self.vertices.keys())):
            # Imprime o nome do vértice, sua lista de vizinhos e sua ordem de descoberta
            print(key + str(self.vertices[key].vizinhos) + ' ' + str(self.vertices[key].ordemDescoberta))

    # Função recursiva auxiliar para DFS
    def _dfs(self, vertice):
        global ordem
        # Marca o vértice como visitado e define sua ordem de descoberta
        vertice.visitado = 1
        vertice.ordemDescoberta = ordem
        ordem += 1
        # Chama a DFS recursivamente para cada vizinho não visitado
        for v in vertice.vizinhos:
            if self.vertices[v].visitado == 0:
                self._dfs(self.vertices[v])

    # Função principal para iniciar a DFS
    def dfs(self, vertice):
        global ordem
        # Inicializa a ordem de descoberta
        ordem = 1
        # Chama a função auxiliar de DFS
        self._dfs(vertice)

# Programa principal:
G = Grafo()
# Cria o vértice de origem 'A'
origem = Vertice('A')
# Adiciona o vértice de origem ao grafo
G.addVertice(origem)

# Adiciona vértices ao grafo, de 'A' a 'F'
for i in range(ord('A'), ord('G')):
    G.addVertice(Vertice(chr(i)))

# Define as arestas a serem adicionadas no formato 'UV'
arestas = ['AB', 'AD', 'BC', 'CD', 'CE', 'CF']
# Adiciona cada aresta ao grafo
for aresta in arestas:
    G.addAresta(aresta[:1], aresta[1:])

# Executa a DFS a partir do vértice de origem
G.dfs(origem)
# Imprime a lista de adjacências do grafo
G.printGrafo()
```

### Explicação dos principais componentes:

1. **Classe `Vertice`**:
    - `__init__`: Inicializa um vértice com um nome (`n`), uma lista vazia de vizinhos, a ordem de descoberta (`ordemDescoberta`) e uma flag de visitado (`visitado`).
    - `addVizinho`: Adiciona um vizinho à lista de vizinhos, se ainda não estiver presente, e mantém a lista ordenada.

2. **Classe `Grafo`**:
    - `vertices`: Um dicionário onde as chaves são os nomes dos vértices e os valores são os objetos `Vertice`.
    - `ordem`: Uma variável global para controlar a ordem de descoberta dos vértices durante a DFS.
    - `addVertice`: Adiciona um vértice ao grafo, verificando se é uma instância de `Vertice` e se ainda não está presente.
    - `addAresta`: Adiciona uma aresta entre dois vértices, verificando se ambos os vértices existem no grafo. Adiciona cada vértice à lista de vizinhos do outro.
    - `printGrafo`: Imprime a lista de adjacência de todos os vértices no grafo, incluindo a ordem de descoberta.
    - `_dfs`: Função recursiva auxiliar para realizar a DFS a partir de um vértice, marcando-o como visitado e definindo sua ordem de descoberta.
    - `dfs`: Função principal para iniciar a DFS, inicializando a ordem de descoberta e chamando a função auxiliar `_dfs`.

3. **Programa Principal**:
    - Cria uma instância do grafo.
    - Cria o vértice de origem 'A' e o adiciona ao grafo.
    - Adiciona vértices com os nomes de 'A' a 'F'.
    - Adiciona arestas entre os vértices especificados na lista `arestas`.
    - Executa a DFS a partir do vértice de origem.
    - Imprime a lista de adjacência do grafo, incluindo a ordem de descoberta de cada vértice.
![[Pasted image 20240618221829.png]]

---
##  <span style="color:#32CD32">■ Algoritmo de dijkstra</span> 
Aqui está a implementação do grafo com lista de adjacência e o algoritmo de Dijkstra comentada:

```python
# Implementação com lista de adjacência
class Vertice:
    def __init__(self, n):
        # Inicializa o vértice com um nome, uma lista vazia de vizinhos e uma lista vazia de pesos
        self.nome = n
        self.vizinhos = list()
        self.pesos = list()

    def addVizinho(self, v, peso):
        # Adiciona um vizinho e seu peso, se ainda não estiver presente
        if v not in self.vizinhos:
            self.vizinhos.append(v)
            self.vizinhos.sort()  # Mantém a lista de vizinhos ordenada
            self.pesos.append(peso)  # Adiciona o peso correspondente

class Grafo:
    vertices = {}
    ordem = 0

    def __init__(self):
        # Inicializa o total de vértices no grafo
        self.totalVertices = 0

    def addVertice(self, vertice):
        # Verifica se o objeto é de fato um objeto de vértice e se ele ainda não existe no grafo
        if isinstance(vertice, Vertice) and vertice.nome not in self.vertices:
            # Adiciona o vértice no dicionário de vértices e incrementa o total de vértices
            self.vertices[vertice.nome] = vertice
            self.totalVertices += 1
            return True
        else:
            return False

    def addAresta(self, u, v, peso):
        # Verifica se ambos vértices existem no grafo para criar a aresta
        if u in self.vertices and v in self.vertices:
            for key, valor in self.vertices.items():
                # Adiciona v na lista de vizinhos de u e u na lista de vizinhos de v com o peso correspondente
                if key == u:
                    valor.addVizinho(v, peso)
                if key == v:
                    valor.addVizinho(u, peso)
            return True
        else:
            return False

    # Imprime a lista de adjacências
    def printGrafo(self):
        # Percorre todos os vértices ordenados pelo nome
        for key in sorted(list(self.vertices.keys())):
            # Imprime o nome do vértice, sua lista de vizinhos e os pesos das arestas
            print(key + str(self.vertices[key].vizinhos) + ' ' + str(self.vertices[key].pesos))

    # Implementação do algoritmo de Dijkstra para encontrar o caminho mais curto a partir de um vértice de origem
    def Dijkstra(self, origem):
        # Inicializa as distâncias com infinito, visitados com 0 e predecessores com infinito
        distancias = [float('inf') for i in range(0, self.totalVertices)]
        visitados = [0 for i in range(0, self.totalVertices)]
        predecessor = [float('inf') for i in range(0, self.totalVertices)]
        nodos = [v for v in self.vertices]  # Lista de nomes dos vértices

        # Define a distância do vértice de origem como 0
        distancias[nodos.index(origem.nome)] = 0
        predecessor[nodos.index(origem.nome)] = origem

        for x in range(0, self.totalVertices):
            # Encontra o próximo vértice com a menor distância
            minDistancia = float('inf')
            for v in range(0, self.totalVertices):
                if(distancias[v] < minDistancia and visitados[v] == 0):
                    minDistancia = distancias[v]
                    idxProxVertice = v

            # Marca o vértice com menor distância como visitado
            visitados[idxProxVertice] = 1
            nodoAtual = self.vertices[nodos[idxProxVertice]]
            idx = 0
            # Atualiza as distâncias dos vizinhos do vértice atual
            for vizinho in nodoAtual.vizinhos:
                if (visitados[nodos.index(vizinho)] == 0):
                    if(minDistancia + nodoAtual.pesos[idx] < distancias[nodos.index(vizinho)]):
                        distancias[nodos.index(vizinho)] = minDistancia + nodoAtual.pesos[idx]
                        predecessor[nodos.index(vizinho)] = nodoAtual
                idx += 1
        r = 1

        # Impressão dos caminhos
        print('Vértice de Origem: {}'.format(origem.nome))
        for i in range(1, self.totalVertices):
            print('Distância para {} = {}'.format(nodos[i], distancias[i]))
            print('Caminho: {} '.format(nodos[i]), end='')
            j = i
            atual = predecessor[j].nome
            while (atual != origem.nome):
                print('<- {} '.format(atual), end='')
                atual = predecessor[nodos.index(atual)].nome
            print('<- {} '.format(origem.nome))

# Programa principal
G = Grafo()
# Cria o vértice de origem 'A'
origem = Vertice('A')
# Adiciona o vértice de origem ao grafo
G.addVertice(origem)

# Adiciona vértices ao grafo, de 'A' a 'F'
for i in range(ord('A'), ord('G')):
    G.addVertice(Vertice(chr(i)))

# Define as arestas a serem adicionadas no formato 'UV' e seus respectivos pesos
arestas = ['AB', 'AD', 'BC', 'CD', 'CE', 'CF']
pesos = [10, 3, 4, 1, 2, 2]
i = 0
# Adiciona cada aresta com seu peso ao grafo
for aresta in arestas:
    G.addAresta(aresta[:1], aresta[1:], pesos[i])
    i += 1

# Executa o algoritmo de Dijkstra a partir do vértice de origem
G.Dijkstra(origem)
#G.printGrafo()  # Descomente para imprimir a lista de adjacências do grafo
```

### Explicação dos principais componentes:

1. **Classe `Vertice`**:
    - `__init__`: Inicializa um vértice com um nome (`n`), uma lista vazia de vizinhos e uma lista vazia de pesos.
    - `addVizinho`: Adiciona um vizinho à lista de vizinhos, se ainda não estiver presente, e adiciona o peso correspondente à lista de pesos. Mantém a lista de vizinhos ordenada.

2. **Classe `Grafo`**:
    - `vertices`: Um dicionário onde as chaves são os nomes dos vértices e os valores são os objetos `Vertice`.
    - `ordem`: Uma variável global para controle (não utilizada neste exemplo).
    - `__init__`: Inicializa o total de vértices no grafo (`totalVertices`).
    - `addVertice`: Adiciona um vértice ao grafo, verificando se é uma instância de `Vertice` e se ainda não está presente. Incrementa o total de vértices.
    - `addAresta`: Adiciona uma aresta entre dois vértices, verificando se ambos os vértices existem no grafo. Adiciona cada vértice à lista de vizinhos do outro com o peso correspondente.
    - `printGrafo`: Imprime a lista de adjacência de todos os vértices no grafo, incluindo os pesos das arestas.
    - `Dijkstra`: Implementa o algoritmo de Dijkstra para encontrar o caminho mais curto a partir de um vértice de origem. Inicializa as distâncias, visitados e predecessores. Atualiza as distâncias dos vizinhos do vértice atual e imprime os caminhos mais curtos.

3. **Programa Principal**:
    - Cria uma instância do grafo.
    - Cria o vértice de origem 'A' e o adiciona ao grafo.
    - Adiciona vértices com os nomes de 'A' a 'F'.
    - Adiciona arestas entre os vértices especificados na lista `arestas` com os respectivos pesos.
    - Executa o algoritmo de Dijkstra a partir do vértice de origem e imprime os caminhos mais curtos.
![[Pasted image 20240618222018.png]]
