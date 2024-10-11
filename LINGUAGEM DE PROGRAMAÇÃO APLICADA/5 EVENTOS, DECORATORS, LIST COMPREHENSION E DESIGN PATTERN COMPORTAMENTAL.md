# <span style="color:orange">EVENTOS DE TECLADO:</span>
- Para fazer interrupções de teclado em Python, utiliza-se a ``biblioteca keyboard``
- Esta requer permissões de acesso ao teclado, que pode variar dependendo do SO

## <span style="color:yellow">EVENTOS DE TEMPO</span>
- Para criar eventos de timer em Python sem bloquear a execução do programa, uma alternativa é usar a ``biblioteca Sched``
- Fornece recursos para agendar e executar funções em momentos específicos ou após determinados intervalos de tempo
`` para para de monitorar o evento crlt+f2
![[Pasted image 20241007214013.png]]``OBS:no import tem que instalar as bibliotecas
![[Pasted image 20241007214106.png]]
> [!SUMMARY] schuduler
> `scheduler.enter(intervalo, 1, agendar_evento, (scheduler, intervalo, mensagem))`:
>**Parâmetros:**
>- `intervalo`: O tempo (em segundos) até que o evento ocorra. 
>- `1`: A prioridade do evento (quanto menor o número, maior a prioridade).  
>- `agendar_evento`: A função que será chamada quando o tempo especificado (`intervalo`) passar.
>- `(scheduler, intervalo, mensagem)`: Argumentos passados para a função `agendar_evento`

---
# DECORATORS
- São funções para modificar ou estender a funcionalidade de funções ou classes sem precisar alterar o seu código interno
- Os Decorators são implementadas usando a sintaxe do @
- Existem dois tipos principais de decorators em python
	- Decorators de função
	- Decorators de classe
## <span style="color: #1E90FF">Decorators de função</span>
- São aplicados a funções individuais e permitem adicionar funcionalidades extras antes, depois ou ao redor da função decorada
```python
# Definindo o decorator para medir o tempo de execução

def medir_tempo(funcao):
    def wrapper(*args, **kwargs):
        inicio = time.time()
        resultado = funcao(*args, **kwargs)
        fim = time.time()
        print(f"A função '{funcao.__name__}' demorou {fim - inicio:.6f} segundos para ser executada.")
        return resultado
    return wrapper
# Aplicando o decorator usando o símbolo @

@medir_tempo
def exemplo_funcao(tempo_espera):
    time.sleep(tempo_espera)
    print("A função foi executada.")

@medir_tempo
def exemplo_funcao2(tempo_espera):
    time.sleep(tempo_espera)
    print("A função foi executada.")
    
# Chamando a função decorada
exemplo_funcao(2)
exemplo_funcao2(4)
```
## <span style="color:yellow">Decorators dde classe</span>
- Os decorators de classe são aplicados a classes inteiras e permitem modificar ou estender o comportamento da classe
```python
# Tema 2 part3
# Definindo o decorator de classe
class Carro:
    def __init__(self, classe_decorada):
        self.classe_decorada = classe_decorada
    def __call__(self, *args, **kwargs):
        # Instancia a classe original
        instancia_classe = self.classe_decorada(*args, **kwargs)
        # Adiciona o atributo extra
        instancia_classe.num_rodas = 4
        return instancia_classe

# Aplicando o decorator de classe usando o símbolo @
@Carro
class Automovel:
    def __init__(self, modelo):
        self.modelo = modelo

# Criando uma instância da classe decorada
new_auto = Automovel('Gol')

# Chamando o método da classe e exibindo o atributo extra
print(new_auto.modelo)
print(new_auto.num_rodas)
```

---
# COMPREENSÃO DE LISTA(LIST COMPREHENSION)
É UMA MANEIRA DE ESCREVER COM MENOS LINHA DETERMINADO CÓDIGO
- Permite criar uma nova lista a partir de uma expressão ou iteração em uma única linha
	- Caso com somente uma condição
![[Pasted image 20241007222139.png]]
- Caso com somente uma condição
![[Pasted image 20241007222319.png]]

