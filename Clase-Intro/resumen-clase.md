# CLASE: Herramientas Avanzadas - Principios de Desarrollo Front-End

### Temas del día:

- Editores (VSCode), inspector del navegador
- Entorno/Herramientas de desarrollo: localhost, MAMP
- Principios básicos de accesibilidad y web semántica, SEO
- IA para la generación de código
- Control de versiones: Git / GitHub

## Editores (VSCode), Inspector del Navegador

### Exploradores / Navegadores Web

Para probar nuestra web se necesitaremos más de un explorador para ver si los mismos soportan las etiquetas aplicadas al diseño. Los exploradores más comunes son:

- [Google Chrome](https://www.google.com/intl/es-419/chrome/dr/download/)
- [Mozilla Firefox](https://www.mozilla.org/es-AR/firefox/new/)
- [Opera](https://www.opera.com/es/)
- [Safari](https://www.apple.com/la/safari/)
- [Microsoft Edge](https://www.microsoft.com/es-es/edge/download)

> **`Inspector del navegador`**: El inspector de código es una herramienta proporcionada por los propios navegadores web. Posee varias pestañas con diferentes funcionalidades, como la depuración de HTML, CSS y JavaScript, el análisis de rendimiento y red, entre otras cosas.

Lo ideal es tener al menos dos o tres exploradores para probar la web.

### Editores de código

Son programas que nos permiten **_realizar o escribir el código fuente_** de nuestros proyectos, al ser dinámicos son idóneos para cuando se desarrolla un proyecto con varios lenguajes de programación, permitiendo que se codifiquen todos en un mismo lugar.

Por ejemplo: en el caso de diseño web se puede usar, `HTML`, `CSS`, `JavaScript` o `PHP`, y con un editor de código se puede manejar cualquiera de estos lenguajes y no causar ningún conflicto entre archivos.

El código en sí **_no es más que texto_**, que será interpretado como código cuando se ejecute en el **_contexto_** adecuado. La diferencia es que los editores de código nos ayudan con la tarea de verificar dicho código, autocompletando funciones o palabras claves propias del lenguaje de programación, detectando errores e incluso volviendo más prolijo y legible nuestro código al darle un formato.

Existen muchas opciones que podemos utilizar:

- Visual Studio Code ([versión desktop](https://code.visualstudio.com/Download) / [versión online](https://vscode.dev/))
- [Brackets](https://brackets.io/)
- [WebStorm](www.jetbrains.com/es-es/webstorm/download/)
- [Atom](https://atom-editor.cc)
- [PHPStorm](https://www.jetbrains.com/es-es/phpstorm/download/)

Nosotros vamos a usar `Visual Studio Code (VSC)`. Este editor de código es de propiedad de `Microsoft`, igual que `Github`.

#### Ventajas de VSC

- Se puede personalizar totalmente el aspecto.
- Posibilidad de instalar extensiones para cualquier funcionalidad.
- Compatible con muchos lenguajes de programación.
- Autocompletado inteligente.
- Control de versiones (`git`) integrado.
- Es ligero y rápido de ejecutar.
- Tiene la terminal integrada.
- Gratuito y de código abierto.

#### Más info:

- [Overview de las Chrome Dev Tools](https://developer.chrome.com/docs/devtools/overview)
- [Las 15 mejores extensiones para VSC](https://www.youtube.com/watch?v=lv88bCi7eyg)
- [Atajos de teclado en VSC](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf)

## Entorno / Herramientas de desarrollo

Los entornos de desarrollo nos ayudarán a, entre otras cosas, desplegar un **_servidor local_**.

Cuando creamos sitios web que usan tecnologías como HTML, CSS y especialmente PHP, bases de datos, etc., necesitamos un servidor web que los pueda interpretar y ejecutar. Pero no queremos subir nuestros archivos a internet cada vez que hacemos un cambio...

Por eso usamos un **_servidor local_**: una simulación de un `servidor real`, pero en nuestra propia computadora.

### ¿Qué ventajas tiene?

- **Probar sitios sin internet**: Podemos ver cómo funcionan nuestras páginas directamente en nuestra PC.
- **Ahorramos tiempo**: No tenemos que subir y descargar archivos cada vez que modificamos algo.
- **Trabajamos en privado**: Nadie más podrá ver lo que estamos haciendo hasta que decidamos publicarlo.
- **Simulamos el entorno real**: Un servidor local se comporta como uno en internet, así que podemos ver cómo funcionará nuestro sitio en producción.
- **Usamos lenguajes del lado del servidor**: Tecnologías como `PHP` o `MySQL` no funcionan solo abriendo un archivo en el navegador. Necesitan un servidor que las interprete.

### Configuración de `localhost`

Permite probar nuestros sitios web de forma segura, sin necesidad de subirlos a internet.

**`localhost`** es un término que se usa en informática, más bien un **nombre de dominio reservado**, que se usa para referirse al propio ordenador en el que se está ejecutando un programa. Es como decirle al sistema: _"comunícate contigo mismo"_.

Cuando un desarrollador crea una aplicación web, puede ejecutarla en su propio ordenador y acceder a ella desde el navegador escribiendo:

```bash
http://localhost

http://localhost:3000
```

> Aunque accedamos a `localhost`, realmente nuestro navegador se está comunicando con él mismo a través de _protocolos de red_, igual que lo haría con cualquier sitio web externo. Por eso, es muy útil para **desarrollar y depurar software**.

### Herramientas para utilizar un servidor local

- **[MAMP](https://www.mamp.info/en/mac/)**: Es un paquete que instala Apache, MySQL y PHP en tu computadora (Mac o Windows). Sirve para crear un entorno de desarrollo web local sin complicaciones.
- **[XAMPP](https://www.apachefriends.org/es/index.html)**: Otro paquete similar a MAMP, pero disponible para Windows, Mac y Linux. También instala Apache, MySQL, PHP y Perl. Es muy popular y fácil de usar.
- **Soluciones nativas del sistema**: Algunos sistemas operativos, como Mac y Linux, ya traen Apache preinstalado. No hace falta instalar MAMP o XAMPP: puedes usar lo que el sistema ya trae.
- **[WSL (Windows Subsystem for Linux)](https://www.youtube.com/watch?v=L4f1XHrSJEg)**: Una herramienta que permite usar Linux dentro de Windows. Nos sirve para ejecutar herramientas de desarrollo que normalmente funcionan mejor en Linux.

#### Otros posibles entornos de desarrollo

- **Máquinas virtuales**: Programas que simulan otra computadora dentro de la tuya (como una “computadora dentro de otra”). Nos sirven para probar proyectos en diferentes sistemas operativos o configuraciones sin afectar tu equipo real.
- **Docker (gestor de contenedores)**: Una herramienta moderna que permite crear entornos de desarrollo “contenidos” y portables. Nos sirve para que tu proyecto funcione igual en cualquier computadora o servidor, sin “errores por diferencias de entorno”.
- **Entorno de desarrollo en un servidor remoto**: Desarrollar directamente en un servidor que está en internet (no en tu PC). Es útil si trabajamos en equipo o si nuestra aplicación debe estar siempre disponible desde cualquier lugar.

### Terminal o Consola

En informática, una **_terminal_** o **_consola_** es la aplicación que se utiliza para interactuar con el computador a través de `comandos`. Todos los sistemas operativos la traen.

Para activarla dependiente de cada sistema operativo es:

- **Windows**: Ve al menú o pantalla de Inicio, y escribe "Símbolo del Sistema". O en el cuadro de búsqueda escribe "CMD".
- **Linux**: Aplicaciones → Accesorios → Terminal, o Aplicaciones → Sistema → Terminal.
- **OS (Mac)**: Ve a Aplicaciones → Utilidades → Terminal.

Para manejarse en la terminal existen comando básicos que nos permitirán movernos entre los diferentes directorios, crear carpetas, copiar o eliminar.

Estos son algunos de los más utilizados:

- `LS`: Sirve para ver el contenido de una carpeta.
- `CD`: Sirve para entrar en una carpeta o salir de ella (CD ..).
- `TOUCH`: Sirve para crear archivos.
- `MKDIR`: Con este comando crearás una carpeta nueva. Con RMDIR podrás eliminarla.
- `RM`: Es el comando para eliminar un archivo. Recuerda que no irá a la Papelera, así que
  piensa muy bien antes de borrar algo. Y para eliminar carpeta usa el comando RM -RF.
- `CLEAR`: Limpia la consola.
- `EXIT`: Cierra la ventana de la línea de comandos o símbolo del sistema.

#### Tips de Ayuda

Se recomienda a la hora de iniciarse en el mundo del diseño y desarrollo web:

- Preparar el equipo donde se estará trabajando.
- Instalar todas las aplicaciones necesarias.
- Establecer un objetivo a alcanzar.
- Ser organizado.
- Mantener la curiosidad activa.
- No quedarse sólo con lo visto en clase, el buscar nuevas tecnologías, métodos y desear hacer algo fuera de lo cotidiano, ayuda a crecer profesionalmente.
- Usar palabras claves a la hora de buscar en la web.
- Cumplir con los desafíos.
- Practicar. La práctica, hace al maestro.
- Apoyarse en los recursos de Shifta.
- El internet y las ganas de aprender, son los mejores amigos.

## Principios básicos de accesibilidad y web semántica, SEO

Estos 3 conceptos están muy relacionados. Si una web está bien hecha a nivel de SEO posiblemente también es accesible y utiliza etiquetado semántico.

### Accesibilidad

La accesibilidad web se refiere a la **_práctica de diseñar y desarrollar sitios web que puedan ser utilizados por personas con diversas capacidades_**, incluidas aquellas con discapacidades visuales, auditivas, cognitivas, de movilidad u otras limitaciones que **_no permitan al usuario final percibir la web de la misma forma que nosotros_**.

Esto implica que las páginas web sean navegables con herramientas como lectores de pantalla, teclados alternativos, o subtítulos para el contenido multimedia.

La accesibilidad es importante para asegurar que todas las personas puedan **_interactuar y obtener información en la web de manera equitativa_**, sin barreras.

En resumen tenemos que asegurarnos que nuestra web se puede navegar con el teclado (sin usar el ratón o el trackpad) y que los elementos están suficientemente etiquetados con texto (para que en el caso de los usuarios que no pueden ver puedan entender cada parte del documento).

El organismo **`w3.org` (World Wide Web Consortium)** cita [10 pasos sencillos](https://www.w3.org/WAI/quicktips/) para hacer una web accesible:

1. **_Imágenes y animaciones_**: Usa el atributo `alt` para describir la función de cada elemento visual.
2. **_Mapas de imagen_**: Emplea mapas del lado del cliente y proporciona texto para los puntos de acceso.
3. **_Multimedia_**: Proporciona subtítulos y transcripciones de audio, así como descripciones para los videos.
4. **_Enlaces de hipertexto_**: Usa texto que tenga sentido fuera de contexto. Por ejemplo, evita expresiones como "haz clic aquí".
5. **_Organización de la página_**: Utiliza encabezados, listas y una estructura consistente. Emplea CSS para el diseño y el estilo cuando sea posible.
6. **_Gráficos y diagramas_**: Resume el contenido o utiliza el atributo `longdesc` para descripciones más detalladas.
7. **_Scripts, applets y complementos_**: Proporciona contenido alternativo en caso de que las funciones activas no sean accesibles o no estén soportadas.
8. **_Marcos (frames)_**: Usa el elemento `noframes` y títulos significativos.
9. **_Tablas_**: Organiza el contenido de forma que pueda leerse línea por línea de manera coherente. Proporciona un resumen.
10. **_Revisa tu trabajo_**: Valida el contenido. Utiliza herramientas, listas de verificación y guías.

### Niveles de accesibilidad

Los **_niveles de accesibilidad_** se refieren a los grados de conformidad que puede tener una web con las _Pautas de Accesibilidad para el Contenido Web (WCAG)_, un conjunto de recomendaciones para hacer que los sitios web sean accesibles para todas las personas.

#### `Nivel A` (Básico)

Es el nivel mínimo de accesibilidad. Cumple con los requisitos más esenciales para que un sitio web sea usable por personas con discapacidades.

Por ejemplo:

- El contenido no debe depender exclusivamente del color para transmitir información.
- Se debe poder navegar solo con teclado.
- El texto debe tener alternativas para contenido no textual (como imágenes).

> 📌 Obligatorio para que el sitio no sea inaccesible.

#### `Nivel AA` (Intermedio)

Es el estándar más adoptado (exigido por leyes en muchos países). Incluye todos los requisitos del Nivel A, más criterios adicionales que mejoran la experiencia para un mayor número de usuarios.

Por ejemplo:

- Contraste suficiente entre texto y fondo.
- Navegación coherente en todas las páginas.
- Texto redimensionable sin pérdida de contenido o funcionalidad.

> 📌 Recomendado como objetivo para la mayoría de los sitios web.

#### `Nivel AAA` (Avanzado)

Es el nivel más alto de accesibilidad. Cumple con todos los criterios de los niveles A y AA, además de otros más exigentes.

Por ejemplo:

- Subtítulos en tiempo real para todo contenido multimedia en directo.
- Lenguaje más simple y comprensible.
- Posibilidad de personalizar la presentación del contenido.

> 📌 Difícil de alcanzar en todos los contenidos, no es obligatorio ni siempre recomendable para todo tipo de sitios, pero sí ideal para casos específicos (como portales gubernamentales, educativos o de salud).

#### Atributos ARIA

Los atributos **`ARIA` (Accessible Rich Internet Applications)** complementan el código HTML y proporcionan información adicional a tecnologías de asistencia, como lectores de pantalla, cuando no existe otro mecanismo por el cual puedan ser correctamente interpretadas.

Por ejemplo, ARIA habilita accesibilidad a widgets de JavaScript, sugerencias de formularios, mensajes de error, actualizaciones de contenido en vivo y más.

Incluyen roles (para definir el tipo de elemento), propiedades (para describir su contexto) y estados (para indicar condiciones como “expandido” o “seleccionado”), mejorando así la navegación y usabilidad en entornos web.

> [Guía ARIA](https://developer.mozilla.org/es/docs/Web/Accessibility/ARIA)

#### Herramientas que podemos utilizar

- [Análisis de accesibilidad](https://www.accessibilitychecker.org/)
- [Validador de HTML y CSS](https://validator.w3.org/)
- [Listado de herramientas](http://www.w3.org/TR/WCAG)
- [Video: Curso de accesibilidad (6 videos cortos)](https://www.youtube.com/watch?v=wY8hC5wCNIE)

### Web semántica

Se refiere al uso apropiado de etiquetas HTML5 de manera que se pueda entender su función dentro de todo el documento.

Es posible construir una web entera usando solo etiquetas `<div>`, pero en una web semántica debemos usar etiquetas con sentido como `header`, `nav`, `main`, `article`, `section`, `aside`, `footer`, `figure`, etc.

Usar HTML semántico mejora la accesibilidad, facilita la indexación por motores de búsqueda y da una estructura más lógica al contenido de una página.

### SEO desde el punto de vista de la programación

El **_SEO (Search Engine Optimization)_** es un conjunto de estrategias y técnicas que se aplican en un sitio web para mejorar su posicionamiento en los resultados de búsqueda orgánicos (no pagados) de motores como Google.

El objetivo principal del SEO es **_aumentar el tráfico de calidad_** al sitio web, logrando que aparezca en los primeros lugares cuando los usuarios busquen términos relacionados con su contenido o servicios, logrando que llegue así a nuestro _cliente potencial_.

Existen 4 aspectos a tratar para conseguir un buen posicionamiento:

1. A nivel técnico, etiquetar correctamente el html con encabezados, títulos explicativos, urls claras y descriptivas, etiquetas meta y en general HTML semántico.

```html
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="Ejemplo de Descripción" />
  <meta
    name="keywords"
    content="HTML, CSS, JS, META, PALABRAS CLAVE, EJEMPLO"
  />
  <title>Título</title>
</head>
```

2. Un contenido de calidad siempre será más relevante para los buscadores.
3. A nivel técnico, que la web se cargue rápido y las imágenes estén optimizadas, que el diseño responsive funcione bien, beneficia también al SEO.
4. Finalmente es bueno aumentar la reputación del sitio consiguiendo menciones de calidad (links) en otros sitios web. Además, un `sitemap` (un documento xml que describa la estructura de la web) también es bueno para posicionar nuestra web.

#### Más info:

- [Guia SEO de Google](https://developers.google.com/search/docs/fundamentals/seo-starter-guide?hl=es)

#### Herramientas:

- [Google Search Console (para optimizar a partir de un sitemap)](https://search.google.com/search-console/about)
- [Google Analytics (analítica web)](https://developers.google.com/analytics?hl=es)
- [Seoptimer (herramienta para auditar webs)](https://www.seoptimer.com/)

## IA para la generación de código

La **_inteligencia artificial_** en el desarrollo de software hace que el proceso sea mucho **_más ágil y eficiente_**.

Ayuda a los desarrolladores **_generando fragmentos de código_** automáticamente y hasta **_automatizando pruebas_**, así que se pierde menos tiempo en tareas repetitivas.

También sirve para **_optimizar el rendimiento_** de las aplicaciones, sugiriendo cambios que hacen que el software sea más rápido y use menos recursos.

Herramientas de IA como `GitHub Copilot` o `ChatGPT` funcionan como “compañeros de equipo” virtuales, ayudando a los desarrolladores a resolver dudas o sugiriendo mejoras al código.

- [GitHub Copilot](https://github.com/features/copilot)
  - Existe una [versión de educación de Github Copilot](https://education.github.com/discount_requests/application?type=student) para estudiantes.
- [Chatgpt](https://chatgpt.com/)
- [Claude](https://claude.ai/new)
- [Google Gemini](https://gemini.google.com/)
- [NotebookLM](https://notebooklm.google/)
- [Augment Code](https://www.augmentcode.com)
- [Google Stitch](https://stitch.withgoogle.com) (Diseño)

### Límites y potencial de la IA en la generación de código

La IA todavía **_comete errores_** en lógica compleja o cuando las instrucciones son ambiguas. Además, tiende a reproducir patrones comunes y podría no ofrecer soluciones novedosas para problemas específicos.

Aun así, combinada con **_supervisión humana_**, es una herramienta poderosa que puede mejorar la productividad en el desarrollo de aplicaciones.

---

<div align="center">
  <a href="./git-github.md">Guía Git / Github</a>
</div>
