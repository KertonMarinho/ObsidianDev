# <span style="color:purple">Hive</span> 
- Data waehouse projetado para o Hadoop
- HiveQL
- Online analytical processing(olap)
- Opera sobre MapReduce ou Tez
- Integra extensões customizadas e programas externos
![[Pasted image 20240808223240.png|500]]

## <span style="color:yellow">■ HiveQL</span>
- Dialeto SQL
- Database: catálogo de tabelas
- Databases e tabelas são armazenados em uma árvore de diretórios
- Otimiza consultas por meio do MapReduce
- Schema on read

---
---
# Integrando Hadoop com banco de dados relacionais

## <span style="color:yellow">■ Sqoop</span>
- transferência de dados entre Hadoop e aplicações externas
- Utiliza MapReduce ou Hive
- Grande flexibilidade
![[Pasted image 20240808223905.png|500]]

## <span style="color:orange">Exemplo de importação:</span>
```sql
soop import --connect
jdbc:mysql://localhost/foobar --driver
com.mysql.jdbc.Driver --table foo
```
``funcões
``connect = qual banco de dadso
``jdbc = conector utilizado para acessar os bancos de dados
``localhost = sua localização
``--driver = definição qual driver a ser utilizado
``com.mysql.jdbc.drive = definição
``table = define o nome da tabela
``foo = o nome da tabela
`-m = defie quantos maps`

![[Pasted image 20240808224651.png]]
``os dados do sql serão importados diretamente para o Hive

### <span style="color:khaki">■ importação incremental</span>
Mantêm os dados no Hadoop sincronizados com o banco de dados relacional

![[Pasted image 20240808225036.png]]

![[Pasted image 20240808225245.png]]

----
----
# Banco de dados não relacionais
## <span style="color:#BDB76B">Teorema CAP</span>
Serve para dizer qual a estratégia principal de banco
- <u>Caracterísitca:</u>
	- Consistência
	- Disponibilidade
	- Tolerância a falhas(partição)
---
## <span style="color:khaki">■ NoSQL</span>
- Característica:
	- Escalabilidade horizontal
	- Dados estruturados, semiestruturados, não estruturados
	- Complexidade de bancos de dados tradicionais
---
## <span style="color:aquamarine">■ Tipos da banco de dados</span>
### <span style="color:#8A2BE2">Banco de dados de esquema chave-valor</span>
- Modelo mais simples
- Dados não estruturados
- Os registros são armazenados como arrays associativos
- Flexibilidade de tipos
- Discretamente ordenado
### <span style="color:6B8E23">Banco de dados baseado em documentos</span>
- Extensão do modelo de esquema chave-valor
- Dados semiestruturados
- XML, YAML, JSON, BSON
- Esquema altamente flexíveis
- Capaz de consultar campos dos documentos

## <span style="color:#20B2AA">Banco de dados baseado em colunas</span>
- Famílias de colunas
- Dados semiestruturados
- dados esparsos
- Versionamento de registros

### <span style="color:#F4A460">Banco de dados baseados em grafos</span>
- Teoria dos grafos: nós e relações
- Dados Semiestruturados
- As relações são mais importante que os dados
- Pode utilizar outro tipo de armazenamento nos nós

---
---
# <span style="color:#20B2AA">■ HBase</span>
Banco de dados NoSQL dentro do Hadoop
- não implementa SQL
- API Java baseado em CRUD
- Baseado no MapReduce
![[Pasted image 20240811214614.png]]
---
---
# BANCO DE DADOS NOSQL EXTERNOS
## <span style="color:#8A2BE2">Cassandra</span>
- Banco de dados NoSQL distribuído
- Modelo de armazenamento chave-valor
- Linguagem CQL semelhante à do SQL
- Disponibilidade e tolerância a falhas
- Consistência eventual
- Integração nativa com Hadoop
- DIfrenças com banco relacionais:
	- Suporta transações leves que suortam propriedades ACID parcialmente
	- Não efetus JOIN
	- Não possui chaves estrangeiras
	- Não possui integridade referencial
- Nomenclaturas do cassandra:
	- Keyspace
		- Tabelas
		- Materialized view
		- Agregate
		- Tipos e funções customizados
![[Pasted image 20240811225156.png]]
---
# <span style="color:#FF4500">MongoDB</span>
- Banco de dados NoSQL distribuído
- Modelo de dados baseado em documentos
- JSon
- Consistência e tolerância a falhas
- Coleções
	- Documentos
- Esquemas e modelagem dos dados
	- estratégias de modelagem
		- Modelos de dados embutidos
		- Modelos de dados normalizados
![[Pasted image 20240812220754.png]]
- <span style="color:orange">particionamento:</span>
	- Nós secundários não aumentam a escalabilidade do cluster, mas a disponibilidade
	- Múltiplos conjuntos de replicação
	- Cluster
	- Partição(shard)
	- Servidores de configuração

---
---
# MOTORES DE CONSULTA SQL
#### Aplicações que fazem acesso a diversos banco de dados para retornar uma única consulta ou resultado.
## <span style="color:#FF4500">■ Drill</span>
- Modelo de dados em formato JSON
- Suporte à sintaxe do padrão SQL:2003
- Capaz de operar com ferramentas de BI
- Extensão ao SQL
- Múltiplas fontes de dados (NOSQL e sistemas de arquivos)
## <span style="color:#FF4500">■ Drillbit</span>
- Ambiente de execução distribuída
- Responsável por aceitar e processar as consultas e retornas resultados
- Pode ser instalados nos nós de diversos ambientes distribuídos, como Hadoop
- Utiliza o ZooKeeper para coordenar o conjunto de serivços
---
##  <span style="color:yellow">■ Phoenix</span>
- Consultas SQL para o HBase
- Pode ser utilizado para OLTP
- Oferece transações com propriedades ACID
- Possui integração com MapReduce, Spark, Hive e Flume
![[Pasted image 20240812222208.png|500]]
---
## <span style="color: #1E90FF">■ Presto</span>
- Consulta SQL para OLAP
- Compatível com ANSI SQL
- Projetado pelo Facebook
- Múltiplas fontes de dados(NoSQL, banco relacionais, sistemas de arquivos)
#### <span style="color: #1E90FF">■ Arquitetura Presto</span>
- Nó coordenador
- Nós trabalhadores
- Esquemas e referência de dados são armazenados em catálogos