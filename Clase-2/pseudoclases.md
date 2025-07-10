# PSEUDO-CLASES

<br>

## ¿Qué es una pseudo-clase?

Una _**pseudo-clase CSS**_ es una palabra clave que se añade a los selectores y que especifica un estado especial del elemento seleccionado.
Por ejemplo, `:hover` aplicará un estilo cuando el usuario pase su mouse sobre el elemento especificado por el selector.

Su sintaxis es la siguiente:

```css
/* Pseudocódigo */

selector:pseudo-clase {
  propiedad1: valor;
  propiedad2: valor;
}
```

```css
/* Ejemplo real */

a:hover {
  color: red;
}
```

Las **_pseudo-clases_**, junto con los **_pseudo-elementos_**, permiten aplicar un estilo a un elemento no sólo en relación con el contenido del árbol de documento, sino también en relación a factores externos como:

- El historial del navegador (`:visited`),
- El estado de su contenido (como `:checked` en checkbox de formularios),
- La posición del ratón (`:hover`).

> 🔗 [Documentación Pseudo-Clases](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

<br>

## Pseudo-clase `:link`

La pseudo-clase `:link` representa un elemento que aún no se ha visitado. Coincide con cada elemento no visitado `<a>`, `<area>`, o `<link>` que tiene un atributo `href`.

```css
a:link {
  background-color: #ff0055;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/:link).

<br>

## Pseudo-clase `:visited`

La pseudo-clase `:visited` representa enlaces que el usuario ya ha visitado. Por motivos de privacidad, los estilos que se pueden modificar con este selector son muy limitados.

```css
a:visited {
  background-color: #ff0055;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited).

<br>

## Pseudo-clase `:hover`

La pseudo-clase `:hover` coincide cuando el usuario interactúa con cierto elemento con un dispositivo señalador, pero no necesariamente lo activa. Generalmente se activa cuando el usuario se desplaza sobre un elemento con el cursor (puntero del mouse).

```css
a:hover {
  background-color: #ff0055;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover).

<br>

## Pseudo-clase `:active`

La pseudo-clase `:active` representa un elemento que el usuario está activando. Cuando se usa un mouse, la "activación" generalmente comienza cuando el usuario presiona el botón primario del mouse y termina cuando se suelta.

```css
a:active {
  background-color: #ff0055;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/:active).

> 🚨 **IMPORTANTE**: Los estilos de las pseudo-classes `link`, `visited`, `hover`, y `active` podrán ser anulados entre ellos dependiendo del orden en el que fueron definidos. Para darle un estilo apropiado a los enlaces, coloque las reglas como lo define el orden **LVHA**: `:link — :visited — :hover — :active`.

<br>

## Pseudo-clase `:focus`

La pseudo-clase `:focus` representa un elemento (como una entrada/input de formulario) que ha recibido el foco. Generalmente se activa cuando el usuario hace click, toca un elemento o lo selecciona con la tecla "Tab" del teclado.

```css
input:focus {
  background-color: #ff0055;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus).

<br>

## Pseudo-clases `:disabled` & `:checked`

La pseudo-clase `:disabled` de CSS representa a cualquier elemento deshabilitado. Un elemento se encuentra deshabilitado si no puede ser activado (por ejemplo ser selecionado, hacer click en él o aceptar texto de entrada) ni aceptar el foco. El elemento tiene además un estado habilitado en el cual puede ser activado o recibir foco.

La pseudo-clase `:checked` de CSS representa cualquier radio (`<input type="radio">`), checkbox (`<input type="checkbox">`) u option (`<option>` en un elemento `<select>`) que está marcado o conmutado a un estado **_on_**.

> 🚨 **IMPORTANTE**: Estas pseudo-clases solo son aplicables a elementos de formularios.

```css
*:disabled {
  background-color: #ff0055;
}

input:checked {
  background-color: #ff0055;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento (`:disabled`), haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled).

> 🔗 Para ver un ejemplo de su funcionamiento (`:checked`), haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked).

<br>

## Pseudo-clases `:first-child` & `:last-child`

La pseudo-clase `:first-child` de CSS representa el primer elemento entre un grupo de elementos hermanos.

Y la pseudo-clase `:last-child` de CSS representa el último elemento entre un grupo de elementos hermanos.

```css
a:first-child {
  background-color: #ff0055;
}

a:last-child {
  background-color: #ff0055;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento (`:first-child`), haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/:first-child).

> 🔗 Para ver un ejemplo de su funcionamiento (`:last-child`), haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/:last-child).

<br>

## Pseudo-clase `:nth-child( )`

Con `:nth-child(N)` podremos aplicar sus estilos a todos los elementos hijos cuya posición sea un número “N” respecto a un padre. Este número "N" no tiene que ser necesariamente un número entero para especificar una posición fija (la posición 2, por ejemplo), ya que también permite insertar fórmulas y palabras específicas.

```css
a:nth-child(2) {
  background-color: #ff0055;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child).

<br>

## Pseudo-clase `:not( )`

La pseudo-clase `:not( )` representa elementos que no coinciden con una lista de selectores. Es decir, aplica a todos los elementos "A", excepto a los incluidos como elementos "B".

Como evita que se seleccionen elementos específicos, se lo conoce como la **pseudo-clase de negación**.

Por ejemplo, podríamos aplicar unos estilos a todos los elementos `<a>` y evitar que éstos se apliquen a otras capas con un `id` o `class` determinado. En el siguiente ejemplo hacemos justo esto, evitando que se apliquen los estilos a los elementos del tipo `<a>` que tienen como clase “boton”.

```css
a:not(.boton) {
  background-color: #ff0055;
}
```

> 🔗 Para ver un ejemplo de su funcionamiento, haz click [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/:not).

<br>
<hr>

<div align="center">
<a href="../Clase-1/bootstrap.md">⬅️ Extra: Bootstrap</a>
	&#160;	&#160;	&#160;	&#160;	&#160;	🔸  &#160;	&#160;	&#160;	&#160;	&#160;
<a href="./pseudoelementos.md">Pseudo-Elementos ➡️</a>
</div>
