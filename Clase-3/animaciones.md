# TRANSICIONES Y ANIMACIONES EN CSS

<br>

CSS no solo sirve para diseñar elementos estáticos. Gracias a **transiciones** y **animaciones**, podemos agregar movimiento y dinamismo a los sitios web, mejorando la experiencia del usuario y aportando modernidad al diseño.

<br>

## Transiciones

Las **_transiciones_** permiten cambiar suavemente el valor de una o varias propiedades CSS durante un período de tiempo específico.

La propiedad `transition` es una propiedad que engloba el uso de las propiedades `transition-property`, `transition-duration`, `transition-timing-function`, y `transition-delay`. Permite definir la **_transición_** entre dos estados de un elemento.

Hay diferentes estados que pueden ser definidos utilizando **_pseudo-clases_** como `:hover` o `:active` o aplicado dinámicamente usando JavaScript.

Su sintaxis es la siguiente:

```css
.elemento {
  transition: property duration easing-function delay;
}
```

O por separado:

```css
.elemento {
  transition-property: property;
  transition-duration: duration;
  transition-timing-function: easing-function;
  transition-delay: delay;
}
```

Ejemplo al hacer hover sobre el elemento `button`:

```css
button {
  background-color: orange;
  transition: background-color 4s ease-in-out 1s;
}

button:hover {
  background-color: red;
}
```

O también:

```css
button {
  background-color: orange;
  transition-property: background-color;
  transition-duration: 4s;
  transition-timing-function: ease-in-out;
  transition-delay: 1s;
}

button:hover {
  background-color: red;
}
```

Entonces al hacer `:hover` sobre el elemento `button` este cambiará de color.

> 🔗 [Documentación Transiciones](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_transitions/Using_CSS_transitions)

### Propiedades de transiciones y sus valores iniciales

- 🔗 [transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition): all 0s ease 0s
- 🔗 [transition-property](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property): all
- 🔗 [transition-duration](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration): 0s
- 🔗 [transition-timing-function](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function): ease
- 🔗 [transition-delay](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay): 0s

> 🚨 **IMPORTANTE**: Solo algunas propiedades pueden ser animadas (colores, tamaños, posición, opacidad, etc).

<br>

## Animaciones con `@keyframes`

Las **_animaciones_** permiten definir múltiples estados a lo largo del tiempo, no solo entre dos valores como en las transiciones.

Es un efecto que se loopea (repite) tantas veces como se desee, y no depende del cambio de estados (el elemento se animará desde la carga de la web).

Una animación es la unión de dos partes. Por un lado una línea de tiempo (llamada `keyframe`) con la información de los cambios. Y por otro lado, aplicar ese `keyframe` a un elemento que será el que se verá animado.

> 🔗 [Documentación Animaciones](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations/Using_CSS_animations)

### Línea del tiempo

Es un elemento `@keyframes` con un nombre. Luego del nombre, y entre llaves, se definen los puntos donde cambiará el CSS. Cada cambio pasa en un porcentaje de la animación.

Por cada punto de inflexión, y entre llaves, van las reglas CSS que se aplicarán en ese momento. El cambio es paulatino de un porcentaje al otro.

```css
@keyframes nombre-animacion {
  0% {
    propiedad: valor-inicial;
    ...;
  }
  50% {
    propiedad: valor-intermedio;
    ...;
  }
  100% {
    propiedad: valor-final;
    ...;
  }
}
```

**EJEMPLO:**

```css
@keyframes arco_iris {
  0% {
    background-color: red;
  }
  15% {
    background-color: darkorange;
  }
  30% {
    background-color: yellow;
  }
  45% {
    background-color: green;
    width: 300px;
  }
  60% {
    background-color: mediumblue;
  }
  75% {
    background-color: indigo;
  }
  90% {
    background-color: purple;
  }
  100% {
    background-color: deeppink;
  }
}
```

> Podemos tener tantos pasos intermedios como queramos, pero siempre respetando el inicio en `0%` y el final en `100%`.

O, en el caso de ser una animación que solo conste de **2 pasos** (similar a una **_transición_**), podemos especificarlos de esta forma:

```css
@keyframes nombre-animacion {
  from {
    propiedad: valor-inicial;
    ...;
  }
  to {
    propiedad: valor-final;
    ...;
  }
}
```

**EJEMPLO:**

```css
@keyframes cambio_color {
  from {
    background-color: yellow;
  }
  to {
    background-color: darkorange;
  }
}
```

