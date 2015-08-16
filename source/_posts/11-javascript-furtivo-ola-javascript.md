title: JavaScript Furtivo | 02 - Olá JavaScript!
date: 2014-04-08 21:15:01
tags: 
	- javascript
	- furtivo
---

![02 - olá javascript](http://i.imgur.com/WeMRkre.png)

> Confira os outros artigos da série **JavaScript Furtivo** no final [desta](http://ericdouglas.github.io/2014/04/08/10-javascript-furtivo-apresentacao/) página.

Antes de iniciarmos as apresentações, vou lhe contar algo que você deverá tomar cuidado ao compartilhar, pois pode lhe gerar algumas discussões, mas o fato é que o mercado nunca foi tão interessante e animador para um programador JavaScript como agora, e nunca foi tão onipresente para qualquer linguagem como está sendo para a JavaScript!

Sério, hoje podemos fazer maravilhas com a JavaScript, desde programação front-end (no lado do cliente [navegador]), como no back-end com o espetacular **Node.JS**, que além disso permitiu que a JavaScript fosse utilizada em diversas outras áreas além dos navegadores e mundo web.

O trio *HTML*, *CSS* e *JavaScript* está cada vez mais presente nos celulares, seja como aplicações híbridas ou até mesmo como o próprio sistema operacional, tendo como exemplo o Firefox OS.

> Para mais motivação para aprender JavaScript, veja [este](http://ericdouglas.github.io/2014/02/17/01-bushido-dev-web/) link.

## O que é JavaScript?

Vamos fazer uma analogia de uma aplicação web, seja um simples site ou um complexo sistema, com uma casa. 

Na casa, toda a parte estrutural (tijolos, telhado) é equivalente à nossa HTML. Elá é responsável por estruturar e definir, *semanticamente*, quais elementos estarão presentes no nosso *documento* (outro nome para nossa página HTML). É muito importante ter em mente **exatamente** o que cada tecnologia nos oferece, para aproveitarmos o melhor de cada, e não delegar tarefas de uma para a outra.

O CSS é responsável de fazer o acabamento da casa, digo, da aplicação. É a parte que devemos "estilizar" todo o documento, para que o mesmo não fique com cara de apenas um documento para impressão, mas sim com a cara de uma aplicação/programa o mais agradável e utilizável possível.

**OBS**: Tanto fato é a questão da HTML ser um documento, que sua origem foi justamente essa. A WWW (World Wide Web) foi criada com fim de auxiliar pesquisadores a mandarem seus trabalhos acadêmicos uns para os outros. A HTML foi a linguagem criada para identificação do navegador de onde se teria um título, um parágrafo, uma citação, e por ai vai... O que vemos hoje com a HTML5 é um sonho utópico, analisando o cenário atual com a mentalidade de quando esta tecnologia (HTML) fora criada.

Por último, e não menos importante, temos a JavaScript! Em relação a uma casa, a função da JavaScript seria dar "vida" a casa, ou seja, seria a luz e a água da mesma, por exemplo. De forma menos lúdica, de fato a JavaScript cuida das interações da página com o usuário, e vice-versa. 

A função primária para qual a JavaScript foi criada era a de tratar informações do lado do cliente, sem que fosse necessário o envio de informações para processamento no servidor. Vale mais uma vez ressaltar a importância da base histórica para real compreensão e valorização das tecnologias, ferramentas que nos auxiliam a realizar determinada tarefa.

Hoje em dia, o acesso a internet se faz em grande parte utilizando serviços de banda larga. Bom, **atualmente** é assim! No início da nossa querida web, você poderia levar tranquilamente 1 minuto apenas para receber uma mensagem que seu formulário foi preenchido **incorretamente**...

Isso é só o começo, teremos uma longa caminhada para desvendar os segredos dessa linguagem fantástica que nos permite criar diversas coisas, tantas quanto nossa imaginação permitir!

> Em alguns momentos eu uso **a** JavaScript, e em outros **o** JavaScript. Peço desculpas por estar fazendo confusão na sua cabeça, mas vou explicar o motivo. Quando estou me referindo **à** linguagem JavaScript, creio que o mais correto seja usar **a**. Quando falo sobre **o** código JavaScript, então o uso do **o** é o correto. Sei que fica estranho **a** JavaScript, mas se não fizer assim, irá parecer um alemão falando português: "- vou pegar **a** ônibus!". hahaha! 

## Chega de conversa, vamos aprender Java!!!

Meu amigo, de coração, **nunca** diga *Java* referindo-se à nossa querida JavaScript. **Nunca**!!! Este nome, infelizmente, foi uma terrível escolha de marketing feita no início da história da JavaScript. Como a linguagem *Java* estava muito em alta na época em que a JavaScript foi criada, resolveram <del>estragar</del> nomear a mesma de tal forma. Essa é a maior semelhança que Java e JavaScript tem.

## JavaScript™

Nossa linguagem foi criada por Brendan Eich em 1995 quando o mesmo trabalhava na *Netscape* (hoje *Mozilla*). Já teve o nome de Mocha e LiveScript, porém quando foi apresentada a implementação de *Java* nos navegadores da Netscape em conjunto com a *Sun Microsystems* (hoje *Oracle*), teve seu nome alterado para *JavaScript*. Este nome, JavaScript, é marca registrada da Oracle atualmente.

Quando a JavaScript foi padronizada pelo grupo *ECMA* (European Computer Manufacter's Association), recebeu o nome de ECMAScript, e temos então essa versão padronizada implementada nos navegadores.

Já na ECMAScript temos que ter atenção atualmente a três versões da mesma. A primeira é a versão **3** (ECMAScript 3), que é completamente suportada por todos os navegadores atuais. A segunda versão é a **5** (ECMAScript 5) que está em grande parte implementada, mas iremos analisar quando alguma *feature* (propriedade, recurso) da mesma não for comum entre os navegadores. A versão 5 é a que iremos abordar principalmente nessa série. E a próxima versão é a **6** (ECMAScript 6), que deverá ser lançada em breve. Preocupe-se hoje com a 3 e 5, a 6 é bom, no presente momento, apenas ter conhecimento de que está para chegar. =)

* Mais sobre o início da JavaScript [aqui](http://pt.wikipedia.org/wiki/JavaScript);

> Veja o próximo artigo [#03 - Conhecendo o Idioma JavaScript](http://ericdouglas.github.io/2014/04/08/12-javascript-furtivo-conhecendo-o-idioma-javascript/)