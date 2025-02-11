---
layout: post
title: Jekyll Includes
excerpt: Tutorial para aprender a ocupar los includes de Jekyll.
featuredimage: true
hero:
  size: wide
  src: /posts/jekyll_includes2x.png
  caption:
---

[Jekyll](https://jekyllrb.com/){: target="_blank"} utiliza [Markdown](https://daringfireball.net/projects/markdown/){: target="_blank"} y [Liquid](https://github.com/Shopify/liquid/wiki){: target="_blank"} para generar el contenido. El output es un sitio estático que es rápido y liviano.
Pero eso no significa que no puedes integrar contenido dinámico en tus páginas.

Hace poco aprendí a ocupar los includes de Jekyll y son bastante poderosos sobre todo cuando los mezclas con variables personalizables. Optimizas tu tiempo y evitas hacer tareas repetitivas.

## Lo básico

La sintaxis de un ```include``` se ve así:

{% raw %}
```
{% include menu.html %}
```
{% endraw %}

Funciona de manera similar a los includes de ```PHP``` como:

```php
<?php include 'menu.php';?>
```

Al igual que en ```PHP```, es posible incluir variables adicionales para un contenido más dinámico. Pero de manera más simple e intuitiva, definiendo las variables que queramos como ID, clase o incluso atributos personalizados.

Veamos cómo funciona.

## Manos a la obra

Digamos que quiero incluir un botón que pueda modificar su enlace y etiqueta en cada página. Vamos a crear el código para nuestro botón:

```
<a href="#" class="button">Texto</a>
```

Necesitamos definir nuestras variables dinámicas. Crearemos una variable para el link y una para el texto. Si desglosamos nuestras variables serían:


{% raw %}
```
href --> {{ includes.link }}
texto --> {{ includes.text }}
```
{% endraw %}

Entonces, nuestro botón debería quedar así:

{% raw %}
```
<a href="{{ includes.link }}" class="button">{{ includes.text }}</a>
```
{% endraw %}

Una vez conforme, guárdalo en la carpeta ```_includes``` en el directorio de tu sitio Jekyll con la extensión ```.html``` al final.

## Incluyendo el resultado
Ahora para incluir nuestro botón en cualquier parte de nuestro sitio, debemos usar el código y ajustar nuestras variables:
{% raw %}
```
{% include boton.html link="https://www.ejemplo.com/" text="Ejemplo" %}
```
{% endraw %}
Y voilá, cuando compilemos nuestro sitio, mostrará el botón con las variables actualizadas que definimos. ¿Genial no?