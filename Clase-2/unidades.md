# UNIDADES DE MEDIDA

<br>

Las medidas en CSS se emplean, entre otras, para definir la altura, anchura y márgenes de los elementos y para establecer el tamaño de letra del texto. Todas las medidas se indican como un valor numérico entero o decimal seguido de una unidad de medida (sin ningún espacio en blanco entre el número y la unidad de medida).

> 📌 **Nota:** Si el valor es 0, la unidad de medida es opcional. Si el valor es distinto a 0 y no se indica ninguna unidad, la medida se ignora completamente. Algunas propiedades permiten indicar medidas negativas, aunque habitualmente sus valores son positivos. Si el valor decimal de una medida es inferior a 1, se puede omitir el 0 de la izquierda (`0.5em` es equivalente a `.5em`).

<br>

## Unidades Absolutas y Relativas

CSS divide las unidades de medida en dos grupos, absolutas y relativas:

- Las medidas **_relativas_** definen su valor en relación con otra medida, por lo que para obtener su valor real, se debe realizar alguna operación con el valor indicado. Estas **se adaptan** al contexto, como el tamaño del contenedor, del texto base o de la ventana del navegador.

- Las unidades **_absolutas_** establecen de forma completa el valor de una medida, por lo que su valor real es directamente el valor indicado. Estas unidades **no cambian** según el entorno (pantalla, resolución, etc.). Son fijas.

> 📌 **Nota:** Aunque sean _absolutas_, el resultado puede variar en pantallas con diferentes densidades de píxeles.

Dentro de las unidades de medida más utilizadas, están:

| Absolutas                        | Relativas                                             |
| -------------------------------- | ----------------------------------------------------- |
| `px`: Píxeles (unidad más común) | `em`: Relativa al tamaño de fuente del elemento padre |
| `pt`: Puntos (1 pt = 1/72 in)    | `rem`: Relativa al tamaño de fuente raíz (`html`)     |
| `pc`: Picas (1 pc = 12 pt)       | `ex`: Altura de la letra "x" del elemento actual      |
| `in`: Pulgadas (1 in = 2.54 cm)  | `ch`: Ancho del dígito "0" (cero) del elemento actual |
| `cm`: Centímetros                | `%`: Porcentaje del valor del elemento padre          |
| `mm`: Milímetros                 | `vw`: 1% del ancho del viewport (pantalla)            |
|                                  | `vh`: 1% de la altura del viewport                    |
|                                  | `vmin`: 1% del menor entre ancho y alto del viewport  |
|                                  | `vmax`: 1% del mayor entre ancho y alto del viewport  |

> 🔗 [Documentación Unidades de Medida](https://developer.mozilla.org/es/docs/Learn_web_development/Core/Styling_basics/Values_and_units#n%C3%BAmeros_longitudes_y_porcentajes)

<br>

## Modificar el valor por defecto de `rem`

La unidad de medida `rem` significa **"root em"**, toma como referencia el tamaño de fuente del elemento raíz, es decir, el `<html>`.

Por defecto, la mayoría de los navegadores asignan al `<html>` un tamaño de **16px**, por lo tanto:

- `1rem` = 16px
- `0.5rem` = 8px
- `2rem` = 32px

Pero tú puedes cambiarlo así:

```css
html {
  font-size: 10px;
}
```

Ahora:

- `1rem` = 10px
- `0.5rem` = 5px
- `2rem` = 20px

Este truco es muy común porque **simplifica los cálculos**. Muchos desarrolladores lo usan para trabajar con `rem` como si fueran píxeles.

> 📌 **Nota:** Cambiar el `font-size` del `<html>` afecta a todos los valores definidos en `rem`. Pero **no afecta a `em`**, que depende del tamaño de fuente **del elemento padre**, no del raíz.

Otra posibilidad es cambiar el `font-size` del elemento raíz a un valor de **62.5%**, ya que el 62.5% de 16px es igual a **10px**.

```css
html {
  font-size: 62.5%;
}
```

Esto mantiene compatibilidad con los navegadores y es más flexible para escalado responsivo.

<br>
<hr>

<div align="center">
<a href="./fonts.md">⬅️ Fonts</a><!--
  &#160;	&#160;	&#160;	&#160;	&#160;	🔸  &#160;	&#160;	&#160;	&#160;	&#160;
<a href="">Animaciones y Transiciones ➡️</a>-->
</div>
