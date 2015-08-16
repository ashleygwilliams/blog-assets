title: JavaScript Furtivo | 06 - Expressões JavaScript
date: 2014-04-23 19:23:01
tags: 
	- javascript
	- furtivo
---

![expressões javascript](http://i.imgur.com/tFOGzAX.png)

> Confira os outros artigos da série **JavaScript Furtivo** no final [desta](http://ericdouglas.github.io/2014/04/08/10-javascript-furtivo-apresentacao/) página.

Estamos de volta com mais um artigo dessa nossa longa jornada, rumo à maestria em JavaScript! Hoje iremos falar exclusivamente sobre **expressões**. Confira um resumo do que será abordado...

## Tabela de Conteúdo

1. [O que é uma Expressão?](#o-que-e-uma-expressao)
1. [Expressões Básicas](#expressoes-basicas)
1. **Expressões "Complexas"**
	* [Expressões de Inicialização](#expressoes-de-inicializacao)
	* [Expressões de Definição](#expressoes-de-definicao)
	* [Expressões para Acessar Propriedades](#expressoes-para-acessar-propriedades)
	* [Expressões de Invocação](#expressoes-de-invocacao)
	* [Expressões de Criação](#expressoes-de-criacao)
1. [Mais Expressões](#mais-expressoes)
	* Expressões Matemáticas
	* Expressões de Relação
	* Expressões Lógicas
	* Expressões de Atribuição

<h2><a id="o-que-e-uma-expressao">O que é uma Expressão</a></h2>

Expressão é um fragmento de código JavaScript que pode ser interpretado para produção de um valor. Fazendo uma breve analogia, a expressão está para seu programa JavaScript assim como uma frase está para um texto. Um exemplo de expressão é uma atribuição de valor à uma variável.

`var atribui = 'e a névoa começa a se dissipar...'`

Podemos combinar expressões para formar outras mais elaboradas.

> Vimos várias expressões no artigo anterior, enquanto falávamos sobre os operadores. Todos aqueles exemplos são ótimos para o entendimento de expressões. Na realidade, o que iremos ver hoje é apenas uma formalização do estudo passado, apenas nomeando coisas que já sabemos intuitivamente.
>
> Aproveite pois o artigo de hoje será bem leve, mas fique sabendo que nossa base para criação de programas JavaScript está quase pronta, e em breve a diversão irá começar de fato ;D

<h2><a id="expressoes-basicas">Expressões Básicas</a></h2>

Esse tipo de expressões são assim denominadas pois não incluem outras expressões, ou seja, são o menor fragmento possível do nosso código. Vejamos alguns exemplos:

<div data-gist-id="11199425" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

<h2><a id="expressoes-de-inicializacao">Expressões de Inicialização</a></h2>

Essas expressões são **muito** importantes, pois nos possibilitam a criação de *objetos* e *arrays* de forma *literal*, e isso nos dá uma facilidade e praticidade muito grande na hora de tais tarefas. Veja abaixo a forma de se criar um objeto e array de forma literal e da forma utilizada com o auxílios de seus *construtores* (iremos conhecer mais sobre construtores futuramente).

<div data-gist-id="11199737" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

Viram o quão econômica e elegante é a forma literal de inicialização de objetos e arrays? Use-a sem moderação!

Um dos motivos de enquadrarmos esta e as expressões seguintes no campo de *expressões complexas*, é que elas podem receber as expressões básicas para comporem seu valor, pois obviamente, um objeto, um array, só são úteis por carregarem em si valores agrupados de acordo com algum propósito. Além de valores básicos, podemos também passar valores "complexos" para expressões complexas. Traduzindo, ter arrays dentro de arrays, objetos dentro de objetos, arrays dentro de objetos, objetos dentro de arrays, e por ai vai...

Vamos agora então, dar sentido a existência de nossos objetos e arrays!

<div data-gist-id="11199959" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

No exemplo acima, na variável `estudos` (que é um *objeto*, veja pelo sinal `{}` que *abraça* os demais valores), temos as *propriedades* `JavaScript` e `Outros` recebendo arrays como valores, e estes arrays recebem *strings*, por sua vez.

No caso da variável `livros`, que é um array `[]`, ela recebe três *strings* como itens de sua lista de valores.

Brinque um pouco agora criando arrays e objetos de diferentes tipos, preenchidos com diversos valores!

<h2><a id="expressoes-de-definicao">Expressões de Definição</a></h2>

Usamos essa expressão para definir uma função em nosso programa. Para criarmos essa expressão devemos seguir os seguintes passos:

1. Usar a palavra chave `function`
1. [opcional] Dar um nome para a função (caso não tenha nome, iremos chamá-la de *função anônima*)
1. Passar os argumentos que serão usados na função, que podem ser de 0 (zero) até quantos você quiser, todos colocados dentro dos parênteses `()` e separados por vírgulas. Ex: `(valor1, valor2, valor3)`
1. Criação do *corpo da função*, que conterá outras expressões, que são as *tarefas* que deverão ser feitas todas as vezes que a função for chamada. O corpo da função é delimitado por chaves `{ ... mais expressões aqui ... }`

Para chamarmos nossa função posteriormente, devemos ou atribuí-la a uma variável ou então nomeá-la.

Veja alguns exemplos:

<div data-gist-id="11234132" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

<h2><a id="expressoes-para-acessar-propriedades">Expressões para Acessar Propriedades</a></h2>

Usamos esse tipo de expressão para obter o valor de alguma propriedade/item de um objeto ou um array. Podemos fazer isso usando dois tipos de sintaxe diferentes, a de notação por ponto (`expressao.chave`) ou a de notação por colchetes (`expressão['chave']`). Vamos ver com mais detalhes cada uma delas.

### Acessando Propriedades com ponto

##### `expressão.chave`

Essa forma é utilizada exclusivamente para acessar *propriedades* e *métodos* de **objetos**. Onde temos escrito *expressão*, iremos utilizar o nome do nosso objeto, e onde temos *chave*, iremos passar o nome da propriedade/método que queremos avaliar. Vamos para o console e tornar isso mais claro.

<div data-gist-id="11227222" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

Notem que tivemos um erro ao tentar acessar o segundo item da propriedade cordas! Isso se deve pelo motivo que para acessar itens de arrays, utilizamos outro tipo de notação, que irei lhe explicar agora!

### Acessando Itens e Propriedades com Colchetes

##### `expressão['chave']`

Com esse tipo de notação podemos acessar tanto os itens de um array quanto as propriedades de um objeto. Onde temos o valor *expressão* iremos substituir pelo nome do array ou objeto, e onde temos chave, iremos substituir pela posição do item (caso seja um array) ou pelo nome da propriedade, caso seja um objeto. Vamos agora utilizar do nosso exemplo anterior, porém acessando o objeto e o array com esta notação por colchetes.

<div data-gist-id="11227495" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

### Dicas de "Acessibilidade"

* Caso você tente acessar propriedades em `null` e `undefined`, você obterá uma exceção *TypeError*, ou seja, um erro, pois esses valores não podem ter propriedades.
* Caso acesse uma propriedade ou índice que não esteja definido, o valor retornado será `undefined`.
* A notação de ponto, por ser mais direta, deve ser utilizada quando já se sabe exatamente qual propriedade será acessada.
* A notação por colchetes permite que seja passado variáveis como valor para acesso, pois caso a propriedade tenha sua *chave* (identificador) sendo um número, contendo espaço no nome ou sendo uma palavra reservada de JavaScript, a única forma de acessá-la é assim, através da notação de colchetes, utilizando ou não uma variável para *contenção* desse valor.

<h2><a id="expressoes-de-invocacao">Expressões de Invocação</a></h2>

Essa expressão é utilizada para chamar (invocar, executar) uma função ou *método*.

> Quando uma função está atribuída à uma chave em um objeto, essa passa a se chamar **método**.

Para usar essa expressão devemos indicar o nome da função que desejamos invocar seguida de parênteses. Caso a função receba argumentos, os mesmos devem ser passados dentro dos parênteses.

**ps**: Lembre-se de usar no seu código o `;` depois de chamar a função! Somente omitiremos o ponto e vírgula no console para agilizar os testes.

Vamos ver um exemplo:

<div data-gist-id="11229463" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

### Entendendo o Processo de Invocação

Irei explicar sucintamente como funciona este processo, o qual será devidamente aprofundado quando estivermos falando especificamente sobre funções. Veja quais são as etapas:

1. Verificação da existência de uma função (ou objeto, visto que a função é um tipo de objeto) com o nome passado. Caso não exista tal objeto, um erro é lançado.
1. Criação de uma lista de valores a partir dos argumentos passados, que são avaliados para produzirem tais valores.
1. Atribuição dos valores aos respectivos parâmetros da função.
1. Execução do corpo da função.
1. Se a função tiver `return`, esse valor será o retornado como resultado da avaliação da função.

<h2><a id="expressoes-de-criacao">Expressões de Criação</a></h2>

São utilizadas como uma alternativa na forma de se criar objetos. É bom ter conhecimento dessas expressões, mas saiba que dificilmente você irá utilizá-las (para arrays e objetos), pois a forma literal é bem mais direta.

Nessas expressões utilizamos as *funções construtoras* para criar novos objetos, juntamente com a palavra chave `new` (iremos estudar sobre funções construtoras mais a frente).

Alguns exemplos da utilização dessas expressões:

<div data-gist-id="11230512" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

<h2><a id="mais-expressoes">Mais Expressões</a></h2>

No último artigo já vimos vários exemplos de expressões que utilizam operadores. Irei deixar aqui indicado o nome da expressão com seus respectivos operadores, e após vista a teoria aqui, vá para o outro artigo e procure as respectivas expressões em uso.

Os outros tipos de expressões que temos são:

* **Expressões Matemáticas ou Aritméticas**: `+`, `-`, `/`, `*`, `%` 
* **Expressões Relacionais**: `==`, `===`, `!=`, `!==`, `<`, `>`, `<=`, `>=`
* **Expressões Lógicas**: `&&`, `||`, `!` 
* **Expressões de Atribuição**: `+=`, `-=`, `*=`, `/=`, `%=` 

## Conclusão

Estamos evoluindo! Viram o quanto já aprendemos? Mas isso é apenas o começo, e te garanto, a melhor parte nem começou ainda!

No próximo artigo iremos falar sobre **Instruções**, e finalizar a base necessária para aprofundarmos nas melhores partes do JavaScript!

Até a próxima! =D