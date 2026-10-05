# Instrucción para la herramienta de IA · Guía práctica 2 (Reto IA)

> Instrucción única que cubre las tres páginas. Se adjuntan a la conversación el `index.html` y el `STIAL.css` del sitio de la Guía práctica 1.

## 1. Contexto y objetivo

Tengo un sitio web del Centro Comercial La Joya (El Salvador), hecho en la Guía práctica 1 con HTML y CSS. Adjunto el `index.html` y el `STIAL.css` actuales.

**Quiero que conserves el sitio y solo lo mejores.** Mantén el mismo contenido, la misma estructura de secciones (hero con video, beneficios, locales, restaurantes, promociones, cómo llegar, pie de página) y los mismos datos (dirección, teléfono, horario, nombres de locales, precios y niveles). No inventes datos nuevos. Cambia la identidad visual para que siga estrictamente el sistema de diseño `design.md` que aparece más abajo.

Construye **tres páginas HTML con navegación funcional entre sí** y una sola hoja de estilos compartida (`STIAL.css`):

1. `index.html`: la página de inicio, retrabajada con el nuevo estilo.
2. `contacto.html`: página de contacto con formulario (con validación), datos de ubicación y preguntas frecuentes.
3. `nosotros.html`: página institucional del centro comercial.

## 2. Requisitos de las páginas

**Comunes a las tres:** idioma español; barra de utilidad con el horario; menú fijo con Inicio, Locales, Restaurantes, Promociones, Nosotros y Contacto, marcando la página actual; pie de página con enlaces a las tres páginas y formulario de suscripción; enlace "Saltar al contenido"; diseño responsive; foco visible con teclado.

**index.html:** hero alineado a la izquierda, con la palabra "conviene" teñida de verde; el video de fondo original ahora dentro de una tarjeta de 28px de radio, con botón para pausarlo; botón principal azul "Ver locales" y botón neutro "Cómo llegar"; bandas alternadas #ffffff y #f5f5f7; las etiquetas de nivel (Planta baja, Segundo nivel) como píldoras con borde de acento; sin emojis, con íconos lineales pequeños solo donde aporten.

**contacto.html:** formulario con nombre, correo, teléfono (opcional), motivo y mensaje; validación en el cliente con mensajes claros y confirmación de envío; tarjeta con dirección, teléfono, horario y botón a Google Maps; preguntas frecuentes con el componente "Pill Disclosure Item" del design.md, usando solo información que ya está en el sitio.

**nosotros.html:** propuesta de valor basada en los textos del sitio original; cifras derivadas del contenido existente (7 días, 12 horas de atención, 6 restaurantes y cafés, 3 farmacias, 3 bancos); directorio de locales por nivel; cierre con botones de acción.

## 3. Animaciones y transiciones (obligatorio)

Al menos una página debe incluirlas; aquí las tres las llevan, con moderación:

- **index.html:** secuencia de carga del hero (aparición escalonada del texto y de la tarjeta de video, y la palabra teñida pasa de negro a verde); aparición escalonada de las tarjetas al cargar cada sección; zoom suave de la foto al pasar el cursor.
- **contacto.html:** preguntas frecuentes en `<details>` que se despliegan con un ícono "+" que rota y la respuesta aparece con una animación de entrada; los campos cambian de color de borde según sean válidos o no.
- **nosotros.html:** aparición escalonada de las tarjetas de cifras y del directorio al cargar la página.
- Respeta `prefers-reduced-motion`.

## 4. Restricciones técnicas

**Sin JavaScript.** Solo HTML5 semántico y CSS (sin frameworks). Todo lo interactivo debe lograrse con elementos y pseudo-clases nativas:
- Preguntas frecuentes: `<details>/<summary>`, con el ícono "+" girando mediante el selector `[open]`.
- Validación del formulario: atributos nativos (`required`, `type="email"`, `minlength`, `pattern`) y color de borde con `:invalid` / `:valid`.
- Envío del formulario: `action="mailto:..."` (abre el programa de correo del visitante; no hay backend).
- Video: atributo `controls` del propio navegador, sin botón personalizado.
- Animaciones: `@keyframes` y `transition` puros, disparadas al cargar la página o con `:hover`/`:focus`/`[open]` — nunca por scroll, ya que eso exige JavaScript.

Sin sombras ni degradados (lo prohíbe el design.md). Usa Inter como sustituto de SF Pro, con pesos 400 y 600 únicamente.

## 5. Sistema de diseño (contenido del design.md)