---
# Padrão de design de comportamental (Mediator)
O design pattern mediator é utilizado quando você tem um conjunto de objetos que precisam se comunicar entre si, mas quer evitar que eles se comuniquem diretamente, promovendo um acoplamento fraco entre eles.
- Útil quando você tem vários componentes que precisam se comunicar entre si de forma desacoplada
- Gerência as interações entre os componentes, promovendo a baixa dependência
```python
class TorreDeControle:
    def __init__(self):
        self.avioes = []
        
    def adicionar_aviao(self, aviao):
        self.avioes.append(aviao)
        aviao.registrar_torre(self)

    def enviar_mensagem(self, aviao, mensagem):
        print(f"Torre de controle para {aviao.nome}: {mensagem}")
        for outro_aviao in self.avioes:
            if outro_aviao != aviao:
                outro_aviao.receber_mensagem(aviao, mensagem)

class Aviao:
    def __init__(self, nome):
        self.nome = nome
        self.torre = None

    def registrar_torre(self, torre):
        self.torre = torre

    def enviar_mensagem(self, mensagem):
        self.torre.enviar_mensagem(self, mensagem)

    def receber_mensagem(self, aviao, mensagem):
        print(f"{self.nome} recebeu uma mensagem de {aviao.nome}: {mensagem}")

# Criando a torre de controle
torre_de_controle = TorreDeControle()

# Criando os aviões
aviao1 = Aviao("Aviao 1")
aviao2 = Aviao("Aviao 2")
aviao3 = Aviao("Aviao 3")

# Adicionando os aviões à torre de controle
torre_de_controle.adicionar_aviao(aviao1)
torre_de_controle.adicionar_aviao(aviao2)
torre_de_controle.adicionar_aviao(aviao3)

# Enviando mensagens entre os aviões
aviao1.enviar_mensagem("Vamos decolar!"
aviao2.enviar_mensagem("Confirmado, prontos para decolar.")
aviao3.enviar_mensagem("Aguardando autorização para decolar.")
```

---
# PADRÃO DE DESIGN DE CRIACIONAL OBSERVADOR
O design pattern observer é usado quando você tem um objeto (o "sujeito" ou "observável") que precisa notificar outros objetos (os "observadores") sobre mudanças em seu estado. É como se você estivesse sintonizando (se inscrevendo) em uma estação de rádio para ouvi-la.
```PYTHON
class Mensageiro:
    def __init__(self):
        self.observadores = []

    def adicionar_observador(self, observador):
        self.observadores.append(observador)

    def remover_observador(self, observador):
        self.observadores.remove(observador)

    def notificar_observadores(self, remetente, mensagem):
        for observador in self.observadores:
            observador.receber_notificacao(remetente, mensagem)


class Usuario:
    def __init__(self, nome):
        self.nome = nome

    def receber_notificacao(self, remetente, mensagem):
        print(f"[{self.nome}] Nova mensagem de {remetente}: {mensagem}")


class Grupo:
    def __init__(self, nome):
        self.nome = nome
        self.membros = []

    def adicionar_membro(self, membro):
        self.membros.append(membro)

    def receber_notificacao(self, remetente, mensagem):
        print(f"Grupo {self.nome}: Nova mensagem de {remetente}: {mensagem}")


mensageiro = Mensageiro()

# Criando usuários
usuario1 = Usuario("Alice")
usuario2 = Usuario("Bob")
usuario3 = Usuario("Charlie")

# Criando grupos
grupo1 = Grupo("Família")
grupo2 = Grupo("Trabalho")

# Adicionando observadores ao mensageiro
mensageiro.adicionar_observador(usuario1)
mensageiro.adicionar_observador(usuario2)
mensageiro.adicionar_observador(usuario3)

# Adicionando membros ao grupo
grupo1.adicionar_membro(usuario1)
grupo1.adicionar_membro(usuario2)

grupo2.adicionar_membro(usuario2)
grupo2.adicionar_membro(usuario3)

# Enviando mensagens
mensageiro.notificar_observadores("Admin", "Bem-vindos ao nosso aplicativo de mensagens!")
grupo1.receber_notificacao("Admin", "Nova reunião marcada para amanhã.")
usuario3.receber_notificacao("Alice", "Oi, tudo bem?")
```