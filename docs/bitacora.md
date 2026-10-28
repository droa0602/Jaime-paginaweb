# Bitácora

Una nota corta al cerrar cada sesión.

<!-- Formato sugerido:
## AAAA-MM-DD
- Qué hice:
- Qué quedó pendiente:
-->

## 2026-10-25
- Qué hice: estructura de `docs/`; pasé el diseño de `Jaime Bohorquez.html` a Astro (una página para celular: portada, foto, quién soy, servicios, contacto, botón fijo de WhatsApp).
- Qué quedó pendiente: foto real de Jaime (hoy hay un recuadro de marcador); pegar el brief en `docs/brief.md`.
- Corrección: el apellido es "Bohórquez" (el diseño original decía "Bohorquéz"). Corregido en la página y en CLAUDE.md.
- Versión para computador (ver `decisiones.md`).
- Título grande de la portada cambiado de "Jaime Bohórquez" a "Electricista Villanueva"; el nombre pasó al texto de "Quién soy" ("Soy Jaime Bohórquez, ...").
- Servicios movidos arriba, al lado de la portada; la foto pasó junto a "Quién soy". En celular el orden queda: portada, servicios, foto, quién soy, contacto.

## 2026-10-28
- Qué hice: llené `docs/brief.md` (estaba vacío) con lo que ya se sabía y una lista de cosas por confirmar. Rehíce toda la interfaz con la skill design-taste-frontend (ver `decisiones.md`): amarillo y negro, Zilla Slab, fotos de Wikimedia Commons, cupón que arma el mensaje de WhatsApp. El inspector de la skill queda en 0 fallos en 1440, 768 y 390 px.
- Qué quedó pendiente: foto real de Jaime (hoy la sección "Quién soy" muestra breakers nuevos) y fotos de sus trabajos; confirmar con Jaime los textos de ejemplo (detalles de cada servicio y la carta de "Quién soy"), las veredas que cubre, el horario y qué cubre la garantía.
- Después, a pedido del cliente: quité "Quién soy", el cupón "Cuénteme qué pasó", la foto de los cultivos y el pie "Voy hasta su puerta"; la caja de 30 años / 24 h / garantía pasó a la sección de servicios. Borré las fotos que ya no se usan. El inspector de la skill marca ahora "pocas fotos" (queda una sola), lo que es esperado con este cambio.
- Los recuadros amarillos (hoja de servicios y caja de datos) ahora tienen bordes rectos, como la portada.
- La tarjeta de la portada quedó derecha. Texto sobre fondo oscuro en #e5ded2 y texto sobre amarillo en #132841.
- Los recuadros y botones amarillos pasaron a azul #132841 y todo el texto a #e5ded2. La hoja de servicios quedó alineada a la izquierda, en una columna centrada en el recuadro.
- Recuadro de experiencia rediseñado: 30 años de oficio en grande, y "De lunes a domingo" y "Trabajo con garantía" debajo.
- Botón flotante de WhatsApp en #798da6 con letra azul oscuro; su borde y la franja de la barra del celular en #132841.
- La frase bajo el recuadro de experiencia quedó alineada con su texto. Descripciones de servicios con punto final.
- Configuré la publicación en GitHub Pages (workflow en .github/workflows/deploy.yml, base /Jaime-paginaweb). Pendiente: activar Pages en Settings > Pages > Source: GitHub Actions.
