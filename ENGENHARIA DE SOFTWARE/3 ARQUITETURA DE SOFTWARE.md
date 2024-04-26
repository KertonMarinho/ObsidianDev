# Projeto de arquitetura de software
- Representa a estrutura de dados e os componentes de programa necessários para construir um sistema computacional. Ele considera o estilo de arquitetura que o sistema assumirá, e estrutura e as propriedades dos componentes que constituem o sistema, bem como as interrelações que ocorrem entre todos os componentes da arquitetura de um sistema. (pressman,2011, p.229)
- Conforme Pressman, as etapas de um projeto de arquitetura são:
	1. Projeto de dados
	2. Derivação da estrutura da arquitetura do sistema
	3. Análise de estilo ou padrões de arquitetura alternativos
	4. Implementação da arquitetura utilizando-se um modelo de processos
![[Pasted image 20240424214014.png]]
![[Pasted image 20240424214034.png]]
![[Pasted image 20240424214059.png]]
- Pfleeger(2004) destaca que o projeto é um processo iterativo composto por:
1. Projeto conceitual
2. Projeto técnico

## <span style="color:#BDB76B">1. Projeto conceitual</span>
- Apresenta ao cliente exatamente o que o sistema fará
- Sendo aprovado, é traduzido, dando origem ao projeto técnico
		- Linguagem UML
		- Diagrama de casos de uso
![[Pasted image 20240424214455.png|300]]

## <span style="color:#BDB76B">2. Projeto técnico</span>
- Determina hardware necessário
- Determinar software necessário
- Descrever a forma que o sistema terá
![[Pasted image 20240424214642.png|400]]

---
# PADRÕES DE ARQUITETURA DE SOFTWARE
- É como uma descrição abstrata, estilizada, das práticas recomendadas que foram testadas e aprovadas em diferentes subsistemas e ambientes(Sommerville,2018):

### <span style="color:red">Principais padrões:</span> 

![[Pasted image 20240424215043.png|600]]
- Essa arquitetura pode ser considerada como uma das mais aplicadas quando nos referimos ao desenvolvimento de sistemas de informação. Conforme Pressman (2011), um repositório de dados, tal como um banco de dados, reside no centro dessa arquitetura e, em geral, é acessado por outros componentes que atualizam, acrescentam, eliminam ou, de alguma forma, modificam dados contidos nesse repositório. A Figura 5 ilustra a representação dessa arquitetura.
---

![[Pasted image 20240424215134.png]]
- Também conhecida como arquitetura de duto e filtro, essa arquitetura se aplica quando dados de entrada devem ser transformados por meio de uma série de componentes computacionais ou de manipulação em dados de saída (Pressman, 2011). Conforme Sommerville (2018), o processamento dos dados está organizado de modo que cada componente de processamento (filtro) seja discreto e realize um tipo de transformação de dados.
- Normalmente esse tipo de arquitetura é representada em sistemas desenvolvidos na metodologia de programação estruturada, por meio da representação de diagramas de atividades da linguagem UML
----

![[Pasted image 20240424215245.png]]
Nessa arquitetura, o sistema é organizado em camadas com a funcionalidade relacionada associada a cada camada (Sommerville, 2018). Conforme Pressman (2011), na camada mais externa, os componentes atendem operações de interface do usuário. Na camada mais interna, os componentes realizam a interface com o sistema operacional e, nas camadas intermediárias, são fornecidos serviços utilitários e funções de software de aplicação.

Como um exemplo de um sistema de arquitetura em camadas, podemos visualizar o exemplo proposto por Sommerville (2018, p. 157), de um sistema de aprendizagem digital para apoiar a aprendizagem de todas as disciplinas nas escolas

----

![[Pasted image 20240424215423.png]]
- A arquitetura cliente-servidor é muito utilizada para sistemas distribuídos e sistemas web. De acordo com Sommerville (2018), nessa arquitetura, o sistema é apresentado como um conjunto de serviços, e cada serviço é fornecido por um servidor separado. Os clientes são usuários desses serviços e acessam os servidores para usá-los.

Podemos considerar essa arquitetura como uma das mais utilizadas, pois todos os serviços que acessamos diariamente ao conectarmos na internet, são baseados na arquitetura cliente-servidor, e dentre eles podemos citar nosso e-mail, sites de _streamming_ de vídeos, jogos online, entre outros.

