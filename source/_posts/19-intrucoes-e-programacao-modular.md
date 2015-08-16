title: JavaScript Furtivo | 07 - Instruções e Programação Modular no JavaScript - Pt 1
date: 2014-10-05 13:13:00
tags: 
	- javascript
	- furtivo
---

![programação modular no javascript](http://i.imgur.com/LEo3Iof.png)

> Confira os outros artigos da série **JavaScript Furtivo** no final [desta](http://ericdouglas.github.io/2014/04/08/10-javascript-furtivo-apresentacao/) página.

Finalmente chegamos na parte final do nosso material introdutório ao JavaScript! Iremos aprender agora como criar *instruções* nos nossos programas, e como organizá-las de forma **estruturada** e **modular**. 

Como nosso objetivo é de fato **entender** o que estamos fazendo, e não apenas *copiar/usar/escrever* algumas linhas de código aleatórias, iremos ter um embasamento sintetizado, porém sólido, de como funciona nosso primeiro programa em JavaScript! Sim isso mesmo, a partir do conhecimento adquirido nessa etapa final, você estará **totalmente** apto a criar seus primeiros programas em JavaScript!  

Veja o que será abordado:

1. [O que é um paradigma?](#o-que-e-um-paradigma)
2. [Programação Modular](#programacao-modular)
3. [Módulos ou Subprogramas](#modulos-ou-subprogramas)
4. [Instruções e Estruturas Auxiliares](#instrucoes-e-estruturas-auxiliares)

<h2><a id="o-que-e-um-paradigma">O que é um paradigma?</a></h2>

Paradigma de programação nada mais é do que uma maneira de se pensar e resolver um problema. Na *vida real* temos pessoas *pessimistas*, *otimistas* e *realistas*, certo? E essa definição é feita pelo **modo** como essas pessoas **enxergam/analisam** os seus problemas e os problemas do mundo. Na programação é a **mesma coisa**! Só que no caso, teremos pessoas *imperativas*, *estruturadas*, *funcionais* e por ai vai...

A analogia anterior é uma brincadeira com essas formas de se pensar, mas é algo realmente válido. Uma diferença que temos da vida *real* para a *virtual*, é que em nossos programas não precisamos usar apenas um paradigma, ou seja, uma forma de se pensar. Podemos, e **devemos**, sempre analisar o problema e buscar a forma **mais eficiente** de resolvê-lo, mediante um estudo do mesmo de forma profunda.

Com o passar do tempo, obviamente, essa habilidade de resolução de problemas se torna cada vez maior, e o tempo despendido em cada um será cada vez menor, mas isso se dará após **muito trabalho**, e muitos problemas semelhantes resolvidos. Portanto, não se preocupe muito com isso agora no início. Curta o problema, analise-o, e tente **sempre** resolvê-lo da forma mais consciente possível.

> A partir de agora, uma linha é traçada em nossa jornada... Tudo que fizermos será de fato um **programa JavaScript**! Respire fundo e vamos mergulhar nesse maravilhoso e vasto mundo! =D

<h2><a id="programacao-modular">Programação Modular</a></h2>

A *programação modular* nos remete a *programação estruturada*, que por sua vez tem origens na *programação imperativa*. Muita coisa? Pode deixar que vou te explicar de forma bem simples! Siga comigo neste raciocínio...

### Programação Imperativa

A programação imperativa se dá de forma *natural* (como as linguagens naturais), sendo que as *instruções* do programa são executadas de forma sequencial, de cima para baixo, e só alterada essa sequência linear de execução quando descrito saltos no programa através de marcadores específicos. Esses marcadores fazem com que o seu código seja executado a partir de outro ponto, o que torna a depuração (debug) do código muito difícil.

É a partir dessa dificuldade que surge a *programação estruturada*.

### Programação Estruturada

Neste paradigma de programação, são introduzidas algumas estruturas **essenciais** para facilitação da escrita e principalmente leitura do código.

Essas estruturas são tão poderosas que podemos representar **qualquer** programa apenas com elas. As estruturas são:

* Estrutura de Decisão/Condicional
* Estrutura Sequencial/Laços
* Estrutura de Repetição

Com a inclusão destas estruturas, a necessidade de se fazer saltos dentro do programa já não era mais necessária, pois cada estrutura dessa é como um **subprograma** dentro do nosso programa, onde estes *subprogramas* tratam **localmente** os dados passados a eles e retornam o valor necessário para continuação da execução do programa. **Maravilha**!

Com isso, a evolução natural desta forma de programar nos levou para o **paradigma modular**.

### Programação Modular

Com a absorção desse conceito de subprogramas dentro dos nossos programas, a **modularização** das tarefas realizadas por eles foi uma grande melhoria em relação as técnicas empregadas no desenvolvimento de programas, melhorando **consideravalmente** a *legibilidade* e *manutenabilidade* dos códigos.

Atualmente a palavra *modular* é uma *buzzword* (palavra da moda) em JavaScript, principalmente graças ao **Node.JS** que difundiu concretamente essa prática para nós desenvolvedores JavaScript. Mas isso não é nada de outro mundo, **muito pelo contrário**, código modular é sinônimo de código conciso e reduzido, que realiza uma tarefa apenas, facilitando novamente o **entendimento** e **desenvolvimento** dos programas.

Resumindo, *programação modular* é uma técnica onde criamos estruturas **objetivas** em nossos programas, usando subprogramas, ou subrotinas, e funções.

<h2><a id="modulos-ou-subprogramas">Módulos ou Subprogramas</a></h2>

Para fixar o entendimento do *paradigma modular*, precisamos entender verdadeiramente como funcionam suas peças, ou módulos, e o objetivo de se criá-los.

Os módulos (ou subprogramas/subrotinas) são divisões do nosso programa principal com a capacidade de serem desenvolvidos de forma independente, ou seja, de forma separada. Essas peças são então **conectadas** para formar um programa que realiza diversas tarefas.

Um **excelente** benefício dessa prática é a possibilidade de **reutilização** do código, visto que esses módulos não são dependentes de outros programas e subprogramas, podendo ser novamente rearranjados para construção de novos programas.

Podemos dividir esses módulos em duas categorias: **funções** e **procedimentos** (que são as três estruturas citadas anteriormente).

### O que um Módulo pode/deve fazer?

Ao se criar um módulo, devemos ter em mente que o mesmo deve ser capaz de:

* ser invocado através de um nome específico;
* ser considerado um programa, tendo capacidade de **receber**, **manipular** e **produzir** valores;
* receber e retornar dados do programa que o envolve.

É importante ressaltar que no momento que um módulo (ou subprograma) está sendo executado, o programa que o chamou deixa temporariamente de ser executado, e retoma suas atividades após a conclusão da execução das rotinas do módulo.

### Benefícios da Programação Modular

Essa *filosofia modular* é notoriamente uma forma bem sucedida de se compor programas, sendo a base da elaboração de programas **NodeJS** e, principalmente, a base do sucesso do **UNIX**. Vejamos os seus benefícios:

* Facilidade de escrita;
* Facilidade de leitura;
* Facilidade para manutenção;
* Facilidade de reutilização de código;
* Programas mais curtos;
* Ganhos na capacidade de abstração dos problemas.

> Escreva programas que façam apenas uma coisa mas que façam de forma bem feita.
>
> Escreva programas que trabalhem juntos.
>
> Escreva programas que manipulem streams de texto, pois esta é uma interface universal.
>
> - Filosofia **UNIX**, por **Doug McIlroy**.

Agora que temos uma base sólida de como devemos pensar para criar nossos primeiros programas, vamos finalmente criá-los!

<h2><a id="instrucoes-e-estruturas-auxiliares">Instruções e Estruturas Auxiliares</a></h2>

As instruções são efetivamente os comandos, ou as ordens que iremos dar para o programa poder então executar determinada tarefa. Basicamente, programas não são nada mais do que sequências de instruções.

Além das *expressões* vistas anteriormente, temos algumas estruturas que facilitam **muito** nossa vida, e iremos vê-las agora:

### Estruturas de Decisão ou Estruturas Condicionais

Essa estrutura é utilizada para determinar um novo "caminho" que nosso código deve seguir. É mais fácil entender com essas ferramentas em mãos, então veja quais são elas:

#### `if` e `else`

Essa estrutura verifica **SE** (`if`) uma condição é verdadeira, então um trecho de código é executado, **SENÃO** (`else`), o código é executado por outro caminho.

**Exemplo**: Vamos fazer um programa que verificará a porcentagem lida de um determinado livro e mostrará uma mensagem de parabenização ou incentivo para o leitor.

Iremos usar além das estruturas de decisão, funções para separar cada parte do código, deixando-o reutilizável e com apenas uma responsabilidade. Mãos a obra!

<div data-gist-id="eaa588e45a39ce2abe93" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

Perceba que nossa função `calculaPorcentagem()` pode ser reutilizada em qualquer outro programa que necessite desse tipo de cálculo.

> Você pode usar somente a estrutura `if` para fazer algum tipo de avaliação. Nesse caso, caso a avaliação da expressão passada para o `if`seja verdadeira, ele executará o bloco de código relativo a tal, e caso a avaliação seja falsa, o código irá continuar a ser executado como se não existisse essa cláusula `if`.

Agora, vamos imaginar que tenhamos que criar notificações para o leitor a cada 25% da leitura realizada. Como vamos fazer?

É ai que entra a junção das duas estruturas apresentadas acima, formando uma *"nova"* chamada `else if`. A função dessa estrutura é apenas concatenar mais possibilidades em uma mesma avaliação.

Vamos fazer a nova etapa do programa com mensagens a cada 25% de leitura completada.

<div data-gist-id="9718be41fc105bdc09d2" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

Ótimo! Conseguimos agrupar as verificações sem ter que criar duas verificações para cada *etapa*.

#### `switch`

Pense que você queira realmente verificar muito detalhadamente o progresso da leitura, e retornar mensagens a cada **5%** de leitura concluída. Neste cenário, teremos que fazer muitas estruturas `if else if`, deixando o código com uma péssima legibilidade.

Para nos auxiliar, iremos conhecer uma nova estrutura condicional, ou estrutura de decisão, chamada `switch`. Com essa estrutura conseguimos deixar o código mais legível, veja como ela se parece:

<div data-gist-id="8be45c7d420e9a117375" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

De forma mais teórica, seu funcinamento acontece da seguinte maneira:

1. Declaramos o nome da estrutura: `switch`
2. Em seguida, inserimos uma expressão dentro de parênteses que será comparada com os casos dentro do bloco de código criado após essa estrutura.
3. Criamos um bloco de código com chaves.
4. Inserimos *casos* onde o valor na frente da palavra reservada `case` será comparado com o valor passado como *argumento* ao switch. Caso esse valor seja igual ao valor do *case*, então o bloco de código após os dois pontos `:` e antes da outra palavra chave `break` será executado.
5. Ao encontrar o comando `break`, a execução na estrutura `switch` se encerra e retorna para execução do programa principal, ou o sub-programa que o chamou.
6. Caso não seja encontrado nenhum *case* que coincida com o valor passado, o código após `default` será executado, e a execução de `switch` chegará ao fim.

Agora que sabemos como utilizar a estrutura `switch`, vamos adaptar nosso código anterior fazendo a alteração para imprimirmos uma mensagem para o usuário do nosso programa a cada 5% de leitura completada.

<div data-gist-id="e6163f776b820cc7d846" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

**Perfeito!** Agora conhecemos mais uma estrutura do JavaScript que nos auxilia na resolução de problemas cotidianos.

No próximo capítulo concluiremos os assuntos restantes com mais exemplos para fechar este nosso ciclo de estudos.

Bons estudos e até breve!