---
layout: post
title: DIY Soundboard
excerpt: Tutorial para aprender a programar un soundboard simple.
featuredimage: false
hero:
  size: wide
  src: calc2x.png
  caption: El código de fuente de mi sitio.
---

Actualmente me encuentro trabajando en un mini sitio, algo así como un _soundboard_[^1] pero de sonidos antiguos.
Aquí compartiré un pequeño tutorial sobre cómo puedes hacer tu propia versión con un poco de Javascript.

## Lo básico

Lo primero es definir nuestros componentes principales: **Un botón y un reproductor de audio HTML5.**

```
<audio id="player"></audio>
<button>Sonido</button>
```

Y luego, declarar sus identificadores en nuestro Javascript:

```
let soundButtons = document.querySelectorAll('[data-audio-source]');
let soundPlayer = document.querySelector('#player');
```

Si te das cuenta, cada botón invoca un atributo llamado ```data-audio-source``` el cual se encargará de asignar el sonido específico. Por ejemplo:

```
<button data-audio-source="sonido1.wav">Sonido 1</button>
```

Entonces un <code>addEventListener</code> nos ayudará a iniciar la lógica donde **cada botón presionado, este buscará el sonido asociado** y luego se reproducirá:

```
// Primero obtén el sonido, luego dale play
soundButtons.forEach(button => {
    button.addEventListener('click', () => {
        const soundFile = button.getAttribute('data-audio-source');
        playSound(soundFile);
    });
});
```


> Si el botón no tiene definido un atributo ```data-audio-source``` no se activará.


Finalmente, necesitamos definir la función ```playSound``` para manejar la reproducción de nuestros sonidos y a la vez evitar que se dupliquen múltiples instancias del mismo sonido:

```
// Reproduce el sonido desde el inicio en cada click
function playSound(soundFile) {
    soundPlayer.pause();
    soundPlayer.src = soundFile;
    soundPlayer.play();
}
```

## Afinando detalles
Lo último que puedes hacer es ocultar el reproductor de audio con CSS:

```
#player {
    display:none;
}
```

Aunque por temas de usabilidad, deberías **incluir un botón que detenga los sonidos.** Vamos a crear una función que silencie y reinicie el reproductor:

```
function stopSound(soundFile) {
    soundPlayer.src = soundFile;
    soundPlayer.pause();
    soundPlayer.currentTime = 0;
}
```

Y lo asociaremos a un botón adicional, donde podemos llamar la función:

```
<button onClick="stopSound();">Stop</button>
```

## Resultado

<iframe height="400" style="width: 100%;margin:1.2em auto;" scrolling="no" title="Botonera Sonidos" src="https://codepen.io/darriagada/embed/poMZYBJ?default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/darriagada/pen/poMZYBJ">
  Botonera Sonidos</a> by Diego (<a href="https://codepen.io/darriagada">@darriagada</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

Como lo ves, esta es una versión muy simplificada del código, pues hay más cosas que agregar como por ejemplo, asignarle una clase a cada botón activo, agregarle más colores o etiquetas, etc.

Estoy seguro que hay otras formas de resolver esto pero es la que mejor se adoptó para mi caso.

[^1]: Una soundboard es una mesa de botones con diversos sonidos para reproducir in-situ al resaltar una broma, un guiño, etc. Las soundboards están de moda gracias a streamers y podcasters. 