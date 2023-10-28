## <span style="color:orange">Requisitos Funcionais</span>
- diz respeito ao que o software deve fazer, ou seja, quais funções ele deve possuir.
## <span style="color:orange">Requisitos não Funcionais</span>
- diz respeito às restrições do software
- ----
# Modelo cascata
- Mostra as atividades fundamentais do processo de software distribuídas em fases distintas. Devido à cascata de uma fase para outra, é definido como modelo cascata ou ainda conhecido como ``modelo de ciclo de vida do software (SDLC)``. 
- São cinco fases que compõem o modelo cascata:
1.  Na etapa de requerimento ocorre o levantamento de requisitos. As metas e restrições são identificadas com os usuários. 
2.  Na etapa de projeto os requisitos identificados na etapa anterior são mapeados em componentes de hardware e software. 
3.  Na etapa de implementação, o projeto de software é implementado em unidades de programas. Nessa fase ocorre também o teste de unidade, que envolve a verificação de cada unidade e se cada uma cumpre a sua especificação. 
4. Na etapa de verificação as unidades de programas são integradas e testadas como um sistema completo. 
5. Na etapa de manutenção o sistema é instalado e colocado em operação. Aqui, são corrigidos os erros que não foram descobertos nas fases anteriores. Novas funcionalidades podem ser identificadas e se há a necessidade da repetição do ciclo.

![[Pasted image 20231026223000.png|500]]
>[!info]
>Esse modelo apresenta desvantagens, pois é improdutivo quanto ao tempo, já que a etapa posterior só pode iniciar depois da finalização da etapa anterior. A Visão Sequencial também não corresponde ao mundo real, fornecendo pouca visibilidade do estado do projeto, pois é demandado muito tempo para a primeira entrega.
---
# Metodologia Agil

- A metodologia ágil entrega as funcionalidades de software mais rapidamente aos seus clientes.
- Essa metodologia tem foco no software e não no projeto ou na documentação. 
- É adequada para aplicações em que os requisitos mudam rapidamente. 
- Veremos duas abordagens utilizadas na metodologia Ágil: o extreme Programming e o SCRUM
### XP (eXtreme Programming)
-  A programação extrema introduziu práticas ágeis ao desenvolvimento tradicional de software. As práticas da XP refletem os princípios do manifesto ágil. O quadro seguinte descreve as práticas do XP e suas respectivas descrições.
![[Pasted image 20231024220334.png]]

----
## Scrum
- O Scrum é um framework estrutural, não é considerado uma metodologia.
Basicamente, uma metodologia diz o que fazer e como fazer. O Scrum indica uma trajetória, mas não como fazer. Sendo assim, o Scrum é um arcabouço de informações, um esqueleto.
- O Scrum possui três artefatos, cinco eventos, cinco valores e três papéis.
 ![[Pasted image 20231024220553.png|400]]
- No Scrum, os projetos são divididos em ciclos chamados de Sprints. As
Sprints são a essência, o coração do Scrum. Uma sprint é um time-boxed de um mês ou menos, durante o qual um “Pronto”, incremento de produto potencialmente liberável é criado. O time-boxed é a expressão para definir uma unidade de tempo no Scrum. Cabe, ainda, ressaltar que as Sprints têm durações consistentes ao longo de todo o desenvolvimento. Uma nova Sprint só se inicia imediatamente após a conclusão da Sprint anterior. As sprints podem ser vistas como as iterações que ocorrem ao longo do desenvolvimento de software.
### <span style="color:yellow">Artefatos</span>
- No Scrum representam o trabalho feito para fornecer transparência ao processo. São projetados para maximizar a transparência das informações-chave para que todos no time recebam as informações relevantes e tenham a mesma compreensão do que deve ser feito.
-  Scrum possui três artefatos: o product backlog, o sprint backlog e o increment
1. <span style="color:aquamarine">Product Backlog</span>
- É uma lista ordenada de tudo que é conhecidamente
necessário para fornecer o produto. É a única origem dos requisitos para qualquer mudança a ser feita no produto. O product backlog é, então, uma lista de produtos pendentes. 
2. <span style="color:aquamarine">Sprint backlog</span> 
- Possui os itens do product Backlog selecionados para a Sprint, com o plano para entregar o incremento do produto e atingir o objetivo da Sprint. Possui também uma previsão do Time de Desenvolvimento sobre qual funcionalidade estará no próximo incremento. O Sprint Backlog é um plano feito por e para desenvolvedores. É uma imagem em tempo real altamente visível do trabalho que os desenvolvedores planejam realizar durante o Sprint para atingir o objetivo do Sprint. 
3. <span style="color:aquamarine">Increment (incremento)</span> 
- O  é a soma de todos os itens do Product Backlog completados durante a Sprint e o valor dos incrementos de todas as Sprints anteriores.
### <span style="color:yellow">Eventos</span>
- O Scrum prescreve alguns eventos formais para inspeção e adaptação: 
	-  Sprint;
	- Sprint Planning (Planejamento da Sprint); 
	- Daily Scrum (Reunião diária); 
	- Sprint Review (Revisão da Sprint); 
	- Sprint Retrospective (Retrospectiva da Sprint). 
