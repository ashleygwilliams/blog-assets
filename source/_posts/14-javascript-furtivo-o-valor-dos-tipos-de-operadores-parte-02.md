title: JavaScript Furtivo | 05 - O Valor dos Tipos de Operadores - Parte 2
date: 2014-04-19 21:10:01
tags: 
	- javascript
	- furtivo
---

![valores, tipos e operadores](http://i.imgur.com/Mk6vtOi.png)

> Confira os outros artigos da série **JavaScript Furtivo** no final [desta](http://ericdouglas.github.io/2014/04/08/10-javascript-furtivo-apresentacao/) página.

Continuando o último artigo onde falavamos sobre **valores**, **tipos** e **operadores**, veja o que será apresentado hoje, na tabela abaixo. 

## Tabela de Conteúdo

1. [Valores Booleanos](#valores-booleanos)
2. [Valores *Truthy* e *Falsy*](#valores-truthy-e-falsy)
3. [Truques com o Operador `!`](#truques-com-o-operador-de-negacao)
4. [Cuidado com a Falsidade!](#cuidado-com-a-falsidade)
5. [Valores *undefined*](#valores-undefined)
6. [Operadores Unários](#operadores-unarios)
7. [Operadores de Incremento](#operadores-de-incremento)
8. [Operadores de Comparação](#operadores-de-comparacao)
9. [Coerção (ou conversão) de Tipo](#coercao-de-tipo)
10. [Como Evitar a Coerção de Tipo](#como-evitar-a-coercao-de-tipo)
11. [Operadores Lógicos](#operadores-logicos)
12. [Curiosidades sobre os Operadores Lógicos](#curiosidades-sobre-os-operadores-logicos)
13. [Operador Ternário](#operador-ternario)
14. [Regras de Precedência](#regras-de-precedencia)


<h2><a id="valores-booleanos">Booleanos</a></h2>

Esse **tipo** de dado, `boolean`, é bem específico, tendo apenas dois valores possíveis, `true` ou `false` (verdadeiro ou falso). Conseguimos obter estes valores através de operações de comparação (x é maior que y ? A resposta é sempre sim ou não, verdadeiro ou falso no caso) e através de um "truque" utilizando o *operador unário* `!` (mais sobre operadores unários e comparações adiante).

Este operador `!` (negação) inverte o valor passado à ele para um valor booleano oposto ao original. Vou explicar melhor, acompanhe comigo:

Quando aplicamos o operador `!` à uma variável que tenha *realmente* um valor **considerável**, obtemos o valor `false` como retorno desta operação. Mas para ficar mais claro o que é um valor considerável, vou te explicar o que é um valor *descartável*.

<h2><a id="valores-truthy-e-falsy">Valores *Truthy* e *Falsy*</a></h2>

> Agora você já precisa ter os conceitos de **valor**, **tipo** e **operador** em JavaScript bem consolidados. Faça um exercício mental de definir para você mesmo o que cada um é.

Todos os tipos de **valores** em JavaScript têm, intrínsicamente (em sua essência), um respectivo *valor booleano* associado. Estes valores são claramente perceptíveis quando fazemos *comparações* entre valores e quando utilizamos o operador unário de negação `!`.

Valores *falsy* (falsos) são os que tem em sua essência o valor booleano `false`. Estes valores são:

* `false`
* `0` (zero)
* `""` (string vazia)
* `null`
* `undefined`
* `NaN`

Todos os outros valores em JavaScript são considerados *truthy* (verdadeiros). Alguns valores *truthy* peculiares são:

* `"0"` (zero como string)
* `"false"` (false como string)
* `function() {}` (funções vazias)
* `[]` (arrays vazios)
* `{}` (objetos vazios)

<h2><a id="truques-com-o-operador-de-negacao">Truques com o Operador `!`</a></h2>
Agora que sabemos **exatamente** quais valores booleanos cada valor do JavaScript carrega, podemos tranquilamente e **conscientemente** utilizar o operador `!` para obter o valor **contrário** do natural do valor em operação. Vamos aos exemplos, e portanto, **ao console**!:

<div data-gist-id="10958488" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

Um modo interessante de saber qual é o valor *truthy* ou *falsy* de um valor é negando-o duas vezes com o operador `!`. Sim, é como na Matemática, `-1 x -1 = 1`. Então temos que:

<div data-gist-id="10958548" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

<h2><a id="cuidado-com-a-falsidade">Cuidado com a Falsidade!</a></h2>

Iremos ver ainda neste artigo como comparar valores através dos operadores de comparação, mas é importantíssimo que eu lhe explique mais uma última coisa sobre os valores *falsy*.

As regras de comparação entre estes valores é um pouco *não-intuitiva*, logo ter o conhecimento dos valores esperados em determinados casos é crucial na hora de um eventual *bug*. Vamos ver quais são essas peculiaridades.

### `false`, `0` e `""`

Quando comparamos dois destes três valores utilizando o operador `==`, o resultado é sempre `true`. Vamos testar no console o código abaixo:

> **OBS**: Quando utilizamos o console, podemos omitir o sinal `;` (ponto e vírgula) no fim das expressões, pois estamos fazendo apenas um **teste rápido**, porém no seu código JavaScript de fato, **sempre utilize o ponto e vírgula**!!!

<div data-gist-id="10979318" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

### `null` e `undefined`

Os valores `null` e `undefined` somente são equivalentes a eles mesmos. Vejamos:

<div data-gist-id="10980063" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

O último valor falsy que temos para citar é o `NaN`, porém este já foi abordado no artigo anterior, e sabemos que é o **único** tipo de dado em JavaScript que não é igual a ele mesmo.

<h2><a id="valores-undefined">Valores Undefined</a></h2>

Temos definidos no JavaScript dois tipos indefinidos, usados para representar a falta de representatividade de algum dado.

**ps**: O paradoxo da frase anterior é apenas uma brincadeira, pois a definição é muito simples, e vou lhe explicar agora! =)

Como já foi explicado no artigo anterior, na realidade apenas `undefined` é de fato um tipo primitivo de dado, `null` é um tipo de objeto, quando fazemos sua inspeção no console podemos verificar isso.

O valor `undefined` aparece quando declaramos uma variável e não atribuímos a ela nenhum valor. Já o valor `null` é um valor que deve ser atribuído a uma variável, e representa a ausência de valor nesta variável.

Confira os exemplos no artigo anterior na seção [tipos de dados](http://ericdouglas.github.io/2014/04/15/13-javascript-furtivo-o-valor-dos-tipos-de-operadores-parte-01/#tipos-de-dados) para fixar esta diferença.


<h2><a id="operadores-unarios">Operadores Unários</a></h2>

Alguns operadores são *palavras* ao invés de símbolos. Utilizamos um destes operadores muito nos exemplos do artigo anterior, o operador `typeof`, que produz uma string identificando o tipo do valor do elemento que você passou a ele.

**ps**: Para ver o operador `typeof` em funcionamento, volte no [artigo anterior](http://ericdouglas.github.io/2014/04/15/13-javascript-furtivo-o-valor-dos-tipos-de-operadores-parte-01/) onde você encontrará vários exemplos da utilização dele.

Outros operadores unários são `delete` e `void`. Para este material não se tornar muito extenso, você pode procurar o que cada um faz [aqui(delete)](https://developer.mozilla.org/pt-BR/docs/JavaScript/Guide/Expressions_and_Operators#delete) e [aqui(void)](https://developer.mozilla.org/pt-BR/docs/JavaScript/Guide/Expressions_and_Operators#void).

> Operadores unários utilizam **um** valor para fazer seu trabalho, operadores binários e ternários, **dois** e **três** valores respectivamente.

<h2><a id="operadores-de-incremento">Operadores de Incremento</a></h2>

Temos dois tipos de operadores de incremento: os utilizados para números e os utilizados para *strings* e números.

### Incrementando Números

Os operadores `++` e  `--` são utilizados para incrementar variáveis/valores do tipo `number`. São operadores frequentemente utilizados para auxiliar na estrutura lógica do programa, aumentando ou diminuindo em **uma unidade** o valor da variável. A partir do próximo artigo iremos começar a focar em pedaços de código maiores, e assim iniciar a criação de *mini-programas*, para depois chegarmos no nosso objeto de juntar todas essas peças para criarmos o que quisermos. Por agora, vamos ver no console como funcionam estes operadores.

Uma última informação. Estes operadores podem ser utilizados **antes** ou **depois** da variável, sendo assim denominados operadores de **pré-incremento** ou **pós-incremento**. Qual a diferença entre eles? A diferença é que quando utilizamos o operador **antes** da variável, ela será alterada antes da execução do código, então o valor processado para a operação **atual** será o já modificado, e quando usamos o operador **depois** da variável, essa alteração será percebida apenas **depois** quando esta variável for solicitada. 

Vamos aos testes!

<div data-gist-id="11039924" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

### Incrementando Números e Strings

Estes operadores serão utilizados **sempre** por você! São realmente MUITO importantes e elegantes, diga-se de passagem. A função deles é adicionar mais conteúdo a antiga variável mas sem precisar declarar isso de forma *verbosa* (escrevendo mais do que se poderia/deveria). De fato, estes operadores **operam** e **atribuem** o valor para a mesma variável. Ele pode ser utilizado para *somar*, *subtrair*, *multiplicar* e *dividir* números, ou para *concatenar* novas strings em variáveis que contém valores deste tipo.

Vamos dar uma olhada como estes operadores trabalham. `#partiuconsole`

<div data-gist-id="11041498" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

<h2><a id="operadores-de-comparacao">Operadores de Comparação</a></h2>

Operadores de comparação são um dos tipos de *operadores binários*, que no caso, utilizam dois valores para efetuarem a operação. Os operadores de comparação sempre retornam um *booleano*, dizendo se a comparação é verdadeira ou falsa. São também utilizados na estrutura lógica do programa.

Vamos conhecer estes operadores!

`<` : **menor que** - verifica se o número da esquerda é menor que o número/string da direita
`<=` : **menor ou igual que** - verifica se o número da esquerda é menor ou igual ao número/string da direita
`>` : **maior que** - verifica se o número da esquerda é maior que o número/string da direita
`>=` : **maior ou igual que** - verifica se o número da esquerda é maior ou igual ao número/string da direita

#### Cuidado ao Comparar Strings!

A maneira de comparar strings pode não ser muito intuitiva, pois qualquer letra *maiúscula* será sempre **menor** que uma letra *minúscula*.

Vamos confirmar toda essa teoria agora. Já sabé né? Console! =)

<div data-gist-id="11043904" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

### Comparadores de Igualdade

Além dos comparadores mostrados acima, também temos os *comparadores de igualdade*, que são constantemente usados em nossos códigos, porém tem algumas peculiaridades que se você não souber, **certamente** irá gerar erros nos seus programas. Mas fique tranquilo, é bem simples de entender a diferença entre eles, e irei lhe provar agora! Primeiro, vamos conhecer quais são estes outros operadores.

`==`: testa igualdade
`!=`: testa desigualdade
`===`: testa igualdade de forma **restrita**
`!==`: testa desigualdade de forma **restrita**

A grande diferença entre um operador e outro é que a primeira dupla (`==` e `!=`) ao comparar os valores, caso eles não sejam do mesmo **tipo**, procedem com uma particularidade do JavaScript chamada de **Coerção de Tipo** (ou conversão de tipo), e isso pode gerar **muita** dor de cabeça para você. Sério!

Irei explicar sobre coerção de tipo no próximo tópico, mas antes vamos tentar entender pelo código, de forma prática, como cada operador trabalha, e depois irei explicar de forma teórica e encerrar o assunto. Vamos lá!

<div data-gist-id="11093383" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

> Vale ressaltar mais uma vez... Entender o que está acontecendo no código é super importante, e muitas vezes temos que realmente ler várias vezes e/ou ficar vários minutos para conseguir entendê-lo. E sim, isso é algo super importante, não tenha "dó" de **investir** tempo nisso!

Neste próximo tópico irei lhe explicar o que aconteceu no código anterior, então, vamos para o próximo!

<h2><a id="coercao-de-tipo">Coerção de Tipos</a></h2>

O nome assusta um pouco né?! E de fato devemos ter cuidado com isso pois surgem muitas <del>pérolas</del> bugs no seu código a partir deste esforço que o JavaScript faz para efetuar todas as instruções recebidas.

**Sempre** que você usa um operador no JavaScript (no caso então, faz uma operação), você irá receber um valor de retorno, nunca um erro, mesmo que você tente trabalhar com tipos diferentes de dados.

A **coerção de tipos** (ou **conversão** de tipos) é justamente isso! Quando tentamos fazer operações com tipos de dados **diferentes**, o JavaScript nos agracia com a conversão de um dos valores para algum outro tipo... Só que o grande e terrível problema disso é que dificilmente você consegue prever qual será este novo valor, pois as regras para tal conversão **não** são intuitivas, o que pode causar alguma(s) falha(s) em sua aplicação.

<h2><a id="como-evitar-a-coercao-de-tipo">Como Evitar a Coerção de Tipos</a></h2>

Para evitar toda essa preocupação, você **deve** usar os operadores `===` e `!==`, que fazem a mesma verificação de igualdade que seus "primos", porém **NÃO** fazem coerção de tipos!

**ps**: Por questões de segurança, sempre opte por usar os comparadores de igualdade **restrita**.

Parabéns! Agora você finalmente sabe o que é essa bendita *coerção de tipos* e como evitá-la! lol

> Quando algo que não é obviamente um número é convertido para tal, o valor dessa operação é convertido para `NaN`. Portanto, sempre que encontrar `NaN` em seu código, procure por coerções de tipo acidentais.

<h2><a id="operadores-logicos">Operadores Lógicos</a></h2> 

Sempre que pensamos na parte lógica do programa devemos pensar em valores booleanos, e para gerar estes valores booleanos a partir dos valores que nossas variáveis carregam, iremos usar os *operadores lógicos*, que são um tipo de *operador binário*, ou seja, necessitam de dois valores para geração de um terceiro.

**ps**: O operador `!` é um operador lógico pois retorna um valor booleano, porém é uma exceção a regra por ser um operador *unário*.

Conheça agora os operadores lógicos:

* `&&` : este operador é chamado de "**E**" lógico
* `||` : este operador é chamado de "**OU**" lógico
* `!` : este operador é chamado de "**NÃO**" lógico

### `&&` E lógico

Este operador lógico e binário retorna `true` se ambos os valores (ou operandos) forem verdadeiros. Isso no caso será utilizado em estruturas condicionais, assunto que iremos abordar no próximo artigo. Por enquanto você só precisa saber disso.

### `||` OU lógico

Este operador lógico e binário retorna `true` se um dos valores forem verdadeiros.

### `!` NÃO lógico

Como já vimos anteriormente, este operador transforma o operando em booleano, porém com a peculiaridade de inverter seu valor *truthy/falsy* para um booleano de fato.

<h2><a id="curiosidades-sobre-os-operadores-logicos">Curiosidades sobre os Operadores Lógicos</a></h2>

Quando utilizamos os operadores lógicos **fora** de estruturas condicionais, eles tem uma forma peculiar de trabalhar, que vale muito a pena ser entendida para que possamos deixar nosso código mais elegante e conciso.

Sempre que usamos `&&` e `||`, eles convertem o valor do lado esquerdo para um booleano, para saberem qual valor será retornado dessa operação.

### Entendendo o Operador `||`

O operador `||` retorna o valor da sua esquerda quando ele pode ser convertido para `true`, ou seja, quando seu valor é do tipo *truthy*, e sempre retorna o valor da direita caso contrário, independente de qual valor seja esse, até mesmo outro valor *falsy*. Veja isso na prática.

<div data-gist-id="11095317" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

Viram? Mesmo o valor da direita sendo *falsy*, ele é retornado pois a regra é: "se o valor da esquerda for falsy, retorne o da direita sem nem ver qual é". E depois, quando alteramos o valor da esquerda para um valor *truthy*, ele foi retornado. Legal né?! =)

Vamos ver agora o outro operador.

### Entendendo o Operador `&&`

Este operador faz o contrário. Quando o valor da esquerda é *falsy*, ele é retornado, independente de qual valor seja o da sua direita. E o valor da direita **sempre** será retornado quando o da esquerda for *truthy*, mesmo que este valor da direita seja *falsy*. Vamos ver o código para ficar mais claro.

<div data-gist-id="11095652" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

**Muito bom!** Estamos quase terminando, e a essa altura você já sabe de várias peculiaridades do JavaScript! Vamos em frente =)

<h2><a id="operador-ternario">Operador Ternário</a></h2>

Este operador é de fato muito poderoso, pois evita verbosidade no código, deixando-o então bem mais elegante.

Ele é chamado *operador ternário* pois envolve três peças em sua operação. Vamos analisá-lo abaixo. Primeiramente irei mostrá-lo em funcionamento e depois irei explicá-lo.

<div data-gist-id="11096006" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

Como funciona isso? Lhe explico já!

Primeiramente criamos a variável `usuario` e atribuimos uma string vazia a ela. Ou seja, um valor *falsy*. Após isso, usamos o operador ternário que funciona da seguinte forma:

1. Indicamos a variável ou condição que deve ser avaliada. No caso, usamos a variável `usuario`.
2. Este valor a ser analisado será transformado em um booleano, a partir de seu valor *truthy/false* (está vendo a importância da teoria?!)
3. Caso seu valor seja *truthy*, então o operador retorna a instrução **após** o sinal `?`. Caso o valor seja *falsy*, o valor retornado será o que está **após** o sinal `:`.
4. Você pode retornar qualquer expressão JavaScript como valor de retorno dessa avaliação, veja outro exemplo:

<div data-gist-id="11096534" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

Entendeu como funciona? Esse operador é **muito** legal! =D

**ps**: Altere o valor de cozinheiro para `true` e veja o que acontece!

<h2><a id="regras-de-precedencia">Regras de Precedência</a></h2>

Para saber qual operação irá ocorrer primeiro, você precisa conhecer a ordem de precedência dos operadores. Confira abaixo a lista na ordem do maior (no topo) para o menor (embaixo) operador em relação a sua precedência.

* `++`, `--` pré/pós incremento/decremento
* `!` altera valor booleano
* `typeof`, determina o tipo do operando
* `*`, `/` e `%` multiplica, divide e resto
* `+` e `-` soma e subtrai
* `+` concatena strings
* `<`, `<=`, `>` e `>=` comparação de ordem numérica
* `<`, `<=`, `>` e `>=` comparação de ordem alfabética 
* `==` teste de igualdade
* `!=` teste de desigualdade
* `===` teste de igualdade restrita
* `!==` teste de desigualdade restrita
* `&&` E lógico
* `||` OU lógico
* `?:` operador ternário
* `=` atribuição à variável ou propriedade
* `*=`, `/=`, `%=`, `+=` e `-=` operação e atribuição

> Veja mais sobre regras de precendência [aqui](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)

## Conclusão

Finalmente terminamos! Bom, esse foi o maior post até agora, e com certeza foi o mais interessante, por termos visto várias peculiaridades da linguagem JavaScript e termos sedimentado uma base sólida para os capítulos seguintes.

Não perca os próximos episódios! Bons estudos! =D

> Veja o próximo artigo [#06 - Expressões JavaScript](http://ericdouglas.github.io/2014/04/23/15-javascript-furtivo-expressoes-javascript/)