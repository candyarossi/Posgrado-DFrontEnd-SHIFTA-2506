# DISEÑO RESPONSIVE

<br>

## ¿Qué es el Diseño o Desarrollo Responsive?

El `diseño web adaptable` es una filosofía de diseño y desarrollo cuyo objetivo es adaptar la apariencia de las páginas web al dispositivo que se esté utilizando para visitarlas.

Esta filosofía asegura que tu sitio web sea **_accesible y atractivo_** en cualquier dispositivo, desde móviles hasta pantallas de escritorio. Utiliza lo que se conoce como **_media queries_**, herramientas que nos permiten cambiar estilos según el tamaño de la pantalla, lo que garantiza una **_experiencia de usuario óptima_**. Además, la técnica **_mobile-first_** nos obliga a diseñar pensando en la simplicidad y accesibilidad de los dispositivos móviles, que son los más utilizados.

Todo esto lo podemos lograr mediante el uso de:

- **Media Queries**
- **Breakpoints**
- **Unidades relativas**
- **Diseños fluidos**

### ¿Por qué es importante?

Un diseño que no es responsivo puede provocar:

- Texto difícil de leer en pantallas pequeñas.
- Contenido que se desborda fuera del viewport.
- Navegación difícil o poco intuitiva.
- Baja retención de usuarios y peor posicionamiento SEO.

### Meta Viewport

El _navegador_ es el encargado de detectar automáticamente el ancho de la pantalla y, a partir del mismo, adapta todos los elementos de la página, desde el tamaño de letra hasta las imágenes y los menús, ofreciendo al usuario la mejor experiencia posible. Para ello, utiliza la etiqueta `<meta name="viewport">` del encabezado del documento HTML. Esta etiqueta da al navegador las instrucciones sobre cómo controlar las dimensiones y el ajuste a escala de la página.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

- Al incluir `width=device-width, initial-scale=1.0` dentro del atributo `content` se establece una relación de 1:1 entre los píxeles CSS (unidad de medida `px`) y los píxeles independientes del dispositivo.

<br>

## Media Queries

Las `Media Queries` son reglas CSS que nos permiten aplicar estilos CSS dependiendo de ciertas condiciones, como el ancho de la pantalla, la orientación del dispositivo, la resolución, etc.

Sintaxis básica de una `media query`:

```css
@media (condicion) {
  /* Reglas CSS */
}
```

> 🔗 [Documentación Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries).

### Breakpoints

Los **Breakpoints** o puntos de corte son los anchos de pantalla donde queremos que el diseño cambie. No hay una lista fija, pero algunos valores comunes son:

| Dispositivo           | Breakpoint común |
| --------------------- | ---------------- |
| Móviles en vertical   | 320px            |
| Móviles en horizontal | 480px            |
| Tablets               | 768px            |
| Escritorios pequeños  | 1024px           |
| Escritorios grandes   | 1280px           |

### Ejemplo práctico

Para probarlas vamos a hacer una maquetación de 3 columnas iniciales:

```html
<h1>Media Queries</h1>
<main>
  <div>
    <h2>Item 1</h2>
    <p>lorem40</p>
  </div>
  <div>
    <h2>Item 2</h2>
    <p>lorem40</p>
  </div>
  <div>
    <h2>Item 3</h2>
    <p>lorem40</p>
  </div>
  <div>
    <h2>Item 4</h2>
    <p>lorem40</p>
  </div>
</main>
```

```css
* {
  margin: 0;
  padding: 0;
}

body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

h1 {
  text-align: center;
  margin: 30px;
}

main {
  display: flex;
  flex-wrap: wrap;
  align-content: stretch;
  justify-content: stretch;
}

div {
  width: 25%;
  padding: 20px;
  margin: 5px;
  background-color: lightgray;
}

@media (max-width: 790px) {
  div {
    width: 40%;
  }
}

@media (max-width: 590px) {
  div {
    width: 95%;
  }
}
```

Además, se pueden sumar diferentes indicaciones con las `Media Queries`, las cuales se utilizan con el operador `and`.

```css
@media (min-width: 590px) and (max-width: 890px) {
  div {
    background-color: lightblue;
  }
}
```

Y en este caso, sólo se reproducirá el estilo si la pantalla está en formato horizontal.

```css
@media (max-width: 1024px) and (orientation: landscape) {
  div {
    background-color: lightpink;
  }
}
```

Puedes llegar a hacer cosas muy avanzadas y personalizar completamente el aspecto de una web según el tamaño del dispositivo.

- Cambiar el tamaño y la posición de una imagen.
- Modificar la posición de cualquier elemento.
- Cambiar el tamaño de letra, la fuente o su color.
- Aplicar combinaciones de estilos avanzados.

<br>

## Mobile-first vs. Desktop-first

- **_Mobile-first_**: El diseño comienza para móviles y luego se adapta a pantallas más grandes usando **media queries**.
- **_Desktop-first_**: El diseño se empieza para pantallas grandes y luego se ajusta para dispositivos más pequeños.

> 💡 **_¿Cuál usar?_** En la mayoría de los casos, se recomienda `mobile-first` debido a que la **mayor parte de los usuarios utilizan dispositivos móviles**.

### Ejemplo práctico

#### A) Diseño Mobile-First

```css
/* Estilo predeterminado (móviles) */
body {
  font-size: 16px;
  background-color: lightblue;
}

/* Estilo para pantallas de 768px o más (tabletas) */
@media (min-width: 768px) {
  body {
    font-size: 18px;
    background-color: lightgreen;
  }
}

/* Estilo para pantallas de 1024px o más (escritorios) */
@media (min-width: 1024px) {
  body {
    font-size: 20px;
    background-color: lightcoral;
  }
}
```

- En móviles, el fondo es azul y el texto tiene tamaño de 16px.
- En tabletas (768px o más), el fondo es verde y el texto se aumenta a 18px.
- En escritorios (1024px o más), el fondo es coral y el texto crece a 20px.

#### B) Diseño Desktop-First

```css
/* Estilo predeterminado (escritorios) */
body {
  font-size: 20px;
  background-color: lightcoral;
}

/* Estilo para pantallas de 768px o más (tabletas) */
@media (max-width: 1024px) {
  body {
    font-size: 18px;
    background-color: lightgreen;
  }
}

/* Estilo para pantallas pequeñas (móviles) */
@media (max-width: 768px) {
  body {
    font-size: 16px;
    background-color: lightblue;
  }
}
```

- En escritorios grandes, el fondo es coral y el texto tiene tamaño de 20px.
- En tabletas (máximo 1024px), el fondo es verde y el texto disminuye a 18px.
- En móviles (máximo 768px), el fondo es azul y el texto se reduce a 16px.

<br>
<hr>

<div align="center">
<a href="../Clase-3/sass.md">⬅️ Sass</a>
  &#160;	&#160;	&#160;	&#160;	&#160;	🔸  &#160;	&#160;	&#160;	&#160;	&#160;
<a href="./imagenes.md">Imágenes Responsive ➡️</a>
</div>
