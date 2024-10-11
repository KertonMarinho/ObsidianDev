#  INTRODUÇÃO SQLITE3
Ë UM SISTEMA DE GERENCIAMENTO DE BANCO DE DADOS RELACIOANL EMBUTIDO(RDBMS)
- Conhecido por ser leve, rápido, confiável e não requer configurações ou servidores adicionais
- Ele é uma biblioteca que fornece uma maneira de armazenar, gerenciar e recuperar dados estruturados usando a linguagem sql
![[Pasted image 20241009224228.png]]
---
### Casos em que o SQLITE3 não é recomendado
- Aplicações com requisitos de escalabilidade, concorrência pesada ou necessidade de compartilhamento de banco de dados entre vários processos ou servidores
### SQLite3 e Python
- É uma biblioteca padrão que permite interagir com banco de dados SQLite. Co ea, você pode criar, conectar, manipular e consultar bancos de dados
---
---
# PROGRAMANDO banco de dados SQLITE3
0. Import sqlite3
```python
import sqlite3
```
1. Conecte ao banco de dados(cria um novo se não existir)
```python
conn = sqlite.connect('animal.db')
```
2. Cria um cursor para executar comandos SQL
```python
cursor = conn.cursor
```
3. Cria a tabela
```python
cursor.execute('''CREATE TABLE IF NOT EXISTS dog (
					id INTEGER PRIMARY KEY AUTOINCREMENT,
					name TEXT,
					weigth REAL,
					height REAL,
					breed TEXT
))
```
4. Exemplo de dados para inserir na tabela
```python
pets_data =[
			('luke', 9, 45, 0.80, 'Pastor alemao')
			('Buddy', 2, 7.2, 0.3, 'Golden Retriever')
			('Whiskers', 1, 7.2, 0.15, 'Siamese')
			('Max', 4, 5.0, 0.4, 'Labrador')
]
```
5. Inserindo os dados na tabela
```python
for pet in pets_data:
	cursor.execute("INSERT INTO dog "
	"(name, age, weigth, height. breed) "
	"VALUES (?, ?, ?, ?)",
	pet)
```
6. Commit das alterações
```python
conn.commit()
```
7. Fechando a conexão com o banco de dados
```python
conn.close()
print("regsitros inseridos com sucesso.")
```

>[!warning]
>Quando executar o codigo criará o arquivo ``animal.db`` , a qual não terá acesso sua visualização interna
>---
>![[Pasted image 20241010222555.png]]


---
# Leitura do banco de dados
0. Import sqlite3
```python
import sqlite3
```
1. Conecte ao banco de dados(cria um novo se não existir)
```python
conn = sqlite.connect('animal.db')
```
2. Cria um cursor para executar comandos SQL
```python
cursor = conn.cursor
```
3. Selecione todos os registros da tabela
```python
cursor.execute("SELECT * FROM dog")
rows = cursor.fetchall()
```
4. Mostrando os registros
```python
for row in rows:
	print(f"ID: {row[0]}, "
		f"Name: {row[1]}, "
		f"Age: {row[2]}, "
		f"Weigth: {row[3]}, "
		f"Height: {row[4]}, "
		f"Breed: {row[5]}, "
	)
```
7. Fechando a conexão com o banco de dados
```python
conn.close()
```
---

## Padrão de design estrutural: proxy
O padrão de design **Proxy** é um dos padrões estruturais mais conhecidos da programação orientada a objetos, incluindo em Python. A ideia principal do padrão Proxy é fornecer um **substituto ou placeholder** para outro objeto para controlar o acesso a ele.

Esse padrão é muito útil quando você precisa adicionar alguma lógica extra ao acessar um objeto, como controle de acesso, controle de memória, carregamento preguiçoso (lazy loading) ou operações de log. O objeto Proxy age como um intermediário que gerencia a comunicação com o objeto "real" (chamado de **real subject**).

### Tipos de Proxy

Existem vários tipos de proxy dependendo do uso:

1. **Virtual Proxy**: Atrasa a criação ou o carregamento de um objeto pesado até que seja necessário (lazy loading).
2. **Remote Proxy**: Permite que um objeto local se comunique com um objeto remoto como se estivesse acessando um objeto local.
3. **Protection Proxy**: Controla o acesso ao objeto real, garantindo que apenas usuários autorizados possam acessar certos métodos.
4. **Smart Proxy**: Executa ações adicionais quando um objeto é acessado. Pode, por exemplo, gerenciar referências, contagem de acessos ou fazer cache.
![[Pasted image 20241010231514.png]]

