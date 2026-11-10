# CreaCo Design System

**Crealisatie Coöperatie (CreaCo)** — *een organisatie in beweging.* A cooperative that develops places for makers (werkplaatsen, ateliers, maakgemeenschappen) and finances them step by step: for-profit start, rental income growth, non-profit refinancing. Related projects/partners: Urban Scouts, Maakgemeenschap De Hoop, Sluiskwartier.

Brand brief from the client: *"Onze stijl is die van typische makers, onze kleur is machine-groen, en voelt aan als de jaren '20."*

## Sources
- `uploads/Asset 2–7.png` — logo lockups (copied to `assets/`).
- `uploads/Dekking projecten infographic.jpg` — the client's own "good example of our style" (copied to `assets/examples/`).
- House-style notes for CreaCo slides, based on the Google Slides deck "CreaCo - VisieDocument Sluiskwartier" (https://docs.google.com/presentation/d/1H_Xq5ntv3aiu0jYQoyFCrS3pRIXYOqksskUS2G1V4Cw/edit — not accessed directly).
- No codebase, Figma or product UI was provided. **There is no UI kit** for that reason; the main surfaces are documents, infographics and slides.

## Content fundamentals
- **Language:** Dutch. Direct, plain, businesslike but warm.
- **Voice:** *we* (the cooperative) — "We financieren for profit…", "We herfinancieren voor non profit." Address the reader as *je* when inviting ("Doe je mee?").
- **Headlines:** short, often a question or 1–3 words. Sentence case in display type ("Hoe dekken we onze projecten?", "Ambitie", "Uitgangspunten"). All-caps only on CTA slides (white on pink) ("BOUW MEE AAN DE WERKPLAATS").
- **Body:** short sentences and bullet fragments. **Bold the one or two key phrases per line** — e.g. "van **fee** naar **verhuur**, tot we kunnen **herfinancieren voor non profit**."
- **Labels:** uppercase, bold, tracked: FOR PROFIT · NON PROFIT · DEKKING VAN DE KOSTEN · TIJD →.
- **Breadcrumb:** `Organisatie – Sectie` with an en dash: "Crealisatie Coöperatie – Financiering".
- CTAs are imperative and exclamatory: "Maak het mee!"
- **No emoji.** Unicode arrows (→) are fine in labels.

## Visual foundations
- **Colour:** machine green `#67AF71` carries everything — headlines, full-bleed covers, buttons, table headers. Light green `#D6E8D8` and deep green `#3F804A` make three-step phase fields (light → mid → deep). Pink `#D9729A` is the single loud accent: one milestone, one CTA, the culminating step. Ink `#18171C` (from the wordmark) for body; white paper. Warm paper `#F4F1EA` is available for a 1920s-print feel on alternate sections — use sparingly.
- **Type:** *Impact* (`--font-display`) for big headlines only — the heavy 1920s-poster voice, tight leading ~0.88–0.92. *Special Gothic Condensed One* (`--font-subhead`) for subheads inside charts/cards and tabs. Step numerals (1, 2, 3) use Impact. *Impacted* (`--font-display-alt`) is a decorative variant for one-word poster moments. *Arial* for body (Arimo shipped as metric-compatible webfont fallback). Labels are bold Arial caps with 0.08em tracking. Big display numerals (1, 2, 3) mark steps.
- **Layout:** generous white margins; breadcrumb top-left; huge headline top-left with intro paragraph pushed right; content in 2–3 column grids. Charts and color fields are flat and square, drawn with a 2px ink axis.
- **Backgrounds:** flat fills only — white, full-bleed green (cover/section/divider), full-bleed pink (CTA). No gradients, no textures, no patterns. Imagery (when used) should be workshop/maker photography; none provided yet.
- **Lines:** dashed ink-200 2px for soft phase dividers; solid pink 3px for the milestone; 2px ink for axes and outline buttons/inputs; 1px green for table cells; white dashed line inside green fields.
- **Corner radii:** square (0) for cards, fields, charts, tables. Fully round **pills** for labels and buttons. Circle only for the logo mark / breadcrumb dot.
- **Cards:** flat colour field or 2px ink outline, no radius, no shadow.
- **Shadows:** none in the print style. `--shadow-overlay` only for floating UI (dialogs, toasts).
- **Transparency/blur:** none, except a 55% ink scrim behind dialogs.
- **Motion:** minimal, mechanical: 120–200ms, `cubic-bezier(.2,.8,.2,1)`. No bounces.
- **Hover:** darken one step (green-500 → green-700, pink → pink-700, ink → ink-700); outline/ghost get a light fill. **Press:** 1px downward nudge.
- **Focus:** 3px green-300 ring.

## Iconography
CreaCo has no own icon set. The brand barely uses icons — typography, numerals, pills and arrows (→) do the work. When UI needs icons, use **Lucide** (outline, 2px stroke — matches the 2px line system) via CDN, wrapped by the `Icon` component (substitution — flagged). No emoji, no PNG icons. The logo mark (bolt/torx head) is the only brand glyph.

## Logos (`assets/`)
- `logo-horizontal.png`, `logo-stacked.png` — green mark + ink text, for white.
- `logo-horizontal-reversed.png`, `logo-stacked-reversed.png` — green mark + white text, for ink/dark.
- `logo-horizontal-white.png`, `logo-stacked-white.png` — all white, for green/photo.
- `logo-mark.png` — mark only (cropped from the lockup).
- `partners/de-hoop-logo-*.png` — Maakgemeenschap De Hoop stamp logo: black (default on CreaCo material, e.g. bottom-right of CTA slides), green, grey, yellow-black, teal-navy. Use as-is; never recolor to CreaCo green. Note its green (#00A651-ish) and the teal/yellow versions belong to De Hoop, not to the CreaCo palette.

## Index
- `styles.css` — entry point (imports only). `tokens/` — fonts, colors, typography, spacing, base.
- `fonts/` — Impact, Impacted (ttf, client-supplied), Special Gothic Condensed One, Arimo (woff2).
- `guidelines/` — foundation specimen cards (Brand, Colors, Type, Spacing).
- `components/` — React primitives:
  - core: **Button**, **IconButton**, **Pill**, **Icon**
  - forms: **Input**, **Select**, **Checkbox**, **Radio**, **Switch**
  - content: **Card**, **Step**, **Breadcrumb**, **DataTable**
  - feedback: **Dialog**, **Toast**, **Tooltip**
  - navigation: **Tabs**
- `slides/` — Cover, Section intro, Divider, Content, Table, CTA, Process (infographic).
- `templates/` — calm A4 document templates (print/PDF), modelled on `assets/examples/businessplan-stijlvoorbeeld.pdf`: `rapport/`, `projectplan/`, `brief/`, `memo/`. White pages, 25mm margins, green section label + 1px green rule, Impact H1 in green, grey (#595959) Arial body ~8.5–9pt, numbered green bold subheads with hanging indent, italic lead sentence with bold key phrase, tables with green header text and hairlines only, green page number bottom-right. No colour fields, no pink, no full-bleed pages.
- `word-templates/` — the same four documents as .docx with named styles (Title, Kop 1, Kop 2 genummerd, Intro, Kernzin, Tekst ingesprongen, Tabeltekst, Meta, Sectielabel) for Word / Google Docs. Impact must be installed/added for headings.
- `SKILL.md` — agent skill entry.

### Intentional additions
No source defined a component library, so the standard set above was authored from the brand's visual rules. Brand-derived: Pill, Step, Breadcrumb, DataTable (from the infographic and slide house style). `Icon` wraps the Lucide substitute set.
