# ✅FUNDAMENTOS DO TESTE DE SOFTWARE

> [!SUMMARY] Pressaman,2011
> "O teste é um processo individualista e o número de tipos diferentes de testes varia tanto quanto as diferentes abordagens de desenvolvimento de software".

 - <span style="color: #1E90FF">ERRO (ERROR):</span>  diferença detectada entre o resultado obtido e o resultado esperado.
 - <span style="color:#00FA9A">DEFEITO (FAULT):</span> Linha de código ou conjunto de dados incorretos que provocam um erro.
 - <span style="color:red">FALHA (FAILURE)</span>  Não funcionamento do software, geralmente ocorre por um defeito.
 - <span style="color:#40E0D0">ENGANO (MISTAKE)</span> Ação que produz um defeito no software.

- O engano caracteriza-se como ação equivocada de um conceito específico do domínio, geralmente causado por humanos.
- A existência de  um defeito em um programa leva à ocorrência de um erro, desde que o defeito seja executado.
- O erro caracteriza-se por um estado inconsistente ou inesperado, devido à execução de um defeito.
- Esse estado inconsistente ou inesperado pode ocasionar uma falha.
---
## <span style="color:#8A2BE2">■ Verificação,validação e teste</span>
### <span style="color:yellow">
Verificação</span>
- Analisa o software para ver se foi construído de acordo com a especificação 
### <span style="color:yellow">Validação</span>
- Analisa o software construído para ver se atende às necessidades dos interessados
### <span style="color:yellow">Teste</span>
- Atividade que permite realizar a verificação e a validação do software.
---- 
## <span style="color:#8A2BE2">■ Casaos e dados de teste</span>
### <span style="color: #00FF00">Dado de teste:</span> 
- É um elemento do domínio de entrada de um programa
	✔Programa que computa x<sup>y</sup>, um dado de teste pode ser (2, 5)
### <span style="color: #00FF00">Caso de teste:</span> 
- É um par formado por um dado de teste mais o resultado esperado
	✔Program que computa x<sup>y</sup>, o caso de teste do dado de teste(2, 5) seria ((2, 5), 32)
----
-----
# ⚛TESTE DE FUNCIONALIDADE

- Tem como objetivo verificar e validar se as funções implementadas no software estão corretas.
- Nesse método de teste, são encontrados os testes de unidade, integração, sistema e aceitação.

## <span style="color:#00BFFF">■ Teste de unidade</span>
- São os mais básicos e consistentes em verificar se um componente individual do software (unidade) foi implementado corretamente.

## <span style="color:orange">■ Teste de integração</span>
- É feito quando unidades estão prontas, são testadas isoladamente e precisam ser integradas para gerar uma nova versão do sistema.
## <span style="color:#40E0D0">■ Teste de sistema</span>
- Verifica se a atual versão do sistema permite executar processos ou casos de uso completos do ponto de vista do usuário, sendo capaz de obter os resultados esperados
- Se cada uma das operações do sistema já estiver testada e integrada corretamente, então, deve-se verificar se o fluxo principal do caso de uso pode ser executado corretamente, bem como os fluxos alternativos.
## <span style="color:salmon">■ Teste de aceitação</span> 
- Teste realizado pelo cliente ou usuário do sistema, que consiste na aceitação da aplicação desenvolvida
- Costuma ser realizado utilizando-se a interface final do sistema.
---
---
# 🌚TESTE ESTRUTURAL

- Conhecido como teste da caixa branca, pois todos os testes são executados com conhecimento do código-fonte
- É capaz de detectar uma quantidade substancial de defeitos pela garantia de ter executado pelo menos uma vez todos os comandos e condições do programa.
- Destacam-se entre os possíveis critérios de teste  os critérios baseados na complexidade e no fluxo de controle.
---
## <span style="color:#00FA9A">■ Critérios baseados na complexidade</span>
- Utilizam informações sobre a complexidade do programa para derivar requisitos de software
- Dois critérios bastante conhecidos são a complexidade ciclomática e os caminhos linearmente independentes
### <span style="color: #1E90FF">Complexidade ciclomática</span>
- Métrica que proporciona uma medida quantitativa da complexidade lógica de um programa.

