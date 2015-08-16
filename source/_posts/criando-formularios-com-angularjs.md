title: Criando Formulários com AngularJS
date: 2015-01-25 08:30:00
tags: 
  - angularjs
---

![]()

Para sistemas que tenham muitos formulários, com certeza AngularJS é uma ótima pedida, pois diminui bastante as partes burocráticas, nos ajudando tanto na **validação** quanto **recuperação** das informações inseridas.

As validações são baseadas nos estados dos elementos do formulário, estados estes que o Angular coloca para que possamos trabalhar com as classes CSS para mostrar ao usuário os campos certos e errados, e para que tenhamos controle do estado do formulário antes de enviar as informações ao servidor. 

Os estados são:

  * `$valid` - campo válido
  * `$invalid` - campo inválido
  * `$pristine` - campo "virgem" (que ainda não foi modificado)
  * `$dirty` - campo já modificado (mesmo que esteja em branco, se já foi inserido algo, ele ainda terá essa classe)
  * `$error.tipoDoErro` - estado informando que existe algum erro. Substitua `tipoDoErro` pelo nome do atributo que o Angular deve verificar
  * `$submitted` - quando o form for submetido, essa classe será adicionada
  * **ps**: Atributos aceitos *built-in*: `email`, `max`, `maxlength`, `min`, `minlength`, `number`, `pattern`, `required`, `url`, `date`, `datetimelocal`, `time`, `week`, `month`

## Elementos Essenciais

Estes são os principais elementos que você irá usar na criação dos seus formulários.

### 1. `<form>`

  * `novalidate` - evita a validação padrão do HTML5, pois faremos nós mesmos essa tarefa.
  * `name="nameForm"` - usado para o Angular enxergar os campos do *form*.
  * `ng-submit="vm.save()"` - ação que vai acontecer quando o usuário submeter o *form*.

### 2. `<div>`

Elemento que vai encapsular o `<input>` para fins de posicionamento e estilo da página.

Podemos usar o `ng-class` para verificar se campo do formulário está preenchido de forma incorreta, ou se não é mais "virgem" (`$pristine`), ou se já foi "usado" (`$dirty`).

Nossa validação ficaria assim:

<div data-gist-id="4946075be091cb5e2636" data-gist-file="validation.html" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

### 3. `<input>`

Aqui será onde, de fato, o Angular vai olhar para dar o veredito final e dizer se seu formulário está preenchido de forma correta ou não.

  * `name="inputName"` - quando formos nos referenciar a esse campo, é através do `name` do `<form>` mais o `name` do `<input>` que o Angular vai olhar.
  * `ng-model` - é através desta diretiva que você vai ligar o valor do campo ao objeto que será submetido.
  * **Dica**: acho interessante manter o mesmo nome em `name` com a chave usada no `ng-model`, para manter um padrão.

### 4. `<p>`

Você pode colocar frases de notificação para seus usuários aqui. Assim, apenas quando determinada condição for satisfeita, essas notificações irão aparecer.

<div data-gist-id="4946075be091cb5e2636" data-gist-file="p.html" data-gist-hide-footer="true" data-gist-hide-line-numbers="true"></div>

Mostra uma mensagem para o usuário caso a senha digitada seja menor que o mínimo estipulado no `<input>` *linkado* com `formName.inputName`

### 5. `ng-disabled`

Caso algum campo do form esteja inválido, o form também estará, então podemos usar o ng-disabled para desativar a possibilidade de envio do formulário.

  * `ng-disabled="formName.$invalid"`

### 6. Exemplo

Vamos juntar todas essas informações e criar nosso formulário!

* [Source code](https://github.com/ericdouglas/ng-form-validation)
* [Live Example](http://ericdouglas.github.io/ng-form-validation/)


## Referências

O Angular te proporciona mais coisas, que podem ser conferidas nos links abaixos, mas estas demonstradas já cobrirão praticamente tudo que você precisa para criar um excelente formulário!

1. [form.FormController](https://docs.angularjs.org/api/ng/type/form.FormController)
1. [AngularJS Form Validation](https://scotch.io/tutorials/angularjs-form-validation)
1. [ng-input](https://docs.angularjs.org/api/ng/directive/input)