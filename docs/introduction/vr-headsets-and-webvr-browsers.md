---
title: "VR Headsets & WebVR Browsers"
type: introduction
layout: docs
parent_section: introduction
order: 3
---

[w3c]: https://w3c.github.io/webvr/

<!--toc-->

## ¿Qué es Realidad Virtual?

Realidad Virtual (virtual reality, VR) es una tecnología que usa visores montados en la cabeza con pantallas para generar imagenes, sonidos y otras sensaciones realisticas con la finalidad de colocar a los usuarios en un entorno virtual inmersivo. La Realidad Virtual nos permite crear mundos ilimitados donde la gente puede caminar e interactuar usando sus manos, hacerlos sentir como si estuvieran en otro lugar.

### ¿Qué diferencias hay entre los visores?

Hay varios visores de realidad virtual con diferentes caracteristicas en el mercado. Es importante distinguir características como estas:

- Que tenga seguimiento de posición (positional tracking) de seis grados de libertad (6DoF) o solo seguimiento de rotación (rotational tracking) con tres grados de libertad (3DoF).
- Controles disponibles o no disponibles, en caso de tenerlos que tengan seis o tres grados de libertad (6DoF o 3DoF). Usualmente, el número de grados de libertad de los controles coinciden con el visor.
- Que sean alimentados por una computadora, un dispositivo móvil o un smartphone.

El seguimiento de rotación permite al usuario mirar alrededor o rotar objetos. Todos los visores proveen de seguimiento de rotación.

El seguimiento de posición permite al usuario moverse alrededor y acercarse a los objetos. Conforme la industria de realidad virtual va evolucionando, la experiencia minima viable tenderá a tener visores con capacidad de dar seguimiento de posición y controles con seguimiento de posición también. El seguimiento de posición es importante para dar al usuario presencia, y así hacerlo sentir que se encuentra en un entorno real. Cuando sólo se usa seguimiento de rotación el usuario esta limitado a sólo mirar alrededor y mover un control.

### ¿Cuáles son los visores disponibles en el mercado?

[HTC Vive]: https://www.vive.com/
[Oculus Rift]: https://www.oculus.com/rift/
[Google Daydream]: https://vr.google.com/daydream/
[Samsung GearVR]: http://www.samsung.com/global/galaxy/gear-vr/

| Visor           | Plataforma | Seguimiento de posición | Controles        | Seguimiento de posición del control |
|-------------------|----------|---------------------|--------------------|---------------------------------|
| [HTC Vive]        | PC       | :white_check_mark:  | :white_check_mark: | :white_check_mark:              |
| [Oculus Rift]     | PC       | :white_check_mark:  | :white_check_mark: | :white_check_mark:              |
| [Google Daydream] | Android  | :x:                 | :white_check_mark: | :x:                             |
| [Samsung GearVR]  | Android  | :x:                 | :white_check_mark: | :x:                             |

Los próximos visores a presentarse son de Realidad Mixta y Realidad Aumentada desde ventanas, que funcionan con A-Frame en cierto nivel.

## ¿Qué es WebVR?

[vlad]: https://en.wikipedia.org/wiki/Vladimir_Vuki%C4%87evi%C4%87

WebVR es una API de JavaScript para crear experiencias inmersivas en 3D de realidad virtual en tu navegador. WebVR fue concebido originalmente en Mozilla por [Vladimir Vukicvic]. Lee la [especificación de WebVR API en el W3C][w3c].

A-Frame usa la API de WebVR para tener acceso a los sensores de los visores de realidad virtual (posición, orientación). Para transformar la camara y para renderizar contenido directamente al visor de realidad virtual. Cabe destacar que WebVR, que provee los datos, no debe ser confundido o combinado con WebGL que provee gráficos y renderizado.

