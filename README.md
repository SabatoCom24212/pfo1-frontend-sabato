# PFO1 · Landing de portafolio personal

Landing personal desarrollada para la **PFO1 – Landing de portafolio personal** de la materia
*Desarrollo de Sistemas Web · Front End* (2do cuatrimestre, 2026). La consigna pedía construir,
en HTML y CSS, una página que presente el perfil, las habilidades y una vía de contacto,
enlazando de forma visible el perfil de GitHub, cumpliendo requisitos técnicos de semántica,
maquetación con Flexbox/Grid, tipografía con Google Fonts, diseño responsive, una animación o
transición, imágenes con `alt` y un formulario accesible con `label`.

- **Autor:** Ángel Sabato
- **GitHub:** <https://github.com/SabatoCom24212>
- **URL publicada:** <https://pfo1-frontend-sabato.vercel.app/>

## Cómo está construida

- `index.html` — estructura semántica (`header`, `nav`, `main` con `section`s, `footer`).
- `styles.css` — hoja de estilos propia, sin frameworks.
- `assets/` — una ilustración SVG propia (`hero-terminal.svg`), no generada por IA ni de bancos de imágenes.

## Decisiones de diseño

El concepto visual es el de una **sesión de terminal**: la navegación imita la barra de una
ventana de terminal, cada sección se presenta como un comando (`$ whoami`, `$ cat skills.json`,
`$ git log --formacion-continua`, `$ contact --send`) y la sección de "Formación continua" se
muestra como un historial estilo `git log`, con una línea de tiempo vertical construida con
`::before`/posicionamiento absoluto en lugar de librerías externas. Elegí esta metáfora porque
conecta directamente con mis tres áreas de interés (desarrollo, testing y ciberseguridad), en
vez de usar una estética genérica.

- **Color:** paleta oscura (`#0b0f0e` / `#121815`) con dos acentos con significado propio: ámbar
  (`#f0a868`) para la identidad principal y foco, y cian (`#6ee7d8`) para elementos interactivos
  y de navegación, evitando el verde neón típico de las interfaces "hacker" genéricas.
- **Tipografía:** `JetBrains Mono` para títulos, etiquetas y elementos de interfaz (refuerza la
  estética de terminal) y `Inter` para el texto de lectura (mejor legibilidad en párrafos
  largos). Ambas se importan desde Google Fonts y se referencian mediante variables CSS
  (`--font-mono`, `--font-sans`), junto con variables de color, espaciado y radios de borde
  definidas en `:root` y usadas en toda la hoja de estilos.
- **Maquetación:** Grid para las secciones de habilidades, "Sobre mí" y contacto (columnas que
  colapsan a una sola en mobile) y Flexbox para la navegación, los chips de tecnologías y los
  botones.
- **Animación:** la sección de inicio simula un efecto de "boot sequence"/máquina de escribir
  (`@keyframes type-h1`, `reveal`, `blink`) hecho enteramente en CSS, con delays escalonados por
  línea y un cursor parpadeante. Se respeta `prefers-reduced-motion` para desactivar todas las
  animaciones cuando el usuario lo prefiere.
- **Accesibilidad:** hay un *skip link* al contenido principal, `focus-visible` visible en todos
  los elementos interactivos, roles y `aria-label` en la navegación y el enlace a GitHub, texto
  alternativo descriptivo en la imagen decorativa e informativa `hero-terminal.svg`y el formulario de contacto usa `<label for="">` asociado a cada campo (`name`,
  `email`, `message`) en vez de solo `placeholder`.
- **Contenido:** las tecnologías se agruparon por categoría (lenguajes, frontend, backend, datos
  y ML, testing, bases de datos, herramientas) en lugar de listarlas todas juntas, para que la
  sección sea legible pese a ser una lista larga.

## Declaración de uso de IA

Para esta entrega usé **Claude** (modelo Sonnet, gratuito) como asistente para:

- Traducir la consigna del PFO1 y mis datos personales (perfil, habilidades, historial de
  formación) en la estructura HTML y la hoja de estilos CSS completas.
- Proponer el concepto visual de "terminal / sesión de comandos" y la paleta de colores, la
  tipografía y la animación de escritura, a partir de mis intereses declarados (desarrollo,
  datos, testing y ciberseguridad).
- Redactar este README.

Ya había usado Claude antes para tareas de programación en general, pero no para maquetar una
página completa desde cero, así que esta fue mi primera vez pidiéndole un desarrollo front-end
end-to-end.

Sobre el proceso: revisé el HTML generado para confirmar que la información personal (nombre,
enlace de GitHub, fechas y nombres de los cursos, listado de tecnologías) fuera exactamente la
que yo aporté, sin datos inventados. Ajusté manualmente el orden cronológico de la línea de
tiempo y la agrupación de tecnologías por categoría. También revisé que los requisitos técnicos
de la consigna estuvieran cubiertos uno por uno (semántica, Flexbox/Grid, Google Fonts,
responsive, animación, `alt`, `label`) antes de dar la entrega por terminada, y probé la página
en el navegador reduciendo el ancho de pantalla para confirmar el comportamiento responsive.

No usé imágenes generadas por IA: la ilustración `assets/hero-terminal.svg` es un SVG creado a partir de formas básicas dentro de la misma conversación con Claude, sin fotografías propias ni imágenes de bancos externos.