> 🔗 [Documentación `@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)

### Aplicar el efecto

Ahora, ese `keyframe` hay que vincularlo a un elemento, dándole la propiedad `animation` que requiere mínimamente:

- `duration`: Duración de toda la animación (este valor se usará en el `keyframe` como **100%**). Se mide `seconds`.
- `easing-function`: Función de desaceleración.
- `delay`: Delay entre que se carga la web y arranca la animación. También en `seconds`.
- `iteration-count`: Cuantas veces repetir, esto puede ser un número (cantidad exacta) o `infinite`.
- `name`: Su nombre.

```css
.elemento {
  animation: duration easing-function delay iteration-count name;
}
```

O por separado:

```css
.elemento {
  animation-duration: duration;
  animation-timing-function: easing-function;
  animation-delay: delay;
  animation-iteration-count: iteration-count;
  animation-name: name;
}
```

**EJEMPLO:**

```css
div {
  width: 100px;
  height: 100px;
  margin: 30px;
}

div:first-child {
  animation: 9s ease-in 0s infinite arco_iris;
}

div:nth-child(2) {
  animation-duration: 3s;
  animation-timing-function: ease-in;
  animation-delay: 0s;
  animation-iteration-count: infinite;
  animation-name: cambio_color;
}
```

### Propiedades de animaciones y sus valores iniciales

- 🔗 [animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation): 0s ease 0s 1 none
- 🔗 [animation-duration](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration): 0s
- 🔗 [animation-timing-function](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function): ease
- 🔗 [animation-delay](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay): 0s
- 🔗 [animation-iteration-count](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count): 1
- 🔗 [animation-name](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name): none

<br>

## Comparación entre Transiciones y Animaciones

| Característica     | Transiciones                                       | Animaciones                                    |
| ------------------ | -------------------------------------------------- | ---------------------------------------------- |
| Activador          | Interacción del usuario (`:hover`, `:focus`, etc.) | Automáticas o por clase                        |
| Complejidad        | 1 solo estado de cambio                            | Múltiples etapas con `@keyframes`              |
| Control del tiempo | Limitado                                           | Completo (inicio, fin, repeticiones)           |
| Repetición         | No                                                 | Sí (`infinite`, `alternate`, etc.)             |
| Ideal para         | Hover, focus, cambios simples                      | Ciclos, movimientos complejos                  |
| Ejemplo típico     | Hover en botones                                   | Banners animados, loaders, movimiento continuo |

<br>

## Buenas prácticas

- **_No abuses de las animaciones_**: úsalas para mejorar la experiencia, no para distraer.
- Asegúrate de que las animaciones _no dificulten la accesibilidad_.
- Usa `prefers-reduced-motion` para respetar las preferencias del usuario.

### ¿Qué es `prefers-reduced-motion`?

Es una **_función multimedia CSS_** que se utiliza para detectar si un usuario ha activado una configuración en su dispositivo para minimizar el movimiento innecesario.

Esta configuración indica al navegador del dispositivo que el usuario prefiere una interfaz que elimine, reduzca o reemplace las animaciones basadas en movimiento.

Estas animaciones pueden causar molestias a personas con trastornos del movimiento vestibular. Animaciones como escalar o desplazar objetos grandes pueden ser desencadenantes del mismo.

Para desactivar animaciones y transiciones en caso de que el usuario así lo prefiera, podemos hacerlo con el siguiente código:

```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation: none !important;
    transition: none !important;
  }
}
```

> 🔗 [Documentación `prefers-reduced-motion`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion)

<br>

## Generadores y/o alternativas a Animaciones y Transiciones

Existen distintos tipos de generadores de código CSS, tanto para animaciones, transformaciones y/o gradientes entre otros. Un ejemplo de ellos es [CSS3 Maker](https://www.toptal.com/developers/css3maker).

Además, también existen librerías de código que podemos incluir a nuestros proyectos para agregar animaciones mediante el uso de clases en nuestros elementos HTML, algunas de ellas son [Animate CSS](https://animate.style) y [Wow JS](https://wowjs.uk).

- `Animate.css`: Es una biblioteca que ofrece una colección de clases CSS predefinidas para animaciones (fadeIn, bounce, slideIn, etc.).

- `WOW.js`: Se encarga de detectar cuando un elemento entra en la vista del usuario (al hacer scroll) y le aplica animaciones de **_Animate.css_**.

> 🚨 **IMPORTANTE**: `WOW.js` no funciona con `Animate.css` versión 5+, por eso si las quieren usar en conjunto deberían usar la versión 4.1.1 o menor.

<br>
<hr>

<div align="center">
<a href="../Clase-2/unidades.md">⬅️ Extra: Unidades de Medida</a>
  &#160;	&#160;	&#160;	&#160;	&#160;	🔸  &#160;	&#160;	&#160;	&#160;	&#160;
<a href="./sass.md">Sass ➡️</a>
</div>
