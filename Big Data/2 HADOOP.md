# ➫ O ecossistema Hadoop
- Hadoop é uma plataforma de software open source para o armazenamento e processamento distribuído de conjuntos de dados muito grandes em clusters de computadores (Hortonworks)
- Hortonworks é a empresa que cuida do Hadoop
# <span style="color:orange">Conjunto das aplicações principais do sistema Hadoop:</span>
![[Pasted image 20240805220502.png]]

---
# ➫ Hadoop Distributed File System

- Sigla HDFS
- Sistema distribuído para Cluster
- Tolerante a falhas (partição)
- Alta disponibilidade
- Escalabilidade horizontal
- Acesso paralelo aos dados
# <span style="color:aquamarine">■ Arquitetura HDFS</span>

- Os dados são distribuídos em blocos de 128 MB
- Os blocos são replicados nos nós do Cluster
- Name Nodes
- Data Nodes

![[Pasted image 20240805221503.png|500]]
![[Pasted image 20240805221605.png|500]]

---
---
# ➫MapReduce

- Os mappers trasnformam os dados
- Os reducers agregam os resultados
- Tolerante a falhas
![[Pasted image 20240805222042.png|500]]

---
## <span style="color:brown">■ Shuffle and sort</span>
- Embaralhar e ordenar
- Processo automático
- Agrega dados por chave

---
## <span style="color:aquamarine">■ Reducer</span>
- Extrai as informações dos conjuntos de dados
![[Pasted image 20240805222615.png|500]]

---
---
# ➫ Além do MapReduce
#  <span style="color:#32CD32">■ Pig</span> 
- Estende a capacidade do MapReduce
- Oferece uma linguagem semelhante à do SQL
- Executa mappers e reducers otimizados

#  <span style="color:#32CD32">■ Pig Latin</span> 
- Facilidade de programação
- Oportunidade de otimização
- Extensibilidade
- Termos correspondente com do bancos de dados tradicionais:
	- relação -> tabela
	- Tupla -> registro(linha)
	- Campo -> coluna
- Permite operações JOIN
- Pode ser executado em conjunto com substitutos do MapReduce
	- Tez, Spark
- Interfaces
	- CLI Grunt
	- Ambari
	- Hue
#  <span style="color:#32CD32">■ Tez</span> 
- Substitui o MapReduce
- Grafos acíclicos direcionados
- Pode otimizar a execução de outros componentes
![[Pasted image 20240805223716.png|500]]

---
---
# ➫ Gerenciamento de Cluster
##  <span style="color:#32CD32">■ YARN</span> 
- Yet Another Resource Navigator
- Gerenciador de recursos global
- Distribui e gerencia o processamento pelo cluster
- Desmembramento do MapReduce original
![[Pasted image 20240805224111.png|500]]

#  <span style="color:#32CD32">■ ZooKeeper</span> 
- Coordenador de aplicação distribuídas
- Alta disponibilidade
- Estrutura de árvores de diretório
- Permite manter informações dos nós e tarefas de uma aplicação
![[Pasted image 20240805224439.png|500]]

#  <span style="color:#32CD32">■ Oozie</span> 
- Orquestração de trabalhos
- Fluxo de dados por vários componentes Hadoop
- Agendamento e execução de trabalhos
- Grafos acíclicos direcionados