![[Pasted image 20240506220117.png]]
- Pontuação baseada nos pontos acima:

| <span style="color:green">Simples e fáceis de testar:</span>       | <= a  10     |
| ------------------------------------------------------------------ | ------------ |
| <span style="color:yellow">Médio risco em relação ao teste:</span> | >10 e <= 20  |
| <span style="color:red">Alto risco:</span>                         | > 20 e <= 50 |
| <span style="color:#FF4500">Não testáveis:</span>                  | >50          |
###  <span style="color:#32CD32"> Caminhos linearmente independentes</span> 

- Refere-se a qualquer caminho do programa que introduza pelo menos um  novo conjunto de instruções de processamento ou uma nova condição
- Para analisar os caminhos de um programa, sugere-se usar o grafo de fluxo de controle (GFC)
- Todos os comandos são representados em nós
	- Fluxo de controle em arestas
---
## <span style="color:red">■ Critérios baseados no fluxo de controle</span> 
-  Fazem uso do GFC de modo similar ao critério de caminhos linearmente independentes
- Utilizam apenas características de controle da execução do programa, como comandos ou desvios, para determinar quais estruturas são necessárias
- Destacam-se os critérios: Todos-Nós, Todas-Arestas e todos-caminhos

### <span style="color:#4682B4">Critérios Todos-Nós</span> 
- Exige que a execução do programa passe, ao menos uma vez, em cada vértice do GFC
- Conforme a figura, o critério Todos-Nós exige que sejam criados casos de teste que executem ao menos uma vez os nodos 1, 2 e 3
![[Pasted image 20240506222930.png|200]]


### <span style="color:#00FFFF">Critério Todas-Arestas</span> 
- Requer que cada aresta do garfo seja exercitada pelo menos uma vez
- Conforme a figura, o critério Todas-Arestas exige que sejam criados casos de teste que passem ao menos uma vez pelas arestas (1, 2), (2, 2) e (2, 3)
![[Pasted image 20240506223440.png|200]]

### <span style="color:#ADFF2F">Critérios Todos-caminhos</span> 
- Requer que todos os caminhos possíveis do programa sejam executados
- Conforme a figura, o critério Todos-caminhos exige que sejam definidos casos de teste que percorrem os caminhos (1, 2, 3) e (1, 2, 2, 3) ao menos uma vez
![[Pasted image 20240506223811.png|200]]
---
---
# 🚀TESTE FUNCIONAL

- É executados sobre as entradas e saídas do programa sem que se tenha conhecimento do seu código-fonte, sendo, portanto, identificando como teste de caixa preta
- Destacam-se como principal critérios do teste funcional o particionamento em classes de equivalência, a análise do valor limite e o error guessing
## <span style="color:orange">■ Particioanemento em classes de equivalência</span>
- Considerando que o teste exaustivo é, em geral, impossível de se aplicar, torna-se necessária a identificação de subconjuntos de casos de teste (Delamaro; Maldonado; Jino, 2007). Com isso, parafraseando Wazlawick (2013), se um programa aceita um conjunto de dados e rejeita outro conjunto, pode-se dizer que existem duas classes de equivalência para os dados de entrada do programa
	 A  técnica de particionamento de equivalência considera a divisão das entradas de um programa da seguinte forma:
- Entrada especificada como um intervalo de valores
	- Um conjunto válido e dois inválidos
- Entrada especificada com uma quantidade de valores
	- Um conjunto válido e dois inválidos
- Entrada especificada com um conjunto de valores aceitáveis
	- Um conjunto válido para cada uma das formas de tratamento
	- Um conjunto inválido para outros valores quaisquer
- Entrada especificada com uma condição
	- Um conjunto válido e um invalido
