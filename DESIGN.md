---
name: Crónica Serrana Artesanal
description: Arquetipo editorial (pliego de imprenta y monografía botánica) para La Picosita de la Sierra, Motozintla, Chiapas.
colors:
  parchment: "#FAF7F0"
  linen: "#F6F3EC"
  linen-deep: "#F0EEE7"
  rule: "#E2DCCE"
  hairline: "rgba(30, 58, 47, 0.15)"
  laurel: "#1E3A2F"
  laurel-deep: "#07241A"
  ink: "#1C1C18"
  ink-soft: "#3F443F"
  morita: "#9E2A2B"
  morita-deep: "#7E2021"
  morita-light: "#AB3333"
  panela: "#C88242"
  panela-ink: "#7A4A17"
  panela-light: "#E3B685"
typography:
  display:
    fontFamily: "Playfair Display, Georgia, serif"
    fontSize: "clamp(2.5rem, 6.2vw, 5.25rem)"
    fontWeight: 700
    lineHeight: 1.02
    letterSpacing: "-0.02em"
  headline:
    fontFamily: "Playfair Display, Georgia, serif"
    fontSize: "clamp(2rem, 4.2vw, 3.5rem)"
    fontWeight: 600
    lineHeight: 1.1
  title:
    fontFamily: "Playfair Display, Georgia, serif"
    fontSize: "1.3125rem"
    fontWeight: 600
    lineHeight: 1.15
  body:
    fontFamily: "Manrope, system-ui, sans-serif"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.65
  label:
    fontFamily: "Space Grotesk, ui-monospace, monospace"
    fontSize: "0.6875rem"
    fontWeight: 600
    lineHeight: 1.4
    letterSpacing: "0.1em"
  price:
    fontFamily: "Space Grotesk, ui-monospace, monospace"
    fontSize: "1.5rem"
    fontWeight: 700
    lineHeight: 1
rounded:
  none: "0px"
  max: "2px"
spacing:
  margin: "clamp(1.25rem, 5vw, 5rem)"
  gutter: "clamp(1rem, 2.5vw, 2.5rem)"
  card-pad: "1rem"
components:
  button-primary:
    backgroundColor: "{colors.morita}"
    textColor: "{colors.parchment}"
    typography: "{typography.label}"
    rounded: "{rounded.none}"
    padding: "15px 24px"
  button-primary-hover:
    backgroundColor: "{colors.morita-deep}"
  button-on-dark:
    backgroundColor: "{colors.panela-light}"
    textColor: "{colors.laurel-deep}"
    rounded: "{rounded.none}"
    padding: "15px 24px"
  card-label:
    backgroundColor: "{colors.parchment}"
    textColor: "{colors.ink}"
    rounded: "{rounded.none}"
    padding: "1rem"
  size-stamp-selected:
    backgroundColor: "{colors.laurel}"
    textColor: "{colors.parchment}"
    rounded: "{rounded.none}"
---

# Design System: Crónica Serrana Artesanal

## Overview

La Picosita de la Sierra se comporta como un cuaderno de campo agroindustrial y un pliego de imprenta, no como una plantilla de app. La composición es asimétrica y disciplinada: márgenes amplios, columnas de lectura de 55 a 75 caracteres, folios y metadatos de imprenta (REG. MOTOZINTLA-CHIS., FOLIO DE COSECHA: LOTE-2026, coordenadas 15°22′ N · 92°15′ O). La jerarquía se resuelve con filetes, plecas dobles y capitulares, nunca con tarjetas flotantes.

## Colors

Regla 60-30-10, aplicada así en el código:

- **60 · Lienzo:** Pergamino fino `#FAF7F0` (base), Lino `#F6F3EC` (catálogo), Lino hondo `#F0EEE7` (hover y campos inertes).
- **30 · Estructura:** Laurel de la Sierra `#1E3A2F` (titulares, filetes, cabeceras, secciones de proceso y pie), Laurel hondo `#07241A` (folio superior y módulo B2B), Carbón `#1C1C18` y `#3F443F` para texto.
- **10 · Foco y conversión:** Morita Tostado `#9E2A2B` (botón de compra, badges, chilómetro; hover `#7E2021`; `#AB3333` reservado para superficies grandes) y Terracota/Panela `#C88242` (sellos de origen, filetes interiores y líneas de corte).

