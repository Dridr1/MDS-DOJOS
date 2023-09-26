JavaScript é uma linguagem de programação amplamente utilizada em Web. Ela é uma linguagem interpretada, ou seja, não há necessidade de compilar o código para que ele rode no seu navegador. Na verdade, caso queira ter o seu primeiro contato com a linguagem, bastar abrir o console do seu navegador (F12) e brincar um pouco com a linguagem :)

Nesse bloco iremos introduzir a sintaxe da linguagem com conceitos básicos chave para programar na linguagem e também alguns métodos presentes em classes exclusivas de navegadores.

### Sintaxe

* Variáveis:
	O JavaScript é uma linguagem com tipagem dinâmica, ou seja, não há necessidade de especificar o tipo da variável. Mas é importante frisar que existem variáveis "naturais" e "não naturais". 

```javascript tipo de variáveis
// Variáveis naturais
// Boolean
let isTrue = true;

// Number
const num = 13;

// String
var textinho = "Doutor me explica por que é que as vezes quando eu fico parado...";

// Variáveis não naturais
// Objeto 
let eu = {
	nome: "Adriano",
	idade: 23
};

// Função
// Essa é interessante porque tem mais de uma forma de expressar
// A 1 é a que mais estamos acostumados a ver
function sayMyName(name){
	console.log(name);
}

// Ela também pode ser escrita como uma função anônima (também chamada de arrow funciton)
(name) => console.log(name);
// Ou até mesmo escrita como uma variável que vai guardar a função escrita como função anônima
const sayMyName = (name) => console.log(name); //Essa é minha favorita haha

// Date (de data, não daquele date lá que cê tá penando pra conseguir)
const date = new Date();

// RegExp
let pattern = /\d+/;

// Error
throw new Error("IIIIIIH RAPAZ, DEU RUIM!");
```

### JS e navegadores

Uma das melhores partes do JS é que ele tem um objeto que lida diretamente com o DOM. Com esse objeto nos conseguimos fazer todo tipo de coisa com nossa página estática!

Experimente abrir o console do seu navegador e ver a lista de possibilidades que temos ao digitar ```document.``` (lembra do ponto!).


### Selecionando elementos do DOM com JS

Utilizando scripts é possível selecionar elementos HTML utilizando métodos presentes no objeto ```
document``` . Sendo os principais métodos os:
*  document.getElementById
	Seleciona um objeto pelo seu id atribuído.
* document.getElementByClassName
	Seleciona um objeto pelo nome da sua classe.
* document.querySelector
	Seleciona qualquer objeto tanto pela classe quanto id. Mas nesse caso você precisa especificar qual é qual usando "#bananinha" ou ".bananinha". Esse método seleciona apenas um objeto.
* document.querySelectorAll
	Faz o mesmo do querySelector, só que seleciona todos os objetos que cumpram com a condição de nome de classe ou nome.

Exemplos de uso:
```html
<div id="mae" class="pato">quak quak quak quak</div>
<div id="pato1" class="pato">voltei!</div>
<div id="pato2" class="pato">voltei!</div>
<div id="pato3" class="pato">voltei!</div>
<div id="pato4" class="pato">voltei!</div>
<div id="pato5" class="pato"></div>
```

```javascript
let pato1 = document.getElementbyId("pato1");
const patos = document.querySelector(".pato");
const pato5 = document.querySelector("#pato5");
```

### Tá, mas faço o quê com isso agora?

Bom, agora que você tem o elemento selecionado você pode fazer o que quiser com ele, desde alterar atributos até mesmo seu conteúdo interno. Você pode estabelecer condições para ele mudar de cor, tamanho, conteúdo interno, ativar e desativar atributos, o que for possível fazer você pode.

## Desafio

Faça uma ToDo list usando os conhecimentos de HTML, CSS e JS adquiridos até agora!

Requisitos:
- Adicionar tarefa;
- Marcar como feita;
- Desmarcar como feita;
