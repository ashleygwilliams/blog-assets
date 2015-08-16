title: JavaScript Furtivo | 03 - Conhecendo o Idioma JavaScript
date: 2014-04-08 21:30:01
tags: 
	- javascript
	- furtivo
---

![03 - conhecendo o idioma javascript](http://i.imgur.com/xxoWts4.png)

> Confira os outros artigos da série **JavaScript Furtivo** no final [desta](http://ericdouglas.github.io/2014/04/08/10-javascript-furtivo-apresentacao/) página.

Para você começar estudar a **linguagem** de programação JavaScript, é necessário que tenha o entendimento de como se dá esse intercâmbio dos caracteres que inserimos com a forma que os mesmos são interpretados pelo computador. Muito difícil? Vamos simplificar!

É algo bem simples, você se comunica com outras pessoas através de uma linguagem, a qual nada mais é que uma padronização de sequências de letras e fonemas que juntos referem-se a alguma coisa e dão sentido a tal. Na área da programação é exatamente a mesma coisa! Temos que conhecer as estruturas básicas da linguagem para começarmos a montar palavras, frases e textos, que no nosso caso serão os programas.

Essa estrutura de comunicação básica, ou estrutura léxica, nos indica como a linguagem deve ser escrita, sendo essa estrutura o nível mais baixo de abstração da mesma, nos indicando como criar e nomear variáveis, como inserir comentários nos códigos e como escrever as *expressões* e *instruções* que farão toda a mágica acontecer.

Agora que já temos em mente o que precisamos aprender, vamos, então, aprender!

Nesse artigo você irá aprender:

* Qual o padrão de escrita usado na JavaScript;
* Detalhes de nomenclatura;
* Como inserir comentários
* Como nomear variáveis;
* O que são identificadores e palavras-reservadas.

> Leia sempre com bastante atenção cada tema passado e reflita-o um pouco para iniciar a absorção das informações. Todo o conteúdo destes artigos são de suma importância para seu aprendizado e crescimento como desenvolvedor JavaScript, porém, não pense que você terá que aprender tudo na primeira vez que ler e/ou praticar. O aprendizado é algo que leva tempo e muito esforço repetitivo, e muitas coisas não são triviais, e é isso que no final fará toda a diferença e dará a sua satisfação em ter vencido cada etapa do processo. =)

## As "Letras" do Nosso Alfabeto

Nosso código JavaScript é escrito com base no **padrão Unicode**, que podemos sucintamente definir como um padrão que permite aos computadores representar e manipular, de forma consistente, texto de qualquer sistema de escrita existente. Este é composto com mais de 107 mil caracteres!

## JavaScript não é Javascript nem javaScript!

A linguagem JavaScript **faz diferenciação** de letras maiúsculas de letras minúsculas, portanto, todo o devido cuidado deve ser tomado para evitar discordâncias na chamada de funções e todas as propriedas próprias da JavaScript e implementadas por você.

<div data-gist-id="10212671" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

Nesse código acima, quando testado no Devtools do Chrome, por exemplo, terá como resultado os valores na frente da seta `->`. 

Veremos como comentar nosso código agora.

## "Rodinhas", digo, Comentários no Código

Existe uma grande discussão de até que ponto é interessante um código muito comentado. Uns defendem dizendo que tal prática ajuda a esclarecer o que está ali feito, ajudando no futuro quando você revisitar tal seção, mas por outro lado, o lado *prático*, vemos que muito comentário simplesmente quebra o fluxo de leitura do código, fazendo com que você tenha que ficar saltando entre todos os textos, ou tendo que ler centenas/milhares de linhas a mais do que o necessário. Sem contar que quando o código é atualizado, o comentário também deve ser, e um comentário desatualizado é infinitas vezes pior do que a falta do mesmo.

Pense comigo, o que estamos fazendo já não é escrever em uma linguagem? Tudo bem, eu sei que a mesma é diferente da nossa linguagem usada para comunicação interpessoal, porém, ela por si só deve ser **auto-explicável**. Como conseguir isso? Nomeando suas funções de forma inteligente por exemplo, definindo no nome exatamente o que ela faz. E ai vem outra dica, código modular é **vital** para o sucesso de um programa. E para ter algo modular, esse algo deve fazer uma, e apenas **uma** tarefa. Conseguindo deixar um pedaço isolado de código fazendo apenas **uma** coisa, será mais fácil nomear essa coisa, fazendo com que o nome já se auto-explique.

Outra forma é criar uma documentação para seu código separado do mesmo, para evetuais consultas. Isso é algo bem elegante, diga-se de passagem.

Você vai me dizer: "Cara, você não acha que está pegando pesado demais não?! Nem me mostrou código e já está me mandando modularizar?!"

Ai meu amigo que é a parte boa! Sendo modular, você terá que fazer menos coisas! E assim irá ficar mais fácil desde o início da sua vida de programador =)

