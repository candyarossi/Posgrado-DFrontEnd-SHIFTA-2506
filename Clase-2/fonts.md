# TIPOGRAFÍA EN CSS

<br>

Cuando se trata de tipografías, tenemos varias formas en las que podemos incluirlas en nuestros proyectos. Las más comunes son:

- `Fuentes del sistema (preinstaladas)`: Usas las fuentes que ya vienen instaladas en el sistema operativo del usuario.

  - **Ventajas:** No necesitas importar nada.
  - **Desventajas:** Estás limitado a las fuentes disponibles en cada sistema, y no tenemos certeza de que el usuario tenga instalada la tipografía solicitada. En tal caso, se mostrará una tipografía por defecto.

- `Google Fonts`: Es la opción más popular y sencilla para incluir fuentes personalizadas.

  - **Ventajas:** Fácil de usar, gran variedad.
  - **Desventajas:** Depende de una conexión externa (Google).

- `@font-face (Fuente personalizada local o remota)`: Puedes cargar tus propias fuentes desde archivos locales o URLs.

  - **Ventajas:** Control total sobre las fuentes.
  - **Desventajas:** Mayor peso, necesitas alojar los archivos y cuidar los formatos.

- `Adobe Fonts (antes Typekit)`: Necesitas una cuenta de Adobe y usar el código Javascript que te proporcionan. Luego puedes usar la fuente en tu CSS como cualquier otra.

- `CDNs o repositorios de fuentes (Fontshare, Bunny Fonts, etc.)`: Similares a Google Fonts, pero alojadas en otros servidores.

<br>

## Uso de `@font-face`

`@font-face` permite cargar fuentes personalizadas directamente desde tu servidor o un directorio local. Esto es útil si quieres usar una fuente que no está disponible en Google Fonts o necesitas control total sobre su distribución.

```css
@font-face {
  font-family: "Stick";
  src: url("typo/StickNoBills-Regular.ttf") format("ttf");
  font-weight: normal;
  font-style: normal;
}

body {
  font-family: "Stick";
}
```

Asegúrate de incluir los archivos en una carpeta accesible desde tu HTML.

> 🔗 [Documentación @font-face](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face)

### Recomendación de formatos si usas `@font-face`:

- **WOFF2**: Moderno, comprimido y recomendado.
- **WOFF**: Más compatible con navegadores antiguos.
- **TTF/OTF**: Antiguos, pero aún funcionales.
- **EOT**: Muy antiguo, solo para IE <=8.
- **SVG**: Obsoleto.

<br>

## Uso de Google Fonts

Google Fonts es una librería de fuentes gratuita, ampliamente utilizada en proyectos web. Optimiza la carga de fuentes y ofrece muchas variantes de peso y estilo.

Puedes integrarla fácilmente a través de una URL en el `<head>` de tu documento.

```html
<!-- En el <head> de tu HTML -->
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
  href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap"
  rel="stylesheet"
/>
```

```css
/* En tu CSS */

body {
  font-family: "Roboto", sans-serif;
  font-optical-sizing: auto;
  font-weight: 400;
  font-style: normal;
  font-variation-settings: "wdth" 100;
}
```

O puedes tener todo el código dentro de tu archivo CSS:

```css
/* En tu CSS */
@import url("https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap");

body {
  font-family: "Roboto", sans-serif;
  font-optical-sizing: auto;
  font-weight: 400;
  font-style: normal;
  font-variation-settings: "wdth" 100;
}
```

Las reglas `@import` deben ir al inicio de tu documento de estilos.

El código anterior lo puedes obtener seleccionando una tipografía en Google Fonts y a continuación las opciones `Get font` > `Get embed code`.

> 🔗 [Google Fonts](https://fonts.google.com/)

<br>

## Comparación rápida

| Característica       | `@font-face`                      | Google Fonts                        |
| -------------------- | --------------------------------- | ----------------------------------- |
| Fuente alojada en... | Tu servidor                       | Servidores de Google                |
| Implementación       | Requiere descargar archivos       | Solo copiar un `<link>` o `@import` |
| Ideal para...        | Fuentes personalizadas o privadas | Fuentes públicas y populares        |
| Formatos requeridos  | `.woff`, `.woff2`, `.ttf`, etc.   | Google ya lo optimiza por ti        |

### Buenas prácticas

- Usar máximo 2 o 3 fuentes por proyecto para rendimiento.
- Elegir formatos modernos (`woff2` > `woff` > `ttf`).
- Siempre tener **fuentes de respaldo** (`font-family: 'Roboto', sans-serif;`).

<br>

## Tipografía fluida con `clamp()`

Una "_app web de tipografía fluida_" es una aplicación o sitio web en la cual las tipografías se adaptan dinámicamente al tamaño de la pantalla. En lugar de usar tamaños de fuente fijos, estas tipografías se escalan proporcionalmente, garantizando una experiencia de lectura consistente en diferentes dispositivos.

La `tipografía fluida` se basa en el uso de **_unidades relativas_**, como `vw` (_viewport width_) y `vh` (_viewport height_), que representan un porcentaje del ancho y la altura de la ventana de visualización del navegador. Estas unidades permiten que el tamaño de la fuente se ajuste automáticamente según el tamaño del dispositivo, manteniendo una relación de aspecto adecuada.

Existen varias herramientas web que facilitan la creación de tipografías fluidas, una de ellas es la función `clamp()`, que permite definir un tamaño de fuente adaptable a cualquier tamaño de pantalla, sin necesidad de `media queries`. Es muy útil para diseño responsivo moderno y mejora la accesibilidad visual.

Su sintaxis es la siguiente:

```css
font-size: clamp(min, ideal, max);
```

Por ejemplo:

```css
h1 {
  font-size: clamp(1.5rem, 5vw, 3rem);
}
```

Esto significa que el tamaño del texto será como mínimo `1.5rem`, idealmente `5vw` (5% del ancho del viewport), y como máximo `3rem`.

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp).

<br>
<hr>

<div align="center">
<a href="./pseudoelementos.md">⬅️ Pseudo-Elementos</a>
  &#160;	&#160;	&#160;	&#160;	&#160;	🔸  &#160;	&#160;	&#160;	&#160;	&#160;
<a href="./unidades.md">Extra: Unidades de Medida ➡️</a>
</div>
