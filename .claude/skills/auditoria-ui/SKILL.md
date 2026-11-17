---
name: auditoria-ui
description: Usar cuando el usuario quiera revisar o rediseñar la apariencia del portafolio para que se vea profesional, con identidad propia y no genérico ni "hecho con IA".
---
# Auditoría de UI del portafolio

Objetivo: que la página parezca diseñada por una persona con criterio, no salida de una plantilla de IA.

## 1. Mirar antes de opinar
Abrir el sitio con `/preview`. Capturar: escritorio (1280px) y móvil (375px), tema claro y oscuro, ES y EN. Toda observación debe apoyarse en una captura o en una línea de código concreta.

## 2. Señales de "vibecodeado" a buscar
- Fondos con degradados radiales de colores + cuadrícula + desenfoque (glassmorphism) en TODAS las tarjetas.
- Todo con bordes muy redondeados (24–32px) y sombra grande, sin jerarquía: cada bloque pesa lo mismo.
- "Pills"/etiquetas en mayúsculas sobre cada título (eyebrow repetido en cada sección).
- Hover que levanta todo (`translateY`) aunque no sea clicable.
- Cifras sin respaldo ("100%", "24/7", "+3") y frases genéricas ("soluciones robustas, escalables y mantenibles", "construir un mundo mejor").
- Iniciales en un cuadrado en lugar de foto; placeholders tipo "Espacio para imagen".
- Paleta turquesa + ámbar sobre azul marino; fuentes Space Grotesk/Manrope/Inter por defecto.
- Tres tarjetas de habilidades con título + párrafo genérico.

## 3. Criterios de un diseño con identidad
- Jerarquía clara: un elemento protagonista por pantalla; los proyectos son el contenido principal, no los adornos.
- Contenido específico > decoración: métricas reales, stack real, capturas reales, un párrafo con voz propia.
- Un solo color de acento, usado con intención (enlaces, CTA principal).
- Tipografía: máximo dos familias, escala consistente, líneas de 60–75 caracteres.
- Espaciado en una escala (4/8/16/24/48/96) en vez de valores arbitrarios.
- Superficies planas o con borde fino; sombras/blur solo donde aporten profundidad.
- Interacción solo en lo clicable; foco visible con teclado; contraste AA en ambos temas.
- `prefers-reduced-motion` respetado.

## 4. Entregable
1. Lista de hallazgos ordenados por impacto, cada uno con: qué se ve, por qué resta (en lenguaje no técnico), archivo:línea y propuesta.
2. Esperar confirmación del usuario antes de editar.
3. Al aplicar: cambiar los tres sitios de texto si aplica (ver CLAUDE.md), volver a capturar y mostrar antes/después.
4. No ejecutar git: entregar los comandos al usuario.
