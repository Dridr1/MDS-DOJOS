Ok, vimos como fazer páginas bem legais usando HTML, CSS e JS. Mas isso não é tudo que se pode fazer usando essas tecnologias!!!

O JavaScript permite que você trabalhe com bibliotecas externas que podem ser instaladas por meio de um gerenciador de pacotes chamado npm. Para usar o npm é necessário ter o Node, um runtime de JavaScript, instalado em sua máquina. 

Para instalar o Node e gerenciar múltiplas versões dele instalado eu recomendo fortemente que você use o nvm (Node Version Manager). Para instalar ele basta seguir o readme do repositório do projeto aqui nesse [link]([nvm-sh/nvm: Node Version Manager - POSIX-compliant bash script to manage multiple active node.js versions (github.com)](https://github.com/nvm-sh/nvm)) . Ah, ele funciona somente em sistemas Unix like, ou seja: distros Linux e MacOS. Mas caso queira usar ele no Windows, basta usar o WSL para rodar uma camada de compatibilidade do Linux no Windows ([doc do WSL aqui!](https://learn.microsoft.com/en-us/windows/wsl/)). 

### Como settar meu projetinho React?

Para criar um novo projeto React você vai precisar apenas do npm disponível em sua máquina e executar um pacote chamado create-react-app com o npx (um executor de pacotes integrado ao npm). 

- Passo 1:
	Escolher onde o projeto será criado:
```shell
// aqui irei criar na minha pasta Documents
cd Documents
```
- Passo 2:
	Executar o create-react-app já com o nome do seu projeto
```shell
npx create-react-app bananinha
``` 
- Passo 3:
	Após executar esse comando e baixar metade da internet, teremos um projeto básico de React que já pode ser executado!. Para isso, iremos entrar na pasta do projeto e executar com o npm:
```shell
cd bananinha
npm run start
```

Tcharam!! Temos um projetinho React criado!!! Vamos dar uma olhada no que foi criado:

```
.
└── bananinha/
    ├── node_modules
    ├── public/
    │   ├── favicon.ico
    │   ├── index.html
    │   ├── logo192.png
    │   ├── logo512.png
    │   ├── manifest.json
    │   └── robots.txt
    ├── src/
    │   ├── App.css
    │   ├── App.js
    │   ├── App.test.js
    │   ├── index.css
    │   ├── index.js
    │   ├── logo.svg
    │   ├── reportWebVitals.js
    │   └── setupTests.js
    ├── package.json
    └── package-lock.json
```

Essa é a pastinha que iniciamos o nosso projeto. Muito do que tem aí não vai ter tanta utilidade pro nosso projeto, então já podemos começar fazendo uma limpa e deixar nosso projeto assim:
```
.
└── bananinha/
    ├── node_modules
    ├── public/
    │   ├── favicon.ico
    │   ├── index.html
    │   ├── logo192.png
    │   ├── logo512.png
    │   ├── manifest.json
    │   └── robots.txt
    ├── src/
    ├── package.json
    └── package-lock.json
```

A pasta "src" será o nosso maior ponto de ação, é nela que todos os nossos componentes ficarão armazenados.

### E por falar em componentes, toma aqui um pouco de componentização

Vimos que conseguimos fazer estruturas em HTML de forma dinâmica usando JavaScript, mas o que ainda não vimos é que é possível tornar mais dinâmico ainda utilizando algo que no React chamamos de componentes. A componentização é uma forma de tornar ainda mais fácil reutilizar estruturas HTML.
Por exemplo:

```html
<div id="cat-card">
	<h1>Cats</h1>
	<h2>I Love Cats</h2>
	<p>Run up and down stairs sweet beast curl up and sleep on the freshly laundered towels, for pee in the shoe i like to spend my days sleeping and eating fishes that my human fished for me we live on a luxurious yacht, sailing proudly under the sun, i like to walk on the deck, watching the horizon, dreaming of a good bowl of milk. Bite nose of your human eat from dog's food so meow in empty rooms and furrier and even more furrier hairball. Make it to the carpet before i vomit mmmmmm eat the fat cats food so sugar, my siamese, stalks me (in a good way)</p>
</div>
```

Se eu quiser reaproveitar toda essa estrutura dentro da div com id="cat-card" eu teria que fazer isso com JS puro, usando funções e blá blá blá. É possível, mas sabemos que vai levar um tempinho. Com React não!!! Podemos simplesmente chamar novamente o componente criado. Tudo isso funciona como se estivéssemos criando uma nova tag HTML, como se se pegássemos uma tag vazia e abríssemos ela pra construir ela do zero. 
De forma componentizada ficaria:

```jsx
const CatCard = () => {
return(
	<div>
	<h1>Cats</h1>
		<h2>I Love Cats</h2>
		<p>Run up and down stairs sweet beast curl up and sleep on the freshly laundered towels, for pee in the shoe i like to spend my days sleeping and eating fishes that my human fished for me we live on a luxurious yacht, sailing proudly under the sun, i like to walk on the deck, watching the horizon, dreaming of a good bowl of milk. Bite nose of your human eat from dog's food so meow in empty rooms and furrier and even more furrier hairball. Make it to the carpet before i vomit mmmmmm eat the fat cats food so sugar, my siamese, stalks me (in a good way)
		</p>
	</div>
)
}
```

"Tá, você adicionou a estrutura dentro de uma função. Qual a vantagem disso?"

Agora podemos dinamizar mais ainda essa estrutura usando o que chamamos de "props", as nossas propriedades de de atributos em tags HTML! 
Por exemplo, se eu quiser reutilizar minha estrutura com um texto diferente:

```jsx
const CatCard = (props) => {
return(
	<div>
	<h1>{props.title}</h1>
		<h2>{props.subtitle}</h2>
		<p>{props.paragraph}</p>
	</div>
)
}
```

E se quisermos enxugar mais ainda isso pra não ficar chamando o objeto toda hora podemos usar desmontar esse objeto da seguinte forma. Também já vamos exportar nosso componente:

```jsx
const CatCard = ({title, subtitle, paragraph}) => {
return(
	<div>
	<h1>{title}</h1>
		<h2>{subtitle}</h2>
		<p>{paragraph}</p>
	</div>
)
}

export default CatCard;
```

Olha só como fica mais show de bolinha!

Tá, mas e agora, como fazemos pra colocar nosso componente pra renderizar?

Easy bizi lemon squeezy! Basta importar o componente criado no componente principal da nossa aplicação, geralmente um componente chamado "App":

```
.
└── bananinha/
    └── src/
        ├── App.js
        ├── index.js
        └── CatCard.js
```

App.js
```jsx
import CatCard from "./CatCard.js";

const App = () => {
	return(
		<CatCard
			title="Cats"
			subtitle="I love Cats!"
			paragraph="Run up and down stairs sweet beast curl up and sleep on the freshly laundered towels, for pee in the shoe i like to spend my days sleeping and eating fishes that my human fished for me we live on a luxurious yacht, sailing proudly under the sun, i like to walk on the deck, watching the horizon, dreaming of a good bowl of milk. Bite nose of your human eat from dog's food so meow in empty rooms and furrier and even more furrier hairball. Make it to the carpet before i vomit mmmmmm eat the fat cats food so sugar, my siamese, stalks me (in a good way)"
		/>
	)
}
```

index.js
```jsx
import React from "react";
import ReactDOM from "react-dom/cliente";
import App from "./App.js";

const root = ReactDOM.createRoot(document.getElementById('root'));

root.render(<App/>);
```

Com isso, nosso componente criado foi adicionado e agora renderizado!!!

### useState e a introdução ao mundo mágico dos React Hooks

Sempre que algo é renderizado e alterado no nosso navegador usando uma stack mais simples (html, css, js) a página inteira é atualizada. Isso porque quando fazemos uma alteração todo o DOM precisa ser atualizado. O React é um tiquinho diferente! Primeiro que (pasmem) aquilo que colocamos no retorno das funções dos nossos componentes não é HTML! é uma linguagem de marcação chamada JSX. Segundo que o React renderiza nossos componentes em um ambiente chamado _Virtual DOM_! Esse ambiente permite que o Reac renderize apenas o necessário, inclusive pequenas alterações!
Mas se você faz alterações em partes dos componentes simplesmente alterando o valor das props ou mesmo usando funções dentro do componente você vai perceber que ele simplesmente não vai alterar o valor!!! 
Isso ocorre porque precisamos "avisar" para o React que ele precisa alterar algo no virtual DOM! Para dar esse "aviso" utilizamos algo chamado de hook, e o primeiro que iremos aprender agora é um que altera valores no DOM. 

Nesse exemplo criaremos um contador que cada vez que clicamos no botão o valor será atualizado em +1 unidade.

```jsx
import React, { useState } from 'react';

const Counter = () => {
	// O useState é um array que pode ser dividido em duas variáveis
	// na posição 0 fica nosso valor
	// na posição 1 fica uma função que altera o nosso valor
	
    const [count, setCount] = useState(0);
	// no atributo onClick precisamos de uma função que chamamos de handler
    const increase = () => setCount(count + 1);

    return (
    <>
        <div>Contador</div>
        <div>{count}</div>
        <button onClick={increase}>+1</button>
    </>
    )
}

export default Counter

```

#### Desafio desse módulo:

* Crie um contador que pode adicionar e diminuir o valor da nossa contagem!
* Para isso você vai precisar de outro handler pra outro botão
* Não se preocupe em estilizar!



### Routing

Ok, criamos uma página, beleza. Mas e se eu quiser criar várias e enfiar elas na minha aplicação???
Então, se você enfiar vários componentes dentro do nosso componente App, você vai perceber que...
.
.
.
.
....
Deu ruim!!!
Quebrou!!!
E isso acontece porque pra trabalhar com múltiplas páginas precisamos de um recurso de react chamado react-router-dom

Para utilizarmos a ferramenta de rotas primeiro precisamos instalar as dependências necessárias:

```
npm i react-router-dom
```

Existem alguns componentes (sim! Componentes!) importantes que vamos utilizar para rootear nossa aplicação. São eles:

- `<BrowserRouter/>` 
- `<Routes/>`
- `<Route path={} element={} />`
- `<Link to={} />`

Também é interessante ter uma página que vai indexar nossas outras páginas!
(Setter é o nome que dei para o desafio de useState! Coloque o seu ou qualquer outra página genérica caso queira testar).
```jsx
import React from 'react'
import { Link } from 'react-router-dom'

const Menu = () => {
  return (
    <div>
        <h1>Menu:</h1>
        <div>
            <Link to="/counter">Counter</Link>
        </div>
        <div>
            <Link to="/setter">Setter</Link>
        </div>
    </div>
  )
}

export default Menu;
```

Agora vamos atualizar nossa página App com o roteamento!
```jsx
import { BrowserRouter, Route, Routes } from 'react-router-dom';
import Counter from './Counter';
import Menu from './Menu';
import Setter from './Setter';

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path='/' element={<Menu/>} />
        <Route path='counter' element={<Counter/>}/>
        <Route path='setter' element={<Setter/>}/>
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

Com isso finalmente podemos criar páginas simples sem estilização...

### ... Mas e os estilos hein?

Bom, as facilidades do React não param por aí! Existem várias libs auxiliares que nos ajudam a estilizar nossas Single Page Applications. Vou focar aqui em um específico que é amplamente utilizado no mercado e, como já vimos CSS, ele vai ser o mais tranquilo de pegar.
Contemplem o:

### Styled Components!

Antes de mais nada, vamos instalar as dependências!

`npm i styled-components`

Agora podemos criar componentes simples já estilizados!

Por exemplo, quero que meu título seja vermelho:
```jsx
const Title = styled.h1`
    color: red;
`
```

Prontinho! Temos um novo componente que é uma tag `<h1></h1>` que a fonte será vermelha!

O legal disso é que não ficamos apenas limitados a títulos. Podemos estilizar divs para criar containers com bordas e tudo o que sua imaginação e seu conhecimento em CSS permitirem!