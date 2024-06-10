>[!ATENÇÃO]
>![[Pasted image 20240609221505.png|500]]
# TABELA HASH

![[Pasted image 20240609221756.png]]
![[Pasted image 20240609221832.png]]
# FUNÇÃO DO EMPREGO DE UMA FUNÇÃO HASH
## <span style="color:orange">■ Array</span>
- Acesso ao dado na memória do array: O(1)
- Busca de um dado no array: depende do algoritmo de busca, pesquisa sequencial O(n)  e pesquisa binária O(logn)

## <span style="color:orange">■ Tabela hash</span>
- Acesso ao dado na memória na tabela: O(1), pois é implementada como um array sequencial
- Busca de um dado na tabela hash: O(1), pois acessa o índice por meio de uma função hash
- Deixamos de precisae fazer uma varredura no array e tornamos o acesso ao dado independente do tamanho conjunto de dados

# IMPLEMENTAÇÕES EM LINGUAGENS DE PROGRAMAÇÃO

- C++, Container associativo Map
- Java, classe HashMap
- Python, dicionário (dict)

## <span style="color: #1E90FF">■ Relebrando Dicionário em python</span> (relembrando)

```python
#Cria o dicionário
caderno = dict()
#atribui dados ao dicionário
caderno['kiwi'] = 3.12
caderno['abacaxi'] = 1.97
caderno['banana'] = 2.65
caderno['uva'] = 6.99

#imprime o dicionário mapeado: chaves:valores
print(caderno)

#imprime somente o valor da chave banana
print(caderno['banana'])

#imprime todas a chaves
for fruta in caderno.keys():
    print(fruta)
```
![[Pasted image 20240609223040.png]]
## <span style="color:orange">OBS:</span> Não iremos trabalhar com estruturas de hash prontas igual acima na linguagem de programação, iremos apreender a construir uma do zero

## <span style="color:brown">■ Aplicação  de Hash</span>
- Podemos manter um rastreamento de jogadas efetuadas por jogadores em jogos como xarez, damas ou diversos outros jogos com alta quantidade de possibilidades
- Aplicações voltadas para segurança, como criptografia  e autenticação de mensagens e assinatura digital, empregam hashs
- A estrutura de dados-base que permite as populares criptomoedas, como bitcoin, operarem são hashs.
- Elas trabalham com cadeias de hashs altamente complexas para manipular transações, oferecendo segurança e descentralização das operações
---
---
# FUNÇÃO HASH
