# PESQUISA EM UM CONJUNTO DE DADOS

## PESQUISA SEQUENCIAL
Ao fazer esse tipo de tentativa, você está eliminando da lista apenas um valor por vez. Como o valor correto é 99, você precisa de 99 chances para acertar.

A implementação dessa lógica em um algoritmo nos remete a um simples laço de repetição. Se estivermos manipulando uma estrutura de dados de vetor, faremos uma varredura desse vetor iniciando no índice zero, até o final dele.

## PESQUISA BINÁRIA
- O número central sempre quebra o conjunto de dados ao meio
- reduzindo se o  conjunto de dados ao meio, até restar somente o valor buscado. Esse princípio de raciocino lógico é chamado de **dividir para conquistar**.
----
----
# █ ÁNALISE DE ALGORITMO
- Algoritmo mais eficiente para resolver um problema é um algoritmo de menor complexidade
- A complexidade do algoritmo cresce à medida que o tamanho do conjunto de dados(n) também cresce.
# <span style="color:yellow">■ Complexidade de algoritmos, envolve</span>
### <span style="color:#00BFFF">☐ Complexidade de tempo</span>
### A Quantidade de tempo que um algoritmo leva para completar sua execução
- A quantidade de instruções do código impacta diretamente este desempenho
## <span style="color:#00FA9A">☐ Complexidade de espaço</span>
### A quantidade de memória requerida para um algoritmo executar
- A quantidade de variáveis e seus tamanhos impactam diretamente este desempenho
---
# <span style="color:#00BFFF">■ Complexidade de tempo</span>
Tamanho do conjunto de dados de dados de entrada(n): quanto mais dados temos para manipular, mais tempo.
Disposição dos dados dentro de conjunto: a ordem com que os dados estão organizados no conjunto implica distintas situações.

![[Pasted image 20240528232149.png]]
- A notação nos dá a tendência de funcionamento de um algoritmo. A ordem de grandeza
- Para sebermos a complexidade de um algoritmo utilizando a notação Big-O, basta encontrarmos o termo de maior grau da equação que o descreve.

>[!info]
>TIPOS DE NOTAÇÃO
> - Big-O: pior caso(limite inferior)
> - Big-Ω: melhor caso(limite superior)
> - Big-Θ: caso médio

![[Pasted image 20240528233451.png|500]]
![[Pasted image 20240528233516.png]]

----
---
