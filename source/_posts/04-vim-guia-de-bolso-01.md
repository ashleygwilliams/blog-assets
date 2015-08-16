title: Vim Guia de Bolso - parte 1
date: 2014-02-17 18:48:00
tags: vim
---

![vim](http://i.imgur.com/I2iaV4k.jpg)

Neste primeiro post vamos sintetizar os comandos básicos necessários para um pouco de diversão com este fantástico editor de textos.

Se você não conhece nada sobre o Vim, após a leitura deste guia recomendo que comece pelo tutorial contido no próprio editor, pois este artigo é uma síntese dos 3 primeiros módulos lá contidos, com alguns bônus no fim. Para acessá-lo, digite no seu terminal o seguinte comando, aperte *enter* (após a instalação do **vim**, obviamente) e divirta-se =) 

<pre><code>vimtutor</code></pre> 

Além deste material, alguns outros materiais de referência podem ser encontrados [aqui](https://github.com/ericdouglas/dev-log/blob/master/resources/workflow.md#vim).

Vamos as mágicas =D

### Engatinhando no Terminal hahaha

* <code>h</code> move o cursor para a esquerda
* <code>j</code> move o cursor para baixo
* <code>k</code> move o cursor para cima
* <code>l</code> move o cursor para direita

### Abrir/fechar/salvar aquivo

* <code>:q</code> fecha o arquivo
* <code>:q!</code> fecha o arquivo mesmo sem ter salvo as alterações
* <code>ZZ</code> ou <code>:wq</code> salva e fecha um arquivo

### Deletando palavras e linhas

* <code>dw</code> deleta até o fim da palavra, incluindo o espaço
* <code>de</code> deleta até o fim da palavra, NÃO incluindo o espaço
* <code>d$</code> deleta até o fim da linha

### Operadores e Movimentos

* <code>d</code> é o **operador** deletar
* <code>w</code> é o **movimento** do cursor até o início da palavra seguinte
* <code>e</code> é o **movimento** do cursor até o fim da palavra, e depois até o fim da palavra seguinte
* <code>b</code> é o **movimento** do cursor até a palavra anterior (pontuação é considerado uma palavra)
* <code>$</code> é o **movimento** do cursor até o fim da linha
* **OBS**: aperte os comandos de movimento para navegar pelo arquivo

### Contador de Movimento

**dica**: digitando um número antes de um movimento faz com que ele se repita *n* vezes.

* <code>2w</code> move o cursor 2 palavras à frente
* <code>3e</code> move o cursor para o fim da terceira palavra adiante
* <code>0</code> move o cursor para o início da linha.

### Deletando mais conteúdo com Contadores

* <code>d3w</code> com o cursor sobre a primeira letra da palavra, este comando deletará a mesma mais as duas palavras seguintes
* <code>d2e</code> deleta a palavra com o cursor em cima e a próxima, mas deixa um espaço a mais (recomendado usar com o operador <code>w</code>)
* <code>5dd</code> o operador <code>dd</code> faz com que se delete uma linha inteira. Logo, utilizando um contador, ele irá deletar **n** linhas =)

### Desfazendo Ações

* <code>u</code> desfaz última ação
* <code>U</code> restaura as alterações na linha inteira
* <code>ctrl r</code> refaz os comandos (desfaz os undo's)

### Comando Put

* <code>p</code> insere a última deleção (<code>dd</code>). O texto será inserido **abaixo** da linha de onde o cursor estiver.

### Replace

* <code>rx</code> troca o caracter sob o cursos por "x". Digitando <code>ra</code>, será trocado por "a", e assim sucessivamente.

### Operador Change

* O operador  <code>c</code> trabalha como o <code>d</code> delete, porém <code>c</code> deleta e altera para modo de inserção.
* <code>cw</code> altera toda a palavra, ou parte dela se o cursor estiver posicionado depois do início
* <code>c$</code> altera toda a linha a partir de onde o cursor estiver.

### Bônus: Múltiplas telas

* <code>:e</code> edita outro arquivo
* <code>:split nomedoarquivo</code> divide a tela e abre outro arquivo
* <code>ctrl-w ctrl-w</code> Pressionando duas vezes "ctrl w", você altera o arquivo em foco
* <code>ctrl-w_</code> Usando "ctrl w _" você maximiza a tela atual
* <code>ctrl-w=</code> Deixa todas as telas do mesmo tamanho
* <code>10 ctrl-w+</code> Aumenta em 10 linhas o tamanho da tela atual
* <code>:vsplit nomedoarquivo</code> divide a tela verticalmente e abre outro arquivo
* <code>:sview nomedoarquivo</code> divide a tela e abre o arquivo somente para leitura
* <code>:hide</code> esconde a tela atual
* <code>:only</code> deixa somente a tela atual aberta
* <code>:ls</code> mostra os *buffers* (processos/arquivos) atuais
* <code>:b 2</code> abre o buffer 2 na tela atual

### Bônus 2: Copiando e Colando

* Estes que são os atalhos mais conhecidos, são um pouco mais trabalhosos no Vim. Veja como funciona:
* <code>v</code> entra no modo Visual, assim você pode usar os comandos de movimento para selecionar a palavra/frase que deseja
* <code>" + y</code> você deve apertar estas 3 teclas, para então copiar o texto selecionado
* <code>" + p</code> cola o texto do *clipboard* a partir de onde o cursor estiver posicionado

Nos vemos na próxima =D

> Confira a **parte 2** deste guia **[aqui](http://ericdouglas.github.io/2014/03/08/07-vim-guia-de-bolso-02/)**.