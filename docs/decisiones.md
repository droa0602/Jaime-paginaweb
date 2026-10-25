# Decisiones

Por qué elegí X y no Y (colores, estructura, herramientas).

<!-- Formato sugerido por entrada:
## AAAA-MM-DD — Tema
**Elegí:** X
**En vez de:** Y
**Por qué:** ...
-->

## 2026-10-25 — Paso del diseño HTML a Astro
**Elegí:** extraer el HTML y los recursos del archivo exportado (`Jaime Bohorquez.html`) y reescribirlo como `src/pages/index.astro` + `src/layouts/Base.astro` + `src/styles/global.css`.
**En vez de:** usar el archivo exportado tal cual.
**Por qué:** el archivo exportado necesita JavaScript para "desempaquetarse" (pesa ~370 KB y la página no se ve sin JS). En Astro sale HTML estático, rápido en celulares con mala señal.

## 2026-10-25 — Fuentes
**Elegí:** servir Barlow (400, 700) y Barlow Condensed (600) desde `public/fonts/`, solo los subconjuntos latin y latin-ext.
**En vez de:** Google Fonts o todos los pesos/subconjuntos del diseño.
**Por qué:** son los únicos pesos que usa la página; el subconjunto vietnamita no hace falta para español. Sin peticiones a terceros.

## 2026-10-25 — CSS del sistema de diseño
**Elegí:** quedarme solo con los tokens y clases que usa la página (botones, marco "blueprint", duotono).
**En vez de:** copiar el sistema completo (formularios, tablas, diálogos, etiquetas...).
**Por qué:** menos CSS que mantener; se puede recuperar del archivo original si hace falta.