Aplica este `design.md` de forma consistente en las tres páginas:

---

# Apple (España) — Style Reference
> white museum gallery at noon

**Fuente:** https://styles.refero.design/style/569ba4c0-0431-44fb-92df-0dbea7f3e63d
**Theme:** light

Apple's product page language is a luminous white gallery: every pixel of chrome is stripped away so the photographed product and one bold typographic statement own the screen. Headlines in SF Pro Display at 64–96px do nearly all of the work, set in near-black (#1d1d1f) with selectively tinted words — a green verb for one emotion, a blue verb for another — that turn the headline itself into a micro-product story. Surfaces are paper-flat: no shadows, no gradients, no decorative borders, only hairline rules and generous whitespace. Interaction is reduced to two button archetypes — a blue pill (#0071e3) for the purchase moment and a subtle neutral pill (#e2e2e5) for everything else — surrounded by a sea of 28px-rounded cards that float on a #f5f5f7 canvas. The whole system is engineered to feel weightless, confident, and barely-designed: the brand is the product, and the design system is the silence around it.

## Tokens — Colors

| Name | Value | Token | Role |
|------|-------|-------|------|
| Pure Canvas | `#f5f5f7` | `--color-pure-canvas` | Page background, section bands, card surfaces — a near-white that separates structural surfaces from pure white product highlights without introducing tint |
| Paper White | `#ffffff` | `--color-paper-white` | Elevated card surfaces, icon fills, and inverted text on dark/colored backgrounds |
| Obsidian | `#1d1d1f` | `--color-obsidian` | Primary text, headlines, card borders, nav rules — the singular dark anchor; not pure black |
| Iron Gray | `#707070` | `--color-iron-gray` | Secondary nav borders, list dividers, subdued UI metadata |
| Slate | `#474747` | `--color-slate` | Nav borders, link underlines, secondary text in dense lists |
| Charcoal | `#333336` | `--color-charcoal` | Nav text, button labels on neutral surfaces |
| Mist | `#e2e2e5` | `--color-mist` | Neutral pill button fill, secondary surface tier for compact controls and list rows |
| Fog | `#d6d6d6` | `--color-fog` | List row backgrounds, hairline separators in data-dense sections |
| Void | `#000000` | `--color-void` | Icon fills on light surfaces, nav logo — reserved for the most absolute contrast moments |
| Signal Blue | `#0071e3` | `--color-signal-blue` | Blue action color for filled buttons, selected navigation states, and focused conversion moments |
| Deep Link Blue | `#0066cc` | `--color-deep-link-blue` | Inline link text and link underlines throughout body copy — the only chromatic text color permitted in paragraph flow |
| Pulse Green | `#03aa49` | `--color-pulse-green` | Accent word within hero headlines — used to color-code an emotional concept inside otherwise monochrome type |
| Deep Green | `#03873a` | `--color-deep-green` | Darker green variant for text-level green accents and underlined links |
| Ultraviolet | `#8668ff` | `--color-ultraviolet` | Violet outline accent for tags, dividers, and focused UI edges |
| Ember Orange | `#ed6300` | `--color-ember-orange` | Orange outline accent for tags, dividers, and focused UI edges |
| Lagoon Teal | `#00a1b3` | `--color-lagoon-teal` | Teal outline accent for tags, dividers, and focused UI edges |

## Tokens — Typography

### SF Pro Display — Hero headlines, section headings, and the page-level brand statement
- **Substitute:** Inter, Helvetica Neue, system-ui
- **Weights:** 600 (the heaviest weight on the entire site — never go heavier)
- **Sizes:** 21px, 24px, 28px, 39px, 64px, 76px, 80px, 96px
- **Line height:** 1.04–1.17 for display sizes; 1.33 for sub-heading sizes
- **Letter spacing:** -0.0190em at 96px, -0.0150em at 64px, -0.0090em at 39px, 0.0110em at 21px
- **Role:** Set in semibold at very large sizes (64–96px) with aggressive negative tracking that tightens the headline into a single confident block. Smaller sizes (21–28px) carry section headings and card titles.

### SF Pro Text — Body copy, nav labels, button text, spec text, and large display numerals (44px)
- **Substitute:** Inter, Helvetica Neue, system-ui
- **Weights:** 400, 600
- **Sizes:** 12px, 14px, 17px, 20px, 44px
- **Line height:** 1.18–1.47 for body
- **Letter spacing:** -0.0220em at 44px, -0.0190em at 20px, -0.0160em at 17px, -0.0100em at 14px, -0.0030em at 12px
- **Role:** Weight 400 is the paragraph default; weight 600 marks links, button labels, and emphasis within body text.

