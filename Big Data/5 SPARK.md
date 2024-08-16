#### Spark é um sistema de computação em cluster para propósito geral criado e mantido pela Fundação Apache. É uma das ferramentas de processamento de big data mais interessantes atualmente.
## <u>Característica:</u>
- O Spark utiliza grafos acíclicos dirigidos (DAG) para otimizar o fluxo de trabalho, tornando-o muito eficiente
- Python, scala ou Java
![[Pasted image 20240815204625.png]]
### <span style="color:#00BFFF">Spark streaming</span>
-  foi projetado para realizar a ingestão e o processamento de dados em tempo real
### <span style="color:#00BFFF">Spark SQL</span>
- implementa uma interface SQL para o Spark de forma a permitir a utilização de consultas SQL e o processamento de dados estruturados no Spark
### <span style="color:#00BFFF">MLLib</span>
- é a biblioteca de aprendizado de máquina (machine learning) do Spark para que seja possível extrair significado do conjunto de dados
### <span style="color:#00BFFF">GraphX</span>
- O GraphX implementa funções relativas à teoria dos grafos em Spark

![[Pasted image 20240815205035.png]]

---
##  <span style="color:#32CD32">■ RDD</span> 
- Resilient Distributed Dataset
- RDDs são conjuntos de dados distribuídos e resilientes, ou seja, consistem em uma coleção de elementos particionados pelo cluster que podem ser operados em paralelos
- Existem duas formas de criar um RDD: paralelizando uma coleção de dados existente no driver program ou referenciando um conjunto de dados em um sistema de armazenamento externo tal como um sistema de arquivos compartilhados, HDFS, HBase, ou qualquer fonte de dados que ofereça um Hadoop InputFormat
####  <span style="color:#32CD32">SparkContext</span> 
- é o componente responsável por tornar os RDDs resilientes e distribuídos
- Criado por Driver Program
- Definição do SparkConf *(armazena a configuração de sua aplicação):
```python
conf = SparkConf().setAppName(appName).setMaster(master) 
sc = SparkContext(conf=conf)
```
###  <span style="color:#32CD32">Operações com RDD</span> 
#### RDDs suportam basicamente dois tipos de operações
####  <span style="color:orange">Transformações</span> 
- criam um novo conjunto de dados de outro já existente
- Que são:
	- map(p é uma transformação que passa cada elemento de um conjunto de dados por uma função e retorna um novo RDD representando os resultados)
	- reduce(uma ação que agrega todos os elementos de um RDD utilizando alguma função e retorna o resultado final ao driver program)
	- flatMap
	- filter
	- distinct
	- sample
	- union
	- intersection
	- cartesian
#### <span style="color:violet">Ações</span> 
- retornam um valor ao driver program após realizar a computação de um conjunto de dados
- Que são:
	- reduce
	- collect
	- take
	- first
	- takeSample
	- takeOrdered
	- foreach
---
---
# SPARK SQL
- é o módulo do Spark utilizado o processamento de dados estruturados
- Suporte ao Hive
- Structured Streaming (é um motor de processamento de fluxos escalável e tolerante a falhas criado com base em Spark SQL)+
![[Pasted image 20240815211917.png]]- Os formatos de fontes de dados suportados de maneira nativa pelo Spark SQL são:
### <span style="color:green">Parquet</span> 
- formato de armazenamento colunar suportado por diversos sistemas e disponível em qualquer projeto do ecossistema Hadoop independente da escolha do framework de processamento de dados, modelo de dados ou linguagem de programação
### <span style="color:green">JSON</span> 
- Javascript object notation. É um formato leve projetado para troca de dados e que possa ser de fácil leitura e escrita por seres humanos.
### <span style="color:green">ORC</span> 
- Optimized row columnar. É um formato de arquivo que permite o armazenamento altamente eficiente de arquivos Hive
### <span style="color:green">CSV</span> 
- Comma-separated values. É um formato de arquivo que armazena texto de forma tabular que utiliza vírgulas para separar valores. Cada linha do arquivo é um registro.
### <span style="color:green">LibSVM</span> 
- é a implementação da API de fonte de dados do Spark para Support-vector machines, que são modelos de aprendizagem supervisionada associados a algoritmos de aprendizados que analisam dados utilizados em clarificação e análise de regressão
### <span style="color:green">JDBC</span> 
- é a fonte de dados utilizada para ler dados em outros bancos de dados
---
## <span style="color:aquamarine">Datasets</span> 
- RDD com otimizações do Spark SQL
- Não possui API para Python e R
## <span style="color:yellow">DataFrame</span>
- e é um dataset estruturado em colunas nomeadas. Conceitualmente é equivalente a uma tabela de um banco de dados relacional ou um dataframe em Python ou R, porém com melhores otimizações
- Extensão de RDDs e Datasets
- Possui schema(esquema)
### <span style="color:red">Structured Streaming</span> 
- é um motor de processamento de fluxos escalável e tolerante a falhas criado com base em Spark SQL. Ele permite a definição de computações em fluxo da mesma forma que seriam definidos no processamento em dados estáticos. O motor Spark SQL mantém de forma contínua e incremental a atualização dos resultados finais à medida que os dados continuam a ser recebidos
---
---
# SPARK STREAMING
- Spark streaming é uma extensão da API core do Spark que permite o processamento de fluxo de dados de forma escalável, com alta eficiência e tolerante a falhas
- . Os dados podem ser importados de diversas fontes tais quais: 
	- Kafka, 
	- Flume, 
	- Kinesis, 
	- sockets TCP, 
	- além de sistemas de armazenamento distribuído como HDFS e S3.
