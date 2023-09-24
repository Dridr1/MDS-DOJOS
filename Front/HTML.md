Já vimos que os navegadores utilizam o HTML para renderizar páginas e que existem protocolos de transferência que enviam textos (e nisso, arquivos HTML) de um lugar para o outro utilizando o protocolo HTTP e TCP/IP. Mas afinal, como raios eu faço essas páginas que vão ser renderizadas no meu navegador? 

Pra começar, precisamos de um arquivo HTML:

```html index.html
<!DOCTYPE html> <!-- Arquiv informamos ao navegador que esse é um documento HTML a ser renderizado -->

<html lang="en"> 
<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Document</title>

</head>

<body>

</body>

</html>
```

Os documentos HTML são compostos por palavras reservadas inseridas de uma forma específica no documento. Essas palavras são escritas entre chevrons e precisam de uma abertura e um fechamento:

```html
<tag> abertura da tag
Conteúdo
</tag> fechamento da tag
```

Nesse documento que criamos temos algumas tags essenciais para que o navegador reconheça nosso documento HTML:
```html
<html></html> -> tag contendo todo o conteúdo do nosso documento HTML.

<head></head> -> tag com o cabeçalho do nosso documento.
	<meta> -> tag contendo configurações sobre nossa página, como o o conjunto de caracteres que usaremos (UTF-8, por exemplo) e configurações de escala da página.
	
	<title></title> -> título da nossa página (é o que aparece na aba do navegador)
<body></body> -> literalmente o "corpo" da nossa página. Onde o conteúdo será inserido
```

Com isso, conseguimos criar o nosso primeiro "Hello, World!" com HTML!
Experimente criar um arquivo index.html e inserir a tag `<h1></h1>` com o nosso "Hello, World!" dentro dela:
```html
<!DOCTYPE html>
<html lang="en"> 
<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Document</title>

</head>

<body>
	<div>Hello, World!</div>
</body>

</html>
```

Abra o arquivo com o seu navegador e tcharam!!! 
![[helloWorld.png]]

Com isso, vocês já serão capazes de ir atrás das tags HTML (SÃO VÁRIAS!!!) 
Alguns tópicos legais de se pesquisar:
- Tags semânticas
- Listas e listas ordenadas