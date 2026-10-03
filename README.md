# La Picosita de la Sierra

Obrador de salsas y curtidos en Motozintla, Chiapas. Sitio de un solo archivo (`index.html`): catálogo, pedido por WhatsApp y manifiesto de mayoreo.

## Publicar en Cloudflare

Se publica como Worker de assets estáticos (`wrangler.jsonc`); no necesita compilación. Dos formas:

- **Desde GitHub** (cada push a `main` publica): Workers & Pages → Create → **Import a repository** → este repositorio. Build command: *(vacío)*; Deploy command: `npx wrangler deploy`.
- **Desde la terminal**: `npx wrangler login` (una vez) y `npx wrangler deploy`.

Queda en `https://la-picosita-de-la-sierra.<tu-cuenta>.workers.dev`. Usa Workers y no Pages: en la misma cuenta que Scan-bar, la página lo encuentra sola y Scan-bar sabe a qué URL mandar sus códigos. Pasos de todo el sistema: `docs/DESPLIEGUE.md` en el repositorio Scan-bar.

## Scan-bar (catálogo y códigos)

Scan-bar es la base de datos de productos y códigos de barras de los negocios. Los frascos del arreglo `P` se registran solos en Scan-bar (Scan-bar revisa este repositorio cada 10 minutos; `npm run sync:repos` allá lo fuerza): **cada presentación (gramaje) es un producto con su propio código** (`CUR-01-250G`), lista para su etiqueta. Lo que se agrega desde Scan-bar (*Administración → Productos y etiquetas*) aparece en el catálogo sin tocar este archivo.

- Conexión: junto a `index.html` va `scanbar.js`. Automática si la página vive en `la-picosita-de-la-sierra.<tu-cuenta>.workers.dev` (usa `scan-bar.<tu-cuenta>.workers.dev`). En otro dominio: `data-url="https://URL-DE-SCAN-BAR"` en su etiqueta `<script>`; `data-url="off"` la apaga.
- Probar en local: `python -m http.server` y abrir `http://localhost:8000/?scanbar=http://localhost:3000`.
- En Scan-bar: categoría `curtido` o `salsa`; variantes en gramos (`270 g, 350 g, 450 g`) con su precio; atributo opcional `picor` (1 a 5).
- Contrato y diseño completo: `docs/INTEGRACION-WEBS.md` en el repositorio Scan-bar.
