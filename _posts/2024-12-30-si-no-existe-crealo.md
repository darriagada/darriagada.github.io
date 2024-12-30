---
layout: post
title: Si no existe, créalo
excerpt: Cuando necesitas resolver algo y terminas armando más de la cuenta.
featuredimage: true
hero:
  size: wide
  src: /posts/diy_hero2x.png
  caption: 
---

El trabajo tiene muchos procesos repetitivos que se vuelven tediosos.

Hoy tenemos IA y herramientas que nos permiten agilizar estos procesos de alguna manera y la verdad no tengo nada en contra de estos métodos, sin embargo, yo sigo siendo _old school_ y me gusta tener la excusa para poner a prueba mis habilidades de programador amateur cada vez que pueda.

Estas son las **3 herramientas que desarrollé en mi paso por Compraquí** para hacerme la vida más fácil a mí y a mi equipo.

## Elimina enlaces en tus mailings ✂️
🌎 [Visitar sitio](https://darriagada.com/mata-links/){:target="_blank"} | 🧰 [Código de fuente](https://github.com/darriagada/mata-links){:target="_blank"}

Cuando trabajas en instituciones bancarias, es un hecho que **los enlaces están tajantemente descartados** por el riesgo a que se generen estafas o phishing. Es algo que debes tener presente cuando toca diseñar un mailing nuevo.

{% include full_img.html id="Toolset" figcap="https://darriagada.com/mata-links/" image="hero_url_file2x.png" %}

Pensaba, debería existir una herramienta para "matar" enlaces y evite la necesidad escribir códigos cada vez. Así que, armé algo muy rápido que deconstruye la URL para evitar que se genere automáticamente.

```
// El loop busca estos elementos
www. 
.com
.cl 
.org
.net
etc
```

> 👀 Desgraciadamente esto no es amigable para el usuario y es una pésima práctica de usabilidad, pero cuando no hay soluciones para evitar estos ataques, _tienes que improvisar._

## Adjuntos simples en Marketing Cloud 📎
🌎 [Visitar](https://darriagada.com/mkt-adjunto/){:target="_blank"} | 🧰 [Código de fuente](https://github.com/darriagada/mkt-adjunto){:target="_blank"}

Marketing Cloud es un bodrio. **Seamos honestos.**

A la hora de adjuntar archivos complementarios en tu correo, no es tan simple como presionar un botón y punto. Debes escribir un jeroglífico de variables que ni Indiana Jones podría descifrar:

```
%%=AttachFile("ContentBuilder","395e5926-d91f-4b88-a6a0-c4d66dd29bff","Documento de Prueba.pdf")=%%
```

{% include full_img.html id="Toolset" figcap="https://darriagada.com/mkt-adjunto/" image="hero_mtk_file2x.png" %}

Para evitar hacer esa tarea tediosa de recordar ese jeroglífico, la idea fue agilizar el proceso y llenar los campos con los datos solicitados y listo. Este genera de forma automática la variable para copiar y pegar.


## Conoce tus comisiones 💰
🌎 [Visitar](https://darriagada.com/calc/){:target="_blank"} | 🧰 [Código de fuente](https://github.com/darriagada/calc){:target="_blank"}

Si estás emprendiendo, obviamente te importa saber cómo funcionan las comisiones de tus ventas. Pero seamos honestos, muy pocos servicios son claros o simples para explicar sus números. Yo quiero saber de forma clara, **cuánto voy a recibir a cambio.**

{% include full_img.html id="Toolset" figcap="https://darriagada.com/calc/" image="hero_calc_file2x.png" %}

De esta forma, tomé un archivo Excel que tenía los valores y lo transcribí a un ``Javascript`` simple que calcula automáticamente los montos en tiempo real para los productos de Compraquí.

Las comisiones están pre-definidas en el código, por ejemplo:

```
let debito = 1.29;
let credito = 1.59;
let prepago = 1.44;
```


## ¿Qué hago con esto?
Estas herramientas son un Frankenstein, así que, puedes ver el código de cada uno, copiar, etc. Todas están bajo la [licencia MIT](https://choosealicense.com/licenses/mit/){:target="_blank"}, que básicamente te invita a que experimentes todo lo que quieras y adaptes el material como quieras.

Veamos qué desafíos y/o herramientas nuevas trae este 2025.