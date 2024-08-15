# FERRAMENTAS ANALÍTICA DE BAIXA LATÊNCIA
### Aqueles que conseguem processar mais rapidamente que a chegada de novos dados

## <span style="color:salmon">■ Arquitetura Lambda</span> 
 - é projetada para aplicações que possuem atrasos na coleção de dados e processamento devido ao uso de interfaces interativas ou dashboards e passos de validação de dados
- ideia principal da arquitetura lambda é construir um sistema de big data em camadas em que cada camada é responsável por um subconjunto de propriedades
- Marz Warren (2015)
- Processamento em lotes
- Processamento de fluxo de dados
## <span style="color:aquamarine">Camadas da arquitetura Lambda</span> 
### Batch layer 
- armazena todo o conjunto de dados e préprocessa uma quantidade de consultas em forma de views (visualizações) para serem acessadas instantaneamente.
### Serving Layer 
- é uma base de dados distribuída especializada em carregar as views geradas pelas demais camadas)
### Speed layer 
- é a camada que implementa o processamento de fluxo de dados com o objetivo de superar a latência do processamento de grandes volumes de dados e oferecer percepções úteis antes de armazená-las

![[Pasted image 20240813222129.png|500]]
---
---
# Kafka
- Plataforma de processamento de fluxo de dados
- Fundação Apacha
- Alta capacidade e baixa latência
- Fila de mensagens
## <span style="color:#40E0D0">■ Característica centrais do Kafka</span>
- A capacidade de publicar e se inscrever em fluxos de eventos de forma semelhante a um sistema de filas de mensagens
- armazenamento de fluxos de eventos de uma forma durável e tolerante a falhas;
- Processamento em tempo real

## <span style="color:#8A2BE2">■ Cluster Kafka(componentes)</span>
- Eventos
- Tópicos
- Um cluster Kafka armazena fluxos de eventos em categorias chamadas tópicos. Cada servidor é capaz de manter a última mensagem recebida por consumidor. Isso permite que um fluxo de eventos que tenha sido interrompido possa continuar a sua transmissão sem que haja perda de eventos. Os eventos recebidos são armazenados por determinado tempo e publicados em tópicos. Cada evento consiste em uma chave, um valor e um timestamp
## <span style="color:red">■ Kafka como um...</span> 
- Sistema de mensagens
- Sistemas de armazenamento
- Sistemas de processamento de fluxos
![[Pasted image 20240813223631.png]]
![[Pasted image 20240813223730.png]]
- Produtores publicam dados dos tópicos de sua escolha. O produtor é responsável por escolher qual evento deve ser atribuído a qual partição em um tópico+
- Consumidores se agrupam em grupos de consumidores, e cada evento publicado a um tópico é entregue a uma instância consumidora dentro da inscrição de um grupo consumidor
---
---
# ░ Flume
- é um sistema distribuído, confiável e de alta disponibilidade para coletar, agregar e mover eficientemente grandes quantidades de dados de log de muitas fontes diferentes para um armazenamento centralizado
- Projeto Apache
- criado originalmente para o Hadoop como um sistema de agregação de log com suporte nativo ao HDFS e ao HBase
- Coletar, agregar e mover grandes quantidades de dados
![[Pasted image 20240813224018.png]]
- A arquitetura do Flume pode ser resumida da seguinte forma: os dados gerados por diversas aplicações, por meio de clientes Flume, são coletados por agentes Flume, que são compostos de fontes (sources), canais (channels) e destinos (sinks)
## <span style="color: #00FF00">■ Componentes Flume</span> 
- Eventos (um evento é uma unidade de dado que pode ser transportada)
- Source(é a fonte que recebe e gerencia os dados de aplicações externas e os transfere para um ou mais canais)
- Channel ( funciona como um elemento que armazena os eventos das sources até que eles sejam consumidos pelos sinks)
- Sink (é a contraparte da source. É o componente que gerencia como os dados serão entregues. Consome os eventos de um channel e os entrega a seu destino final)
- Runners (é um componente interno às sources e aos sinks responsável por sua execução)
- Agente (de forma genérica, é qualquer processo independente (Java Virtual Machine – JVM) executando em um sistema Flume)
- Provedor de configuração (diversos plugins de sistemas de configurações diferentes;)
- Cliente (funciona como um conector que envia os dados a um agente)
![[Pasted image 20240813224327.png]]
![[Pasted image 20240813224505.png]]
- resultados:
![[Pasted image 20240813224619.png]]
---
---
# ¤ Storm
- Projeto Apache
- Storm é um sistema de computação distribuída em tempo real desenvolvido para permitir o processamento de fluxos de dados ilimitados e pode ser utilizado com qualquer linguagem de programação
- Alto desempenho e baixa latência
- Escalabilidade de carga
- Balanceamento de carga
- Tolerância a falhas
- Arquitetura:
	- Mestrer-trabalhador
	- Nimbus
	- Supervisores
