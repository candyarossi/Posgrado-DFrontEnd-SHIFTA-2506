# PREPROCESADORES CSS Y SASS

<br>

CSS es muy poderoso, pero en proyectos grandes puede volverse difícil de mantener. Por eso existen los **preprocesadores CSS**, que nos permiten escribir código más organizado, reutilizable y modular.

Uno de los preprocesadores más populares es **SASS**. En este módulo aprenderemos qué es, cómo instalarlo y cómo usar sus principales características como variables, anidamiento, mixins y funciones.

<br>

## ¿Qué es un preprocesador CSS?

Un **_preprocesador_** es una herramienta que amplía las funcionalidades de CSS permitiendo usar características como:

- Variables
- Funciones
- Operaciones matemáticas
- Reutilización de bloques

Luego interpreta la sintaxis del código y la convierte a `CSS` puro. Se escribe el código en un lenguaje como `SASS` y lo "compilas" a `CSS tradicional` que los navegadores pueden entender.

Los **_preprocesadores_** nos permiten escribir hojas de estilo mucho más claras, mantenibles y escalables.

Estos son algunos de lo preprocesadores CSS más populares:

- SASS
- LESS
- Stylus
- PostCSS

> 🔗 [Documentación Preprocesadores CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS_preprocessor)

<br>

## ¿Qué es SASS?

`Sass` significa **_“Syntactically Awesome Stylesheets”_**, es una herramienta escrita en lenguaje `Ruby`, que nos permite crear hojas de estilos estructuradas, limpias y fáciles de mantener.

Vamos a poder escribir hojas de estilo que nos ayudarán a generar ficheros CSS más optimizados, incorporando mayor contenido semántico y permitiendo utilizar funcionalidades que normalmente encontraríamos en lenguajes de programación tradicionales.

`SASS` ofrece dos sintaxis:

- `.sass`: Es conocida como `Indented Syntax` (**_sintaxis de indentación_**). Utiliza la indentación en lugar de corchetes para expresar el anidamiento de selectores y saltos de línea en lugar de (;) punto y coma para separar las diferentes propiedades que se declaren. Usarla es muy sencillo, solo debemos crear un archivo con terminación `.sass`.
- `.scss`: La más popular, es conocida como `SCSS` (**_Sassy CSS_**), es muy similar a la sintaxis nativa de CSS, tanto así que nos permite importar hojas de estilos CSS (copiar y pegar) directamente en un archivo SCSS y obtener un resultado válido. Para utilizarla solo debemos crear un archivo con terminación `.scss`.

En este módulo trabajaremos con `.scss`, ya que es más familiar para quienes ya conocen CSS.

