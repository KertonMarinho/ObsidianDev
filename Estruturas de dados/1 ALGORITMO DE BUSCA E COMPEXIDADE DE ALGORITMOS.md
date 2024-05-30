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
# ENCONTRANDO O BIG-O DE ALGORITMOS

## <span style="color:#00FA9A">■ Algoritmo sem laço</span>
![[Pasted image 20240530104709.png|500]]
- Sempre que encontrar um algoritmo que não tem laços de repetição e não tem recursividade esse algoritmo não tem dependência de o tamanho  conjunto de dados. Portanto o seu big-O(sua complexidade) é big-O unitário.
---
# <span style="color: #1E90FF">■ Laço simples</span>
Repetição simples. O código a seguir faz a varredura de um vetor e imprime, na tela, um valor. O que está sendo executado dentro do laço é irrelevante para nossa análise.

É importante compreender o que acontece quando um _loop_ é executado. A cada iteração de um laço, todas as instruções dentro de sua estrutura serão executadas _n_ vezes. Neste exemplo, _n,_ é o tamanho de nosso vetor. Se o vetor/lista for de dimensão 10, o laço ocorre 10 vezes.
![[Pasted image 20240530104937.png|500]]
- Quando tem dois laços:
![[Pasted image 20240530105054.png|500]]
- se soma dois laços:
![[Pasted image 20240530105150.png]]
- Sempre que houver um trecho de código aninhado a outro, ou seja, com relação de dependência entre eles, multiplicaremos suas notações. A seguir, observe dois laços de repetição simples sendo executados aninhados.
![[Pasted image 20240530105553.png|500]]
``(quando existe uma dependência de um conjunto de dados)``
![[Pasted image 20240530105707.png]]

---
## <span style="color:violet">■ Progressão Aritmética</span> 
#### Quando temos um aninhamento de laços, precisamos analisar a quantidade de iterações geradas com base na dependência entre os laços. A maneira como essa dependência existe irá representar a quantidade de vezes que o laço interno irá executar, caracterizando uma progressão matemática.
![[Pasted image 20240530105943.png]]

## Relembrando:
![[Pasted image 20240530110017.png]]
![[Pasted image 20240530110127.png]]
![[Pasted image 20240530110151.png]]
### Então meu Big-O é n².
![[Pasted image 20240530110300.png]]

----
# <span style="color:#FF4500">■ Progressão geométrica(PG)</span>
#### Uma série geométrica é uma sequência de números na qual há uma razão entre um número e seu sucessor**. Um algoritmo caracterizado por uma PG também irá trabalhar com dois laços aninhados.
![[Pasted image 20240530110445.png]]

![[Pasted image 20240530110526.png]]
Observe o exemplo a seguir: há dois laços aninhados, portanto, teremos O(n²), certo? Errado; precisamos analisar a progressão dos dados. Nesse cenário, o laço interno (linha 4), contém uma condição de parada na qual _j_ depende de i _(j_ _< i²)_.
![[Pasted image 20240530110651.png]]
**![[Pasted image 20240530110712.png]]

----
# DIVIDIR PARA CONQUISTAR
- Técnica para resolver problemas 
- Um problema muito complexo pode ser dividido em partes menores
![[Pasted image 20240530112554.png]]
![[Pasted image 20240530112719.png]]
![[Pasted image 20240530112753.png]]
![[Pasted image 20240530112812.png]]
![[Pasted image 20240530112829.png]]
![[Pasted image 20240530112918.png]]

---
# COMPLEXIDADE DA RECURSIVIDADE

#### Passos para encontrarmos o Big-O da recursividade:
1. Calcular a complexidade de uma única chamada da função
2. Expressar o número de chamadas recursivas através dos parâmetros de entrada
3. Multiplicar o número de chamadas recursivas pela complexidade de uma chamada de recursiva

## <span style="color:orange">Exemplo</span>
1. Complexidade de uma chamada da função O(1)
![[Pasted image 20240530120921.png]]
``primeiro item da chamada constante é Big-O
2. Quantidade de chamadas recursivas: n
``Quantas vezes vou chamar a constante recursiva
![[Pasted image 20240530121215.png]]
3. Por fim, fazemos: 
![[Pasted image 20240530121244.png]]
