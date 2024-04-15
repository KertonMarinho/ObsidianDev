# PROCESSOS DE SOFTWARE
-  Referem-se a um conjunto de atividades relacionadas que levam a produção de um sistema de software. 
- Não há um método universal de engenharia de software que seja aplicável todos os tipos diferentes de sistemas de software existentes.
## Quatro atividades fundamentais em engenharia de software
1. <span style="color: #1E90FF">Especificação:</span> A funcionalidade do software e as restrições sobre a sua operação devem ser definidas.
2. <span style="color: #1E90FF">Desenvolvimento:</span> O software deve ser produzido para atender a especificações.
3. <span style="color: #1E90FF">Validação:</span> O software deve ser validado para garantir que atenda o que cliente deseja.
4. <span style="color: #1E90FF">Evolução:</span> O software deve evoluir para atender as mudanças nas necessidades dos clientes.
---
#  <span style="color:#32CD32">Modelos de processos de softaware</span> 
####  <span style="color:red">- Processos prescritivos</span> 
Modelos de processos tradicionais, que surgiram com o propósito de organizar e direcionar as atividades inerentes o desenvolvimento de software.
 • Integração e configuração: baseia-se na disponibilidade de componentes ou sistemas reutilizáveis. O processo de desenvolvimento 6 se concentra na configuração desses componentes para que sejam utilizados em um novo contexto e na integração deles em um sistema
• Espiral: tem como característica principal a realização de ciclos de prototipação para a redução de riscos de projeto. 
• Sashimi: introduz a noção de que as fases do modelo cascata não são estanques, mas que em determinado momento ele pode estar simultaneamente em mais de uma dessas fases. 
• Modelos V e W: Focam no teste durante o desenvolvimento de software e indicam que este deve ser uma preocupação constante, e não apenas uma etapa colocada ao final do processo. 
• Modelo orientado a cronograma: tem foco prioritariamente no desenvolvimento das funcionalidades mais importantes, deixando as demais para o final. Caso ocorram atrasos e o prazo for rígido, ao menos as funcionalidades mais críticas serão entregues no prazo. 
• Entrega em estágios: tem como prioridade planejar e entregar partes prontas do sistema antes do final do projeto. 
• Prototipação evolucionária: propõe o uso de protótipos para ajudar na compreensão da arquitetura, da interface e dos requisitos do sistema, quando não é possível conhecer bem esses aspectos a priori. 
• Entrega evolucionária: combina a prototipação evolucionária com a entrega em estágios, mostrando que é possível fazer um planejamento adaptativo em que, a cada nova iteração, o gerente de projeto decide se vai acomodar as requisições de mudança que surgiram ao longo do projeto ou manter-se fiel ao planejamento inicial. 
• Modelos orientados a ferramentas: família de modelos cuja única semelhança costuma consistir no fato de que eles são indicados para uso com ferramentas específicas. 
• Linhas de produto de software: tipo de processo que se aplica somente no desenvolvimento de uma família de produtos semelhantes. Desse 7 modo, é possível que a reusabilidade de componentes seja efetivamente planejada
#### <span style="color:red">- Pocessos ágeis</span> 
Possuem interações curtas, nas quais o resultado é medido através do produto pronto, ao contrário dos modelos prescritivos, em que o desenvolvimento é marcado dividido em etapas bem definidas.

----
# <span style="color:violet">Modelo Cascata</span> 
- Desenvolvido na década de 1970.
- Derivado dos modelos utilizados na engenharia de grandes sistemas militares.
- Apresenta o processo de desenvolvimento de software como uma série de fases.
![[Pasted image 20240414212851.png|500]]
![[Pasted image 20240414213045.png|500]]
#### Vantagens:
- Fases bem definidas ajudam a detectar erros mais cedo
- Procura promover a estabilidade dos requisitos
- Funciona bem quando os requisitos são conhecidos e estáveis
- É adequado para equipes tecnicamente fracas ou inexperientes
#### Desvantagens:
- Não produz resultados tangíveis até a fase de codificação
- É difícil estabelecer requisitos completos antes de começar as codificar
- Desenvolvedores sempre reclamam que os usuários não sabem expressar aquilo de que precisam
- Não há flexibilidade com requisitos

É possível observar que o modelo cascata é sequencial, possibilitando retornar às fases anteriores somente após a fase de operação e manutenção. Isso o torna um modelo impraticável, visto que muitos problemas descobertos em fases mais avançadas não necessariamente foram originados na fase imediatamente anterior
Tentando solucionar esse problema, Royce (1970) propôs o modelo de cascata dupla, de modo que problemas encontrados em uma fase podem ser resolvidos retornando-se à fase anterior para efetuar as correções:
# ![[Pasted image 20240414213948.png|500]]

# <span style="color:salmon">Modelo V</span> 
- Avanço do modelo cascata
- Com o intuito de amenizar as dificuldades impostas pelo modelo cascata, o modelo V originou-se com base naquele, prevendo uma fase de validação e uma de verificação para cada fase de construção do sistema. A Figura 4 apresenta a especificação do modelo V
![[Pasted image 20240414214059.png|500]]