> 🔗 [Documentación oficial de SASS](https://sass-lang.com)

### Para tener en cuenta

El navegador solo entiende CSS, de hecho, nos podemos enlazar nuestros archivos SASS a los HTML, necesitamos convertirlos a CSS.

Para convertir SASS a CSS se pueden utilizar comandos de `npm`, o utilizar alguna extensión de VSCode, como [Live Sass Compiler](https://marketplace.visualstudio.com/items?itemName=glenn2223.live-sass).

<br>

## Instalación de SASS

Para instalar SASS, debemos seguir los siguientes pasos:

1. Instala `nodejs` (`npm` viene con `node`) desde la [página oficial](https://nodejs.org/en/download). Es un entorno en tiempo de ejecución JavaScript, de código abierto y multiplataforma, es en parte el encargado de compilar `sass`.

> Para **_Windows 7_** deben instalar la versión `13.6.0` de `Node.js`.

2. Si utilizas Windows, instala `sass` escribiendo el comando `npm install –g sass` en la terminal de tu computadora. Si utilizas Mac o Linux, debes usar el comando `sudo npm install –g sass`.
3. Verifica la instalación escribiendo `sass --version` en la terminal.
4. Compila el código SASS mediante comandos o utilizando tu extensión de preferencia en VSCode.

<br>

## Características principales de SASS

### Nesting (anidamiento)

HTML sigue una estricta estructura de anidación, mientras que CSS por lo general, es un caos total.

Con la `anidación` de Sass puedes organizar tu hoja de estilo de una manera que se asemeja a la de HTML, lo que reduce la posibilidad de conflictos en el CSS.

```scss
/* SCSS */

.container {
  .row {
    button {
      color: white;
    }
  }
}
```

```css
/* CSS */

.container .row button {
  color: white;
}
```

> ⛔ No abuses del nesting. Recomendado: máximo 3 niveles.

> 🔗 [Documentación SASS: Nesting](https://sass-lang.com/documentation/style-rules#nesting)

<br>

### Imports

Una de las características más útiles de Sass es poder separar tus hojas de estilo en archivos separados.

Debes usar `@import` para incluir la fuente de tus archivos individuales en una hoja de estilos maestra.

Al momento de compilar los archivos, SASS compilará todos los archivos de tipo `.sass` o `.scss` que encuentre, generando un archivo CSS por cada uno de ellos.

Para evitar esto y que solo se compile la hoja maestra que contiene las importaciones de los archivos parciales, debemos nombrar al resto de archivos con un guión bajo (`_`) delante de su nombre real, de esta forma:

```txt
+ css
   | index.css
+ scss
   | index.scss
   | _variables.scss
   | _mixins.scss
```

Vista del `index.scss`:

```scss
@import "variables";
@import "mixins";

/* Resto del código SCSS/CSS */
```

Así, SASS se compilará insertando el código de los archivos "variables" y "mixins" al inicio del archivo CSS resultante.

> ⚠️ A la hora de escribir los nombres de los archivos en sus correspondientes `@import`, no debemos incluir la extensión del archivo `scss`, ni el guión bajo (`_`) de su nombre.

> 🔗 [Documentación SASS: Import](https://sass-lang.com/documentation/at-rules/import/)

<br>

### Operaciones y lógica

Con Sass puedes realizar `operaciones matemáticas` básicas en la misma hoja de estilo: es tan sencillo como poner el símbolo aritmético adecuado.

Aunque vanilla CSS actualmente ofrece esta característica también en forma de la función `calc()`, la alternativa de Sass es más rápida, tiene operaciones `%` y puede ser aplicada a una gama más amplia de datos, como por ejemplo **_colores y strings_**.

```scss
/* SCSS */

button {
  width: 400px / 2;
}
```

<br>

| Operación          | Símbolo | Ejemplo                | Resultado          | Notas                                                                                          |
| ------------------ | ------- | ---------------------- | ------------------ | ---------------------------------------------------------------------------------------------- |
| **Suma**           | `+`     | `width: 100px + 50px;` | `width: 150px;`    | Se pueden sumar unidades compatibles (ej. px con px, em con em).                               |
| **Resta**          | `-`     | `margin: 20px - 5px;`  | `margin: 15px;`    | Igual que en suma: deben ser unidades compatibles.                                             |
| **Multiplicación** | `*`     | `font-size: 10px * 2;` | `font-size: 20px;` | Solo una unidad debe tener medida (ej. px \* número, no px \* px).                             |
| **División**       | `/`     | `width: 100px / 2;`    | `width: 50px;`     | ⚠️ Requiere uso de interpolación: `#{100px / 2}` para evitar conflictos con CSS puro. **(\*)** |
| **Módulo** (resto) | `%`     | `width: 10 % 3;`       | `width: 1;`        | Solo para números sin unidad. Útil en cálculos personalizados.                                 |

<br>

> **(\*)** ⚠️ Desde Sass 3.5 en adelante, la división `/` ya no se interpreta como matemática por defecto, principalmente para evitar conflictos con la división de CSS. Puedes usar `math.div()` o interpolación (`#{}`) en su lugar.

```scss
/* SCSS */

@use "sass:math";

button {
  width: math.div(400px, 2);
}
```

```css
/* CSS */

button {
  width: 200px;
}
```

> 💡 Además, se pueden usar `@if`, `@each`, `@for`, etc., parte del control de flujo de SASS. Puedes saber más en [SASS: Control de flujo](https://sass-lang.com/documentation/at-rules/control).

<br>

### Vars (variables)

Las `variables` son una manera de **_guardar información que necesites reutilizar_** en tus hojas de estilos: colores, dimensiones, fuentes o cualquier otro valor. Sass utiliza el símbolo dólar (`$`) al principio de la palabra clave para crear una variable.

Estas `variables` se comportan como valores CSS, y su valor puede ser cualquiera que pudiera adquirir una propiedad CSS.

La idea detrás de todo esto es que luego de guardarlos, podamos **volver a utilizar los mismos valores de una manera rápida**, o si es necesario un cambio, podemos **declarar el nuevo valor en un solo lugar** (la definición de la variable), en lugar de aplicar el cambio manualmente a todas partes afectadas por la propiedad.

Una `variable` **se podrá definir fuera o dentro de algún selector**.

- Si se define **_fuera_**, dicha variable será global y podrá utilizarse en cualquier bloque.
- Si se define **_dentro_** de un selector, la variable será local y únicamente se podrá utilizar en el selector que la contiene y en sus selectores anidados.

Una buena práctica común consiste en definir todas las `variables globales` al principio del fichero, para que puedan localizarse rápidamente.

```scss
/* SCSS */

$colorPrimario: cadetblue;
$tipografiaPrincipal: normal 24px "Open Sans", sans-serif;

button {
  background-color: $colorPrimario;
  font-family: $tipografiaPrincipal;
}
```

```css
/* CSS */

button {
  background-color: cadetblue;
  font-family: normal 24px "Open Sans", sans-serif;
}
```

> 🔗 [Documentación SASS: Variables](https://sass-lang.com/documentation/variables)

> 💡 También se pueden utilizar `maps` o `mapas`, para almacenar varios valores relacionados entre sí, dentro de una misma variable. A ellos accederemos mediante un llamado de `clave : valor` (`key : value`). Puedes saber más [aquí](https://sass-lang.com/documentation/values/maps/).

<br>

### Mixins

Nos permiten definir estilos que puedan ser reutilizados en nuestro proyecto.

Además, los `mixins` pueden **_recibir argumentos_**, los cuales te permitirán producir una gran variedad de estilos con unas simples líneas.

Es así como lo `mixins` serán implementados para _reutilizar fragmentos de estilos que puedan tener un resultado diferente en cada lugar donde los declaremos_.

Se invocan con la regla `@include`.

```scss
/* SCSS */

@mixin bold {
  font-weight: bold;
}

@mixin underline($color, $type) {
  text-decoration: underline;
  text-decoration-color: $color;
  text-decoration-style: $type;
}

.btn-1 {
  @include bold;
  @include underline(rgb(255, 255, 255), double);
}

.btn-2 {
  @include bold;
  @include underline(rgb(255, 255, 0), dotted);
}
```

```css
/* CSS */

.btn-1 {
  font-weight: bold;
  text-decoration: underline;
  text-decoration-color: rgb(255, 255, 255);
  text-decoration-style: double;
}

.btn-2 {
  font-weight: bold;
  text-decoration: underline;
  text-decoration-color: rgb(255, 255, 0);
  text-decoration-style: dotted;
}
```

> 🔗 [Documentación SASS: Mixins](https://sass-lang.com/documentation/at-rules/mixin)

> 💡 Por otra parte, existen los `@extend` en SASS. En este caso, se utilizan para compartir fragmentos de estilos **_idénticos_** entre componentes. Puedes saber más [aquí](https://sass-lang.com/documentation/at-rules/extend/).

<br>

### Funciones

SASS permite definir `funciones` personalizadas para calcular y retornar valores. Para esto, utilizamos las reglas `@function` y `@return` respectivamente.

En algunas ocasiones, pueden parecer iguales o similares a los `mixins` en ciertos aspectos, pero la realidad es que una `función` está pensada principalmente para realizar cálculos y retornarlos como un posible valor de propiedad CSS, y no para reutilizar propiedades y/o valores.

```scss
/* SCSS */

@function rem($pixeles) {
  @return math.div($pixeles, 16) * 1rem;
}

button {
  font-size: rem(32);
}
```

```css
/* CSS */

button {
  font-size: 2rem;
}
```

> 🔗 [Documentación SASS: Funciones personalizadas](https://sass-lang.com/documentation/at-rules/function)

<br>
<hr>

<div align="center">
<a href="./animaciones.md">⬅️ Animaciones y Transiciones</a>
  &#160;	&#160;	&#160;	&#160;	&#160;	🔸  &#160;	&#160;	&#160;	&#160;	&#160;
<a href="../Clase-4/responsive.md">Responsive Design ➡️</a>
</div>
