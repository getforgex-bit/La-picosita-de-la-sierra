# La Picosita de la Sierra

Obrador de salsas y curtidos en Motozintla, Chiapas. Sitio de un solo archivo (`code.html`): catálogo, pedido por WhatsApp y manifiesto de mayoreo.

## Scan-bar (catálogo y códigos)

Scan-bar es la base de datos de productos y códigos de barras de los negocios. Los frascos del arreglo `P` se registran solos en Scan-bar (`npm run sync:repos` allá): **cada presentación (gramaje) es un producto con su propio código** (`CUR-01-250G`), lista para su etiqueta. Lo que se agrega desde Scan-bar (*Administración → Productos y etiquetas*) aparece en el catálogo sin tocar este archivo.

- Activar: junto a `code.html` va `scanbar.js`; en su etiqueta `<script src="scanbar.js" data-url="https://URL-DE-SCAN-BAR" data-tienda="la-picosita-de-la-sierra">`. Vacío = solo el catálogo del archivo.
- Probar en local: `python -m http.server` y abrir `http://localhost:8000/code.html?scanbar=http://localhost:3000`.
- En Scan-bar: categoría `curtido` o `salsa`; variantes en gramos (`270 g, 350 g, 450 g`) con su precio; atributo opcional `picor` (1 a 5).
- Contrato y diseño completo: `docs/INTEGRACION-WEBS.md` en el repositorio Scan-bar.