### Type Scale

| Role | Size | Line Height | Letter Spacing | Token |
|------|------|-------------|----------------|-------|
| caption | 12px | 1.33 | -0.036px | `--text-caption` |
| body-sm | 14px | 1.43 | -0.14px | `--text-body-sm` |
| body | 17px | 1.47 | -0.272px | `--text-body` |
| subheading | 21px | 1.33 | 0.231px | `--text-subheading` |
| heading-sm | 28px | 1.14 | -0.252px | `--text-heading-sm` |
| heading | 39px | 1.07 | -0.351px | `--text-heading` |
| heading-lg | 64px | 1.06 | -0.96px | `--text-heading-lg` |
| display | 96px | 1.04 | -1.824px | `--text-display` |

## Tokens — Spacing & Shapes

**Density:** comfortable

Spacing scale (px): 4, 8, 9, 10, 13, 14, 15, 18, 20, 24, 28, 32, 40, 80, 89, 160

### Border Radius

| Element | Value |
|---------|-------|
| nav | 980px |
| cards | 28px |
| links | 10px |
| buttons | 980px |
| buttons-large | 36px |

### Layout

- **Page max-width:** 1440px
- **Section gap:** 80-120px
- **Card padding:** 28px
- **Element gap:** 8-12px

## Components

### Primary Action Button
The purchase or key conversion moment — the only filled chromatic button. Pill shape at 980px radius, filled with #0071e3, white text in SF Pro Text 17px / weight 600. Padding 11px vertical, 20px horizontal. Letter-spacing -0.022em. No border, no shadow. This is the only button on the page permitted to be blue.

### Neutral Pill Button
Secondary action — 'Learn more', 'See all', disclosure expanders. Pill shape at 980px radius, filled with #e2e2e5, text in #333336 SF Pro Text 17px / weight 600. Same 11px/20px padding as the primary.

### Pill Disclosure Item
Expandable detail rows. Pill shape at 980px radius, transparent fill with 1px border in #d6d6d6. Left side holds a small '+' icon, right side holds the label in SF Pro Text 14px / weight 400 / #1d1d1f. No background fill until expanded.

