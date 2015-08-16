title: Engenharia de Software com JavaScript - 02. Engenharia e seu Real Significado
date: 2014-12-13 20:44:00
tags: 
  - engenharia de software
  - javascript
---

![Engenharia de Software e ECMAScript](http://i.imgur.com/ZAH0z8L.png)
ES \* ES = **E**ngenharia de **S**oftware \* **E**CMA**S**cript

## Tabela de Conteúdo

1. [Motivação](#1)
1. [Importante!](#2)
1. [O que é Engenharia?](#3)
1. [O que faz então um Engenheiro?](#4)
1. [Cientista x Engenheiro x Desenvolvedor](#5)
1. [Definindo Software](#6)
1. [Finalmente, a Engenharia de Software](#7)
1. [Conclusão](#8)
1. [Referências](#9)

## <a id="1">1.</a> Motivação

Agora iniciaremos, de fato, a construção deste material que visa dissolver a linha que separa o conhecimento teórico da experiência prática no campo da Engenharia de Software.

Neste processo iremos utilizar a linguagem **JavaScript**, que também pode ser chamada de **ECMAScript**.  Iremos criar todo o material usando a última versão da linguagem ( versão 6, codinome *Harmony*), que deve ser lançada oficialmente no meio do ano de 2015.

A escolha dessa linguagem é natural devido a sua **ubiquidade**, podendo ser usada para simples efeitos em um *hot site*, até o desenvolvimento de aplicações poderosas, tanto no lado do cliente como no servidor, além de aplicações mobile, sem esquecer de sua presença na área da robótica e por conseguinte na IoT (*Internet of Things*, ou *Internet das Coisas*).

## <a id="2">2.</a> Importante!

Para seu conhecimento, os tópicos apresentados no cronograma do artigo anterior foram cuidadosamente escolhidos, para que a informação apresentada sempre seja utilizada no tópico seguinte, gerando um fluxo contínuo do nosso desenvolvimento.

Iremos iniciar sempre com um embasamento conceitual sobre o tema que for ser estudado, seguido de exemplos práticos.

É **essencial** que você saiba como será conduzido o trabalho, para que possa ajudar a corrigir algo que esteja em desacordo, ou para que fique confortável e aproveite o conteúdo!

Apresentações feitas, vamos iniciar!

## <a id="3">3.</a> O que é Engenharia?

Sempre gosto de verificar a etimologia de uma palavra quando quero internalizar o seu conceito. Muitas vezes seu significado etimológico nos esclarece mais que sua própria definição no dicionário.

> **Etimologia**: Engenharia vem do latim “ingenium” e “ingeniare”, que pode ser resumido em talento natural, capacidade inata de inventar.

De forma mais atual, podemos encontrar uma definição de Engenharia da seguinte forma:

> A engenharia é a **ciência**, a **arte** e a **profissão** de adquirir e de aplicar os conhecimentos matemáticos, técnicos e científicos na criação, aperfeiçoamento e implementação de utilidades.

Vejam que por essa definição mais atual, podemos expandir nossos horizontes e considerar que:

**Arte**: é a parte da engenharia representada pelo talento natural da pessoa de inventar e solucionar problemas cotidianos;

**Ciência**: é a parte teórica, sendo adquirida mediante o estudo do cabedal científico existente (os bens intelectuais e morais adquiridos pelo estudo ou experiência na devida área);

**Profissão**: é a união da ciência com a prática, onde o indivíduo faz dessa combinação uma fonte de sustento.

Nessa conceituação, temos que ter em mente que **nem sempre** o profissional possui a **arte** a seu favor, pois isso está ligado a uma habilidade **inata** e também a uma certa paixão em exercer tal profissão, fato que não é unânime nos indivíduos em nenhuma profissão.

Além disso, a parte **científica** desta profissão também deve ser melhor entendida, pois o engenheiro muitas vezes atuará apenas **analisando** qual o melhor processo a ser usado, qual a melhor ferramenta, mas não no seu desenvolvimento, podendo não ter o conhecimento/habilidade necessária para a confecção das ferramentas/metodologias utilizadas, mas sim o conhecimento de como construir o produto final almejado.

Considerando essas ressalvas, e sabendo um pouco mais sobre o que define essa área do conhecimento, podemos tentar agora definir o que é “ser engenheiro”.

## <a id="4">4.</a> O que faz então um Engenheiro?

Sem nos alongarmos, podemos sucintamente definir que:

> Engenheiro é o indivíduo que, mediante uma habilidade inata de resolver determinados problemas (fator **não obrigatório**), embasado por conhecimentos téoricos e/ou práticos que comprovam a eficiência da sua solução (fator **obrigatório**), vende ou oferece suas soluções para a sociedade, que tem a sua vida facilitada pelos "engenhos", invenções, criados por este.

Veja que para ser considerado **Engenheiro**, e estar de fato fazendo **Engenharia**, a única coisa que deve ser obrigatoriamente considerada é o domínio do indivíduo sobre o tema. O quê isso significa? Significa que **qualquer** pessoa pode criar algo, mas o **engenheiro** cria aquele algo sabendo os prós e os contras daquela decisão/solução!

**Resumo**: o engenheiro faz o que tem para fazer de forma **consciente**!

Mas então para ser um engenheiro eu preciso saber de tudo que está envolvido no processo? Calma meu amigo, vou lhe explicar um pouco melhor no próximo tópico, acompanhe comigo!

## <a id="5">5.</a> Cientista x Engenheiro x Desenvolvedor

Creio haver um engano na definição e entendimento dos papéis de cada um nos processos que definem a criação de um novo produto.

Através de um exemplo claro, irei mostrar meu ponto de vista em relação ao papel do **cientista**, do **engenheiro** e do **desenvolvedor**, e isso poderá até lhe ajudar a definir qual das três atividades se parece mais com seu perfil.

**Imagine a seguinte situação**: Em uma empresa, a busca ao banco de dados estava muito lenta. Foi chamado um engenheiro para avaliar o problema e foi constatado que era necessário uma refatoração no código que fazia o processamento dos dados.

O engenheiro, após um estudo do problema, chegou a 3 possíveis soluções:

* O **algoritmo A** pode ser implementado em 1 dia (+ ou -), possuindo uma lógica relativamente simples, de fácil manutenção para novos colaboradores, e irá melhorar o tempo de retorno das buscas em 60%;

* O **algoritmo B** pode ser implementado em 5 dias (+ ou -), possuindo uma lógica um pouco complexa, exigindo um nível de conhecimento maior para quem for prestar a manutenção, e irá melhorar o tempo de retorno das buscas em 80%;

* O **algoritmo C** pode ser implementado em 15 dias (+ ou -), possuindo uma lógica bem complexa, exigindo um alto nível de conhecimento para quem for prestar a manutenção, mas irá melhorar o tempo das buscas em 94%.

Veja o papel do **engenheiro**:

* identificar o problema;
* buscar soluções para o problema;
* estimar o tempo para resolução de determinado problema, supondo cada solução encontrada;
* pontuar os prós e os contras de cada solução;
* levar em conta o nível de conhecimento da equipe que irá efetuar a modificação, equacionando também os futuros colaboradores que irão cuidar deste código.

Basicamente, isso é a tarefa do engenheiro, fazer uma análise geral do problema, depois ir aprofundando nas soluções mais interessantes, e por fim chegar a solução ideal para aquele caso específico.

Veja que todas essas tarefas são coisas que só podem ser **efetivamente** feitas por quem tem **consciência** do que está fazendo. E todas tem os **prós** e os **contras**.

### E onde fica o cientista nessa história?

Bom, o papel do cientista, nesse caso, foi o de desenvolver os algoritmos (e demais tecnologias utilizadas para criar o produto)!

Vejo que o cientista está ligado a área de pesquisas, e se dispõe a oferecer uma solução (mais ou menos genérica) para um determinado problema/conjunto de problemas.

Fica a cargo dos engenheiros e desenvolvedores utilizar essas soluções para resolver problemas práticos do dia a dia.

### Qual o papel do desenvolvedor, afinal?

O **desenvolvedor** será o responsável por seguir os passos definidos pelo **engenheiro**, implementando o código que resultará no produto final.

**Dúvida**: Então o engenheiro apenas "dita as regras", mas não põe a mão na massa?

**Resposta**: Depende! Pode ser que sim, pode ser que não. Naturalmente, por ter uma visão abrangente do processo, o engenheiro tende a ocupar cargos de gerenciamento, se afastando um pouco dos códigos. 

Vai depender muito do tamanho da empresa e da equipe envolvida, mas nada impede que o engenheiro também codifique!

### Pra mim é tudo igual!

Sem problemas você pensar isso amigo! De fato, na prática essas divisões são muito subjetivas.

Creio que a maior diferença entre estes 3 tipos de profissionais esteja na **mentalidade** de cada um, que vai definir até onde a pessoa se satisfaz com o seu conhecimento atual.

Resumindo:

* **Cientista**: irá sempre buscar criar coisas novas, mesmo que possam não ser utilizadas por ninguém. Grandes responsáveis pelos avanços tecnológicos.

* **Engenheiro**: visa a resolução de problemas cotidianos, empregando as melhores ferramentas/processos da forma mais otimizada possível.

* **Desenvolvedor**: participa da construção de soluções para os problemas de sua área, sem ter muitas responsabilidades e sem se preocupar com todas as variáveis do processo, seja por falta de experiência/conhecimento necessário para isso, ou por falta de interesse.

> **Mas por que tantas definições**? A cada passo, estamos criando o perfil do profissional que queremos ser ao fim dessa jornada. 
>
>É **importantíssimo** esse alinhamento para termos de forma clara em nossa mente o motivo de todo o esforço para aprender tais conteúdos!
>
> O motivo é: vamos ter **todas** as habilidades descritas acima ao fim deste material! =)

## <a id="6">6.</a> Definindo Software

Buscando a definição dessa palavra, encontramos na Wikipedia algo bem interessante e que nos ajuda a reforçar o papel da engenharia neste processo de confecção do software.

Vejamos a definição:

> "**Software** é uma sequência de instruções a serem seguidas e/ou executadas, na manipulação, redirecionamento ou modificação de um dado/informação ou acontecimento."

O ponto interessente que quero ressaltar é a parte final da introdução, que diz o seguinte:

> "Este produto passa por **várias etapas** como: análise econômica, análise de requisitos, especificação, codificação, teste, documentação, treinamento, manutenção e implantação nos ambientes."

Viram como isso está condizente com a nossa definição de engenharia/engenheiro?

Por enquanto isso é o que precisamos para prosseguir. A medida que formos desenvolvendo nossos **softwares**, iremos denominá-los de forma mais específica.

Vamos ao último tópico! 

## <a id="7">7.</a> Finalmente, a Engenharia de Software!

Agora que temos todos os conceitos bem definidos, podemos facilmente entender a definição original do termo *Engenharia de Software*, cunhada pelo professor alemão *Friedrich Ludwig Bauer*, que diz:

> "**Engenharia de Software** é a criação e a utilização de sólidos princípios de engenharia a fim de obter software de maneira econômica, que seja confiável e que trabalhe em máquinas reais."

Um ótimo paralelo de Engenharia de Software com Ciência da Computação pode ser visto na seguinte frase:

> A **Engenharia de Software** se concentra nos aspectos práticos da produção de um sistema de software, enquanto a **ciência da computação** estuda os fundamentos teóricos dos aspectos computacionais.

## <a id="8">8.</a> Conclusão

Com todos os tópicos expostos em mente, creio estarmos bem alinhados e com os conceitos necessários para nos guiar nessa incrível jornada.

Ao decorrer dos próximos artigos, podemos pontuar algo que talvez não tenha sido citado aqui, ou aprofundar um pouco melhor.

Para você que chegou até aqui, **muito obrigado** por investir seu tempo nessa leitura! Caso tenha alguma consideração a fazer, por favor, compartilhe-a conosco!

Em nosso próximo artigo, iremos falar sobre **Processos de Desenvolvimento de Software**, e definir qual será o processo que usaremos para criar os projetos práticos no [thothJS](https://github.com/thothJS).

> **ps**: [Neste post](https://www.facebook.com/groups/javascriptbrasil/permalink/749495901808772/) no grupo **JavaScriptBrasil** podemos encontrar uma explicação excelente feita pela [Ju Gonçalves](https://twitter.com/junspector) do que se é entendido por Engenharia/Engenheiro de Software no âmbito acadêmico.
>
> Recomendo a leitura para que você esteja ciente de como esse assunto é tratado "academicamente", pois pode clarear algumas coisas no seu entendimento pessoal de tudo que foi dito.

## <a id="9">9.</a> Referências

1. [Origem da Palavra Engenheiro](http://www.dicionarioetimologico.com.br/engenheiro/)
1. [Consultório Etimológico](http://origemdapalavra.com.br/site/pergunta/pergunta-612/)
1. [Engenharia](http://pt.wikipedia.org/wiki/Engenharia)
1. [Engineering](http://en.wikipedia.org/wiki/Engineering)
1. [Perfil profissional](http://fga.unb.br/software/perfil-profissional)
1. [Software](http://pt.wikipedia.org/wiki/Software)
1. [Engenharia de Software](http://pt.wikipedia.org/wiki/Engenharia_de_software)

> Confira a lista completa dos artigos desta série [aqui](http://ericdouglas.github.io/2014/12/06/engenharia-de-software-com-javascript-01-introducao/), na seção **cronograma**!