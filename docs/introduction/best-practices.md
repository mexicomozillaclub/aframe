---
title: Best Practices
type: introduction
layout: docs
parent_section: introduction
order: 11
---

## A-Frame

[ecs]: ./entity-component-system.md
[mixins]: ../core/mixins.md
[template]: https://github.com/ngokevin/kframe/tree/master/components/template/

Algunas de las mejores prácticas para el framework son:

- La estructura del núcleo de A-Frame está basada en [entidad-componente (ECS)][ecs]. Coloca y estructura el código de la aplicación solo con los componentes de A-Frame para facilitar la reutilización, modularidad, composición, decoupling, encapsular, declaratividad, y pruebas. Está bien empezar a probar usando contenedores de scripts
  (`<script>`), pero procura utilizar componentes.
- [Mezclar código][mixins] y [hacer plantillas][template] es útil para reutilizar y reducir código HTML repetitivo.

## Desempeño

[asm]: ../core/asset-management-system.md
[hardware]: ./vr-headsets-and-webvr-browsers.md
[merge]: ../components/geometry.md#mergeto
[stats]: ../components/stats.md

El desempeño es crítico en VR. Una alta tasa de cuadros por segundo debe ser mantenida para hacer sentir al usuario cómodo y como si estuviera en otro lugar. A continuación encontrarás algunas formas de mejorar el desempeño de una escena de A-Frame:

- Usa las [especificaciones de hardware recomendadas.][hardware].
- Usa las **[estadísticas del componente][stats]**  para estar atento de varias métricas. (FPS, vertex and face count, geometry and material count, draw calls, number of entities). Queremos maximizar la cantidad de cuadros por segundo y minimizar todo lo demás.

- Usa el **[sistema de administración de assets][asm]**  para beneficiarte del cache del navegador y del precargado. Tratar extraer assets durante el renderizado es más lento que traer todos los assets antes de renderizar.

- Si usas modelos, intenta iluminarlos a través de texturas en lugar de ocupar las sombras y luces en tiempo real.
- Generalmente entre menos entidades y luces en una escena será mejor.
- Asegúrate de que la resolución de tus texturas están en tamaños basados en dos (ejemplo, 256x256, 512x1024) para evitar que el motor de renderizado rescale las texturas durante la ejecución de la escena.
- Limita el número de caras y vértices en los modelos.
- Otras técnicas (aún sin documentar) incluyen instancias de geometría, unión de geometría, nivel de detalles (LOD).
- Al utilizar raycasters o colliders, selecciona qué entidades serán afectadas por el raycast en lugar de afectar a todos los objetos en la escena.
- Cuando agregues continuamente comportamientos ejecutandose, usa los manejadores de componentes (`tick`
  handlers) de A-Frame para enganchar al loop de renderizado global. Usa las utilidades como
  `AFRAME.utils.throttleTick` para limitar el número de veces que un manejador `tick`
  es ejecutado si es apropiado.


### Manejadores `tick` (`tick` Handlers)

En los manejadores de tick de los componentes, sé frugal al crear nuevos objetos. Trata de reutilizar objetos. Un patrón para crear variables auxiliares privadas reusables es con un cierre. Debajo encontrás cómo creamos un vector de ayuda y un cuaternio, y cómo reusarlos entre cuadros, en lugar de crear nuevos en cada cuadro. Ten cuidado de que estas variables no permanezcan fijas porque estarán siendo compartidas entre todas las instancias del componente. Al hacer esto se reducirá el uso de memoria y la colección de basura:

```js
AFRAME.registerComponent('foo', {
  tick: function () {
    this.doSomething();
  },

  doSomething: (function () {
    var helperVector = new THREE.Vector3();
    var helperQuaternion = new THREE.Quaternion();

    return function () {
      helperVector.copy(this.el.object3D.position);
      helperQuaternion.copy(this.el.object3D.quaternion);
    })();
  }
});
```

Incluso si continuamente modificamos un componente en el tick, debemos asegurarnos de que pasemos el mismo objeto para actualizar sus propiedades. A-Frame mantendrá seguimiento del último objeto que ha pasado y deshabilitará el type checking y sus llamadas subsecuentes para obtener un incremento extra de velocidad. Aquí hay un ejemplo de una función de tick recomendada que modifica la rotación en cada tick.

```js
AFRAME.registerComponent('foo', {
  tick: function () {
    var el = this.el;
    var rotationTmp = this.rotationTmp = this.rotationTmp || {x: 0, y: 0, z: 0};
    var rotation = el.getAttribute('rotation');
    rotationTmp.x = rotation.x + 0.1;
    rotationTmp.y = rotation.y + 0.1;
    rotationTmp.z = rotation.z + 0.1;
    el.setAttribute('rotation', rotationTmp);
  }
});
```

## Diseño de VR

[leapmotion]: https://developer.leapmotion.com/assets/Leap%20Motion%20VR%20Best%20Practices%20Guidelines.pdf
[oculus]: https://developer.oculus.com/documentation/intro-vr/latest/concepts/bp_intro/

Diseñar para VR es diferente que diseñar para experiencias planas. Como nuevo medio, hay algunas buenas prácticas a seguir, especialmente para mantener el confort del usuario y presencia.
Sobre esto ya se ha sido escrito a fondo, así que omitimos estas guías. Toma nota que el diseño de interacción en VR es casi nueva:

- [Mejores prácticas de Oculus (para VR)][oculus]
- [Prácticas y lineamientos de mejores prácticas para Leap Motion VR][leapmotion]

Toma en cuenta lo siguiente:

- La regla de oro en común es que nunca se quite inesperadamente el control de la cámara de los usuarios.
- Las unidades (como las de posición) deberán ser consideradas en metros.
Esto es porque la API de WebVR es alimentada en gran parte de los controles de cámara, la cual ofrece la posición en metros. Al considerar los metros como unidad, se logra la escala esperada.
