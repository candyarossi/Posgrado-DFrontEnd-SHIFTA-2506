# IMÁGENES

<br>

## Propiedades poco conocidas

Existen infinidad de propiedades CSS para realizar multitud de acciones con imágenes. Por ejemplo, podemos establecerlas como fondo, o bien podemos modificar su comportamiento, como agregándoles un borde e incluso recortándolas. Sin embargo, también hay propiedades CSS relacionadas con imágenes no tan conocidas, las cuales, al igual que las anteriores, también pueden ser utilizadas con el tag IMG de HTML.

<br>

### Controlar el renderizado de una imagen

Cuando se escala una imagen, el navegador suaviza la imagen para que no se vea pixelada. Pero, dependiendo de la resolución de la imagen y la pantalla, hay veces que esto no nos sirve. Puedes controlar este comportamiento del navegador con la propiedad `image-rendering`.

- Sus posibles valores son: `crisp-edges` y `pixelated`.

```css
img {
  image-rendering: pixelated;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/image-rendering).

<br>

### Estirar imágenes

Los valores `contain`, `cover` y `fill` nos suenan. Los utilizamos en la propiedad `background-size` para controlar cómo la imagen de fondo se acopla al elemento al que pertenece. La propiedad `object-fit` es bastante similar, ya que también determina cómo una imagen se ajusta dentro de su contenedor.

- Sus posibles valores son: `contain`, `cover`, `fill`, `scale-down`.

```css
img {
  object-fit: contain;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit).

<br>

### Mover imágenes

La propiedad `background-position` es una propiedad complementaria de la propiedad `background-size`. En el caso de `object-fit` también cuenta con su propiedad complementaria, `object-position`.

La propiedad `object-fit` mueve una imagen dentro de un contenedor de imágenes a las coordenadas dadas.

Las coordenadas se pueden definir como unidades de longitud absoluta, unidades de longitud relativa, palabras clave (`top`, `left`, `center`, `bottom` y `right`), o una combinación válida de ellas (`top 20px right 5px`, `center right 80px`).

```css
img {
  object-position: top 20px right 5px;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position).

<br>

### Situar imágenes

Muchas veces agregamos un `<img>` (que por defecto es inline) junto a una cadena de texto para agregar información o simplemente, por estética. En este tipo de casos, alinear el texto y la imagen en la posición deseada puede ser algo un poco complicado, sobre todo si no sabes qué propiedad utilizar.

La propiedad `vertical-align` se puede utilizar para alinear un elemento inline dentro de un contenedor inline y, por lo tanto, puede utilizarse para alinear una imagen con una línea de texto.

- Sus posibles valores son: `baseline`, `top`, `middle`, `bottom`, `sub`, `text-top`.

```css
img {
  vertical-align: text-top;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align).

<br>

### Agregar filtros a imágenes

Cuando nuestro sitio web comienza a crecer, utilizamos cada vez más y más imágenes en él, lo cual puede provocar algo de confusión, dificultando que el usuario pueda identificar aquella que debe asociar con la información que se encuentra leyendo. O también, puede ser que necesites aplicar una misma imagen en color, escala de grises y sepia en un mismo proyecto y editar una imagen por cada una de sus aplicaciones termina siendo muy costoso y pesado para el sitio. Para solucionar esto, existe la propiedad `filter`.

Esta propiedad dota de efectos gráficos como el desenfoque o cambio de color en la representación antes de que se muestre el elemento. Los filtros se utilizan comúnmente para ajustar la representación de imágenes, fondos o bordes.

Suele recibir como valor diferentes funciones CSS, puedes ver todas estas funciones y ejemplos de ellas en [este sitio](https://lenguajecss.com/css/efectos/filtros-css/).

```css
img {
  filter: opacity(0);
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/filter).

<br>

## IMÁGENES RESPONSIVAS, `picture`, `lazy load` y `clamp()`

Una **imagen responsiva** se adapta automáticamente al tamaño del contenedor y del dispositivo, asegurando una correcta visualización sin romper el diseño.

Aquí tenemos un ejemplo de código muy sencillo de implementar:

```css
img {
  max-width: 100%;
  height: auto;
}
```

Este simple bloque de código asegura que la imagen no exceda el ancho del contenedor y mantiene su proporción original.

<br>

## Etiqueta `<picture>`

La etiqueta `<picture>` permite mostrar diferentes versiones de una imagen dependiendo del ancho del viewport o del tipo de dispositivo.

```html
<picture>
  <source media="(min-width: 800px)" srcset="grande.jpg" />
  <source media="(min-width: 480px)" srcset="mediano.jpg" />
  <img src="pequeno.jpg" alt="Descripción de la imagen" />
</picture>
```

- El navegador seleccionará la fuente más apropiada según el ancho de la pantalla.
- Si ninguna condición se cumple, usará la imagen `<img>` como fallback.

> 💡 Es Ideal para mostrar imágenes más livianas en móviles y de alta calidad en pantallas grandes.

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/picture)

<br>

## Carga diferida (`lazy loading`)

Con la propiedad `loading="lazy"` puedes indicar al navegador que cargue la imagen solo cuando el usuario esté cerca del viewport, lo que mejora la velocidad de carga inicial del sitio.

```html
<img src="paisaje.jpg" alt="Paisaje" loading="lazy" />
```

- Es una solución nativa compatible con la mayoría de navegadores modernos.
- Reduce el uso innecesario de ancho de banda.

> 🔗 Para saber más sobre el atributo `loading`, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/Performance/Guides/Lazy_loading)

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/img#loading)

<br>

## Función `clamp()` en imágenes

Como ya sabemos, la función `clamp()` nos permite establecer un valor dinámico entre un mínimo y un máximo. Es perfecta para crear **tamaños de fuente, márgenes o imágenes que se adapten automáticamente**.

Si bien no se aplica directamente a imágenes como elemento, se puede usar en propiedades CSS que afecten a las imágenes.

```css
img {
  width: clamp(1.5rem, 4vw, 3rem);
}
```

Esto significa:

- Mínimo: `1.5rem`
- Preferido: `4vw` (4% del ancho del viewport)
- Máximo: `3rem`

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp)

<br>

### Consejos de rendimiento adicional:

- **Optimiza las imágenes** antes de subirlas a la web. Herramientas como [TinyPNG](https://tinypng.com/) o [ImageOptim](https://imageoptim.com/mac) ayudan a reducir el peso de las imágenes sin perder calidad.
- **Usa formatos modernos** como **WebP**, que ofrecen una excelente compresión sin perder calidad.
- Siempre usa **alt text** para las imágenes para mejorar la **accesibilidad**.

<br>
<hr>

<div align="center">
<a href="./responsive.md">⬅️ Responsive Design</a>
</div>
