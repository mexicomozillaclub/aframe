---
title: Installation
type: introduction
layout: docs
parent_section: introduction
order: 2
---

Esta sección te mostrará varias maneras de comenzar con A-Frame.
Varias de las opciones para empezar no requieren de alguna instalación debido a que A-Frame esta basado en HTML y Javascript principalmente.

<!--toc-->

## Editores de código en el navegador web

La manera más rápida de comenzar a jugar es desde el navegador.

### Haz un Remix en Glitch

![Glitch](https://cloud.githubusercontent.com/assets/674727/24480466/54b17d22-1499-11e7-8a18-d4f76b49ad07.jpg)

[glitch]: https://glitch.com/~aframe

[Glitch][glitch]provee un editor de código en línea para implementar y hospedar sitios web instantaneamente. El editor soporta código de front-end y back-end code al igual que multiples archivos y directorios. Glitch permite hacer un remix (ej. copiar) de proyectos existentes y modificarlos para así crear nuestras propias versiones, y hospedar e implementar los cambios para que todos los vean.

[¡Da clic en **Remix** en este proyecto de A-Frame][glitch], modifica el código HTML en
`index.html`, y ve tu sitio publicado en vivo en cada cambio! La base de A-Frame de este proyecto está publicada en `aframe.glitch.me`, por ejemplo, pero para tu proyecto te proveeremos de tu propia URL personalizada.

A continuación encontrarás otros Glitches de A-Frame Glitches para principiantes:

- [aframe-aincraft](https://glitch.com/~aframe-aincraft) - Minecraft demo.
- [aframe-gallery](https://glitch.com/~aframe-gallery) -  Galeria 360&deg; de imagenes.
- [aframe-registry](https://glitch.com/~aframe-registry) - Demostración de varios componentes.
- [aframe-vaporwave](https://glitch.com/~aframe-vaporwave) -Escena Retrofuturista.
- [networked-aframe](https://glitch.com/~networked-aframe) - Multiusuario.

### Otros editores de código

Debajo encontrarás otras opciones para comenzar con A-Frame en editores de código basados en un navegador. Ambas alternativas soportan la opción de hacer remixes o forking:

- [Mozilla Thimble &mdash; A-Frame](https://thimble.mozilla.org/en-US/user/ngokevin/864056)
- [CodePen &mdash; A-Frame](https://codepen.io/mozvr/pen/BjygdO)

## Desarrollo local

### Usa un servidor local

Para las siguientes opciones deberás desarrollar tus proyectos utilizando un servidor local para que los archivos estén disponibles correctamente. Las opciones de servidor local incluyen:

- Descarga la aplicación de [Mongoose](https://www.cesanta.com/products/binary) application
  and open it from the same directory as your HTML file.
- Corre el comando `python -m SimpleHTTPServer` en una terminal en el mismo directorio donde se encuentra tu archivo HTML.
- Corre el comando `npm install -g live-server && live-server` en una terminal en el mismo directorio donde se encuentra tu archivo HTML.

Una vez que tu servidor local está corriendo, puedes abrir tu proyecto en un navegador usando
la URL local y el puerto en el que el servidor está corriendo (ej.`http://localhost:8000`).
Trata de *no* abrir el proyecto usando el protocolo `file://` que no te provee de un dominio,
ya que las URLs absolutas o relativas podrían no funcionar.

### Descarga la plantilla de Boilerplate de GitHub

[ghpages]: https://pages.github.com/

La plantilla de boilerplate contiene:

- Un archivo HTML simple que enlaza a la [versión actual de A-Frame](#builds-prod)
- Una opción para desarrollar en un servidor local
- Un flujo de trabajo fácil de implementar para compartir [GitHub Pages][ghpages] con el mundo

Puedes tomar la plantilla de boilerplate de estas opciones:

<a class="btn btn-download" href="https://github.com/aframevr/aframe-boilerplate/">Fork on GitHub</a>

<a class="btn btn-download" href="https://github.com/aframevr/aframe-boilerplate/archive/master.zip" download="aframe-boilerplate.zip">Download .ZIP<span></span></a>

### Incluye la Build de Javascript

Para incluir A-Frame en un archivo HTML, puedes utilizar la etiqueta `<script>` apuntando a la build en el CDN:

```html
<head>
  <script src="https://aframe.io/releases/0.6.0/aframe.min.js"></script>
</head>
```

Si quieres hospedarlo en tu propio servidor, puedes descargar la build de Javascript:

<a id="builds-prod" class="btn btn-download" href="https://aframe.io/releases/0.6.0/aframe.min.js" download>Production Version <span>0.6.0</span></a> <em class="install-note">Minified</em>
<a id="builds-dev" class="btn btn-download" href="https://aframe.io/releases/0.6.0/aframe.js" download>Development Version <span>0.6.0</span></a> <em class="install-note">Uncompressed with Source Maps</em>

### Instala desde npm

También puedes instalar A-Frame a través de npm:

```bash
$ npm install aframe
```

Así puedes incluir A-Frame dentro de tu aplicación. Por ejemplo con Browserify o Webpack:

```js
require('aframe');
```

[angle]: https://www.npmjs.com/package/angle

Si utilizas npm puedes usar [`angle`][angle], una interfaz de linea de comandos para
A-Frame.  `angle` puede inicializar una plantilla de escena con un solo comando:

```sh
npm install -g angle && angle initscene
```
