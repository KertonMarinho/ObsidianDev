## <span style="color:yellow">Softwares Utilitários</span>
- Ou ferramentas de sistemas.
- são os que acompanham o sistema operacional e o auxiliam nas suas tarefas (por exemplo, gerenciamento de dispositivos, mídias e programas).
- EXEMPLO: antivírus, compactadores, backup, etc.
## <span style="color:yellow">Softwares Aplicativo</span>
- Aplicativos ou APP
- Podemos dizer que é um software que realiza algum trabalho para o usuário, ou seja, são programas que realizam tarefas específicas.
- EXEMPLO:  navegadores.


## <span style="color:yellow">Sistemas Tradutores</span>
- Os sistemas tradutores convertem os programas escritos para um código
em uma linguagem de máquina, mais adequada para manipular bits

## <span style="color:yellow">Interpretadores</span>
- O código é interpretado linha por linha
![[Pasted image 20231024212318.png|400]]
## <span style="color:yellow">Compiladores</span>
Traduzem código todo de uma vez gerando um .ex
![[Pasted image 20231024212355.png|350]]

---
## <span style="color:aquamarine">Sintaxe</span>
- A sintaxe define como a forma ou a estrutura das expressões, dos comandos ou das unidades de programas devem ser, ou seja, ela define se um programa está corretamente escrito em uma determinada linguagem de programação

## <span style="color:aquamarine">Semântica</span>
-Define o significado formal dessas expressões, comandos ou unidades de programas. Ela define o significado da forma de cada trecho de código. Os erros de semântica estão relacionados com a lógica de programação

## <span style="color:aquamarine">Estrutura de dados</span>
- A estrutura de dados diz respeito à forma como estes são armazenados e organizados na memória. Como estrutura de dados mais simples temos os vetores, também chamados de arrays ou listas.
---
## <span style="color:orange">API</span>
- A Application Programming Interface (Interface de Programação de
Aplicativos) pode ser definida como um conjunto de rotinas e padrões de programação que possuem o objetivo de acessar aplicativos de software ou plataformas baseados na web. A API é uma interface utilizada por um programa ou aplicação e não por um usuário

## <span style="color:orange">Framework</span>
- É um conjunto de código de uma linguagem de programação específica que auxilia no desenvolvimento de projetos de web ou de software. Podemos pensar no framework como se fosse uma biblioteca de códigos com funções já prontas

## <span style="color:orange">IDE</span>
É o Ambiente de desenvolvimento integrado
## <span style="color:orange">SDK</span>
- kit de desenvolvimento de software.
---
## <span style="color:aquamarine">Monolítico</span>
- É uma aplicação que roda com um único processo

## <span style="color:aquamarine">Microserviços</span> 
- É uma abordagem arquitetônica e organizacional do desenvolvimento de software na qual o software consiste em pequenos serviços independentes que se comunicam usando APIs bem definidas. Esses serviços pertencem a pequenas equipes autossuficientes. Como características dos microsserviços temos que eles são autônomos e especializados.
---
## <span style="color:aquamarine">SOAP</span>
- Service-Oriented Architecture (Or Application) Protocol (protocolo
de arquitetura orientada a serviços). O SOAP utiliza arquivos xml e o protocolo HTTP como protocolo de transporte

## <span style="color:aquamarine">REST</span>
- REpresentational State Transfer, em português: Transferência
Representacional de Estado, é um conjunto de restrições para criação de webservices. Quando um serviço implementa esse padrão, dizemos que é Restfull. Restfull utiliza arquivos JSON

>[!warning]
>é correto afirmar que todo Webservice é uma API, mas nem toda API é um Webservice, porque tanto o Webservice quanto as APIs realizam a comunicação entre aplicações, porém a forma como são utilizados é totalmente diferente.

---
## <span style="color:salmon">Commit</span> 
- Significa enviar alterações de um determinado trecho do código, ou seja, o envio da criação de uma nova versão do projeto.
## <span style="color:salmon">Versionamento</span>
- Consiste em atribuir um número de versão ao estado do
projeto.
## <span style="color:salmon">GIT</span>
- é um sistema de controle de versão que gerencia as várias versões
no desenvolvimento de um documento
## <span style="color:salmon">Github</span>
- Segundo a própria desenvolvedora, o Github é uma plataforma de
desenvolvedor completa para criar, dimensionar e fornecer software seguro. O github utiliza o Git como sistema de controle.

## <span style="color:green">Debug</span> 
- o debugging ou debugar significa depurar o programa. Ou seja, encontrar erros e tentar resolvê-los.

## <span style="color:khaki">Snapshot</span>
- Cópia instantânea em um determinado tempo de um volume.

## <span style="color:aquamarine">Contêineres</span>
- Contêineres são um método de virtualização do sistema operacional que permite executar um aplicativo e suas dependências em processos isolados de recursos. 
- Simplificadamente os containers empacotam o código, as configurações e as dependências de um aplicativo em um único objeto.
- Basicamente, um contêiner é um pacote que contém um software e todas as dependências necessárias para que ele execute e forneça facilidade de manuseio e economia de tempo, facilitando a implantação (deploy).
### Diferença de Contêineres versus virtualização:
- Segundo Mariano (2020), do ponto de vista do sistema operacional, os contêineres são um método de virtualização do sistema operacional que permite executar um aplicativo e suas dependências em processos isolados de recursos. A virtualização consiste em uma tecnologia que possibilita a execução de um SO dentro de outro por meio de máquinas virtuais (Virtual Machines – VM), contexto em que uma única máquina física pode dividir recursos com vários SO capazes de interagir ou se isolar completamente entre si.
- Geralmente, os contêineres são medidos em megabyte. Eles contêm, no máximo, a aplicação e os arquivos necessários para executá-la. Além disso, costumam ser usados para empacotar funções individuais que realizam tarefas específicas, os famosos microsserviços. Como são leves e têm um sistema operacional compartilhado, os contêineres são muito fáceis de migrar entre vários ambientes.
-  As máquinas virtuais são medidas em gigabyte. Costumam ter seu próprio sistema operacional, o que possibilita a execução simultânea de várias funções com uso intenso de recursos. Por terem um número maior de recursos à disposição, as máquinas virtuais são capazes de abstrair, dividir, duplicar e emular por inteiro servidores, sistemas operacionais, desktops, bancos de dados e redes.
- Ou seja, com a virtualização, é possível executar sistemas operacionais
simultaneamente em um único sistema de hardware, já os contêineres compartilham o mesmo kernel do sistema operacional e isolam os processos da aplicação do restante do sistema

## <span style="color:red">Computação de Borda</span>
- A definição dada pela Intel é de que “a computação de borda se refere ao
processamento, análise e armazenamento de dados mais próximos de onde eles são gerados para permitir análises e respostas rápidas, quase em tempo real”.
- Já a IBM define a computação de borda como “um modelo de computação
distribuída que aproxima os aplicativos corporativos das fontes de dados, como dispositivos de IoT ou servidores de borda local”.