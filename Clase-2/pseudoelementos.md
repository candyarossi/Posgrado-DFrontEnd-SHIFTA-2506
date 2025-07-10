# PSEUDO-ELEMENTOS

<br>

## ¿Qué es un pseudo-elemento?

Un **pseudo elemento** se refiere a una parte específica del contenido de un elemento. Se escribe con dos puntos dobles `::` seguido del nombre del pseudo elemento, y permite aplicar estilos o contenido sin alterar el HTML.

```css
/* Pseudocódigo */

selector::pseudo-element {
  propiedad: valor;
}
```

```css
/* Ejemplo real */

p::first-letter {
  color: red;
}
```

> 🚨 **IMPORTANTE**: Aunque algunos navegadores aún aceptan la sintaxis con un solo `:`, la forma correcta es con `::`.

> 🔗 [Documentación Pseudo-Elementos](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)

<br>

## Pseudo-Elementos más comunes

### `::before` y `::after`

Se usan para insertar contenido antes o después del contenido real de un elemento. Requieren obligatoriamente la propiedad `content` para funcionar.

Son muy útiles para iconografía decorativa, comillas, adornos o elementos de fondo adicionales.

```css
h1::before {
  content: "🔥 ";
}

h1::after {
  content: " ✨";
}
```

> 🔗 Para ver un ejemplo de su funcionamiento (`::before`), haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/::before).

> 🔗 Para ver un ejemplo de su funcionamiento (`::after`), haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/::after).

<br>

### `::first-letter`

Estiliza la primera letra de un párrafo o bloque de texto. Ideal para efectos editoriales como mayúsculas capitulares.

```css
p::first-letter {
  font-size: 2rem;
  font-weight: bold;
  color: #ff5733;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter).

<br>

### `::first-line`

Permite aplicar estilos únicamente a la **primera línea** visible del texto, útil para destacar introducciones o titulares largos.

El efecto depende del tamaño de pantalla y el ancho del contenedor.

```css
p::first-line {
  font-weight: bold;
  color: #555;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-line).

<br>

### `::selection`

Aplica estilos al **texto seleccionado por el usuario**, por ejemplo al hacer clic y arrastrar con el mouse.

Debes tener en cuenta que `::selection` tiene soporte limitado de propiedades (color, background, etc).

```css
::selection {
  background-color: #ffd54f;
  color: black;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/::selection).

<br>

## Diferencias entre Pseudo-Clases y Pseudo-Elementos

| Característica           | Pseudo Clase (`:hover`)                       | Pseudo Elemento (`::after`)              |
| ------------------------ | --------------------------------------------- | ---------------------------------------- |
| Sintaxis                 | Un solo `:`                                   | Dos puntos `::`                          |
| ¿Qué afectan?            | Estados o condiciones de elementos existentes | Partes internas o generadas del elemento |
| Ejemplos comunes         | `:hover`, `:focus`, `:nth-child()`            | `::before`, `::after`, `::first-letter`  |
| ¿Requiere `content`?     | No                                            | Sí (para `::before` y `::after`)         |
| Uso principal            | Interacción y selección                       | Decoración, contenido adicional          |
| HTML adicional necesario | No                                            | No (pero parece que se agrega contenido) |

<br>
<hr>

<div align="center">
<a href="./pseudoclases.md">⬅️ Pseudo-Clases</a>
	&#160;	&#160;	&#160;	&#160;	&#160;	🔸  &#160;	&#160;	&#160;	&#160;	&#160;
<a href="./fonts.md">Fonts ➡️</a>
</div>
