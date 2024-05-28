- Um algoritmo recursivo é uma função que possui chamadas a si mesmo para a resolução de problemas.
- Muitos algoritmos recursivos tem como principio a sua divisão em partes menores
- Se o problema em questão é pequeno, então, deve ser resolvido diretamente.
- Se problema em questão é grande, deve ser reduzido em problemas menores de mesma, aplicando-se o método sucessivas vezes até a solução do problema.

# <span style="color:yellow">EXEMPLO: FATORIAL</span>

##  <span style="color:#32CD32">■ Maneira interativa(laço de repetição)</span> 
```python
def fatorial iterativo(n):
	FAT = 1 #inicio vairavel local(menor valor fatorial é 1)
	if n < 0:
		return None #Para tirar resultados menor que zero
		elif n == 0 or n ==1:
		return fat # n for igual a zero ou um retorne logo 1(valor fatorial de 1,0)
	else:
		for i in range(1, n+1):
			fat *= i
		return fat
print(fatorial(5)) #resultado: 120
```
## <span style="color:red">■ Maneira recursiva</span> 
```python
def fatorial recursiva(n):
	FAT = 1 #inicio vairavel local(menor valor fatorial é 1)
	if n < 0:
		return None #Para tirar resultados menor que zero
		elif n == 0 or n ==1:
		return fat # n for igual a zero ou um retorne logo 1(valor fatorial de 1,0)
	else:
		return n * fatorial_recursiva(n-1) #Função que chama ela mmesma!
		
print(fatorial_recursiva(5)) #resultado: 120
```
`` Primeiro a função fatorial_recursiva roda ate chega no 1(nestea caso 5x) depois que ela sobe e  começa multiplicar. A função faz a pilha ate chegar na fatorila 1 e depois desenpilhando e fazendo  calculo de multiplicação até chegar o resultado 120``
```
n=5 5-1
n=4 4-1
n=3 3-1
n=2 2-1
n=1 depois ela desempilha:
return 2 * 1
return 3 * 2
retur  4 * 6
return 5 * 24
return 120
```
- O sistema cria uma pilha para armazenamento das variáveis e dos valores retornados por funções recursivas.
- A primeira função chamada é a primeira a entrar na pilha e a última a sair.
>[!info]
>Ver aula de recursividade(estrutura de dados_aula 1)