- O Sprint foi explicado previamente. Iniciaremos, então, com a conceituação do Sprint Planning ou o Planejamento da Sprint:
<span style="color:salmon">Sprint Planning</span> 
- O Planejamento do Sprint inicia o Sprint, estabelecendo o trabalho a ser realizado para o Sprint.
- Esse plano resultante é criado pelo trabalho colaborativo de todo o Time Scrum. 
- O Product Owner garante que os participantes estejam preparados para discutir os itens mais importantes do Product Backlog e como eles são mapeados para a meta do produto. 
- O Time Scrum também pode convidar outras pessoas para participar do Sprint Planning para fornecer conselhos.
<span style="color:salmon">Dayly Scrum</span> 
- Objetivo do Daily Scrum é inspecionar o progresso em direção ao Sprint Goal e adaptar o Sprint Backlog conforme necessário, ajustando o próximo trabalho planejado. O Daily Scrum é uma reunião de aproximadamente 15 minutos para os Desenvolvedores do Time Scrum.
<span style="color:salmon">Spriny Review</span> 
- A sprint Review (Revisão do Sprint) tem como objetivo inspecionar o resultado do Sprint e determinar futuras adaptações. 
- O Time Scrum apresenta os resultados de seu trabalho para as principais partes interessadas e o
progresso em direção ao Objetivo do Produto é discutido.
<span style="color:salmon">Retrospective</span> 
- Sprint Retrospective (Retrospectiva da Sprint) tem como objetivo
planejar maneiras de aumentar a qualidade e a eficácia. 
O Time Scrum inspeciona como foi o último Sprint em relação aos indivíduos, interações,
processos, ferramentas e sua Definição de Pronto. Aqui, ainda, é discutido o que
correu bem durante o Sprint, quais problemas foram encontrados e como esses
problemas foram (ou não) resolvidos.

### <span style="color:yellow">Valores</span>
Os cincos valores descritos a seguir sempre foram considerados como partes do Scrum e adicionados oficialmente em julho de 2016 ao guia do
Scrum.
• <span style="color:red">Coragem</span> : o time Scrum precisa ter coragem para fazer a coisa certa e trabalhar em problemas difíceis.
• <span style="color:red">Foco</span> : todos focam no trabalho da Sprint e nos objetivos do time Scrum.
• <span style="color:red">Comprometimento</span>: as pessoas se comprometem pessoalmente em alcançar os objetivos do time scrum.
• <span style="color:red">Respeito</span>: os membros do time scrum respeitam uns aos outros para serem pessoas capazes e independentes.
• <span style="color:red">Abertura</span>: o time scrum e seus stakeholders concordam em estarem abertos a todo o trabalho e aos desafios com a execução dos trabalhos.

### <span style="color:yellow">Papéis</span>
- A unidade fundamental do Scrum é o time. Um pequeno time, ou seja, um pequeno grupo de pessoas que trabalham juntas, definidas de time Scrum. Não existe o conceito de hierarquia no time Scrum, mas cada integrante do time tem um papel (role). São três papeis: Product Owner, Scrum master e developers (desenvolvedores).
1. <span style="color:green">Product owner</span>  é dono do produto, é o responsável por maximizar o valor do produto resultante do trabalho do Time de Desenvolvimento. É a única pessoa responsável por gerenciar o Backlog do Produto.
2. <span style="color:green">Scrum master</span> é o responsável por promover e suportar o Scrum como definido no Guia Scrum. O Scrum Master faz isso ajudando a todos a entenderem a teoria, as práticas, as regras e os valores do Scrum. 
3. <span style="color:green">Time de Desenvolvimento</span>  consiste em profissionais que realizam o trabalho de entregar um incremento potencialmente liberável do produto ao final de cada Sprint.