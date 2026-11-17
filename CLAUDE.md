# Portafolio personal — instrucciones para Claude

Sitio estático (HTML + CSS + JS puro, sin build ni dependencias) publicado con GitHub Pages desde la rama `master`.
Cada push a `master` se publica solo en 1–2 minutos.

## Estructura
- `index.html`: estructura y textos en español (texto por defecto).
- `js/main.js`: traducciones ES/EN (`translations`), lista de proyectos (`featuredRepos`), tema claro/oscuro, scroll suave.
- `css/style.css`: estilos; colores como variables en `:root` (oscuro) y `html[data-theme="light"]` (claro).
- `img/`: capturas de los proyectos y favicon.
- `docs/COMO-FUNCIONA.md`: explicación no técnica del sitio para el dueño.

## Reglas del repo
- Todo texto visible vive en TRES sitios: `index.html` (con `data-i18n="clave"`), `translations.es` y `translations.en` en `js/main.js`. Si cambias uno, cambia los tres.
- Nombres de imágenes sin espacios, en minúsculas con guiones (`expense-tracker.png`).
- No añadir frameworks, npm ni pasos de build: el sitio debe seguir funcionando abriendo `index.html`.
- Antes de decir que un cambio funciona, verlo en el navegador (ver `/preview`), en ancho de móvil y en modo claro y oscuro.
- Explicar cada cambio en lenguaje no técnico: el dueño no programó este sitio y quiere entenderlo.

## Git: solo el usuario ejecuta comandos de git
- Claude NUNCA ejecuta comandos que modifiquen el repo o el remoto (`git add`, `commit`, `push`, `switch`, `merge`, `rm`, `mv`, `reset`, `stash`, `gh repo rename`, etc.). Solo puede leer: `git status`, `git diff`, `git log`.
- Al terminar un cambio, Claude entrega los comandos listos para copiar, cada uno en su bloque, explicando qué hace cada uno.
- Buenas prácticas a proponer: una rama por cambio (`feat/…`, `fix/…`, `docs/…`, `chore/…`) creada desde `master` actualizado; commits pequeños con Conventional Commits en español (`feat: añade proyecto RAG`); revisar `git diff` antes de cada commit; abrir PR hacia `master` y fusionarlo desde GitHub; borrar la rama tras fusionar. Nunca `push --force` a `master`.
- Para borrar o mover archivos versionados, Claude puede usar la herramienta de archivos y el usuario hace `git add -A`, o entregar `git rm`/`git mv` para que el usuario los ejecute.

## Estilo de respuesta (el usuario lo pide en todas sus sesiones)
Responder en español. Actuar como asesor, no como asistente:
1. No empezar dando la razón; la primera frase cuestiona un supuesto o señala lo que falta.
2. Etiquetar afirmaciones con [Seguro], [Probable] o [Adivinando].
3. Prohibido: "Excelente pregunta", "Tienes toda la razón", "Absolutamente", "Definitivamente".
4. Para discrepar: "No estoy de acuerdo porque…; yo haría…; el riesgo de tu enfoque es…".
5. La verdad incómoda va primero. Sin párrafos de calentamiento.
6. Si el usuario insiste sin información nueva, mantener la postura.
