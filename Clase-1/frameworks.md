# FRAMEWORKS CSS

<br>

## ¿Qué es un Framework CSS?

Un **framework CSS** es una librería preconstruida que contiene código CSS ya escrito y organizado, que puedes utilizar para diseñar sitios web sin tener que escribir todo desde cero.

Estos frameworks nos brindan:

- Sistemas de diseño responsivo
- Componentes UI reutilizables (botones, formularios, tarjetas, menús)
- Utilidades para espaciado, colores, tipografía, etc.
- Consistencia visual y buenas prácticas

<br>

### Ventajas de usar Frameworks CSS

- Ahorro de tiempo
- Consistencia en el diseño
- Componentes listos para usar
- Buena compatibilidad entre navegadores
- Comunidad amplia y bien documentada

<br>

## Principales Frameworks CSS

<br>

### Bootstrap

- Desarrollado por Twitter.
- Usa un sistema de grid de 12 columnas.
- Proporciona muchos componentes: navbar, modales, alertas, etc.
- Se puede personalizar con clases o sobrescribir con CSS.

**¿Cómo se usa?**

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
<button class="btn btn-primary">Botón Bootstrap</button>
```

> 🔗 [Documentación oficial de Bootstrap](https://getbootstrap.com)

<br>

### Tailwind CSS

- Framework de utilidad: se enfoca en clases pequeñas que aplican estilos específicos.
- Permite un control detallado sin escribir CSS personalizado.
- Muy usado con herramientas modernas (React, Vue, etc.)

**¿Cómo se usa?**

```html
<script src="https://cdn.tailwindcss.com"></script>
<button class="bg-blue-500 text-white px-4 py-2 rounded">Botón Tailwind</button>
```

> 🔗 [Documentación oficial de Tailwind](https://tailwindcss.com)

<br>

### Bulma

- Framework basado en Flexbox.
- Sintaxis simple, modular y fácil de leer.
- Ligero y sin dependencias de JavaScript.

**¿Cómo se usa?**

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css">
<button class="button is-primary">Botón Bulma</button>
```

> 🔗 [Documentación oficial de Bulma](https://bulma.io)

<br>

### UIkit

- Framework ligero y modular.
- Incluye componentes como sliders, offcanvas, tooltips, etc.
- Basado en una sintaxis muy concisa.

**¿Cómo se usa?**

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/uikit@3.19.1/dist/css/uikit.min.css" />
<script src="https://cdn.jsdelivr.net/npm/uikit@3.19.1/dist/js/uikit.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/uikit@3.19.1/dist/js/uikit-icons.min.js"></script>
<button class="uk-button uk-button-primary">Botón UIkit</button>
```

> 🔗 [Documentación oficial de UIkit](https://getuikit.com)

<br>

### Material UI (para React)

- Implementa el diseño Material Design de Google.
- No es solo CSS, también incluye componentes JavaScript completos.
- Ideal para proyectos con React.

**¿Cómo se usa?**

```bash
npm install @mui/material @emotion/react @emotion/styled
```

```jsx
import Button from '@mui/material/Button';

function App() {
  return <Button variant="contained">Botón Material UI</Button>;
}
```

> 🔗 [Documentación oficial de Material UI](https://mui.com)

<br> 

### Otros...

Existen una gran variedad de Frameworks CSS pero entre los más utilizados en la actualidad, que no han sido nombrados, se encuentran:

- Semantic UI
- Primer
- Materialize
- Pure CSS
- Skeleton
- Spectre
- Susy
- Miligram

<br>

## ¿Cómo elegir uno?

| Criterio         | Bootstrap        | Tailwind CSS      | Bulma           | UIkit           | Material UI (React) |
|------------------|------------------|--------------------|------------------|------------------|----------------------|
| Facilidad inicial| Alta             | Media              | Alta             | Alta             | Media                |
| Personalización  | Media            | Muy alta           | Alta             | Alta             | Muy alta             |
| Complejidad      | Baja             | Alta               | Baja             | Media            | Alta                 |
| Ideal para       | Prototipado rápido| Interfaces precisas| Proyectos simples| UI limpia modular| Interfaces con React |

<br>

## Recomendaciones de uso

- Evita mezclar varios frameworks en un mismo proyecto.
- Si buscas rapidez: Bootstrap o Bulma.
- Si buscas control y personalización: Tailwind o UIkit.
- Si trabajas con React: Material UI.
- Siempre revisa la documentación oficial.

<br>
<hr>

<div align="center">
<a href="./grids.md">⬅️ CSS Grids</a>
	&#160;	&#160;	&#160;	&#160;	&#160;	🔸  &#160;	&#160;	&#160;	&#160;	&#160;
<a href="./bootstrap.md">Extra: Bootstrap ➡️</a>
</div>