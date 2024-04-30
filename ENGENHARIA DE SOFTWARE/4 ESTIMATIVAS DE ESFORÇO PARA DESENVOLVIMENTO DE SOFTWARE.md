# ANÁLISE DE PONTOS DE FUNÇÃO

- Técnica de medição do tamanho de um software
- Possibilita estimar o esforço para implementação do sistema
- Tem por definição medir o que o software faz, e não como foi construído
- "Um ponto de função deve ser entendido como uma unidade de medida que procura definir o tamanho de um aplicativo(software), independentemente de como possa ser produzido e implementado."
- A ideia central é que esteja respaldada nos requisitos lógicos dos usuários.
- Possui seis etapas:
![[Pasted image 20240429215922.png]]
----
# <span style="color:yellow">1°- Determinar o tipo de contagem</span>
### <span style="color:#00FA9A">■ Projeto de desenvolvimento:</span>
- Contagem de pontos de função associados à criação de um novo projeto
### <span style="color:#00FA9A">■ Projeto de melhoria:</span>
- Contagem de pontos de função de funções adicionadas, modificadas ou elimindas em um projeto existente
### <span style="color:#00FA9A">■ Aplicação:</span>
- Contagem de pontos de função de um projeto finalizado
---
## <span style="color:yellow">2°- IDENTIFICAR O ESCOPO DE CONTAGEM E A FRONTEIRA DA APLICAÇÃO</span>
- Identificar o escopo refere-se a determinar se a contagem estará concentrada em um ou mais sistemas ou mesmo em parte de um sistema
- A fronteira da aplicação aponta que ela estabelece um divisor entre os componentes do aplicativo e os componentes de outros aplicativos
---
# <span style="color:yellow">3°-CONTAGEM DAS FUNÇÕES</span>

## <span style="color:#00BFFF">■ Funções tipo dados:</span>
- Funcionalidades fornecidas para o armazenamento de dados da aplicação, podendo ser mantidos dentro ou fora dela
	✔Arquivos lógicos internos(ALI): mantidos dentro da fronteira da aplicação
	✔Arquivos de interface externa(AIE): mantidos fora da aplicação ou lidos de outra
![[Pasted image 20240429222646.png]]
- Depois de calcular a complexidade das funções tido dados calculamos os pontos de função:
![[Pasted image 20240429223513.png]]