Para obtener información a detalle y actualizada sobre WebVR, [visita `https://webvr.rocks`](https://webvr.rocks):

<iframe src="https://webvr.rocks" height="400px" width="100%"></iframe>

## ¿A dónde quiere llevar A-Frame a WebVR?

El proposito de A-Frame es favorecer contenidos de realidad virtual altamente inmersivos e interactivos con un rendimiento similar al nativo. Para esto A-Frame considera que el nivel minimo viable tenderá a tener visores y controles con seguimiento de posición. Este paradigma es en el que A-Frame quiere innovar, además de descubrir nuevos territorios especificamente en realidad virtual para web. (por ejemplo: link traversal, decentralization, identity). Contrastar este tipo de contenidos con imagenes 360&deg; estáticas y planas, y menus.

Al mismo tiempo, A-Frame busca que todos sean capaces de involucrarse en la creación de contenidos de realidad virtual. A-Frame soporta la mayoria de los visores y sus respectivos controles. Afortunadamente con la gran comunidad y contribuyentes, A-Frame podrá satisfacer las necesidades del panorama actual de la realidad virtual al igual que velar por su futuro.

## ¿Qué plataformas soporta A-Frame?

Las plataformas que A-Frame soporta incluyen:

- Realidad Virtual en computadoras de escritorio con un visor
- Realidad Virtual en un dispositivo móvil con un visor
- Computadoras de escritorio (interacción sólo con mouse y teclado)
- Dispositivos móviles (por ejemplo: magic window)

[alt]: https://altvr.com/

Otras plataformas que también han funcionado con A-Frame son:

- Realidad Aumentada (AR) en visores de Realidad Aumentada (por ejemplo: HoloLens, Windows Mixed Reality)
- Realidad Aumentada (AR) en dispositivos móviles (por ejemplo: magic window)
- [AltSpaceVR][alt] a través de su SDK nativo

## ¿Cuáles visores de Realidad Virtual soporta A-Frame?

Los visores de Realidad Virtual que A-Frame soporta son:

- HTC Vive con sus controles y sensores
- Oculus Rift con sus controles táctiles
- Google Daydream con su control
- Samsung GearVR con su control
- Google Cardboard

Para recomendaciones de hardware en general (no son requisitos):

- [Recomendaciones de Hardware de Oculus Rift](https://www.oculus.com/en-us/oculus-ready-pcs/)
- [Recomendaciones de Hardware de HTC Vive](https://www.vive.com/us/ready/)
- Para smartphones un iPhone 6 en el caso la plataforma iOS y al menos un Galaxy S6 para la plataforma Android

## ¿Qué navegadores soporta A-Frame?

[Visita `https://webvr.rocks`](https://webvr.rocks) para más información sobre los navegadores que soportan WebVR. Probablemente esta lista quedará desactualizada rapidamente. A-Frame soporta VR en cualquier navegador que implemente la [[especificación de WebVR][w3c]:

- [Firefox Nightly](https://www.mozilla.org/en-US/firefox/channel/desktop/) (estará disponible pronto en Firefox 55)
- [Builds experimentales de Chromium](https://webvr.info/get-chrome/)
- Chrome para Android (Daydream)
- Oculus Carmel (GearVR)
- Samsung Internet (GearVR)
- Microsoft Edge

[webvrpolyfill]: https://github.com/googlevr/webvr-polyfill

A-Frame soporta la mayoria de los navegadores móviles modernos que no soportan WebVR a través de [WebVR polyfill][webvrpolyfill]. Cabe destacar que estos navegadores no soportan oficialmente WebVR, y que estamos utilizando un polyfill; es importante no tener altas expectativas en la calidad de la experiencia que estos navegadores proveerán y no encapricharse:

- Safari para iOS
- Chrome para Android
- Firefox para iOS
- Samsung Internet
- UC Browser

Para soporte plano o de 3D, A-Frame soporta todos los navegadores modernos, especificamente los que soportan WebGL como son:

- Firefox
- Chrome
- Safari
