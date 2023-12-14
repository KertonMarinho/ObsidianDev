## <span style="color:yellow">Framework jquery Mobile</span>
- Framework Javascript
- Semelhante ao seu equivalente desktop
- Permite a criação de sites e aplicativos multiplataforma com Html5
- Os dispositivos são divididos em três nomenclatura:
	- A- Dispositivo que tem suporte total às funcionalidades desenvolvidas pelo framework
	- B- Dispositivos que têm suporte pleno, menos em Ajax
	- c- Dispositivos que têm apenas disponibilidade para as funcionalidades básicas
- Para utilizar o jQuery Mobile, não é necessário realizar nenhuma instalação. Para desenvolver utilizando esse framework é necessário somente criar na marcação HTML uma referência à biblioteca jQuery, outra referência ao arquivo JavaScript do framework, e outra referência para as folhas de estilo padrão do framework.
- ---
![[Pasted image 20231106223012.png]]

---
# <span style="color:yellow">API</span>
- Application programming Interface
- Interface de Programação de Aplicações
- APIs são um conjunto de ferramentas, definições e protocolos para criação de aplicações de software.
![[Pasted image 20231106223632.png|500]]
---
## <span style="color:red">IHC MOBILE FIRST</span>
- São os projetos web priorizam a usabilidade em dispositivos móveis
- Do design até o desenvolvimento das funcionalidades, tudo é planejado primeiro para o uso mobile e depois adaptado para o desktop.
---
#  <span style="color:#32CD32">ANDROID</span>
- SO móvel open source
- arquitetura baseada na versão 2.6 do kernel linux
- Atualmente a responsabilidade do desenvolvimento das novas versões do Android foi transferida para Open Handset Alliance(OHA), é um consórcio de grandes empresas com o objetivo de popularizar e melhorar os dispositivos móveis
- SDK é o kit de desenvolvimento do Android, utilizando o Intellij IDEA
---
#### Camada do desenvolvimento do Android
![[Pasted image 20231107215425.png]]

---
# <span style="color:red">IOS</span>
- Iphone Operation System
- baseado no SO MAC OS X e projetado para atender às necessidades de aparelhos móveis desenvolvido pela Apple
![[Pasted image 20231107220046.png|500]]
- Kit de desenvolvimento Xcode 5 e IOS 7 sdk, utilizando a linguagem swift
--- 
# <span style="color:yellow">NativeScript</span>
- NativeScript é uma estrutura de código aberto para o desenvolvimento de aplicativos móveis nas plataformas Apple iOS e Android originalmente projetado e desenvolvido pela Progress. NativeScript e todos os plug-ins necessários são instalados usando o gerenciador de pacotes npm. 
- Os aplicativos são desenvolvidos, configurados e compilados por meio da linha de comando ou de uma ferramenta GUI chamada NativeScript Sidekick. 
- Interfaces de usuário independentes de plataforma são definidas usando arquivos XML.
- O NativeScript usa então as abstrações descritas nos arquivos XML, o qual chama os elementos nativos da interface do usuário de cada plataforma
- ---
# <span style="color:aquamarine">Mobile first</span>
- Ele foi criado por Luke Wroblewski (Diretor de Produto do Google) em 2011, ao publicar o livro Mobile first (em tradução livre, “Dispositivos móveis em primeiro lugar”). Ele propôs criar um site pensado primeiro em mobile, para depois ajustá-lo para o computador
---  
# <span style="color:#32CD32">Camada de abstração de hardware</span> 
- A camada de abstração de hardware (HAL) fornece interfaces padrão que
deixam disponíveis as funcionalidades de hardware do dispositivo para a estrutura do Java API de maior nível. A HAL é formada por módulos de bibliotecas, que têm a capacidade de implementar uma interface para um tipo específico de componente de hardware, como um módulo de câmera ou Bluetooth. Quando um framework API
faz uma chamada para acessar o hardware do dispositivo, o
sistema Android carrega o módulo da biblioteca específica para este componente de hardware.