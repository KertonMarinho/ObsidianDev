# TÉCNICA DE ANÁLISE DE PONTOS DE FUNÇÃO

- Técnica de medição do tamanho de um software
- Possibilita estimar o esforço para implementação do sistema
- Tem por definição medir o que o software faz, e não como foi construído
> [!SUMMARY] Oliveira Silva
>- "Um ponto de função deve ser entendido como uma unidade de medida que procura definir o tamanho de um aplicativo(software), independentemente de como possa ser produzido e implementado."
>- A ideia central é que esteja respaldada nos requisitos lógicos dos usuários.

## -  Possui seis etapas:
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
---
## <span style="color:#00BFFF">■ Funções tipo Transações:</span>
- Funcionalidades de processamento de dados do sistema
	✔Entradas externas(EE)
	✔Saídas externas(SE)
	✔Consultas externas(CE)

###  <span style="color:#32CD32">➪Entradas externas(EE)</span> 
- Processo elementar que manipula dados ou informações de controle originados fora da fronteira da aplicação
	✔Tem como função manter(incluir alterar ou excluir dados) um ou mais ALI
	
	![[Pasted image 20240430213730.png]]

### <span style="color:#32CD32">➪Saídas externas(SE)</span>
- Processo elementar que envia dados ou informações de controle para fora da fronteira da aplicação
	✔Tem como função apresentar informações ao usuário por meio de lógica de processamento que não seja apenas a recuperação de dados ou informações de controle

### <span style="color:#32CD32">➪Consultas externas(CE)</span>
- Processamento elementar que envia dados ou informações de controle para fora da fronteira da aplicação
	✔TEm como principal intenção apresentar informações ao usuário por meio de uma simples recuperação de dados ou informações de controle de ALIs e/ ou AIEs. A lógica de processamento não deve conter fórmulas matemáticas ou cálculos.
![[Pasted image 20240430214726.png]]

---
# <span style="color:yellow">4°-DETERMINAR A CONTAGEM DAS FUNÇÃO NÃO AJUSTADOS</span>
➪ Total de pontos de função tipo dados
➪ Total de pontos de função tipo transição
➪Soma-se os dois resultados

----
# <span style="color:yellow">5°-DETERMINAR O VALOR DO FATOR DE AJUSTE</span>
##  <span style="color:#32CD32">■ itens de influência</span> 
![[Pasted image 20240430215819.png]]
- Cada item a equipe deve pontuar de 0 a 5 de acordo com a analise da equipe calcule o fator de ajuste:
![[Pasted image 20240430215850.png]]

<span style="color:orange">Exemplo</span>
![[Pasted image 20240430215958.png|500]]

---
# <span style="color:yellow">6°-CALCULAR O NÚMEOR DE PONTOS DE FUNÇÃO AJUSTADOS(AFP)</span>
- Multiplicando o total de pontos não ajustados pelo fator de ajuste

![[Pasted image 20240430220243.png|500]]

---
![[Pasted image 20240430220502.png]]

----
![[Pasted image 20240430220553.png]]

