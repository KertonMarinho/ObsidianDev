# NORMA ISO/IEC/IEEE 42010:2011
- Conhecida como Sistemas e engenharia de software - Arquitetura de descrição
- Norma criada para estabelecer o objetivo de criar, analisar e descrever arquiteturas de software
- Modelo sugerido pelo iso/iec/ieee:
- ![[Pasted image 20230925214639.png]]
# <span style="color:aquamarine">Representação das visões de Arquitetura de Software</span>
#### <span style="color:green">Visão Lógica</span>
- Essa visão concentra-se na funcionalidade do sistema. Ela descreve
os principais elementos funcionais do sistemas, suas responsabilidades, propriedades e interfaces.
#### <span style="color:green">Visão de Desenvolvimento</span>
- Essa visão aborda a estrutura do software, incluindo seus componentes e subcomponentes. Isso é particularmente útil para os desenvolvedores que estão construindo e integrando o software.
#### <span style="color:green">Visão de Processo</span>
- essa visão trata do aspecto dinâmico do sistema, incluindo o processamento de tarefas, concorrência e sincronização
#### <span style="color:green">Visão Física</span>
- Essa visão descreve a infraestrutura necessária para o sistema, incluindo hardware, software de sistema e redes
---
# Modelos arquitetônicos

<span style="color:aquamarine">Arquitetura em camadas(layered pattern</span> 
- Organiza um sistema se conjunto em camadas que podem ser desconstruídas em diferentes serviços, trazendo um modelo incremental de desenvolvimento.(Ex. mais comuns: software e-commerce e desktop)

![[Pasted image 20230925215419.png]]

---
<span style="color:aquamarine">Arquitetura cliente-servidor(client-server pattern</span>
- Estilo organizado em serviços combinando dados do cliente e do servidor
- É primordial que o cliente disponibilize uma rede de acesso as informações
- Podem ser aplicativos bancários e de e-mail.
- O servidor mantém e gerencia a maior parte dos recursos de dados e funções de negócios, enquanto o cliente é responsável por solicitar esses serviços e apresentar os resultados ao usuário.
- ![[Pasted image 20230925220145.png|500]]
---
<span style="color:aquamarine">Arquitetura MVC( model-view-controller pattern)</span>
- Distribuído em três camadas (modelo, visão e controle)
- Mais comum para online(traz modelo interativo de sistema)
![[Pasted image 20230925220539.png]]
- O "Modelo" é onde os dados e as regras de negócios são armazenados; 
-  A "Visão" é como os dados são apresentados – é a interface do usuário; 
-  O "Controlador" é o que conecta a Visão e o Modelo. Ele atualiza a Visão quando o Modelo muda e atualiza o Modelo quando o usuário interage com a Visão.
---
<span style="color:aquamarine">Arquitetura de microsserviços (microservices pattern)</span> 
- Este padrão utiliza múltiplos serviços e componentes para desenvolver uma estrutura modular favorecida.
- É um dos modelos preferidos dos desenvolvedores  e arquitetos de software por possibilitar a escalabilidade e a independência dos módulos - que até podem utilizar diferentes linguagens e programações
-  Altamente manuteníveis e testáveis; 
- Livremente acoplados, ou seja, cada serviço pode ser independentemente dos outros;
-  Independentes, o que permite que cada serviço seja implantado independentemente;
- Capazes de serem desenvolvidos e implantados por pequenas equipes.
![[Pasted image 20230925221140.png]]
