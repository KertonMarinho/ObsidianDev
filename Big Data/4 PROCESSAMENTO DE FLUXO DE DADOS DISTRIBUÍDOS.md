# FERRAMENTAS ANALÍTICA DE BAIXA LATÊNCIA
### Aqueles que conseguem processar mais rapidamente que a chegada de novos dados

## <span style="color:salmon">■ Arquitetura Lambda</span> 
- Marz Warren (2015)
- Processamento em lotes
- Processamento de fluxo de dados
- Batch layer (camada em processamento em lote)
- Serving Layer (camada de serviços)
- Speed layer (camada que realiza o processamento da dados quase instânraneo)

## <span style="color:#40E0D0">■ Propriedade de sistemas big data</span>
- Robustez e tolerância a falhas
- Escalabiliade
- Generalização
- Consultas ad hoc
- Manutenção mínima
- Debuggability
![[Pasted image 20240813222129.png|500]]
---
---
# Kafka
- Plataforma de processamento de fluxo de dados
- Fundação Apacha
- Alta capacidade e baixa latência
- Fila de mensagens
## <span style="color:#40E0D0">■ Característica centrais do Kafka</span>
- Publicação e inscrição
- Armazenamento durável e tolerante a falhas
- Processamento em tempo real

## <span style="color:#8A2BE2">■ Cluster Kafka(componentes)</span>
- Eventos
- Tópicos
## <span style="color:red">■ Kafka como um...</span> 
- Sistema de mensagens
- Sistemas de armazenamento
- Sistemas de processamento de fluxos
![[Pasted image 20240813223631.png]]
![[Pasted image 20240813223730.png]]

---
---
# ░ Flume
- Projeto Apache
- Hadoop
- LOg
- Distribuído, confiável e da alta disponibilidade
- Coletar, agregar e mover grandes quantidades de dados
![[Pasted image 20240813224018.png]]
## <span style="color: #00FF00">■ Componentes Flume</span> 
- Eventos
- Source
- Channel
- Sink
- Runners
- Agente
- Provedor de configuração
- Cliente
![[Pasted image 20240813224327.png]]
![[Pasted image 20240813224505.png]]
- resultados:
![[Pasted image 20240813224619.png]]
---
---
# ¤ Storm