É muito importante começar a trabalhar as ideias na sua cabeça antes de serem implementadas. O **conceito** é tão importante quanto a **prática**, para quem quer realmente **dominar** o que está fazendo. E precisamos primeiro *tentar* criar algo, e depois de várias tentativas e erros, iremos conseguir fazer tal coisa da forma mais correta.

Voltando para os comentários, as duas formas que temos de inserir comentários nos nossos códigos são:

* Usando duas barras: `//`
* Usando `/* */`

Vamos ver um exemplo:

<div data-gist-id="10213141" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

> O termo do título dessa seção, *rodinhas*, se refere as rodinhas quando estamos aprendendo a andar de bicicleta. No início, são super importantes, mas depois que aprendemos a andar, não precisamos mais delas. Usaremos comentários nos nossos códigos para fins **didáticos**, mas os mesmos devem ser usados de forma muito escassa, pois de fato não são necessários.
>
> "Se você precisa explicar muito detalhadamente alguma parte do seu código, é porque algo ali não está muito correto..."
>
> - Provérbio Chinês

## Como Escrever Meu Código

Ao longo dos artigos, você irá aprender de forma prática as melhores práticas de escrita de código, inclusive teremos uma seção específica para isso, mas inicialmente você apenas precisa saber que seu código JavaScript pode conter qualquer quantidade de espaços em branco entre os sinais delimitadores do programa e, por conseguinte, também ignora quebra de linhas.

<div data-gist-id="10213328" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

> Tome cuidado com as quebras de linhas, pois como veremos no fim deste artigo, em determinadas situações, o seu código pode ter um ponto e vírgula (`;`) adicionado pela própria linguagem, para prevenção de erros, porém que de fato irá gerar outros inesperados (mas que agora são esperados pois eu te falei que vão acontecer =P). 
>
> Para que isso não aconteça, tome cuidado com as quebras de linhas com omissão do ponto e vírgula. E por favor, seja *caprichoso* com seu código, não é porque você **pode** fazer algo que você **deve** fazer.

## Sempre use Ponto e Vírgula ;

Ao final de suas instruções, você <del>não</del> tem a possibilidade de omitir o ponto e vírgula (`;`), símbolo esse que mostra que uma instrução terminou.

O problema é que, como falado anteriormente, isso pode gerar vários erros (in)**esperados**. Mas fica a seu critério, pra que facilitar se podemos complicar, né?!

## Cartório JavaScript

Sim, aqui iremos falar da parte mais "pesada" desse capítulo, que foi bem leve, então de fato essa é a parte *menos leve*. Qual parte é essa? Na verdade são duas: **identificadores** e **palavras reservadas**.

### Identificadores

Um identificador nada mais é do que um nome que usamos para chamar nossas variáveis e funções. Sim, iremos registrar o seu nome na certidão, ou no programa como queira, para que futuramente quando esses meninos e meninas crescerem ainda nos lembremos deles e eles de nós.

Temos apenas algumas restrições para criar nossos identificadores, que são elas:

* Um identificador deve começar com alguma letra, $ ou _ (underscore).
* Números só são permitidos após o primeiro caractere estar de acordo com a regra anterior

Exemplos de nomes válidos: `carro`, `_teste`, `v8`, `$nomeValido`.

### Palavras Reservadas

Essas palavras são as que já estão definidas na linguagem, portanto apenas as **usaremos**. Confira abaixo algumas destas palavras:

	break 
	case catch continue
	debugger default delete do
	else
	finally for function
	if in instanceof
	new
	return
	switch
	this throw try typeof
	var void
	while with

Na ECMAScript 5 temos mais palavras reservadas para uso futuro em novas implementações do padrão, que são:

	class
	enum export extends 
	import
	super

No `strict mode` (modo estrito da linguagem, veremos futuramente do que se trata), temos mais algumas palavras reservadas para futuras implementações

	implements interface
	let
	package private protected public
	static
	yield

> Veja mais sobre palavras reservadas [aqui](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Reserved_Words).

## Conclusão

Neste capítulos nós aprendemos:

* que JavaScript usa o padrão Unicode para seus caracteres;
* que JavaScript diferencia letras maiúsculas de minúsculas;
* maneiras de comentar, e por que *evitar* comentar;
* que devemos **sempre** usar ponto e vírgula (`;`);
* como criar identificadores e como usar os existentes (palavras reservadas).

E vamos seguindo, a cada artigo as coisas vão ficando sempre melhores!

> Veja o próximo artigo [#04 - O Valor dos Tipos de Operadores - Parte 1](http://ericdouglas.github.io/2014/04/15/13-javascript-furtivo-o-valor-dos-tipos-de-operadores-parte-01/)