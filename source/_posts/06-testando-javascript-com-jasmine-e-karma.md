title: Testando JavaScript com Jasmine + Karma
date: 2014-02-25 20:20:57
tags: 
	- jasmine 
	- karma
---

![Avião](http://i.imgur.com/AkNE4ns.jpg)

Nesse post vamos aprender como configurar nosso ambiente de testes de código JavaScript utilizando o framework de testes [Jasmine](http://cerebrobr.github.io/jasmine-br-docs/) e o *test runner* (rodador de testes) [Karma](http://karma-runner.github.io/0.10/index.html). 

Após tudo instalado, iremos fazer nosso primeiro teste e ver o quanto é interessante essa abordagem, e como essa prática pode melhorar nossa abstração, visto que sempre escrevemos nossos testes **antes** de implementar o código, que deve ser assim feito **progressivamente**, criando condições simples para se obter êxito na asserção do teste, e **pouco a pouco** vamos incrementando nosso código até que ele tenha a funcionalidade esperada.

**Vamos lá!**

## Por que testar meu código?

Bom, simples. Programas facilmente obtém centenas, milhares de linhas de código, tornando **impossível** a varredura de toda esta área por uma rápida análise humana. Sendo assim, podemos nos ajudar fragmentando nosso código e fazendo testes em cada parte isoladamente, tendo com isso nossos **testes unitários**, onde cada peça é testada isoladamente.

Essa técnica de testes unitários foi inspirada na engenharia aeronáutica, onde cada peça é exaustivamente testada antes de compor o bloco do elemento principal (no caso o avião). Uma peça que se rompa em meio a um vôo irá causar prejuízos enormes para todas as empresas envolvidas e para todos os transportados, bem como na sua aplicação web, caso algum elemento falhe e cause um colapso no sistema.

**Outro bom motivo**: Correções no seu código serão feitas obrigatoriamente antes ou depois de sua conclusão. Você pode escolher por **testá-lo** ou apenas **debugá-lo**.

Escolhendo a primeira opção, obrigatoriamente você terá um acréscimo no tempo do desenvolvimento do projeto, porém terá confiança no mesmo, pois ele já fora testado previamente e constatado que realmente faz o esperado.

Escolhendo a segunda opção, você pode *ter sorte* e não precisar de corrigir alguma falha no código. Porém, nos imaginando em situações reais, com centenas ou milhares de linhas de código escritas, você acha que consegue escrever tudo isso de forma correta e harmônica de primeira? Nem precisa me responder, pois é óbvio que não. Neste caso, erros vão aparecer na hora de debugar, porém ai que entra o fator surpresa, pois você pode encontrar e corrigir o erro com um tempo muito menor que o utilizado para criar todos os testes, porém, este tempo é uma incógnita, e pode se estender de minutos até horas para se encontrar a falha no sistema, visto que simplesmente a detecção do mesmo é muito difícil! Sem contar que é muito mais interessante **criar** que **consertar**, isso é fato!

Chega de conversa e vamos trabalhar!

## O que precisamos?

Primeiramente, o que precisamos para iniciar é ter instalado em nossa máquian o [Node.js](http://nodejs.org/). Caso não tenha, vá na página oficial do Node e instale-o.

Com o Node "em mãos", precisamos agora de instalar o **Karma**, que irá rodar nossos testes. Para isso, iremos utilizar o **NPM** (**N**ode **P**ackage **M**anager). É muito simples, apenas digite isso na sua linha de comando:

<pre><code>$ npm install -g karma</code></pre>

Com isso, você terá agora instalado, globalmente (**-g**), o Karma.

Pronto! O mais difícil já foi =P Agora precisamos apenas configurar nossa pasta de testes.

## Configurando o Karma Para Seus Testes

O Karma tem incluso um inicializador automático que permite que você configure seu projeto de forma simples e muito rápida.

Na inicialização, serão feitas algumas perguntas a você, como com qual browser você gostaria de rodar os testes (o browser se faz necessário, por exemplo, no caso de testes reais no DOM, para maior segurança de que nosso projeto está de fato funcionando no seu ambiente real), as pastas que contém os arquivos a serem verificados, o framework que você irá utilizar (no nosso caso, o Jasmine) entre outras coisas.

Antes de configurarmos o Karma, vamos criar duas pastas que irão conter nossos códigos. Crie uma pasta chamada <code>jasmine-karma</code>. Dentro desta pasta, você irá criar um arquivo chamado <code>mult.js</code> e uma pasta chamada <code>tests</code>. Dentro da pasta tests, você irá criar um arquivo <code>spec-mult.js</code>. Teremos uma estrutura mais ou menos assim

<pre><code>jasmine-karma/
|
+---mult.js
|
+---tests/
	|
	+---spec-mult.js
</pre></code>

Ótimo! Agora, vamos configurar o Karma. Para isso, temos que voltar ao terminal e digitar o seguinte código, no diretório `jasmine-karma`:

<pre><code>$ karma init karma.conf.js</code></pre>

**OBS:** Você pode também colocar outro nome no seu arquivo de configuração ao invés **karma**.config.js. Poderia ser <code>teste.conf.js</code>.

Após este comando, você deverá responder algumas perguntas (basicamente já está tudo certo, é só dar enter). A única parte que você terá que digitar é na parte dos diretórios onde o Karma vai verificar por mudanças de arquivos. Você terá algo mais ou menos assim:

<pre><code>Which testing framework do you want to use ?
Press tab to list possible options. Enter to move to the next question.
> jasmine
 
Do you want to use Require.js ?
This will add Require.js plugin.
Press tab to list possible options. Enter to move to the next question.
> no
 
Do you want to capture a browser automatically ?
Press tab to list possible options. Enter empty string to move to the next question.
> Chrome
>
 
What is the location of your source and test files ?
You can use glob patterns, eg. "js/*.js" or "test/**/*Spec.js".
Enter empty string to move to the next question.
> js/*.js
> js/tests/*.js
>
 
Should any of the files included by the previous patterns be excluded ?
You can use glob patterns, eg. "**/*.swp".
Enter empty string to move to the next question.
>
 
Do you want Karma to watch all the files and run the tests on change ?
Press tab to list possible options.
> yes
</code></pre>

**Pronto!** Karma totalmente configurado! Vamos para a parte boa =D

## Criando Nosso Primeiro Teste!

Lembra dos arquivos que criamos? Pois bem, chegou a hora de utilizarmos os mesmos. É prática comum desenvolver os testes **antes** do código em si, e após um teste configurado, vamos implementando nosso código aos poucos, com *baby-steps* (passos de bebê). Sendo assim, vamos então abrir nosso arquivo <code>spec-mult.js</code> e criarmos um teste, o qual verificará se nossa função está fazendo a multiplicação de dois números de forma correta.

<div data-gist-id="9220116" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

Bom, o que fizemos aqui? Primeiramente, *descrevemos* (`describe`) o que nossa função faz/deve fazer. Depois disso, configuramos que nossa variável <code>mult</code> será o novo nome para a função <code>multiplicaDoisNumeros</code> que definimos no nosso outro arquivo.

Feito isso, entramos na parte mais direta dos testes, onde verificamos se *isso* (`it`) realmente faz o que *esperamos* (`expect`) que faça.

A primeira asserção é para verificar se nossa função está definida, e a segunda é para verificar se ela realmente faz o que se propõe a fazer, ou seja, multiplica dois valores passados nos parâmetros da função e retorna o resultado desta operação.

Tudo certo! Volte ao terminal e digite o seguinte comando:

<pre><code>$ karma start karma.conf.js</code></pre>

**Erro!** Como ainda não criamos nossa função, obviamente recebemos este alerta de algo errado.

Vamos agora criar nossa função `multiplicaDoisNumeros`, fazendo com que a mesma retorne exatamente o esperado pelo nosso teste, porém da forma mais fácil possível, que é a seguinte:

<div data-gist-id="9220124" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

**Sucesso!** Conseguimos receber nossa tão esperada mensagem de sucesso, mostrando que nosso teste passou, e nossa função realmente faz o que desejamos que ela faça... ou quase isso =P

Vamos implementar agora a função esperada, que recebe dois valores como parâmetros e retorna a multiplicação destes, finalizando assim nosso trabalho com esta função.

<script src="https://gist.github.com/ericdouglas/9220129.js"></script>
<div data-gist-id="9220129" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

**Agora sim!** Finalmente, conseguimos um resultado satisfatório! =D

## Bônus: PhantomJS

Para você que chegou até aqui, deixei uma surpresa bem legal para o final... Para usar somente o terminal, e não precisar ter uma janela do navegador aberta, você pode utilizar o **[PhantomJS](http://phantomjs.org/)**. Para isso, você precisa de fazer apenas duas coisas:

* **1) Instale o phantomJS**: vá para o terminal e digite o seguinte comando:

<pre><code>$ npm install -g phantomjs</code></pre>

* **2) Altere seu arquivo de configuração**: Abra o arquivo `karma.conf.js`, procure pela seção *browsers* e deixe com esta configuração:

<pre><code>browsers: ['PhantomJS'],</code></pre>

Por hoje é isso galera, veja a documentação e comece a brincar com os métodos disponíveis do Jasmine, para que aos poucos esse conceito e filosofia de desenvolvimento seja absorvida e colocada em prática.

Um abraço! =)