# Summit Discourse theme plan

## Reference URLs

- https://www.wealthsimple.com/fr-ca/invest/summit-portfolios
- https://www.wealthsimple.com/en-ca/chequing

Browser access was blocked by Wealthsimple's security page, so extraction used the server-rendered HTML/CSS fetched with a normal browser user agent. No Wealthsimple assets, logos, or exact brand marks will be copied.

## Visual extraction

- Core tone: warm editorial fintech, off-white paper backgrounds, very dark charcoal text, soft sage/olive accent, muted clay/orange action color, and occasional lavender/summit purple panels.
- Observed colors in HTML/CSS:
  - Charcoal: `#32302f`, `#1c1b1b`
  - Warm surfaces: `#faf8f5`, `#eeece7`, `#f1f0f0`, `#fcfcfc`
  - Sage/olive: `#486635`, `#99b56e`, `#9faa75`, `#e4e9d3`
  - Clay/orange: `#a43d12`, `#ff8a71`, `#f9f2ef`
  - Summit/lavender: `#313B58`, `#B4ACBB`, `#D3C7D8`, `#F6E7F8`
- Typography: Wealthsimple uses `the-future` for UI and `tiempos` for editorial text. The theme will approximate this with system sans for UI and Georgia/Iowan-style serif headings; no remote font imports.
- Shape/density: rounded cards/buttons, generous whitespace, soft panels, minimal borders, gentle focus states.
- Shadows: very subtle only; rely on warm surfaces and borders.

## Discourse mapping

- Theme name: `Summit`
- Repo: `/Users/pmusaraj/Projects/discourse-summit`
- Color scheme:
  - `primary`: `32302F`
  - `secondary`: `FAF8F5`
  - `tertiary`: `486635`
  - `quaternary`: `A43D12`
  - `header_background`: `FAF8F5`
  - `header_primary`: `32302F`
  - `highlight`: `E4E9D3`
  - `selected`: `EEECE7`
  - `hover`: `F1F0F0`
- CSS approach: use Discourse variables first; direct selectors only for header/sidebar/topic list/cards/buttons/forms/composer.
- Guardrails: no `position`/`z-index` changes on main layout, no forced `.sidebar-wrapper` sizing/padding/margin, no `.sidebar-container` surface styling, no JS.

## Scaffold

- `about.json` with `color_schemes.Summit`
- `common/common.scss`
- No custom icon component.
- Screenshot metadata deferred until browser verification produces a preview image.

## Testing plan

1. Import on `https://disco2021.musaraj.com` as default/selectable theme.
2. Verify DB theme state, generated `common_theme` stylesheet, and rendered browser stylesheet.
3. Check `/latest`, `/categories`, a topic page, and console errors.
4. Verify button icon/text hover parity and no forbidden sidebar/main layout selectors.