## <span style="color:#FF4500">■ Análise de valor limite</span>
 Ao contrário do particionamento em classes de equivalência, a análise de valor-limite, conforme colocado por Wazlawick (2013), consiste em considerar não apenas um valor qualquer para teste dentro de uma classe de equivalência, mas um ou mais valores fronteiriços com outras classes de equivalência quando isso puder ser determinado.
- Entrada especificada com um intervalo de valores
	- Testa-se os limites desse intervalo e os imediatamente subsequentes
- Entrada especificada com um quantidade de valores
	- Testa-se com nenhum valor de entrada, somente um valor, o limite de valores e um acima do limite
- Se entrada ou saída for um conjunto ordenado
	- Maior atenção ao primeiro e ao último elemento
- Usar a intuição para definir outras condições limites

## <span style="color:yellow">■ Error guessing</span>
- "Essa técnica corresponde a uma abordagem ad-hoc na qual a pessoa pratica, inconscientemente, uma técnica para o projeto de casos de testes, supondo por intuição e experiência alguns tipos prováveis de erro e, a partir disso, definem-se casos de teste que poderiam detectá-lo"
---
----
# ☄TESTE BASEADO EM DEFEITO
## <span style="color: #1E90FF">■ Teste de mutação</span>

- Esta etapa consiste em executar todos os programas mutantes gerados pelos operadores de mutação com o mesmo conjunto **T** aplicado no programa original. Para cada dado de teste aplicado em um mutante, o resultado obtido da execução do programa mutante é comparado com o resultado obtido na execução do programa original.
- Toda vez que o resultado do mutante difere do programa original com algum caso de teste de **T**, esse mutante é considerado morto e descartado. Para um mutante que apresenta o mesmo resultado do programa original, sem que seja possível gerar novos dados de teste que identifiquem a alteração gerada pelo operador de mutação, um defeito pode ter sido revelado ou esse mutante pode ser considerado equivalente ao programa original.

### <span style="color:#00FA9A">Sequência</span>
- Geração dos mutantes
- Execução do programa em teste
- Execução dos mutantes vivos


![[Pasted image 20240507214956.png]]
![[Pasted image 20240507215017.png]]
- De acordo com a Tabela 5, somente um mutante apresentou resultado igual ao programa original, sem ser possível a geração de um dado de teste que diferencie o resultado da execução desse mutante com o resultado da execução do programa original. Portanto, neste exemplo, de um total de 6 mutantes gerados, obtivemos 5 mutantes que apresentaram resultado diferente com algum caso de teste, sendo, portanto, considerados mortos e descartados e somente um igual ao original que é considerado vivo para análise posterior.

- Com o objetivo de averiguar a adequação dos casos de teste utilizados, é aplicado o escore de mutação. O escore de mutação varia entre 0 e 1 e fornece uma medida objetiva de quanto o conjunto de casos de teste analisado aproxima-se da adequação. Assim, dado um programa **P** e o conjunto de casos de teste **T**, calcula-se o escore de mutação _ms(P, T)_ da seguinte maneira:

$$ ms(P,T) = \frac{dm(P<T)}{M(P)-em(P)}
$$
- <span style="color:red">DM(P,T):</span> Número de mutantes mortos pelo conjunto de casos de teste
- <span style="color:red">M(P):</span> Número total de mutantes gerados com base no programa P
- <span style="color:red">EM(P):</span> Número de mutantes gerados que são equivalentes
### <span style="color:#00FA9A">Análise dos mutantes vivos</span>
- Esta etapa aplica-se para identificar, entre todos os mutantes que permaneceram vivos, quais representam um defeito no programa original ou quais são equivalentes
---
---
# 🛰AULA PRÁTICA TESTE DE MUTAÇÃO
1. Abaixa JDK Java no site www.ninite.com
2. Abaixe em runtimes, Java (adopOpenJDK) x64 8
3. O correto é usar o linux, o windows apresenta falhas no programa
4. Pesquise no google ``mujava`` e abaixe no primeiro site <https://cs.gmu.edu/~offutt/mujava/>
5. O foco dela e acadêmico
6. Assista o vídeo em Engenharia de software/A5/video: AP% teste mutaçao mujava