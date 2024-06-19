>[!summary] Mark Hornbeek
>"Sem boas práticas de design, uma implementação Devops não tem esperança de cumprir sua promessa de acelerar a inovação com alta qualidade e escala."

#### Integração contínua (CI, do inglês _Continuous Integration_) no Git é a integração contínua de código usando o Git, um sistema de controle de versão distribuído. A CI automatiza o processo de integração de alterações de código de vários desenvolvedores em um único repositório central.
## <span style="color:yellow">CI/CD</span>
- CI/CD, que significa "Integração contínua" e "entrega contínua"(ou "implementação contínua"), são práticas fundamentais no desenvolvimento de software, que visam automatizar e agilizar o processo de entrega de software.

# ➫ Integração Contínua (CI) Explicada

![[Pasted image 20240612220815.png]]
![[Pasted image 20240612221455.png|500]]

---
---
# ➫ Explicando CI/CD

## <span style="color:khaki"> ■ CI</span>
Na engenharia de _software_, CI é um processo antigo, que trata da prática de mesclar todas as cópias de trabalho dos desenvolvedores em uma linha principal compartilhada, várias vezes ao dia (Muniz et al., 2021).

A CI automatiza a integração de alterações de código de vários desenvolvedores em um único repositório central. Seu objetivo principal é identificar e resolver problemas de integração precocemente, antes que eles se tornem grandes e difíceis de corrigir

## <span style="color:khaki"> ■ CD</span>
Após a automação das compilações e dos testes de integração e unidade na CI, a Entrega Contínua automatiza o lançamento do código validado em um repositório. Portanto, para estabelecer um processo eficiente de entrega contínua, é crucial que a CI esteja integrada ao _pipeline_ de desenvolvimento. O propósito da entrega contínua é manter a base de códigos constantemente preparada para ser implantada em um ambiente de produção (Muniz et al., 2021).

![[Pasted image 20240612221745.png|400]]
![[Pasted image 20240612222125.png|500]]

---
---
# Ferramentas e Framework para CI/CD

![[Pasted image 20240612222356.png|500]]
![[Pasted image 20240612222458.png]]
![[Pasted image 20240612222618.png]]

---
##  <span style="color:#32CD32">■ Ferramentas de CI</span> 
- <span style="color:red">Jenkins</span>  – é uma ferramenta de automação de código aberto amplamente utilizada para automação de compilação, testes e implantação;
- <span style="color:red">Travis CI</span>  – é uma plataforma de integração contínua baseada em nuvem, que se integra facilmente com repositórios no GitHub;
- <span style="color:red">CircleCI</span>  – é uma plataforma de CI/CD que automatiza o processo de construção, teste e implantação;
- <span style="color:red">GitLab CI/CD</span>   – integrado diretamente ao GitLab, fornece recursos integrados de CI/CD dentro da plataforma GitLab;
- <span style="color:red">TeamCity</span>  – desenvolvido pela JetBrains, oferece uma solução robusta para automação de compilação e integração contínua;
- <span style="color:red">Bamboo</span>  – desenvolvido pela Atlassian, é uma ferramenta de CI/CD que se integra bem com outros produtos Atlassian, como Jira e Bitbucket;
- <span style="color:red">GitHub Actions</span>  – é uma plataforma integrada diretamente ao GitHub para automação de fluxos de trabalho, incluindo CI/CD;
- <span style="color:red"> Drone</span> – é uma plataforma de CI/CD leve e flexível que pode ser executada como um contêiner Docker.

## <span style="color: #1E90FF">■ Ferramentas de CD</span>
- <span style="color:orange">Docker:</span> Embora o Docker não seja estritamente uma ferramenta de Continuous Delivery, é uma parte fundamental do processo de entrega moderna. Ele é usado para encapsular aplicativos em contêineres, garantindo que eles sejam executados de maneira consistente em diferentes ambientes. No contexto de CD, os contêineres Docker podem ser implantados de forma rápida e confiável em ambientes de teste, de pré-produção e de produção, tornando o processo de entrega mais eficiente e consistente.
- <span style="color:orange">AWS (Amazon Web Services):</span> A AWS oferece uma ampla gama de serviços que podem ser integrados ao processo de Continuous Delivery. Por exemplo, o AWS CodePipeline pode ser usado para automatizar a construção, teste e implantação de aplicativos. O AWS CodeDeploy pode ser usado para implantar aplicativos em instâncias EC2 ou em serviços gerenciados, como o Amazon ECS (Elastic Container Service) ou o Amazon EKS (Elastic Kubernetes Service). Além disso, a AWS oferece uma variedade de serviços para monitoramento, como o Amazon CloudWatch, que pode ser integrado ao processo de CD para fornecer insights sobre o desempenho do aplicativo.
- <span style="color:orange">Chef: </span>Trata de automação de infraestrutura que pode ser usada para provisionar e configurar servidores de forma automatizada. No contexto de Continuous Delivery, o Chef pode ser usado para garantir que os ambientes de teste, de pré-produção e de produção sejam configurados de maneira consistente e replicável. Ele pode ser integrado aos pipelines de CD para garantir que as configurações de infraestrutura sejam atualizadas automaticamente junto com o código do aplicativo.
- <span style="color:orange">Azure:</span> Assim como a AWS, a Microsoft Azure oferece uma variedade de serviços que podem ser integrados ao processo de Continuous Delivery. O Azure DevOps oferece recursos para automatizar a construção, teste e implantação de aplicativos, enquanto o Azure Kubernetes Service (AKS) pode ser usado para implantar e gerenciar aplicativos em contêineres Kubernetes. Além disso, o Azure Monitor fornece recursos avançados de monitoramento e alerta que podem ser integrados ao processo de CD para garantir que os aplicativos sejam entregues com alta qualidade e desempenho.
- <span style="color:orange">Nagios:</span> Nagios é uma ferramenta de monitoramento de infraestrutura de código aberto que ajuda a detectar e resolver problemas de rede e sistemas. Embora não seja diretamente uma ferramenta de Continuous Delivery, o Nagios pode ser integrado aos pipelines de CD para fornecer feedback em tempo real sobre a integridade e o desempenho dos sistemas durante o processo de entrega.
- <span style="color:orange">Splunk:</span> plataforma de análise de dados que permite coletar, indexar e visualizar logs e métricas de aplicativos e infraestrutura. No contexto de Continuous Delivery, o Splunk pode ser usado para monitorar e analisar o desempenho dos aplicativos em tempo real, identificando problemas e gargalos que podem afetar a entrega.
- <span style="color:orange">Terraform:</span> uma ferramenta de infraestrutura como código que permite provisionar e gerenciar recursos de infraestrutura de forma automatizada e declarativa. No contexto de Continuous Delivery, o Terraform pode ser usado para definir e versionar a infraestrutura necessária para executar aplicativos, garantindo que os ambientes de implantação sejam consistentes e replicáveis em todos os estágios do pipeline de entrega.
---
---
# SCRIPTS DE CONSTRUÇÃO E AUTOMAÇÃO(gitHub)

![[Pasted image 20240618222905.png|500]]
## <span style="color:aquamarine">ISSUES</span>
- ABA DE TAREFAS
## PULL REQUESTS
- VÁRIOS CODIGOS PARALELOS E VC QUER UNIR TODOS EM UM SÓ
##  ACTIONS
- Processos que rodam quando vc está fazendo uma construção
- POde criar uma porcessoas como eventos, estatus
---
---
# 🌚Testes automatizados e garantia de qualidade
![[Pasted image 20240618223040.png|500]]

---
---
# 🤖Aula plática
porou no 6:08