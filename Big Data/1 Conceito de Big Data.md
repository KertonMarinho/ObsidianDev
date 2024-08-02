# <span style="color:orange">Big Data</span>

- É o conjunto de práticas e técnicas que envolvem a coleta e análise de imensos volumes de dados confiáveis e variados com a velocidade necessária para a extração de informações valiosas.

## <span style="color:aquamarine">Obtenção dos dados</span>
- Dados internos
- Dataficação
- Dados de sensores 
- Dados de fontes externas

##  <span style="color:#32CD32">Armazenamento</span> 
- Escalabilidade
- Disponibilidade
- Flexibilidade
---
## <span style="color:red">NoSQL</span> 
- Dados semiestruturados ou não estruturados
- Bancos de dados não relacionais:
	- chave-valor
	- Documentos
	- Colunas
	- Grafos

----
## <span style="color:violet">Escalabilidade</span> 
- Aumentar a capacidade de processamento
- Escalabilidade vertical
- Escalabilidade horizontal

## <span style="color:yellow">HADOOP</span>
- Sistema framework de big data
- Baixo custo
- Escalabilidade
- Tolerância a falhas(partição)
- Balanceamento de carga
- Comunicação entre máquinas 
- Alocação de máquinas
- Tecnologias distribuídas
	- HDFS (armazenamento)
	- MapReduce (processamento)
- Processamento em tempo real
	- Baixa latência
	- Consistência
	- Alta disponibilidade

## <span style="color:yellow">SPARK</span>
- Surgiu para complementar o Hadoop
- Spark Core
- Graphx
- Spark SQL
- Mlib
- Componentes Spark:
	- Driver program
	- CLuster manager
	- Woekers
---
## <span style="color: #1E90FF">Processo de análise de dados</span>
1. Entendimento do negócio
2. Compreensão dos dados
3. Preparação dos dados
4. Modelagem dos dados
5. Avaliação do modelo
6. Utilização do modelo

## <span style="color:#00FA9A">Visualização de dadso</span>
- Visualização exploratória
- Visualização explanatória
### <span style="color:violet">Processo de visualização de dados</span> 
1. Aquisição
2. Estruturação
3. Filtragem
4. Mineração
5. Representação
6. refinamento
7. Interação

---
# AULA PLÁTICA
#  <span style="color:#32CD32">Instalando o Hadoop</span> 
- Instala na página oficial
![[Pasted image 20240731224234.png|300]]
``Mais indicados para profissionais experientes
### Uma forma mais fácil seria instalar:
- Google Cloud Plataform com o Hadoop
![[Pasted image 20240731224430.png|300]]
- Outr opção seria Microsoft Azure
![[Pasted image 20240731224550.png|300]]
- Ou Amazon Web Services
![[Pasted image 20240731224659.png|300]]
- Hortonworks Data Plataform
![[Pasted image 20240731224853.png|300]]
``Gratuito

---
## <span style="color:#FF4500">HortonWorks Data Plataform</span>
- O que será instalado:
	- Imagem Hadoop pré-instalado (sandbox)
- Três versões:
	- Virtualbox, VMWare, Docker
	- Network: Bridge Adapter
- Passos:
1. Instale Cloudera
![[Pasted image 20240801220541.png]]
2. Selecione para fins acadêmicos:
![[Pasted image 20240801220639.png]]
3. Abre o oracle vm virtualbox
![[Pasted image 20240801221008.png]]
4. Importar o arquivo hadoop
![[Pasted image 20240801221108.png]]
![[Pasted image 20240801221143.png]]
demorar um pouco para instalar:
![[Pasted image 20240801225400.png]]
![[Pasted image 20240801225451.png]]
# parou no -22:L20
instale o hadoop no oracle