### Benefícios do Padrão Proxy

- **Controle de acesso**: Útil quando se deseja controlar quem pode acessar ou modificar um objeto.
- **Melhoria de desempenho**: Pode atrasar a criação de objetos pesados até que eles realmente sejam necessários (lazy loading).
- **Monitoramento e logs**: Permite adicionar logs, contadores ou qualquer outra funcionalidade adicional ao acessar um objeto.
----
## Design Pattern: adapter
- Padrão de projeto estrutural que permite a colaboração entre objetos com interface incompatíveis
- Em vez de modificar o código existente, podemos usar o padrão Adapter para criar uma classe intermediária que atua como um adptador entre o cliente e a classe existente.
```python
import sqlite3  # Importa a biblioteca SQLite para manipulação de banco de dados SQL leve
import json  # Importa a biblioteca JSON para manipular dados no formato JSON


class JsonSqliteAdapter:
    def __init__(self, db_name):
        # Construtor da classe que recebe o nome do arquivo do banco de dados como parâmetro
        self.db_name = db_name

    def connect(self):
        # Método para conectar ao banco de dados SQLite
        # Cria uma conexão com o arquivo de banco de dados (ou cria um novo arquivo se ele não existir)
        self.conn = sqlite3.connect(self.db_name)
        
        # Cria uma tabela chamada 'data', se ela ainda não existir
        # A tabela tem duas colunas: 'id' (chave primária) e 'json_data' (onde os dados JSON serão armazenados)
        self.conn.execute("CREATE TABLE IF NOT EXISTS data "
                          "(id INTEGER PRIMARY KEY, json_data TEXT)")

    def save_data(self, data):
        # Converte os dados Python para o formato JSON usando o método json.dumps()
        json_data = json.dumps(data)
        
        # Insere os dados JSON na tabela 'data'
        # O '?' é usado como placeholder para evitar injeção de SQL
        self.conn.execute("INSERT INTO data (json_data) "
                          "VALUES (?)",  # A string JSON é passada como parâmetro
                          (json_data,))
        
        # Confirma as mudanças no banco de dados, efetivando o INSERT
        self.conn.commit()

    def load_data(self):
        # Executa um SELECT para recuperar todos os dados da coluna 'json_data' na tabela 'data'
        cursor = self.conn.execute("SELECT json_data FROM data")
        
        # Extrai os dados JSON do resultado da consulta
        # fetchall() retorna todas as linhas da consulta, e [row[0] for row in cursor.fetchall()]
        # extrai apenas a primeira coluna (json_data) de cada linha
        json_data_list = [row[0] for row in cursor.fetchall()]
        
        # Converte cada string JSON de volta para objetos Python usando json.loads()
        data_list = [json.loads(json_data) for json_data in json_data_list]
        
        # Retorna a lista de objetos Python (dicionários) recuperados do banco de dados
        return data_list

    def close(self):
        # Fecha a conexão com o banco de dados SQLite
        self.conn.close()


# Exemplo de uso
if __name__ == "__main__":
    # Cria uma instância do adaptador para o banco de dados 'data.db'
    adapter = JsonSqliteAdapter("data.db")
    
    # Conecta ao banco de dados (e cria a tabela, se necessário)
    adapter.connect()

    # Dados de exemplo a serem salvos (uma lista de dicionários)
    data_to_save = [{"name": "Alice", "age": 25}, {"name": "Bob", "age": 30}]
    
    # Salva os dados no banco de dados
    adapter.save_data(data_to_save)

    # Carrega os dados do banco de dados e os imprime
    loaded_data = adapter.load_data()
    for item in loaded_data:
        print(item)

    # Fecha a conexão com o banco de dados
    adapter.close()

```
### Explicação Geral

Este código implementa um **adaptador** que permite salvar e carregar dados em formato JSON em um banco de dados SQLite. O objetivo é armazenar dados estruturados como JSON em uma tabela de banco de dados. Cada entrada JSON é convertida para uma string ao ser salva no banco, e ao ser carregada de volta, essa string JSON é convertida novamente para seu formato de objeto Python original.

### Fluxo:

1. O **adaptador** conecta-se ao banco de dados e cria uma tabela se ela não existir.
2. Dados são salvos no formato JSON no banco de dados.
3. O adaptador pode carregar esses dados e convertê-los de volta ao formato Python.
4. A conexão com o banco é encerrada após o uso.