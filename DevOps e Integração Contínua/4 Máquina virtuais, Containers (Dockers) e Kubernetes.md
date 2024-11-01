#devops #terraform #nuvem
#  🤖MÁQUINAS VIRTUAIS E SUA UTILIDADE EM DEVOPS
## <span style="color:orange">■ Máquinas virtuais de Tipo 1(Bare Metal)</span>
- Essa VMs são executadas diretamente sobre o hardware, sem a necessidade deum sistema operacional hospedeiro. O hipervisor age como um sistema operacional dedicado para gerenciar a execução das VMs. Isso resulta em melhor desempenho e eficiência, sendo comumente utilizado em ambiente de produção e servidores
## <span style="color:red">■ Máquinas virtuais do tipo 2(Hospedeiras)</span> 
- Essas VMs são executadas sobre um sistema operacional hospedeiro convencional. Um aplicativo de virtualização é responsável por gerenciar as VMs, e o sistema operacional hospedeiro executa tarefas essenciais
- Embora sejam mais fáceis de configurar e usar, as VMs de tipo 2 geralmente tem um desempenho inferior em comparação com as de tipo 1 e são mais adequadas para ambientes de desenvolvimento e testes
![[Pasted image 20240620222058.png|500]]
![[Pasted image 20240620222133.png]]

---
---
# 👽Contêiner: introdução ao Docker
- Contêiners são ambientes leves e isolados que encapsulam uma aplicação e suas dependências. Eles proporcionam consistência entre diferentes ambientes de desenvolvimento, teste e produção, eliminando as divergências que podem surgir devido a diferenças nos sistemas operacionais ou configurações.
- Um conceito representa um ambiente isolado para o seu código, caracterizado pela ausência de conhecimento sobre o sistema operacional ou os arquivos do host.
![[Pasted image 20240620223040.png|400]]
---
## <span style="color: #1E90FF">■ Docker-Definição</span>
- Uma imagem do Docker consiste em sistemas de arquivos sobrepostos, sendo a base um sistema de arquivos de inicialização, chamado bootfs, semelhante ao típico sistema de arquivos de inicialização do Linus/Unix. Normalmente, os usuários do Docker não interagem diretamente com o sistema de  arquivos de inicialização. Após a inicialização de um contêiner, ele é movido para a memória e o sistema de arquivos de inicialização é desmontado para liberar a RAM usada pela imagem do disco(Docker, 2019)
![[Pasted image 20240620223932.png|400]]
---
---
# 😶‍🌫️Contêiners  x máquinas virtuais
![[Pasted image 20240620224443.png]]
# <span style="color:#00BFFF">■ Vantagens e desvantagens</span>
- Os contêiners proporcionam mais agilidade
- Os contêiners economizam no licenciamento de VM
![[Pasted image 20240620224746.png|500]]
![[Pasted image 20240620224921.png]]

---
---
# 👾Orquestação com Kubernetes

## <span style="color:#40E0D0">■ YAML</span>
A YAML (YAML Ain't Markup Language) é um formato de serialização de dados legível por humanos e de fácil escrita. Comumente utilizado para configurações e descrições de dados hierárquicos, o YAML utiliza espaçamento para definir a estrutura do documento, dispensando o uso de caracteres especiais, como colchetes e parênteses. Sua sintaxe simples e intuitiva o torna amplamente adotado em configurações de software, incluindo a orquestração de containers com ferramentas como Kubernetes. No contexto do Kubernetes, os arquivos YAML são frequentemente empregados para definir configurações de pods, serviços, volumes e outros recursos, proporcionando uma maneira concisa e legível de descrever o estado desejado do sistema.
![[Pasted image 20240620225658.png|400]]
## <span style="color:#FF4500">■ Kubernetes</span>
- Nome em grego significa _timoneiro_ ou _piloto de navio_, _Kubernetes_ é um orquestrador de _containers_ que simplifica o desenvolvimento e a administração de aplicações em ambientes de _containers_. Sem um orquestrador, gerenciar um conjunto de _containers_ pode ser desafiador, exigindo a administração manual de execução, dimensionamento e escalabilidade. O Kubernetes automatiza essas tarefas, gerenciando de maneira eficiente _clusters_ com várias máquinas, destacando-se por sua arquitetura robusta. A estrutura do Kubernetes compreende dois componentes principais: o Mestre, responsável por gerenciar o cluster e manter seu estado desejado, e os Nós (ou trabalhadores), responsáveis pela execução das aplicações. No Mestre, três componentes essenciais se destacam: a API, encarregada de receber e executar comandos; o Scheduler, responsável por determinar onde os Pods (representando cápsulas de containers) serão executados no cluster; e o Controller Manager, que mantém o estado do cluster conforme especificado.
![[Pasted image 20240620230152.png|400]]
![[Pasted image 20240620230307.png|500]]

---
---
# 🦖Escalabilidade e distribuição com contêiners

# <span style="color:yellow">■ IAC</span>
- Código para gerar infraestrutura
![[Pasted image 20240623213525.png]]

# <span style="color:yellow">■ Vantagens e desvantagens</span>
- Com a automatização do provisionamento e da configuração de recursos, a infraestrutura pode ser criada, modificada ou removida rapidamente, reduzindo o tempo de lançamento de novos produtos e serviços.
- Redução de erros: A padronização e a consistência do código, aliados aos testes automatizados, diminuem significativamente a quantidade de erros humanos e a probidade de falhas na infraestrutura
- Versionamento e rastreabilidade: O uso de sistemas de controle de versão, como git, permite rastrear mudanças, identificar problemas e reverter para versões anteriores, facilitando a manutenção e a auditoria
- Escalabilidade e flexibilidade: A automação e a padronização proporcionadas pelo Terraform e IaC facilitam a escalabilidade de recursos e a adaptação a diferenças ambientais, diminuindo a necessidade de intervenção manual e possibilitando o uso de infraestrutura imutável
- Redução de custos: A implementação de Terraform e Iac permite otimizar o uso de recursos, identificar a infraestrutura de acordo com as necessidades específicas de negócios. Isso resulta em economia de custos e maior eficiência operacional
- Segurança e conformidade: A padronização do código e a integração com políticas de segurança garantem a conformidade coma as normas e regulamentações. Além disso, o suo de IaC permite a criação de ambientes isolados, que facilitam a detecção e a correção de vulnerabilidades
---
---

# INSTALAÇÃO E USO  DO DOCKERS
1. Instale o docker normalmente
2. Mostrar os comandos do Docker
```
docker
```
3. No CMD, verifique a versão do docker
```shell
docker --version
```
4. Usar o docker com Hello World
```shell
docker run hello-world
```
![[Pasted image 20240623223246.png]]
5. Mostrar as imagens de docker que já baixou:
```shell
docker image ls
```
![[Pasted image 20240623223502.png]]
6. Parar um container
```shell
docker container stop {ID container}
```
