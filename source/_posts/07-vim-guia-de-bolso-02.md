title: Vim Guia de Bolso - parte 2
date: 2014-03-08 11:50:00
tags: vim
---

![vim-parte-02](http://i.imgur.com/6OwF2Oy.jpg)

Neste post iremos concluir a síntese de comandos apresentadas no **vimtutor**, tendo uma boa base de comandos para uma edição digna de arquivos neste editor.

> Veja a **primeira parte** deste guia **[aqui](http://ericdouglas.github.io/2014/02/17/04-vim-guia-de-bolso-01/)**.

Iremos ver como: 

1. [Nos localizar no arquivo](#localizacao-e-status-do-arquivo)
2. [Encontrar palavras/expressões](#buscando-por-palavras)
3. [Substituir palavras/blocos de texto](#substituindo-palavras)
4. [Executar comandos externos ao ambiente de edição](#executando-comandos-externos)
5. [Salvar arquivos "como"](#salvando-como)
6. [Salvar trechos do arquivo](#salvando-como-parte-do-texto)
7. [Inserir conteúdo externo para o arquivo atual](#inserindo-conteudo-de-um-arquivo-externo)
8. [Entrar no modo de inserção de texto de outras formas](#abrindo-espaco-entre-duas-linhas)
9. [Modo de Substituição](#modo-de-substituicao)
10. [Copiar e colar texto](#copiando-e-colando-texto)
11. [Salvar preferências](#salvando-suas-preferencias)
12. [Agilizar a digitação de comandos e nomes de arquivos](#autocomplete-de-comandos)
13. [Continuar Aprendendo](#mais-referencias)

Sem mais delongas, vamos ao conteúdo =)

<h2><a id="localizacao-e-status-do-arquivo">Localização e Status do Arquivo</a></h2> 

* `ctrl g` informa a sua localização no arquivo.
* `G` leva o cursor para última linha do arquivo.
* `gg` leva o cursor para primeira linha do arquivo.
* `13 G` leva o cursor para linha 13. 

**ps**: Digitando qualquer número no lugar do 13, te leva para a linha digitada.

<h2><a id="buscando-por-palavras">Buscando por Palavras</a></h2>

* `/padrão` vai buscar por uma incidência da palavra *padrão* no texto. Troque *padrão* por qualquer outra palavra que você queira encontrar.
* `/palavra\c` com este comando, a busca somente nessa verificação irá trabalhar sem a diferenciação de maiúscula e minúscula. Substitua *palavra* pelo termo que você quiser procurar.
* `?padrão` busca por palavras na ordem inversa. Substitua *padrão* pela palavra que você deseja procurar.
* `n` vai para a próxima incidência da palavra buscada.
* `N` vai para a incidência anterior da palavra buscada.
* `*` *salta* entre palavras iguais. **Ex**: percorrer todas as `function` do código.
* `ctrl o` com este comando, você volta para as últimas posições no texto em que você esteve.
* `ctrl i` te leva para as posições mais recentes onde você esteve no texto.
* `:set ic` este comando configura a busca para ignorar diferenciação entre maiúsculas e minúsculas.
* `:set noic` desabilita o comando ic.

<h2><a id="substituindo-palavras">Substituindo Palavras</a></h2>

* `:s/aa/a` troca a primeira ocorrência de *aa* por *a*.
* `:s/aa/a/g` troca todas as ocorrências de *aa* por *a* da linha.
* `:s/aa/a/g` troca todas as ocorrências de *aa* por *a* da linha, porém agora será necessária a confirmação para cada troca.
* `:13,25s/a/...` troca todas as primeiras ocorrências de *a* por *...* entre as linhas 13 e 25 **inclusive** (digite o número das linhas que desejar no lugar destes números).
* `:13,25s/a/.../g` troca todas as ocorrências de *a* por *...* entre as linhas 13 e 25 **inclusive** (digite o número das linhas que desejar no lugar destes números).
* `:%s/termo1/termo2` troca a primeira palavra (termo1) **de todas as linhas do arquivo** pela segunda (termo2). Substitua termo1 e termo2 respectivamente para as palavras que você deseja achar e trocar. *Cuidado pois ele irá trocar todas as palavras encontradas 1x em cada linha!*
* `:%s/termo1/termo2/g` troca todas as palavras (termo1) do texto por *termo2*.
* `:%s/termo1/termo2/gc` troca todas as palavras (termo1) do texto por *termo2*, pedindo uma confirmação para cada troca.

<h2><a id="executando-comandos-externos">Executando Comandos Externos</a></h2> 

* `:!comando` Você pode executar qualquer comando que executa normalmente no seu terminal, apenas preceda o comando com `:!`, digite seu comando e aperte `enter`.

<h2><a id="salvando-como">Salvar "Como"</a></h2>

* `:w copia.txt` salva todo o conteúdo do arquivo atual para um outro com o nome `copia.txt`.

**ps**: Faça o teste deste comando, *salvando como* qualquer arquivo que você tenha. Para deletar a cópia após o teste, use o comando `:!rm copia.txt`

<h2><a id="salvando-como-parte-do-texto">Salvando "Como" Apenas uma Parte do Texto</a></h2>

Para salvar uma parte somente do texto atual para um outro arquivo, devemos seguir alguns passos:

1. Digite `v` para entrar no modo visual do Vim;
2. Use algum dos **seletores de movimento** - use os comandos `h j k l` ou as setas do teclado, ou qualquer comando de movimento para percorrer o arquivo e selecionar o texto, que ficará em destaque;
3. Digite `:` para inserir um comando (você irá ver na última linha do editor na frente dos dois pontos o seguinte `'<,'>`);
4. Agora digite `w nome-do-arquivo.txt`, sendo nessa hora escolhido o nome e formato que você quiser para seu novo arquivo.

**ps:** Confirme a criação do novo arquivo com o comando `:!ls`, verificando se o arquivo foi realmente criado.

<h2><a id="inserindo-conteudo-de-um-arquivo-externo">Inserindo Conteúdo de um Arquivo Externo</a></h2>

* `:r nomedoarquivo` com este simples comando, você insere o conteúdo de um arquivo externo no atual. O conteúdo será adicionado na linha abaixo da ocupada pelo cursor.

**Dica**: você pode usar este mesmo comando passando um comando externo, que também retornará algum texto.

**Ex**: `:r !ls` insere o nome dos arquivos do seu diretório atual no arquivo em questão.

<h2><a id="abrindo-espaco-entre-duas-linhas">Abrindo Espaço Entre Duas Linhas</a></h2>

* `o` insere uma linha **abaixo** da atual onde se encontra o cursor e entra no Modo de Inserção.
* `O` igual o comando anterior, porém insere uma linha **acima**.

### Inserindo Texto Depois do Cursor

* `a` com este comando você pode inserir texto **após** o posicionamento atual do cursor (muda para modo inserção).

<h2><a id="modo-de-substituicao">Substituir Texto no Modo de Substituição</a></h2>

* `R` posicione o cursor em cima do conteúdo a ser substituído, aperte este comando e digite o novo texto.

<h2><a id="copiando-e-colando-texto">Copiando e Colando Texto</a></h2>
 
Alguns passos para se copiar e colar texto com tranquilidade:
 
1. `v` entre no modo visual e selecione o texto a ser copiado;
2. `y` este comando copia o texto selecionado;
3. `p` cola o texto selecionado à frente de onde o cursor estiver.
 
* `yw` posicione o curso no início de uma palavra e utilize este comando para copiá-la.
* `y$` copia toda a linha a partir de onde o cursor está posicionado.

<h2><a id="salvando-suas-preferencias">Salvando suas Preferências</a></h2>

* `:e ~/.vimrc` Este comando abre seu arquivo `.vimrc`, onde você pode deixar suas configurações pessoais salvas. 

**ps**: Veja a palestra indicada no fim deste post para saber mais sobre este assunto (no início da palestra já é abordado este tema).

<h2><a id="autocomplete-de-comandos">AutoComplete de Comandos</a></h2>

* Digitando `:`, a primeira letra de um comando e apertando `ctrl d`, o vim irá mostrar uma lista dos comandos que iniciam com esta letra.
* Digitando `:`, a primeira letra de um comando e apertando `<tab>`, o Vim irá completar o comando para você. Apertando `<tab>` várias vezes, você irá passar por todos os comandos que iniciam com o texto digitado. 
* O mesmo vale para o *autocomplete* de nome de arquivos. 

**Ex**: `:edit arq <tab>` - caso você tenho um arquivo denominado `arquivo.txt` no seu diretório, o nome do mesmo será completado pelo vim.

<h2><a id="mais-referencias">Mais Referências</a></h2>

Bom, chegamos ao fim da síntese dos comandos mostrados no **vimtutor**. A partir de agora, é começar a praticar todos estes comandos até que os mesmos fiquem naturais de se usar...

Dentro do próprio vim, você pode digitar `:help` (e apertar `<enter>`) para ver uma lista com vários arquivos de ajuda contidos no próprio editor.

Além deste material, você pode dar uma olhada na seção do [Dev-Log](https://github.com/ericdouglas/dev-log#vim) específica do Vim, onde coloco os links de referências dos meus estudos.

Recentemente, tivemos uma [palestra](https://www.eventials.com/pinceladasdaweb/vim-para-front-end/) e [dois](http://www.pinceladasdaweb.com.br/blog/2014/02/17/como-instalar-plugins-no-vim/) [artigos](http://www.pinceladasdaweb.com.br/blog/2014/02/18/plugins-do-vim-para-frontend/) excelentes do [Marco Bruno](https://twitter.com/marcobrunobr) sobre o Vim. Material obrigatório para quem quiser iniciar seus estudos deste editor.

Até a próxima! =)