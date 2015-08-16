title: JavaScript Furtivo | 04 - O Valor dos Tipos de Operadores - Parte 1
date: 2014-04-15 19:17:01
tags: 
	- javascript
	- furtivo
---

![valores, tipos e operadores](http://i.imgur.com/mYXofYh.png)

> Confira os outros artigos da série **JavaScript Furtivo** no final [desta](http://ericdouglas.github.io/2014/04/08/10-javascript-furtivo-apresentacao/) página.

O título do artigo de hoje é uma representação das 3 coisas que iremos aprender: **Valores**, **Tipos** e **Operadores**.

## Tabela de Conteúdo

1. [Tipos de Dados](#tipos-de-dados)
2. [Tipo Number](#number)
3. [Operadores Matemáticos](#operadores-matematicos)
4. [Números Especiais](#numeros-especiais)
5. [Strings](#strings)

<h2><a id="tipos-de-dados">Tipos de Dados</a></h2>

O que fazemos programando computadores é basicamente *manipular* dados. No JavaScript, chamamos esses dados de **valores**. Estes valores são divididos em dois **tipos**:

* **Tipos Primitivos**
	* `number` (números)
	* `string` (sequência de texto)
	* `boolean` (booleanos ou valores de verdade)
	* **Tipos Especiais**: `null` (nulo) e `undefined` (indefinido)

Todos os valores em JavaScript diferentes dos citados acima, são pertencentes ao tipo `object` (objeto). Vejamos quais são eles:

* **Tipos de Objetos**
  * arrays (vetores)
  * funções
  * Date (data)
  * RegExp (expressões regulares)
  * Error

Bom, agora que vimos teoricamente os tipos de dados em JavaScript, vamos perceber tudo isso de forma **real**. Para isso, você deverá abrir o console do seu navegador (no Google Chrome você pode usar o atalho `ctrl shift j`.

Dentro da seção *console* existente nas *ferramentas do desenvolvedor*, você deverá digitar os comandos abaixo, para perceber que tudo isso que te falei ali em cima é verdade. O resultado esperado está indicado na frente da seta `->`. Caso o resultado não seja o que você conseguiu, certifique-se de ter digitado corretamente o código.

Ah, já ia me esquecendo... **Digite TODO o código, não copie apenas!!! Isso será muito importante para a memorização e internalização dos conceitos.**

**ps**: Não acredite em meus resultados, faça todos os testes! =)

> Quando estamos **dentro** do console, a utilização do comando `console.log()` é desnecessária para visualizar o resultado de uma instrução, pois o resultado da operação sempre é retornado. 
>
> Vamos utilizar o console diretamente apenas para códigos curtos, pois para códigos maiores, iremos rodá-los através de nossa página html, e ai o comando `console.log()` será de grande utilidade.

<div data-gist-id="10434613" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

Olhando o código acima, mais precisamente na parte de *tipos primitivos especiais*, você pode perceber que o *tipo* `null` na verdade é um `object`. Bom, mas por que isso?

Essa peculiaridade do JavaScript na verdade é um *erro* dos primóridios da linguagem que foi herdado pela ECMAScript. Teremos um tópico específico mais a frente para explicar essa questão.

Vamos ver agora no nosso console os tipos existentes de objetos.

<div data-gist-id="10564803" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

Muito bom! Agora já conhecemos **todos** os tipos de dados do JavaScript! Você pode parar um pouco para respirar e beber uma água, pois a partir de agora iremos aprofundar um pouco em cada *tipo primitivo de dados* que acabamos de ver. Os *tipos de objetos* são mais complexos, e por isso cada um terá um artigo próprio (no mínimo)...

<h2><a id="number">Number</a></h2>

Representamos números no JavaScript da mesma forma que escrevemos no nosso dia a dia. `var numero = 13` é a forma que dizemos no JavaScript que a variável `numero` receceu o valor `13`.

Números fracionários são representados com um ponto, ficando assim a representação: `var numero = 1.3`.

Quando tivermos trabalhando com um número muito grande ou muito pequeno, usamos notação científica através da letra `e`, ficando nosso código, no caso, assim: `1.313e13` que é igual a **1.313 x 10¹³**. 

Cálculos com números inteiros menores que *9 quadrilhões* são garantidos de sempre serem precisos, porém não se pode dizer o mesmo para números fracionários, que devem ser tratados como **aproximações**.

<h2><a id="operadores-matematicos">Operadores e Operações</a></h2>

Agora que conhecemos um pouco mais sobre os números no JavaScript, vamos aprender a utilizar alguns operadores para então fazer alguns cálculos com estes números.

Temos os 4 operadores matemáticos básicos representados no JavaScript da seguinte forma:

* `+`: efetua a adição de dois números (ou concatenação, no caso de strings);
* `-`: efetua a subtração de dois números;
* `*`: efetua a multiplicação de dois números;
* `/`: efetua a divisão de dois números;
* `%`: efetua a divisão entre dois números, e retorna o **resto** da divisão.

Agora que já conhecemos os números e operadores, vamos brincar um pouco no console. Digite as operações abaixo e confira se o resultado é o mesmo do indicado no comentário.

<div data-gist-id="10758049" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

<h2><a id="numeros-especiais">Números Especiais</a></h2>

Temos três tipos de números que não se comportam como números. `Infinity`, `-Infinity` e `NaN`. Os dois primeiros são gerados quando tentamos dividir algum número por zero, e o outro, **N**ot **a** **N**umber (`NaN`), surge quando há uma coerção de tipo de string para number, no caso, mal sucedida, pois a string não pode ser convertida em um número *de fato*.

Vamos ver como surgem estes números! De volta ao console! =)

<div data-gist-id="10761538" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

**ps**: Uma particularidade do `NaN` é que ele é o único valor em JavaScript que **não é** igual a ele mesmo. Como verificar isso? A **melhor** forma para saber se uma variável está com valor `NaN` é testando se ela é igual a ela mesmo (ou diferente).

Se você comparar a variável `A` com ela mesmo e o resultado for `false`, logo, `A` é igual a `NaN`. Vamos dar uma olhada mais de perto:

<div data-gist-id="10764201" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

Você poderia também verificar se uma variável está com o valor `NaN` usando o método `isNaN()`, porém o mesmo apresenta alguns comportamentos inesperados por fazer coerção dos valores para o tipo *number*. Veja mais [aqui](https://gist.github.com/kitcambridge/1086528).

<h2><a id="strings">Strings</a></h2>

Este é o tipo de dados básico usado para representação de texto. Para o programa identificar uma string, tal deve estar contida entre aspas duplas ou simples, assim:

* `"isso é uma string"` e
* `'isso também é uma string'`

**ps**: Geralmente, usamos aspas simples no JavaScript e aspas duplas no HTML.

Você pode colocar tudo dentro de uma string, mas alguns caracteres precisam ser colocados com uma certa atenção, como aspas, quebras de linha, tabulação entre outros, e toda a string deve ser escrita como uma simples expressão, apesar de poder ser escrita em várias linhas de código, como será demonstrado logo mais.

Para fazer o *escape* dos caracteres especiais, utilizamos o símbolo da barra invertida `\`. Esse sinal nos diz que temos algum caractere com significado especial na frase.

Vamos praticar um pouco essa "teoria das cordas".

<div data-gist-id="10772969" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

**ps**:O caracter `\` quando colocado no fim da linha, permite que você continue a string de outra linha. Isso é útil para formatação do código, melhorando a sua legibilidade. Use a forma que for mais conveniente e agradável para você.

Vamos encerrar esta primeira etapa por aqui, para que não fique muita informação de uma só vez. No próximo artigo iremos ver mais sobre operadores, booleanos, coerção de tipo e mais algumas coisas.

Até a próxima! =)

> Veja o próximo artigo [#05 - O Valor dos Tipos de Operadores - Parte 2](http://ericdouglas.github.io/2014/04/19/14-javascript-furtivo-o-valor-dos-tipos-de-operadores-parte-02/)