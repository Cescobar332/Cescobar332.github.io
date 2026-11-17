# Cómo funciona tu portafolio (sin tecnicismos)

Piensa en la página como una casa con tres partes:

| Archivo | Analogía | Qué hace |
|---|---|---|
| `index.html` | Los muros y los muebles | Dice QUÉ hay en la página: el menú, el título grande, las secciones "Sobre mí", "Habilidades", "Proyectos", "Contacto". |
| `css/style.css` | La pintura y la decoración | Dice CÓMO se ve: colores, tamaños, bordes redondeados, cómo se reacomoda en el celular. |
| `js/main.js` | La electricidad | Hace que las cosas reaccionen: cambiar idioma, cambiar tema, dibujar las tarjetas de proyectos. |

No hay servidor ni base de datos. GitHub Pages simplemente entrega estos archivos al navegador del visitante, y el navegador los arma.

## Qué pasa cuando alguien abre la página
1. El navegador lee `index.html` y muestra los textos en español.
2. Aplica los estilos de `style.css` (por defecto, tema oscuro).
3. Ejecuta `main.js`, que:
   - **Idioma:** mira si el visitante ya eligió idioma antes (lo recuerda en su navegador). Si no, usa el idioma del navegador. Luego recorre cada texto marcado con `data-i18n="algo"` y lo reemplaza por la traducción guardada en la "libreta" `translations`.
   - **Tema:** igual — recuerda si elegiste claro, oscuro o "sistema" (sigue la configuración del computador del visitante).
   - **Proyectos:** las tarjetas NO están escritas en el HTML. Hay una lista llamada `featuredRepos` en `main.js` y el código fabrica una tarjeta por cada elemento. Para añadir un proyecto se edita esa lista, no el HTML.
   - **Menú:** al hacer clic en un enlace del menú, desliza suavemente hasta la sección.

## La trampa principal
Cada texto está escrito **tres veces**: en `index.html`, en la traducción española y en la inglesa de `main.js`. Si cambias solo el HTML, al cambiar de idioma y volver se pierde tu cambio. Siempre cambia los tres.

## Cosas que sobran
- La carpeta `php/` son ejercicios viejos del repositorio original. GitHub Pages no ejecuta PHP, así que no hacen nada en la página.

## Cómo verla en tu computador
En la carpeta del repo: `python3 -m http.server 8000` y abre http://localhost:8000.
