# <span style="color:yellow">Dados estruturados</span>
- São considerados a forma mais tradicional de armazenamento de dados.
- Modelo de dados predefinido e, portanto, fáceis de analisar.
- Obedecem a um formato tabular com relação entre as diferenças linhas e colunas.

 <span style="color:orange">Exemplo</span>
 - Todos os dados que são reunidos em uma tabela, linha e coluna são dados estruturados
![[Pasted image 20231105221421.png|300]]
---
# <span style="color: #1E90FF">Dados semiestruturados</span>
- São uma forma de dados estruturados que não estão em conformidade com a estrutura formal; dos modelos de dados associados a bancos de dados relacionais ou outras formas de tabelas de dados
- Contêm tags ou outros marcadores para separar elementos semânticos e impor hierarquia de registros e campos dentro de dados
- Também conhecidos como estrutura autodescritiva
![[Pasted image 20231105221910.png|300]]
---
# <span style="color:red">Dados não estruturados</span> 
- São informação que não possuem um modelo de dados predefinido ou não estão organizadas de maneira predefinida.
- As informações não estruturadas geralmente contêm muito texto, mas podem conter dados como datas, número e fatos.
- Resultam em irregularidades e ambiguidades que dificultam a compreensão do uso de programas tradicionais em comparação com os dados armazenados em bancos de dados estruturados.
<span style="color:orange">Exemplo</span>
- Arquivos de áudio, vídeo ou bancos de dados No-SQL
 ![[Pasted image 20231105222658.png|400]]
---
# Data Warehouse
- São grandes armazéns de dados alimentados com dados transacionais oriundo dos diversos bancos de dados da empresa, inclusive dos sistemas ERP. 
- O que diferencia do conceito de banco de dados é a não volatilidade de dados, ou seja, o fato de não alterar seu conteúdo com grande periodicidade.
- O data Mart pode ser considerado um data Warehouse tradicional.
![[Pasted image 20231105223405.png|360]]

# Data Mart
- É um subconjunto de dados com curadoria geralmente gerado para usuários de análise e inteligência de negócios. 
- Os data marts geralmente são criados como um repositório de informações pertinentes para um subgrupo de trabalhadores ou um caso de uso específico. 
- As empresas podem usar data marts para fornecer acesso de usuário àqueles que não podem acessar os dados.
- Os data marts também podem ser menos caros para armazenamento e mais rápidos para análise, devido a seus projetos serem menores e mais especializados.

# Data Mining ou Mineração de dados
- É o processo de análise de dados para encontrar tendências, padrões e associações anteriormente desconhecidos para tomar decisões
- Geralmente, a mineração de dados é realizada por meios automatizados em conjuntos de dados extremamente grandes, como um data warehouse”.
- Em alguns casos, um projeto de mineração de dados é iniciado com um resultado hipotético em mente
- Por exemplo, uma cadeia de supermercados pode já ter alguma ideia de que os padrões de compra mudam após a chuva e deseja obter uma compreensão mais profunda do que exatamente está acontecendo.
- Em outros casos, não há pressupostos e um programa de
20mineração de dados é executado em grandes conjuntos de dados para neles encontrar padrões e associações