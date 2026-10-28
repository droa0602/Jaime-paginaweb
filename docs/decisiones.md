# Decisiones

Por qué elegí X y no Y (colores, estructura, herramientas).

<!-- Formato sugerido por entrada:
## AAAA-MM-DD — Tema
**Elegí:** X
**En vez de:** Y
**Por qué:** ...
-->

## 2026-10-25 — Paso del diseño HTML a Astro
**Elegí:** extraer el HTML y los recursos del archivo exportado (`docs/referencias/Jaime Bohorquez.html`) y reescribirlo como `src/pages/index.astro` + `src/layouts/Base.astro` + `src/styles/global.css`.
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

## 2026-10-25 — Versión para computador
**Elegí:** mantener el diseño de celular tal cual y, desde 900 px de ancho, una página de hasta 1200 px: portada partida (nombre a la izquierda, foto a la derecha), "Quién soy" y "Servicios" en dos columnas, y el botón de WhatsApp flotando abajo a la derecha.
**En vez de:** dejar la columna de 480 px centrada también en computador.
**Por qué:** en pantallas anchas la columna angosta se veía vacía a los lados; el diseño original solo contemplaba celular.

## 2026-10-25 — Servicios antes que la foto
**Elegí:** poner "Servicios" justo después de la portada (al lado en computador) y la foto junto a "Quién soy".
**En vez de:** el orden del diseño original (portada, foto, quién soy, servicios).
**Por qué:** pedido del cliente: que lo primero que se vea sea qué hace Jaime; la foto acompaña mejor la presentación personal.

## 2026-10-28 — Rediseño completo con la skill design-taste-frontend
**Elegí:** rehacer la interfaz con la dirección "la página es el objeto": la portada es la calcomanía con el teléfono que el electricista deja pegada en la tapa del tablero, los servicios son el directorio de circuitos del tablero (una hoja con bordes ondulados), el contacto es un cupón para recortar y el pie es el reverso de la calcomanía.
**En vez de:** el diseño "Industry" (azul grisáceo, marcos con esquinas), que no le gustó al cliente.
**Por qué:** la idea sale del oficio de Jaime y no de una plantilla. Se mantuvo el orden de secciones que le gusta al cliente (portada, servicios, foto + quién soy, contacto, WhatsApp fijo).

## 2026-10-28 — Colores
**Elegí:** solo dos tintas, amarillo `#f5c518` y casi negro `#16130f`, como las señales de "riesgo eléctrico".
**En vez de:** la paleta rosada y berenjena que sorteó la skill.
**Por qué:** el rosado no tiene nada que ver con un electricista; el amarillo y negro es el color propio del oficio y da contraste muy alto para leer al sol en el celular.

## 2026-10-28 — Fuente
**Elegí:** Zilla Slab (400, cursiva 400, 600), servida desde `public/fonts/`.
**En vez de:** Barlow y Barlow Condensed.
**Por qué:** la sorteó la skill; una slab se ve como letra impresa de calcomanía o volante. Se sigue sirviendo desde el sitio, sin Google Fonts.

## 2026-10-28 — Fotos
**Elegí:** fotos de uso libre de Wikimedia Commons (amanecer en Villanueva, cultivos de caucho en Villanueva, arrozal en Maní, un tablero viejo, breakers nuevos), todas en blanco y negro, optimizadas por Astro a WebP y con créditos en el pie.
**En vez de:** dejar recuadros vacíos o usar fotos genéricas de bancos de imágenes.
**Por qué:** todavía no hay fotos de Jaime. Estas muestran su región y su oficio sin hacerse pasar por trabajos suyos. Se cambian cuando lleguen las reales.

## 2026-10-28 — Cupón de WhatsApp
**Elegí:** en Contacto, un formulario donde se elige qué pasó (cada opción parece un breaker que sube) y el barrio o vereda; abre WhatsApp con el mensaje ya escrito.
**En vez de:** solo un botón de WhatsApp.
**Por qué:** a quien tiene una urgencia le ahorra escribir, y a Jaime le llega el problema y el lugar desde el primer mensaje. Funciona también sin JavaScript.

## 2026-10-28 — Sin video
**Elegí:** no poner video, aunque la skill lo sugiere.
**Por qué:** el brief pide una página liviana para celulares con mala señal.

