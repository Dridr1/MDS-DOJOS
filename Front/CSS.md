Sabemos criar documentos com HTML, mas convenhamos né: tá feio demais esse negócio.
Agora iremos aprender a deixar nossas páginas com mais :star: :star2: estilo :star2: :star: :D 

### **O que é CSS?**

CSS significa Cascading Style Sheets, ou Folhas de Estilo em Cascata. É uma linguagem de marcação que define a aparência e o layout de elementos HTML. O CSS é usado para controlar o tamanho, a cor, a fonte, a posição e outros aspectos visuais de uma página web.

### **Como funciona o CSS?**

O CSS funciona definindo regras que associam propriedades a elementos HTML. As regras CSS são escritas em arquivos separados chamados folhas de estilo. Essas folhas de estilo podem ser incorporadas a um documento HTML ou referenciadas por ele.

### **Propriedades CSS**

As propriedades CSS são usadas para controlar os aspectos visuais de um elemento HTML. Algumas propriedades CSS comuns incluem:

- **Cor:** define a cor do texto ou do fundo de um elemento.
- **Fonte:** define o tipo de fonte, o tamanho da fonte e o estilo da fonte de um elemento.
- **Tamanho:** define o tamanho de um elemento.
- **Posição:** define a posição de um elemento na página.
* **Alinhamento:** define o alinhamento do conteúdo de um elemento.
* **Margens:** define o espaço entre um elemento e seus vizinhos.
* **Bordas:** define a aparência das bordas de um elemento.
* **Transições:** define como as propriedades CSS mudam ao longo do tempo.
* **Animações:** define como as propriedades CSS mudam de forma contínua.
* **Estrutura do CSS**

Uma regra CSS consiste em uma propriedade e um valor. A propriedade é o que você deseja controlar, e o valor é o que você deseja que aconteça.

Por exemplo, a seguinte regra CSS define a cor do texto para vermelho:

```CSS
p {
  color: red;
}
```

### **Atribuição de regras CSS**

As regras CSS podem ser atribuídas a elementos HTML de várias maneiras:

- **Incorporação:** as regras CSS são incluídas diretamente no documento HTML.
- **Referência:** as regras CSS são referenciadas por um documento HTML.
- **Herança:** as regras CSS são herdadas de elementos pai.

## **Classes e Ids**

Classes e ids são dois tipos de seletores CSS que permitem direcionar regras de estilo a um ou mais elementos HTML. A principal diferença entre os dois é que **classes podem ser usadas em vários elementos, enquanto ids devem ser únicos**.

### **Classes**

Classes são usadas para aplicar estilos a um grupo de elementos. Por exemplo, você pode usar uma classe para definir o estilo de todos os cabeçalhos de uma página web.

Para usar uma classe CSS, adicione um atributo `class` ao elemento HTML com o valor da classe. Por exemplo:

HTML

```html
<h1 class="titulo">Este é um cabeçalho</h1>
<h2 class="titulo">Este é outro cabeçalho</h2>
```

Em seguida, crie uma regra CSS que use o seletor de classe para aplicar estilos aos elementos. Por exemplo:

CSS

```css
.titulo {
  color: red;
  font-size: 20px;
}
```

Esta regra CSS definirá a cor do texto e o tamanho da fonte para todos os elementos com a classe `titulo`.

### **Ids**

Ids são usados para aplicar estilos a um único elemento. Por exemplo, você pode usar um id para definir o estilo de um botão específico em uma página web.

Para usar um id CSS, adicione um atributo `id` ao elemento HTML com o valor do id. Por exemplo:

HTML

```html
<button id="meu-botao">Clique aqui</button>
```

Em seguida, crie uma regra CSS que use o seletor de id para aplicar estilos ao elemento. Por exemplo:

CSS

```css
#meu-botao {
  background-color: blue;
  color: white;
}
```

Esta regra CSS definirá a cor de fundo e a cor do texto para o elemento com o id `meu-botao`.

**Exemplo de uso com HTML e CSS em arquivos separados**

Aqui está um exemplo de como usar classes e ids com HTML e CSS em arquivos separados:

HTML

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <title>Exemplo de classes e ids</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1 class="titulo">Este é um cabeçalho</h1>
  <h2 class="titulo">Este é outro cabeçalho</h2>
  <button id="meu-botao">Clique aqui</button>
</body>
</html>
```

CSS

```css
.titulo {
  color: red;
  font-size: 20px;
}

#meu-botao {
  background-color: blue;
  color: white;
}
```

Neste exemplo, a classe `titulo` é usada para definir o estilo dos dois cabeçalhos. O id `meu-botao` é usado para definir o estilo do botão.

Aqui está um exemplo de como o código HTML e CSS acima renderizaria no navegador:

```
Este é um cabeçalho
Este é outro cabeçalho
Clique aqui
```

## Desafio

Por que não enfeitar um pouco seu currículo? Tente também adicionar um foto.
Como sugestão, você pode pegar um layout de currículo na internet e tentar reproduzi-lo usando HTML e CSS!