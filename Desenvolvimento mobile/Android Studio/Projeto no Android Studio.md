- Projeto criado e classe MainActivity para edição:
![[Pasted image 20231129215102.png]]
- O próximo passo é adicionar os primeiros componentes ao layout
	- <span style="color:yellow">Arquivo de layout activity_main.xml</span>
![[Pasted image 20231129215358.png]]

# <span style="color:yellow">Layout</span>
- O Android studio apresenta uma visão de design dividida em três partes:
	- <span style="color:orange">Pallete(paleta):</span> Mostra os componentes que podem ser arrastados para a área central
	- <span style="color:orange">Preview(pré-visualização):</span> visão da activity em um dispositivo móvel. Do lado direito um versão simplificada na qual se pode ver apenas os contornos dos componente
	- <span style="color:orange">attributess (atributos):</span> do lado direito, apresenta os atributos do componentes que estiver selecionado na área central
- Além dessa visão de design do arquivo de layout aberto, pode-se escolher visualizar a versão XML do arquivo
- É só clicar na aba TEXT na parte inferior, logo abaixo da paleta de componentes
- Alternar entre as visões Design e Text é um procedimento comum quando se está desenvolvendo o layout de uma activity

# <span style="color:#FF6347">Criando a tela da calculadora</span>
1. Alterar as propriedades do componenes textView que o Android Studio já adicionou no projeto
	 - No quadro das margens do componente em relação ao topo  da tela, clique nas setas de + da esquerda e do topo e configure o valor para 16
	 - Na propriedade text, informe o valor Digite os dois números
	 - Na propriedade textSize, informe o valor 36sp
2. Arrastar um componente LinearLayout(horizontal) da paleta e configurar as propriedades
	- No quadro que representa as margens do componentes, clicar nas setas de + da esquerda, da direita e do topo e configurar o valor para 16
	- Na propriedade layout_height, digite o valor 100 (valor para que o componente seja exibido na tela, sendo alterado mais tarde)
3. Arrastar outro componente linearLayout(horizontal) e configurá-lo do mesmo modo que o anterior
4. Arrastar outro componente textView embaixo dos anteriores e alterar as propriedades
	- Alterar o atributo ID dos componentes para resultadotextView
	- Adicionar as margens do topo, da esquerda e da direita
	- O atributo text deve ficar vazio
	- Altere o atributo textSize para 36sp
![[Pasted image 20231129222607.png]]