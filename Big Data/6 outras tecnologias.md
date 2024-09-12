## Impala
- Banco de dados analíticos massivamente paralelo
- Fundação Apache
- Conslutas SQL + HDFS/HBase
- Bussiness Inteligence

# Accumulo
- Baseado no BigTable(cheve-valor)
- FUndação Apache
- Segurança em nível de célula

# Redis
in-memory storage
Banco de dados
cache
agente de de mensagens

## Ignite
- Computação em mem'ria escalável
- Fundação Apache
- Cache + Storage
- Propriedades ACID
- Consultas SQL

## NIFI
- Porcessamento r distribuição de dados por meio de grafos dirigidos
- FUndação Apache
- Autoatiza e gerencia fluxos
- Altamente configurável

## AMBARI
- Interface web
- Fundação Apache 
- Dividido os componentes em três níveis
	- Core Hadoop
	- Essencial Hadoop
	- Hadoop Supoort
---
---
# DATE LAKE
- Estratégia de gerenciamento de dados
- Identificação, limpeza e integração dos dados
### Gerenciamento de dados
- Dados estão espalhados
- reorganização e reformatação
- Atualização
![[Pasted image 20240818224011.png]]

## Data Swamp
 - Degradação de dados
 - Gerenciamento
 - Acessibilidade 
 - governança

## NÍVEIS DE MATURIDADE
## Data Pudle
- : estágio inicial onde os dados de um data mart são utilizados em conjunto com tecnologia big data.

## Data Pond
- : estágio em que a organização possui uma coleção de data puddles, ou seja, na prática funciona como um data warehouse mal projetado, com diversos data marts para propósitos específicos, que utilizam tecnologia big data, porém, comparado com data puddles, utilizam tecnologias mais baratas e escaláveis que data warehouses e data marts relacionais
## Data Lake(ou lago de dados)
- difere do data pond no sentido em que suportam análise de autoatendimento, ou seja, os usuários são capazes de realizar buscas e localizar dados diretamente.

## Data Ocean
- : o oceano de dados expande o conceito de data lake para toda uma organização
---
---
# SISTEMAS DE RECOMENDAÇÃO
Sistemas de recomendação são uma classe de aplicações que buscam prever a reação dos usuários em relação a um conjunto de opções.

## <span style="color: #00FF00">Tipos de recomendadores</span> 

### <span style="color:yellow">Editorial ou curadoria</span>
- são as listas de recomendações criadas à mão. Normalmente, levam em consideração os interesses de quem está criando, por exemplo, uma lista de favoritos. Não levam em consideração nenhuma característica do usuário
### <span style="color:yellow">Agregação simples</span>
-  listas que agregam alguma característica do próprio conteúdo. Por exemplo: Top 10, listas de popularidade, mais recentes. Essas listas podem até levar em consideração algum fator relacionado com seus usuários, por exemplo, a soma de interações que a totalidade de usuários tem com o conteúdo (vendas, views etc.).

### <span style="color:yellow">Recomendadores individualizados</span>
- são as recomendações que levam em conta as características dos usuários e dos produtos para gerar uma experiência personalizada para cada usuário. Aqui podemos elencar os sistemas de recomendação que nos interessam nesse tema.
### Tipos de recomendadores individualizados:
#### <span style="color:aquamarine">■ Content-based recommendation systems</span>
- A ideia principal dessa abordagem é recomendar ao usuário itens parecidos, ou seja, com características semelhantes aos que ele avaliou. Dessa forma, o foco dessa abordagem está nas características dos itens. A similaridade entre diferentes itens está baseada na similaridade de suas características

#### <span style="color:aquamarine">■ Collaborative filtering</span>
-  A abordagem de filtragem colaborativa (ou collaborative filtering) parte do pressuposto de que usuários com avaliações semelhantes podem ser utilizados para estimar a avaliação que um deles fará de determinado item. Para isso é necessário calcular a similaridade entre os usuários, ou seja, o quanto as suas avaliações são parecidas.
----
---
# CLOUD COMPUTING
(ou computação em nuvem) para armazenar e processar seus dados utilizando tecnologia de big data. Nesse contexto, cloud computing representa o acesso de rede sob demanda a recursos computacionais fornecidos por uma entidade externa.
- Escaláveis e elásticos
- Via internet
- Privada ou pública

## <span style="color:aquamarine">Modelos de serviços de cloud computing</span>
• PaaS (platform as a service): a plataforma como um serviço pode ser entendida como o uso de cloud computing para oferecer plataformas para o desenvolvimento e uso de aplicações customizadas necessárias para analisar grandes quantidades de dados
• SaaS (software as a service): software como um serviço fornece às empresas aplicações que são armazenadas e executam em servidores virtuais.
• IaaS (Infrastructure as a Service): a infraestrutura como um serviço fornece acesso ao uso de equipamentos para recursos computacionais como armazenamento, servidores, dispositivos de rede e outros tipos de hardware

![[Pasted image 20240819222347.png]]
•<u> Amazon EMR:</u> o Amazon Elastic MapReduce é a ferramenta de big data da plataforma Amazon Web Services (AWS) que implementa as camadas IaaS e PaaS. Atualmente é a maior plataforma de big data em nuvem. O EMR é baseado no Hadoop e permite utilizar ferramentas como Spark, Hive, HBase, Flink, Presto, entre muitos outros serviços. O EMR processa big data utilizando clusters Hadoop hospedados nos servidores virtuais da nuvem pública Amazon Elastic Compute Cloud (EC2). Além disso, ele implementa uma infraestrutura de armazenamento distribuída própria, a Amazon Simple Storage Service (S3), que substitui o HDFS. 

• <u>Google Cloud Dataproc:</u> é a ferramenta de big data do Google, que fornece serviços Spark e Hadoop, além de componentes como Hive, HBase, Zeppelin, Zookeeper, Presto, Pig, entre outros. Implementa uma combinação entre as camadas IaaS e PaaS. O Cloud Dataproc está integrado com outros serviços do Google Cloud Platform, como BigQuery, Cloud Storage, Cloud Bigtable, Stackdriver Logging e Stackdriver Monitoring. 

• <u>Microsoft Azure:</u> implementa uma integração entre IaaS e PaaS, que fornece serviços hospedados nos servidores virtuais de cloud computing Azure virtual machines. O Azure também implementa serviços de armazenamento (Azure blob storage), CDN, serviço de containers baseados em docker (Azure container services), processamento em lote (Azure batch), computação sem servidor (Azure functions), e um serviço para permitir o uso e gerenciamento de clusters Hadoop e Spark (Azure HDInsight

---
---
# DESIGN DE ARQUITETURA BIG DATA
