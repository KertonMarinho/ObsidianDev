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