## 2026-10-28 — Página de dos secciones
**Elegí:** dejar solo la portada y los servicios. La caja de datos (30 años, 24 h, garantía) pasó a la columna de servicios, en lugar de la foto del tablero.
**En vez de:** las cinco partes del rediseño (con "Quién soy", el cupón de WhatsApp, la foto de los cultivos y el pie "Voy hasta su puerta").
**Por qué:** pedido del cliente: le sobraban esas secciones. El contacto queda en los botones de la portada y en el botón fijo de WhatsApp. Del pie queda solo el crédito de la foto de la portada, porque la licencia CC BY-SA lo exige.

## 2026-10-28 — Bordes rectos
**Elegí:** que todos los recuadros amarillos tengan bordes rectos, como la calcomanía de la portada.
**En vez de:** la hoja de servicios con bordes ondulados y la caja de datos con línea de puntos arriba.
**Por qué:** pedido del cliente.

## 2026-10-28 — Portada derecha y colores de letra
**Elegí:** la tarjeta de la portada derecha (sin inclinación); el texto sobre el fondo oscuro en `#e5ded2` y el texto sobre el amarillo en azul oscuro `#132841` (los detalles de cada servicio en un azul más suave, `#3e4d63`).
**En vez de:** la tarjeta inclinada, el texto amarillo sobre el fondo oscuro y el casi negro sobre el amarillo.
**Por qué:** pedido del cliente. Los dos colores siguen teniendo buen contraste para leer en el celular.

## 2026-10-28 — Azul en vez de amarillo, una sola letra clara
**Elegí:** todos los recuadros y botones que eran amarillos ahora son azul oscuro `#132841`, y todo el texto es `#e5ded2` (las líneas secundarias, como el detalle de cada servicio, en `#b9b3a8`). El fondo sigue casi negro.
**En vez de:** recuadros amarillos con letra azul (la entrada anterior, que fue un malentendido del pedido).
**Por qué:** pedido del cliente. Se dejó de usar el amarillo de las señales de riesgo eléctrico.

## 2026-10-28 — Servicios alineados a la izquierda
**Elegí:** el contenido de la hoja de servicios alineado a la izquierda, en una columna centrada dentro del recuadro azul.
**En vez de:** títulos centrados.
**Por qué:** pedido del cliente.

## 2026-10-28 — Recuadro de experiencia
**Elegí:** un "30" grande con "años de oficio" al lado y, debajo, dos líneas: "De lunes a domingo" y "Trabajo con garantía". En tablet el número y las dos líneas van lado a lado.
**En vez de:** tres columnas iguales (30 años / 24 h urgencias / Sí garantía).
**Por qué:** pedido del cliente: cambiar "24 h" por "De lunes a domingo" y ordenar mejor el texto. Con una sola cifra grande se lee primero la experiencia, y las otras dos ideas son frases, no números.

## 2026-10-28 — Botón flotante de WhatsApp
**Elegí:** el botón en azul claro `#798da6`, con su borde (en computador) y la franja de fondo de la barra (en celular) en azul oscuro `#132841`. La letra del botón va en azul oscuro.
**En vez de:** botón azul oscuro con borde y franja casi negros.
**Por qué:** pedido del cliente. La letra clara `#e5ded2` sobre `#798da6` tiene muy poco contraste (2,5:1) y no se lee bien al sol; el azul oscuro sí cumple para texto grande.

## 2026-10-28 — Alineación y puntuación en servicios
**Elegí:** la frase "Casas, locales y fincas…" con el mismo borde interno que el texto del recuadro de experiencia, y punto final en cada descripción de la hoja de servicios, en la nota de debajo del título y en las dos líneas finales.
**Por qué:** pedido del cliente. Las descripciones son frases y se leen mejor con su punto; los títulos de cada servicio y de cada grupo siguen sin punto, como títulos.

## 2026-10-28 — Publicar en GitHub Pages
**Elegí:** GitHub Pages, con una GitHub Action que compila y publica la página en cada push a `main`. Dirección: https://droa0602.github.io/Jaime-paginaweb/
**En vez de:** Netlify, Vercel o Cloudflare Pages.
**Por qué:** el código ya está en GitHub y no hace falta crear otra cuenta. Como la página vive en una subcarpeta (`/Jaime-paginaweb/`), `astro.config.mjs` tiene `base`, y los enlaces a archivos de `public/` usan ese prefijo. Si después se compra un dominio propio, se puede apuntar a GitHub Pages y quitar el `base`.
