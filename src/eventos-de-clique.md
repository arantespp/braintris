## Eventos no JavaScript

- Normalmente ao visitarmos páginas web executamos ações atráves de botões ,links ou elementos de ui. Como normalmente esses elementos clicáveis são manipulados através de eventos em JavaScript para podermos executar determinada funcionalidade.

- Um dos eventos mais utilizados é o `onclick` , que é executado quando o usuário clica em um elemento.

- Sintaxe básica do `onclick`:

```
<element onclick="function()">Clique here</element>
```

```
<button onclick="function()">Clique here</button>
```

Note que o atributo `onclick` é puramente JavaScript. O valor que ele recebe é a função que será executada já que ela é passada diretamente na tag de abertura.

Em JavaScript declaramos uma função chamando-a pelo nome e em seguida adicionamos parênteses após o identificador da função(o nome da mesma).

```
function() {
    // código
}
```

- Exemplo de evento onclick:

[Background-changer](https://github.com/biantris/10-PROJECTS-1-HOUR/blob/master/background-changer/script.js)

Basicamente esse projetinho tem como objetivo mudar a cor do background da página ao clicar no botão.

Vamos ver cada parte do código e entender como funciona.

Começando com o nosso código html:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🎨Background Changer🎨</title>
    <link rel="stylesheet" href="style.css" />
    <script src="script.js" defer></script>
</head>
<body>
    <button id="btn">🌈Change Me🌈</button>
</body>
</html>
```

Depois estilização:
```css
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;400;600&display=swap");

* {
    box-sizing: border-box;
}

body {
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: "Poppins", sans-serif;
    margin: 0;
    min-height: 100vh;
}

button {
    background-color: rebeccapurple;
    color: white;
    padding: 1rem;
    font-family: inherit;
    font-size: 1.2rem;
    box-shadow: 2px 2px 6px rgba(0, 0, 0, 0.2);
    border-radius: 5px;
    border: none;
    transition: transform 0.1s linear;
}

button:focus {
    outline: none;
}

button:active {
    box-shadow: 0;
    transform: translate(2px, 2px);
}
```
Resultado:
![background](https://user-images.githubusercontent.com/65451957/161579487-15b86308-99f2-4891-81d9-953f5a505de8.png)

Agora iremos adicionar o nosso evento onclick para mudar a cor do background da página:

```js
const btn = document.getElementById('btn');

btn.addEventListener('click', () =>{
    document.body.style.background = randomBg();
});

function randomBg() {
    return `hsl(${Math.floor(Math.random()
        * 360)}, 100%, 50%)`;
}
```

Primeiramente iremos adicionar a função `btn` onde será passada na tag html <button> e irá chamar o id `btn` que será o nosso botão.

Ao ocorrer o evento de clique será chamado o `addEventListener` que irá executar a função `ramdomBg` que irá retornar uma cor aleatória.

Resultado:
![Gravação-de-tela-de-03-04-2022-23_13_16](https://user-images.githubusercontent.com/65451957/161579581-734054f0-074e-4e36-a1df-980fac2e2c7e.gif)