- Principais conceitos do Storm:
	- Spout (componente responsável por receber novos dados.)
	- Bolt (componente responsável por processamento e entrega desses dados)
	- Topologia (: uma topologia é uma rede de spouts e bolts, em que cada aresta na rede representa um bolt ligado a um fluxo de saída de um spout ou outro bolt)
![[Pasted image 20240814212433.png]]

## <span style="color:6B8E23">Agrupamento de fluxos</span>
#### Agrupamento das tarefas dentro do bolt
- O agrupamento de fluxos é parte da definição da topologia de forma a especificar quais fluxos de tuplas devem ser recebidos para cada bolt.
####  Shufle grouping
- agrupamento embaralhado, ou seja, tuplas são distribuídas aleatoriamente às tarefas dos bolts de forma que as tuplas sejam distribuídas de maneira igualitária;
#### Fields grouping 
- agrupamento por campo, ou seja, as tuplas são distribuídas de acordo com determinado campo definido pelas tuplas
#### Partial key grouping 
- agrupamento por chave parcial, significa que as tuplas são agrupadas pela própria configuração do agrupamento, por exemplo levando em consideração o balanceamento de carga do sistema
#### All grpuping 
- agrupamento total. Nesse caso, o fluxo é replicado para todas as tarefas dos bolts
####  Global grouping
- agrupamento global. O fluxo inteiro é direcionado a uma única tarefa do bolt. A tarefa de menor identificador é especificamente selecionada;
#### None grouping
- indica que nenhum agrupamento foi selecionado. Atualmente esta opção é idêntica ao shuffle grouping;
#### Direct grouping
- agrupamento direto. É um tipo especial de agrupamento em que o produtor do fluxo decide qual tarefa do consumidor deve receber cada tupla;
#### Local or shuffle grouping
- se o bolt que recebe o fluxo possui um ou mais tarefas no mesmo processo trabalhador, as tuplas são distribuídas de forma embaralhadas apenas as tarefas contidas no mesmo processo trabalhador; caso contrário, esse agrupamento se comporta como um shuffle grouping normal
![[Pasted image 20240814212938.png]]
## Interfaces para construção  de topologia
#### Trident
- Trident é uma abstração de alto nível que permite realizar computação de tempo real utilizando o Storm. Essa interface permite combinar o processamento de fluxos em alto desempenho e consultas de baixa latência. Trident permite a execução de operações como join, agregações, agrupamentos, funções e filtros
####  Stream Api
- é construída com base nas APIs spouts e bolts de forma a oferecer uma API para construir fluxos computacionais e suporte a operações funcionais como MapReduce.
#### Storm SQL
- A interface StormSQL permite executar consultas SQL sobre fluxos de dados em Storm.
#### FLUX
- O Flux é um framework ou um conjunto de utilidades que permite facilitar a criação e operação de topologias
----
---
# FLINK
#### Flink é um framework e um motor de processamento distribuído de dados limitados e ilimitados. Ele foi projetado para executar em todos os ambientes de cluster, realizar operações computacionais em velocidade de memória e em qualquer escala, além de permitir tanto o processamento de dados em lote quanto o processamento de fluxos de dados.

