---
title: Introduction
section_title: Introduction
type: introduction
layout: docs
order: 1
parent_section: docs
section_order: 1
installation: true
---

[mozvr]: https://mozvr.com
[three.js]: https://threejs.org
[webvr]: https://iswebvrready.com

![A-Frame](https://cloud.githubusercontent.com/assets/674727/25392020/6f011d10-298c-11e7-845e-c3c5baebd14d.jpg)

## What is A-Frame?

:a:-Frame es un web framework para construir experiencias de realidad virtual (VR). Como los creadores de webVR, el [equipo de Mozilla VR][mozvr] easiest as well as the most powerful way to develop WebVR content. Por ser un [proyecto totalmente abierto](https://github.com/aframevr/), ha crecido hasta convertirse en una de [las comunidades de VR más grandes y acogedoras](https://aframe.io/community/).

A-Frame está basado en HTML, haciéndolo simple para comenzar. Pero A-Frame no es sólo un grafo de escenas 3D (3D scene graph) ni un lenguaje de marcado; el nucleo es un poderoso sistema entidad-componente que provee una estructura declarativa, extensible y componible a [three.js].

A-Frame soporta muchos de los visores de realidad virtual como Vive, Rift, Daydream, GearVR, Cardboard, e incluso puede ser usado para experiencias de realidad aumentada. A pesar de que A-Frame soporta todo el espectro su objetivo definir experiencias de realidad virtual totalmente inmersivas e interactivas con siguimiento de posición y controles que van más allá de sólo contenido básico 360&deg;. El equipo de Mozilla VR actualmente utiliza A-Frame como base para un Metaverso-en-progreso.

<div class="docs-introduction-examples">
  <a href="https://aframe.io/a-painter/?url=https://ucarecdn.com/962b242b-87a9-422c-b730-febdc470f203/">
    <img alt="A-Painter" target="_blank" src="https://cloud.githubusercontent.com/assets/674727/24531388/acfc3dda-156d-11e7-8563-5bd75252f70f.gif" height="190" width="32%">
  </a>
  <a href="https://aframe.io/a-blast/">
    <img alt="A-Blast" target="_blank" src="https://cloud.githubusercontent.com/assets/674727/24531440/0336e66e-156e-11e7-95c2-f2e6ebc0393d.gif" height="190" width="32%">
  </a>
  <a href="https://aframe.io/a-saturday-night/">
    <img alt="A-Saturday-Night" target="_blank" src="https://cloud.githubusercontent.com/assets/674727/24531477/44272daa-156e-11e7-8ef9-d750ed430f3a.gif" height="190" width="32%">
  </a>
  <a href="https://ngokevin.github.io/kframe/scenes/aincraft/">
    <img alt="Aincraft" target="_blank" src="https://cloud.githubusercontent.com/assets/674727/24531777/25b8ff5e-1570-11e7-896c-3446d1419eb8.gif" height="190" width="32%">
  </a>
  <a href="https://github.com/googlecreativelab/webvr-musicalforest">
    <img alt="Musical Forest by @googlecreativelab" target="_blank" src="https://cloud.githubusercontent.com/assets/674727/25109861/b8e9ec48-2394-11e7-8f2d-ea1cd9df69c8.gif" height="190" width="32%">
  </a>
  <a href="https://aframe-gallery.glitch.me">
    <img alt="360 Image Gallery" target="_blank" src="https://cloud.githubusercontent.com/assets/674727/24572552/72f81bec-162e-11e7-9851-037d0280abdb.gif" height="190" width="32%">
  </a>
</div>

## Primeros pasos

[glitch]: http://glitch.com/~aframe

¡A-Frame puede ser desarrollado desde un archivo plano de HTML sin necesidad de instalar nada! Una gran forma de probar A-Frame es hacer un **[remix del ejemplo inicial disponible en
Glitch][glitch]**, un editor de código en línea que hospeda e implementa instantaneamente sin costo. También puedes crear un archivo `.html`  que incluya A-Frame en la etiqueta `<head>`:

```html
<html>
  <head>
    <script src="https://aframe.io/releases/0.5.0/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>
      <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>
      <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>
      <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>
      <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>
      <a-sky color="#ECECEC"></a-sky>
    </a-scene>
  </body>
</html>
```

[Installation]: ./installation.md
[school]: https://aframe.io/school/

La página de [Instalación] provee más opciones para comenzar con A-Frame.
Para empezar a aprender con A-Frame, revisa la [A-Frame School][school] para lecciones paso a paso que complementan la documentación.

## Características

:eyeglasses: **VR de manera simple**: Sólo coloca dentro de una etiqueta `<script>` la etiqueta  `<a-scene>`.
A-Frame se encargará de 3D boilerplate, la instalación de VR, y los controles por default. Sin necesidad de instalar ni pasos para construir.

:heart: **HTML Declarativo**: HTML es fácil de leer, entender y de copiar y pegar. Al estar basado en HTML, A-Frame es accesible para todos: desarolladores web, entusiastas de Realidad Virtual, artistas, diseñadores, educadores, hacedores y niños.

:globe_with_meridians: **VR Multiplataforma**: Construye aplicaciones VR para Vive,
Rift, Daydream, GearVR, y Cardboard con soporte para todos sus respectivos controles.
¿No tienes un visor o controles? ¡No hay problema! A-Frame funciona en computadoras de escritorio y smartphones.

[ecs]: ./entity-component-system.md

:electric_plug: **Arquitectura Entidad-Componente**: A-Frame es un potente framework de [three.js], provee una [estructura entidad-componente][ecs].js. declarativa, componible y reusable. HTML es sólo la punta del iceberg; los desarrolldores tienen acceso ilimitado  a JavaScript, DOM APIs, three.js, WebVR, y WebGL.

[A-Painter]: https://github.com/aframevr/a-painter
[Tilt Brush]: https://www.tiltbrush.com/

:zap: **Rendimiento**: A-Frame está optimizado desde la base para WebVR. Mientras
A-Frame usa DOM, sus elementos no tocan el motor de renderizado del navegador. Las acualizaciones de los objetos 3D son hechas en la memoria con poco sobrecarga para una sola petición `requestAnimationFrame`. Para más referencias puesde ver el [A-Painter], un clon de [Tilt Brush] hecho en A-Frame que corre como una aplicación nativa(90+ FPS).

[React]: https://github.com/aframevr/aframe-react/
[Preact]: https://github.com/aframevr/aframe-react#using-with-preact
[Vue.js]: https://vuejs.org/
[Angular]: https://angularjs.org/
[d3.js]: http://blockbuilder.org/search#text=aframe
[Ember.js]: https://www.emberjs.com/
[jQuery]: http://jquery.com/download/

:hammer: **Herramienta Agnostica**: Debido a que la Web fue creada bajo la noción de HTML,
A-Frame es compatible con la mayoría de las bibliotecas, framework y herramientas incluyendo a [React], [Preact], [Vue.js], [Angular], [d3.js], [Ember.js] y [jQuery].

[inspector]: ./visual-inspector-and-dev-tools.md

:mag: **Inspector Visual**: A-Frame tiene un [inspector visual 3D][inspector] incluido. Abre *cualquier* escema de A-Frame, presiona `<ctrl> + <alt> + i` y podrás ver tras bambalinas.

![Inspector](https://cloud.githubusercontent.com/assets/674727/25377018/27be9cce-295b-11e7-9098-3e85ac1fe172.gif)

[registry]: https://aframe.io/aframe-registry

:package: **Registro**: Toma los potentes componentes que los desarrolladores han publicado y conéctalos directo desde HTML. Similar a la tienda Unity Asset, [el registro de
A-Frame][registry] colecciona y cura estos componentes para su fácil descubrimiento.


[augmented reality]: https://github.com/jeromeetienne/AR.js#augmented-reality-for-the-web-in-less-than-10-lines-of-html
[motion capture]: https://github.com/dmarcos/aframe-motion-capture
[mountains]: https://github.com/ngokevin/kframe/tree/master/components/mountain/
[multiuser]: https://github.com/haydenjameslee/networked-aframe
[oceans]: https://github.com/donmccurdy/aframe-extras/tree/master/src/primitives
[particle systems]: https://github.com/IdeaSpaceVR/aframe-particle-system-component
[physics]: https://github.com/donmccurdy/aframe-physics-system
[speech recognition]: https://github.com/lmalave/aframe-speech-command-component
[super hands]: https://github.com/wmurphyrd/aframe-super-hands-component
[teleportation]: https://github.com/fernandojsg/aframe-teleport-controls

:runner: **Componentes**: Comienza desde cero con los componentes de A-Frame como figuras geometricas, materiales, luces, animaciones, modelos, destellos, sombras, audio posicional, texto y controles de Vive / Touch / Daydream / GearVR / Cardboard. Ve más allá con los componentes de la comunidad como [sistemas de partículas], [física], [multiusuario], [oceanos], [montañas], [reconocimiento de voz], [captura de movimiento], [teletransportación], [super manos], y [realidad aumentada].

## ¡Comienza!

Si es tu primera vez por aquí, este es un plan adentrarse con éxito en A-Frame:

1. Para inspirarte revisa lo que otros han hecho con A-Frame en el [Blog semanal](https://aframe.io/blog/) y
[awesome-aframe](https://github.com/aframevr/awesome-aframe/). Entre los usuarios participan organizaciones como The Washington Post, Amnesty International, Google Creative Labs,
Al Jazeera, NPR, Shopify, iStaging e IDEO.

2. Lee la documentación básica y guias para tomar impulso.

3. Entra en la [A-Frame School](https://aframe.io/school/), y toma un breve tutorial paso a paso.

4. [Únete a nuestro Slack](https://aframevr-slack.herokuapp.com)  Si tienes preguntas puedes [buscar o preguntar en StackOverflow](http://stackoverflow.com/questions/ask/?tags=aframe). ¡Seguro alguien te ayudará!

5. ¡Cuando contruyas algo comparte tu proyecto en línea y lo destacaremos en [*A Week of A-Frame*](https://aframe.io/blog/)!

¡Diviértete!