# <span style="color:khaki">Modelo w</span>
- Com o objetivo de focar ainda mais na fase de testes do sistema, o Modelo W foi proposto como uma variação ao modelo V
- a principal variação para o modelo V está na observação de que há uma divisão muito estrita entre as atividades construtivas do lado esquerdo do V e as atividades de teste no lado direito
![[Pasted image 20240414214145.png|500]]

##  FASES DO MODELO V E W
### <span style="color:brown">Fase de requisitos:</span>
- Apenas requisitos que possam ser testados são aceitáveis ao final dessa fase
### <span style="color:brown">Fase de design arquitetural</span>
- Arquiteturas simples devem ser fáceis de testar. Caso contrário, talvez a arquitetura seja demasiadamente complexa e necessite ser refatorada
### <span style="color:brown">Desing detalhado</span>
- A mesma questão se coloca em relação às unidades. Unidades coesas são mais fáceis de testar

---
# <span style="color:brown">Modelo espiral</span>
- Criado em 1986
- Apresenta a ideia em ciclos iterativos
- O projeto é dividido em subprojetos
- Cada subprojetos aborda um ou mais elementos de alto risco, até que todos os riscos identificados tenham sido tratados
![[Pasted image 20240414215140.png]]

## <span style="color:yellow">Iterações do modelo espiral</span>
-  <span style="color:#32CD32">Primeira iteração:</span>  concepção das operações
-  <span style="color:#32CD32">Segunda iteração:</span>  requisitos de software
-  <span style="color:#32CD32">Terceira iteração:</span>  desenvolvimento do sistema
-  <span style="color:#32CD32">Quarta iteração: </span> Testes

## <span style="color:red">Vantagens e desvantagens</span> 
- As primeiras iterações são as mais baratas do ponto de investimento de tempo e de recursos
- Também são as que resolveram os maiores problemas do projeto
- Esses modelo não provê a equipe com indicações claras sobre a quantidade de trabalho esperado a cada ciclo
- Pode tornar o tempo de desenvolvimento nas primeiras fases bastante imprevisível
---
# MODELO DE DESENVOLVIMENTO EM FASES
- O modelo é projetado de modo que possa ser entregue em partes, possibilitando aos usuários dispor de alguns recursos enquanto o restante do sistema está sendo desenvolvido
### Sistema em produção:
- É o sistema que está sendo atualmente utilizado pelo cliente
### Sistema em desenvolvimento:
- É a versão seguinte que está sendo desenvolvida para substituir o sistema em produção
![[Pasted image 20240414220727.png|500]]
## Abordagem do modelo de desenvolvimento em fases
- <span style="color:orange">Desenvolvimento incremental:</span> o sistema é dividido por funcionalidades e cada versão entregue correspondente a uma delas ou a um conjunto dessas funcionalidades
- <span style="color:orange">Desenvolvimento iterativo:</span> a primeira versão entregue correspondente ao sistema completo, porém, com funcionalidade limitadas. Cada versão posterior corresponde a mudanças realizadas nas funcionalidades limitadas
---
# PROTOTIPAÇÃO EVOLUCIONÁRIA
- Permite que todo o sistema, ou parte dele, seja construído rapidamente
- Tem o mesmo objetivo de um protótipo de engenharia
- Auxilia na definição dos requisitos
- Facilita para garantis que desenvolvedor, usuário e cliente cheguem a um consenso soreb o que é necessário e o que é proposto
### Métodos:
##### <span style="color:#32CD32">Throw away</span> ou descartável: 
 refere-se a protótipos usados unicamente para estudar aspectos do sistema, entender melhor seus requisitos e reduzir riscos
#### <span style="color:red">Cornerstone</span> ou fundamental:
Refere-se a protótipos para serem parte do sistema final, de modo que o protótipo vai evoluindo até se tornar um sistema que possa ser entregue
- Modelo de prototipação evolucionária proposto por Wazlawick:
![[Pasted image 20240414222603.png]]
- Modelo de prototipação evolucionária proposto por Pfleeger:
	- a prototipação segue um modelo orientado por revisões em cada uma das etapas
![[Pasted image 20240414222711.png]]
---
# MODEL0 RUP(Processo unificado da rational)
- Se baseia em quatro etapas:
	- <span style="color:yellow">Concepção</span>: Elabora-se um plano de negócios para o sistema, com o objetivo de identificar as entidades externas e os requisitos, a fim de avaliar a contribuição do sistema para o negócio
	- <span style="color:yellow">Elaboraçao:</span> São desenvolvidos os requisitos e a arquitetura do sistemas
	- <span style="color:yellow">Construção:</span> implementação e testes
	- <span style="color:yellow">Transição:</span>  Implantação em ambiente real
	- ![[Pasted image 20240414223633.png|500]]
	![[Pasted image 20240414223658.png]]
	![[Pasted image 20240414223813.png]]
	