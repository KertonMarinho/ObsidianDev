- Unified Modelling Language
- É uma linguagem ou notação de diagramas para especificar, visualizar e documentar modelos de software desenvolvidos sob os preceitos da orientação por objetos. 
- Cada símbolo gráfico utilizado tem uma semântica bem definida, por isso são chamados de padrão

# modelos
- modelo de processos de desenvolvimento de software, pode simplesmente modelo de processo, pode ser visto como uma representação, ou abstração dos objetos e atividades envolvidas no processo de software
# Tipos de modelos
- Na UML os modelos expressam duas visões diferentes, porém complementares
		<span style="color:yellow">Visão estrutural</span>
- Os modelos estruturados tentam capturar a estrutura do sistema, ou seja, quais elementos compõem a estrutura do sistema e como eles se relacionam
<span style="color:yellow">Visão comportamental</span>
- Os modelos criados tentam capturar a dinâmica do sistema, ou seja, como os elementos que compõem o sistema se comunicam e como se comportam e respondem aos diverso estímulos
---
# <span style="color:orange">ORIENTAÇÃO A OBJETOS</span>
- É um processo conceitual independente de uma linguagem de programação, poia tem como foco visualizar o domínio do problema a ser automatizado como uma coleção de objetos e métodos associados

## CONCEITOS DA ORIENTAÇÃO A OBJETOS
#### <span style="color:aquamarine">Abstração</span>
- Consiste em se concentrar no aspectos essenciais, próprios de uma entidade e em ignorar suas propriedades acidentais, ou seja, dar foco em aspectos relevantes para um determinado propósito
#### <span style="color:aquamarine">Encapsulamento</span>
- Consiste na separação dos aspectos externos de um objeto, acessíveis por outro objetos, dos detalhes internos da implementação daquele objeto, que ficam ocultos dos demais objetos, ou melhor, significa separar o software em partes, o mais isoladas possíveis

#### <span style="color:aquamarine">Herança</span>
- É o compartilhamento de atributos e operações entre objetos com base em um relacionamento hierárquico
- Permite que a estrutura comum seja compartilhada por diversos outros objetos relacionados, sem redundâncias
- Cada objeto em um nível de hierarquia herda as características dos objetos nos níveis acima
---
# Componentes de um diagrama de caso de uso

## <span style="color:red">Ator</span> 
- Representa o papel executado por uma entidade que interage com o sistema em questão
- Um ator troca informações com o sistema, e poder ser um indivíduo ou outros sistemas, ou seja, o ator interage com o sistema, ele não faz parte do sistema
- Um usuário pode executar o papel de vários atores diferentes e um determinado ator pode ser representado por vários usuários

## <span style="color: #00FF00">Relacionamento</span> 
- Mostram a ligação entre os elementos de um diagrama de caso de uso, ou seja, mostram a ligação dos atores com os casos de uso e dos casos de uso entre si

## <span style="color:violet">Relacionamento entre atores</span> 
- A generalização é identificada quando temos dois atores semelhantes, mas com um deles realizando algo mais
![[Pasted image 20240305224434.png|300]]

## <span style="color:#FF4500">Relacionamento entre casos de uso</span>
### <span style="color:#A9A9A9">Include</span>
- Um relacionamento include de um casos de uso A para um caso B indica que B é essencial para o comportamento de A
- Pode ser dito que ``B is_part_of A``
### <span style="color:#A9A9A9">Extend</span>
- Um relacionamento de um caso de uso B para um caso de uso A indica que o caso de uso B pode ser acrescentado para descrever o comportamento de A(não essencial)
---
# DIAGRAMA DE CASO DE USO
![[Pasted image 20240305225439.png|500]]