-----
![[Pasted image 20240424215447.png]]
- A arquitetura orientada a objetos pode ser considerada como uma das arquiteturas mais atuais. Conforme Pressman (2011), nessa arquitetura, os componentes de um sistema encapsulam dados e as operações que devem ser aplicadas para manipular os dados. A comunicação e a coordenação entre componentes são realizadas por meio da passagem de mensagens.

A arquitetura orientada a objetos fornece uma descrição abstrata do software, de modo que tem como intuito aproximar as estruturas de um programa das coisas do mundo real. Essa arquitetura se baseia em dois conceitos:

- **Classes**: é um conjunto de características e comportamentos que definem o conjunto de objetos pertencentes à classe;
- **Objetos**: uma ou várias instâncias de uma classe que correspondem as suas características e comportamentos.

---
![[Pasted image 20240424215529.png]]

Essa arquitetura tem como foco separar a apresentação e a interação dos dados do sistema. Segundo Sommerville (2018), o sistema é estruturado em três componentes lógicos que interagem entre si, modelo, visão e controlador:

- **Modelo**: gerencia o sistema de dados e as operações associadas a esses dados;
- **Visão**: define e gerencia como os dados são apresentados ao usuário.;
- **Controlador**: gerencia a interação do usuário e passa essa interação para a Visão e o Modelo.

---
# REQUISITOS DE SOFTWARE
- São as descrições do que o sistema deve fazer, os serviços que oferecem e as restrições a seu funcionamento.
- São classificados de Funcionais e não funcionais

## <span style="color:brown">Funcionais</span>
- Declaração dos serviços que o sistema deve fornecer
- Como o sistema deve agir com relação a determinadas entradas
- Como o sistema deve se comportar em determinadas situações
- O que o sistema não deve fazer
## <span style="color: #1E90FF">Não funcionais</span>
- Restrições sobre os serviços ou funções oferecidas pelo sistema
	- Restrição de tempo
	- Restrição sobre o processo de desenvolvimento
	- Restrições impostas por padrão
- Aplicam-se ao sistema como um todo, em vez de às características individuais ou aos serviços

## TÉCNICAS PARA ELICITAÇÃO DE REQUISITOS
###  <span style="color:#32CD32">Entrevistas</span> 
- Formais ou informais, com usuários e demais partes envolvidas no sistema
### <span style="color:#FF4500">Cenários</span>
- Podem ser escritos com texto, suplementados por diagramas, telas, entre outros
## <span style="color:#8A2BE2">Casos de usos</span>
- Abordagem mais estruturadas de cenários.
- Identificar os atores envolvidos em uma iteração e dá nome ao tipo de iteração
## <span style="color:aquamarine">Etnogrtafia</span>
- Técnica de observação que pode ser usada para compreender os processos operacionais e ajuda a extrair os requisitos de apoio para esses processos
---
# GERENCIAMENTO DE CONFIGURAÇÃO E MUDANÇA
- É um conjunto de atividades destinadas a gerenciar as alterações identificadas os artefatos que precisam ser alteradas, estabelecendo relações entre eles, definindo mecanismos para gerenciar diferentes versões  desses artefatos, controlando as alterações impostas e auditando e relatando alterações feitas.
## Para Sommerville(2018), o gerenciamento de configuração envolve quatro atividades
## <span style="color:#00BFFF">1. Controle de versão</span>
- Controlar as várias versões dos componentes do sistema
- Garantir que as mudanças feitas não interferem nas outras
## <span style="color:#00FA9A">Construção do sistema</span>
-  Reunir componentes, dados e bibliotecas do programa, compilando-os e ligando-os para criar um sistema executável
## <span style="color:#8B4513">Gerenciamento de mudanças</span>
-  Manter o controle das solicitações de mudança de cliente e desenvolvimento no software já entregue
- Elaborar os custos e o impacto dessas mudanças, bem como decidir se e quando as alteraçoes devem ser implementadas

## <span style="color:#BDB76B">Gerenciamento de lançamento</span>
- Preparar o software para o lançamento externo e acompanhar as versões lançadas para o uso do cliente
---