Reglas de uso: no existe blanco puro ni negro digital. Panela `#C88242` solo como filete o adorno sobre claro (contraste 2.7:1); para texto sobre claro se usa `panela-ink #7A4A17` (6.96:1) y sobre laurel `panela-light #E3B685` (6.64:1 sobre laurel, 8.85:1 sobre laurel hondo). Contrastes verificados: carbón sobre pergamino 15.97, laurel 11.54, morita 6.96, parchment sobre morita 6.96. Todos AA o mejor.

## Typography

Tríada tipográfica:

- **Playfair Display:** titulares de pliego, manifiesto y nombres de producto. Cifras elzevirianas (`oldstyle-nums`) en fechas y folio del recibo.
- **Manrope:** lectura continua, crónica y descripciones de cata. Medida máxima 54 a 64ch.
- **Space Grotesk:** precios en MXN, SKU, gramajes, coordenadas y sellos de lote, con numerales tabulares. Piso de 11px.

Capitular en el primer párrafo de portada. Tracking nunca menor a −0.02em; display máximo 5.25rem.

## Layout

Cuadrícula de 12 columnas con margen y gutter fluidos. La cabecera de cada sección usa una pleca doble de 3px y una nota marginal (columna 1 a 2) que lleva el capítulo. Catálogo en 4 columnas (escritorio), 2 (tablet), 1 (móvil). El manifiesto B2B se convierte en fichas apiladas bajo 760px.

## Elevation & Depth

No hay sombras. La profundidad es capa de papel: tono sobre tono (pergamino, lino, laurel) y filetes hairline de 1px (`#E2DCCE` o laurel al 15%). El recibo y las tarjetas se separan con filete doble (laurel exterior, panela interior). El velo del drawer es un color plano al 55%, sin desenfoque.

## Shapes

Corte guillotina: radio 0 en todo el sistema, 2px como techo absoluto. Sin píldoras, sin círculos. Los selectores de gramaje, pestañas, badges y casillas son rectángulos con filete de 1px.

## Components

- **Tarjeta de etiqueta de botica:** doble filete, registro `N.º 01` arriba, foto 4:5 con filete, nombre en serif, chilómetro (5 glifos de chile, rellenos en morita hasta la intensidad), selector segmentado de gramaje con precio, botón Añadir y sello "Obrador Motozintla — Sierra Madre de Chiapas".
- **Selector de gramaje:** tres sellos tipográficos con radio; el elegido se invierte a laurel. El precio cambia al instante.
- **Manifiesto de carga (B2B):** tabla compacta con SKU, presentación, cajas máster (24 o 48) y piezas; totales de cajas, piezas, peso neto y referencia a precio de menudeo. Descuento por volumen, cubicaje y arancel se cotizan, no se calculan en pantalla.
- **Recibo de pedido (drawer):** folio provisional, fecha en cifras elzevirianas, renglones con puntos guía y filete discontinuo, total con pleca doble. Envío por CP se confirma por WhatsApp.
- **Botones:** primario morita; sobre laurel, panela claro. Transición de 120–140ms, presión de 1px, foco con filete de 1px y desfase de 3px.

## Do's and Don'ts

- Sí: filetes, plecas dobles, capitulares, folios y cifras elzevirianas.
- Sí: precios, SKU y gramajes siempre en Space Grotesk.
- No: `box-shadow` distinto de `none`, radios mayores a 2px, gradientes, glassmorphism, `#FFFFFF`, `#000000`.
- No: reseñas, calificaciones o sellos comerciales inventados. Solo hechos confirmados en PRODUCT.md.
- Excepción documentada: el detector marca la pleca doble de 3px como borde grueso; es la pleca de imprenta del arquetipo y se conserva.
