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
seguimos na figura 34....