## <span style="color:salmon">Principais conceitos:</span> 
Todos os dados em Flink são tratados como fluxos de eventos. Assim como muitos tipos de dados são gerados em fluxos, por exemplo: transações de cartão de crédito, logs de máquina, interações de usuário em um website ou aplicação mobile. Dessa forma os dados podem ser divididos em fluxos limitados, ou fluxos ilimitados
#### <span style="color:yellow">Fluxos ilimitados:</span> 
- possuem um começo, mas não possuem um fim definido. Não terminam e fornecem dados assim que eles são produzidos. Fluxos ilimitados devem ser processados continuamente, ou seja, eventos devem ser tratados tão logo sejam recebidos. Não é possível aguardar o recebimento de todos os dados, pois a entrada dos dados não termina em momento algum. Processar dados ilimitados normalmente exige que os dados sejam recebidos em uma ordem específica, assim como a ordem em que os eventos ocorrem, para ser capaz de avaliar a integridade dos resultados
#### <span style="color: #1E90FF">Fluxos Limitados</span> 
- : possuem um começo e um fim bem definidos. Fluxos limitados podem ser processados após a entrada de todos os dados antes da realização de qualquer computação. Os dados não exigem serem processados em uma ordem específica, uma vez que os dados podem ser ordenados a qualquer momento. O processamento de fluxos limitados também é conhecido como processamento em lote
## o flink possui:
- Paralização em milhares de tarefas 
- Integração com sistemas de gerenciamento de recursos: YARN, MESOS, KUBERNETES
- Rest

### O Flink utiliza um conjunto de conceitos que são utilizados para definir como as aplicações são criadas e como executam:
#### <span style="color:yellow">FLuxos(streams)</span>
- fluxos podem ter diferentes características que afetam como um fluxo pode e deve ser processado. Os fluxos podem ser tanto limitados quanto ilimitados, como já vimos anteriormente. Quanto ao processamento, os fluxos podem ser tanto processados em tempo real quanto em lotes, ou seja, de forma gravada
#### <span style="color: #00FF00">Estado(state)</span> 
-  cada aplicação de fluxo não trivial possui estados, ou seja, apenas aplicações que aplicam transformações em eventos individuais não possuem estados
#### <span style="color:#FF4500">Tempo</span>
- Tempo é outro conceito importante em aplicações de fluxos. A maioria dos fluxos de eventos possuem uma semântica temporal inerente pois cada evento é criado em um ponto específico no tempo. Além disso, várias operações de fluxo são dependentes de tempo, tais como agregações de janelas, sessões, detecção de padrões, e joins baseados em tempo. Um importante aspecto de processamento de fluxos é como uma aplicação mede o tempo, ou seja, a diferença entre o tempo do evento e o tempo do processamento
![[Pasted image 20240814214601.png]]

## <span style="color:aquamarine">Api em camada do flink:</span> 
#### <span style="color:red">Process functions</span> 
- Process Functions é a interface mais complexa que o Flink oferece. Tal interface é adequada para processar um ou dois fluxos de entrada ou eventos que foram agrupados em janelas. Process Functions oferecem um controle preciso sobre tempo e estados.
#### <span style="color:red">Data Streams API</span> 
- A Data Stream API fornece um conjunto de primitivas muito comuns para muitas operações de processamento de fluxo. Essas operações incluem: janelas, gravação por tempo, transformações e enriquecimento ou melhoramento de eventos por meio de consultas em sistemas de armazenamento de dados externos.
#### <span style="color:red">SQL e Table API</span> 
- O Flink oferece duas API relacionais: a SQL e a Table API. Ambas as APIs são utilizadas tanto para processamento de fluxos quanto em lote, ou seja, as consultas são executadas com a mesma semântica em fluxos limitados ou ilimitados e produzindo o mesmo tipo de resultados. As APIs utilizam o Apache Calcite para análise, validação e otimização de consultas.