![[Pasted image 20240815213948.png]]
## <span style="color:red">DStreams</span> 
- ou discretized streams
 - e representa um fluxo contínuo de dados.
 - sequencia de RDDs
 - armazena estados de dados

Spark streaming oferece a capacidade de realizar transformações em janelas, o que permite aplicar transformações em um conjunto de RDDs para computar os resultados de um intervalo maior. Ou seja, transformações aplicadas a uma janela são aquelas que acumulam RDDs em um intervalo de tempo maior e os processa de forma conjunta, gerando um resultado acumulado.
![[Pasted image 20240815214207.png]]

### <span style="color:salmon">Structured Streaming</span> 
- Novo motor de processamento de fluxos
- Fluxos de dados como tabelas
- Baseado em Spark SQL
- Datasets e DataFrames
- Processamento de micro-batches
----
---
# MLLIB
- é a biblioteca de aprendizado de máquina (machine learning) escalável e do Spark.
- Escalável e fácil
- Nova API baseada em DataFrame
- Fornece classes para simplificar o desenvolvimento e implantação de pipelines
## <span style="color:6B8E23">Tipos de aprendizado de máquinas:</span>
#### <span style="color:orange">Aprendizado supervisionado:</span>
-  utiliza conjuntos de dados que contêm ambos os dados de entrada e os resultados esperados, ou seja, os dados de entrada são rotulados. Essa categoria pode ser ainda subdividida em dois conjuntos de algoritmos: classificação e regressão
#### <span style="color:#BDB76B">Aprendizado não supervisionado</span>
- utiliza apenas conjuntos de dados de entrada e, portanto, podemos dizer que os dados não são rotulados previamente
- Algoritmos de clustering fazem parte desta categoria;
#### <span style="color:#FF4500">Aprendizado por reforço</span>
-  baseado nos conceitos de reforço e punição emprestados da psicologia em que um agente tem por objetivo maximizar determinado parâmetro por meio da tomada ações. O agente é recompensado ou punido de acordo com as ações tomadas. A principal diferença para o aprendizado supervisionado é que os dados de entrada nunca são explicitamente relacionados com os seus rótulos.
--- 
## Fluxo de apreendizado de máquina
![[Pasted image 20240815221442.png]]

---
## <span style="color:#FF4500">Componentes da MLLib</span>
• **Algoritmos de aprendizado de máquina**: são os algoritmos mais comuns, como os de classificação, regressão, clustering, filtragem colaborativa, entre outros; 
• **Caracterização:** é a categoria que engloba os algoritmos de extração de características, transformação, redução dimensionalidade e seleção; 
• **Pipelines:** essa categoria inclui as ferramentas utilizadas na construção e otimização de pipelines; 
• **Persistência:** é a categoria das ferramentas utilizadas para armazenar e carregar algoritmos, modelos e pipelines; 
• **Utilidades:** inclui ferramentas de álgebra linear, estatística, manipulação de dados e outras ferramentas auxiliares.

---
![[Pasted image 20240815221805.png]]
- transformador é uma abstração que inclui transformadores de características ou conjunto de atributos de objetos utilizados para calcular a previsão e modelos aprendidos
- estimador abstrai o conceito de um algoritmo de aprendizado, ou qualquer algoritmo de aprendizado que treina sobre um determinado conjunto de dados.
---
![[Pasted image 20240815222021.png]]

---
---
# GRAPHX
- GraphX é o componente do Spark para computação de grafos em sistemas distribuídos de larga escala.
- Teoria de grafos  
	- O suporte à computação em grafos é possibilizado por meio de um conjunto de operações fundamentais assim como um conjunto de algoritmos e construtores que simplificam tarefas analíticas utilizando grafos.
	- Segundo a teoria dos grafos, grafos são estruturas matemáticas semelhantes a um conjunto de objetos nos quais pares de objetos são relacionados de alguma forma. Esses objetos são representados utilizando vértices e suas relações são representadas por arestas
- Sistemas paralelos
- Extensão de RDDs

## <span style="color:orange">Exemplo de algoritmos de grafos paralelos:</span>
### *PageRank*
- determinar importância de nós em uma rede
### *Triangle Counting*
- mede a coesão de comunidades por meio da contagem de triângulos à qual cada nó de um grafo pertence
### *Connected Components*
- busca encontrar todos os componentes de um grafo que estão conectados entre si onde cada vértice (ou componente) dentro de um grupo pode ser alcançado com base em qualquer outro vértice do grupo
---
## <span style="color:blue">API GraphX</span>
- oferece uma forma de armazenar grafos na forma de tabelas e utilizar operações de tabelas para expressar operações de grafos.
![[Pasted image 20240815223116.png]]