### Product Hero Block
Full-bleed showcase above the fold on white canvas (#ffffff). Brand kicker (SF Pro Text 12px / weight 600 / uppercase / letter-spacing tight), then the display headline (SF Pro Display 64-96px / weight 600) where one or two words are tinted in #03aa49, #0066cc, or #8668ff. Headlines are set left-aligned, not centered.

### Headline with Tinted Accent Words
Signature typographic pattern. SF Pro Display 64px / weight 600 / #1d1d1f, with a single verb or noun in #03aa49 (green for energy), #0066cc (blue for intelligence), #8668ff (violet for software), #ed6300 (orange for fitness), or #00a1b3 (teal for health). The tint lives on the word, not a highlight, and the rest of the line stays Obsidian.

### Feature Card
Large rectangular card for photography with caption. Border-radius 28px. Background #ffffff. 1px hairline border in #1d1d1f (very subtle, often absent — the card sits on #f5f5f7 canvas with no border). The image occupies the full card width; caption text in SF Pro Text 17px / weight 400 / #1d1d1f.

### Sticky Top Navigation
White fill, 1px bottom border in #d6d6d6. Nav labels in SF Pro Text 12px / weight 400 / #1d1d1f. Logo at left. Right-side utility items at 980px pill radius with #f5f5f7 background.

### Utility Bar
Full-width band in #f5f5f7 above the main nav. Single line of SF Pro Text 12px / weight 400 / #1d1d1f text, centered. Inline link in #0066cc followed by ">".

### Band Section
Alternating full-width content bands — the page's primary structural unit. Each band is a full-bleed horizontal block, either #ffffff or #f5f5f7. Section heading sits top-left in SF Pro Display 39-64px / weight 600 / #1d1d1f. Content uses the standard max-width container with ~80px top/bottom padding.

### Price + Action Stack
Two elements on one row: price in SF Pro Text 14px / weight 400 / #1d1d1f, followed by the Primary Action Button. The price label has no border, no background.

### Link Inline (Body Flow)
Color #0066cc, 1px underline in #0066cc. SF Pro Text 17px / weight 400.

## Do's and Don'ts

### Do
- Use SF Pro Display weight 600 for any display-size headline; never go heavier than 600
- Tint single words in headlines using #03aa49, #0066cc, #8668ff, #ed6300, or #00a1b3; keep the rest of the line #1d1d1f
- Use #0071e3 fill on a 980px pill as the sole primary action — never apply this blue to text, borders, or non-button surfaces
- Set headlines left-aligned within a left-aligned content column; do not center display type
- Use 28px border-radius for cards and 980px (full pill) for buttons
- Pair every chromatic button with a #1d1d1f text label nearby (price, kicker) so the blue pill remains the singular attention point
- Let photography fill the card; place caption text at the card's edge rather than overlaying the image

### Don't
- Do not introduce box-shadows, glows, or drop-shadows — elevation comes from surface contrast and 1px hairlines only
- Do not use the chromatic accent colors (green, violet, orange, teal) for backgrounds, buttons, or large fills — they are word-tints only
- Do not use #0000ee or any unstyled browser-default link color — always #0066cc with a 1px underline
- Do not set body copy above 20px or below 14px; 17px is the singular paragraph size
- Do not use a border-radius value other than 10px, 28px, 32px, 36px, or 980px
- Do not center the hero headline or the price+CTA cluster — left-alignment is structural, not stylistic
- Do not apply gradients to text, buttons, or cards

## Surfaces

| Level | Name | Value | Purpose |
|-------|------|-------|---------|
| 0 | Canvas | `#f5f5f7` | Page-level background |
| 1 | Card | `#ffffff` | Cards, feature callout blocks, any container that needs to lift off the canvas |
| 2 | Control | `#e2e2e5` | Neutral pill buttons, secondary list rows, compact UI surfaces |
| 3 | Divider | `#d6d6d6` | Hairline separators and subtle row backgrounds |

## Elevation

No box-shadow. Elevation is achieved entirely through surface contrast — #ffffff cards on a #f5f5f7 canvas, with 1px hairlines in #d6d6d6 or #1d1d1f providing the only structural division. Everything sits on the same optical plane.

## Imagery

Photography dominates: large, high-resolution, one or two per band, surrounded by vast white margins. Zero illustration, zero iconographic decoration; the only non-photographic visuals are the logo and occasional small SF Symbol-style icons. Visual hierarchy: photograph > headline > body > UI chrome.

## Layout

Full-bleed bands stacked vertically, each a slice of #ffffff or #f5f5f7. Page max-width is 1440px but content containers sit narrower (~980px) and are left-aligned, never centered. Subsequent bands alternate between image-left/text-right and text-left/image-right compositions at roughly 50/50 width splits. Section gaps are generous (80-120px). The overall rhythm is slow, photographic, and editorial — bands breathe.

## Quick Color Reference
- text (primary): #1d1d1f
- background: #ffffff (cards) / #f5f5f7 (canvas)
- border / hairline: #1d1d1f or #d6d6d6
- link inline: #0066cc with 1px underline
- accent word in headline: #03aa49 (green), #0066cc (blue), #8668ff (violet), #ed6300 (orange), #00a1b3 (teal)
- primary action: #0071e3 (filled action)
- neutral action: #e2e2e5 fill, #333336 text

## CSS Custom Properties

```css
:root {
  --color-pure-canvas: #f5f5f7;
  --color-paper-white: #ffffff;
  --color-obsidian: #1d1d1f;
  --color-iron-gray: #707070;
  --color-slate: #474747;
  --color-charcoal: #333336;
  --color-mist: #e2e2e5;
  --color-fog: #d6d6d6;
  --color-void: #000000;
  --color-signal-blue: #0071e3;
  --color-deep-link-blue: #0066cc;
  --color-pulse-green: #03aa49;
  --color-deep-green: #03873a;
  --color-ultraviolet: #8668ff;
  --color-ember-orange: #ed6300;
  --color-lagoon-teal: #00a1b3;

  --font-sf-pro-display: 'SF Pro Display', ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  --font-sf-pro-text: 'SF Pro Text', ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;

  --radius-lg: 10px;
  --radius-3xl: 28px;
  --radius-3xl-2: 32px;
  --radius-3xl-3: 36px;
  --radius-full: 980px;
}
```

---

## 6. Entrega

Entrega el código completo de `index.html`, `contacto.html`, `nosotros.html` y `STIAL.css` (sin ningún archivo `.js`), listos para abrirse en el navegador desde la misma carpeta.
