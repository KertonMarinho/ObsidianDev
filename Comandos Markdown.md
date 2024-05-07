==highlight ==

```
==highlight ==
```

LInks intermos e externos

```
http://obsidian.md - link externo automático !
[obsidian](http://obsidian.md) - Link externo com descrição
[[obsidian]] - Link interno pelo nome
[[obsidian|outro nome]] - link interno com outro nome
```
http://obsidian.md - link externo automático !
[obsidian](http://obsidian.md) - Link externo com descrição
[[obsidian]] - Link interno pelo nome
[[obsidian|outro nome]] - link interno com outro nome


Citações

```
>uma citação é assim
\-alves,rafaeil

```
>uma citação é assim
\-alves, 

Código em uma linha
`print("hello,world")`
# matemática
```
Para escrever equaçoes
dolar simples $1+1=2$
dolar duplos $$\frac{2^2+2^3}{3}$$
obsidian utiliza aformatção mathjax
```
$1+1=2$
$$\frac{2^2+2^3}{3}$$

# tabelas

```
para gerar uma tabela separa cada item com uma barra vertical
|cabeçalho 1|cabeçalho 2 |
|_--------- |------------|
|item 1     | item2      |
```

| cabeçalho 1 | cabeçalho 2 |     |
| ----------- | ----------- | --- |
| item 1      | item2       |     |


|cabeçalho 1|cabeçalho 2 |
|item 1     | item2      |






# Conteúdo embutido como áudio, imagem, vídeo

```
![[cans.png]]
```
# Chamadas

```
para gerar uma chamda utiliza
[!info]
>este é um bloco de chamda
>ele suprote a notaçao *markdown* e [[link internos]].

```

>[!info]
>este é um bloco de chamda
>ele suprote a notaçao *markdown* e [[link internos]]

>[!warning]
>este é um bloco de chamda
>ele suprote a notaçao *markdown* e [[link internos]].

> [!SUMMARY] The Point™
> The point is that you own this folder just like the other folder of camping photos that you created yourself.
> 
> It’s supposed to be a good thing because you get both **data ownership and privacy** this way. Just keep in mind [[#^0f681f|with great power comes great responsibility]].



# Notas de rodape

```
Para gerar nota de rodape utiliza[^1] no texto e [^1]:
para descrever a nota. Lembre-se de que as notas de roda'pe só serão visiveis no modo de visualização
```


nota de rodapem [^1]


[^1]: descrever a nota. Lembre-se de que as notas de roda'pe só serão visiveis[1^1] no modo de visualização


---
## Links

[](https://github.com/mende1/guia-definitivo-de-markdown?tab=readme-ov-file#links)

É possível colocar algum link em seu _'Readme'_, e ainda colocá-lo por debaixo de uma palavra, é o chamado link-âncora, acessando-o ao clicar na palavra. Entre colchetes [ ] a palava que deseja por debaixo dos panos. E entre parentêses ( ) o link para acesso. Vejamos o exemplo do código:

```
Clique [aqui](https://github.com) para acessar à página do GitHub.
```

Resultado: Clique [aqui](https://github.com/) para acessar à página do GitHub.

Lembre-se que pode criar links para outros repositórios seus no GitHub, também é possível acessar outro arquivo no mesmo repositório, e até mesmo a posição da página do leitor no mesmo arquivo. Por exemplo, clique [aqui](https://github.com/gustavo-mendel/guia-definitivo-de-markdown/blob/master/README.md#a-sintaxe-do-markdown) para acessar o título 'Sintaxe' neste mesmo arquivo. Tais possibilidades deixam seu _README_ bem mais apresentável, e com uma interatividade maior, demonstrando que o escritor do código entende bem de _MarkDown_.

Para links sem uma palavra por cima do link, use '< >' para envolver o link desejado, assim o link aparecerá por inteiro ao leitor. Exemplo: [https://google.com.br](https://google.com.br/)

---
## Links em imagens

[](https://github.com/mende1/guia-definitivo-de-markdown?tab=readme-ov-file#links-em-imagens)

Você pode fazer com que uma imagem carregue um link por debaixo dos panos, e ao clicar nela, acesse o link. É uma mescla tanto semânticamente quanto na sintaxe. Vejamos:

```
Clique na imagem para acessar o Google.
[![Logo_Google_2013_Official svg](https://user-images.githubusercontent.com/5532...](https://google.com.br)
```

Clique na imagem para acessar o Google.
Clique na imagem para acessar o Google.
[![Logo_Google_2013_Official svg](https://user-images.githubusercontent.com/5532...](https://google.com.br)

---






