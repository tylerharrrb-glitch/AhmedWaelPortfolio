# Handoff: Ahmed Wael Metwally — Finance Portfolio

## Overview
A single-page personal portfolio for a finance professional (equity research / financial modeling). The design is an institutional "Wall Street" aesthetic — deep forest green, gold, and cream, with serif headlines (research-report feel), a Bloomberg-style market ticker, and subtle scroll-in motion. It presents: hero, about, experience, projects (equity research notes + a 15-company model library + live engines), certifications, skills, education, and a contact close.

## About the Design Files
The file in this bundle (`Ahmed Wael Metwally — Portfolio.dc.html`) is a **design reference created in HTML** — a working prototype showing the intended look and behavior. It is **not production code to copy directly**. (It is authored in a "Design Component" format with a small custom runtime; treat it as a visual + behavioral spec, not a component to import.)

Your task is to **recreate this design in the target codebase's existing environment** using its established patterns. The user's current site (`ahmedwael.pages.dev`) was built with Claude Code — likely static HTML/CSS or a light framework. Recreate this redesign there using whatever the project already uses (plain HTML/CSS, React, Astro, etc.). If you're starting fresh, plain semantic HTML + CSS (or a static-site setup like Astro) is the most appropriate choice — this is a content site, not an app.

## Fidelity
**High-fidelity (hifi).** Final colors, typography, spacing, and interactions are all specified below. Recreate the UI pixel-perfectly. Every hex value, font, size, and piece of copy in this README is the source of truth.

---

## Design Tokens

### Colors
| Token | Hex | Usage |
|---|---|---|
| Green / base dark | `#0d2119` | Primary dark section background (hero, experience, certs, education) |
| Green / deepest | `#0a1611` | Ticker bar, contact section, footer |
| Green / heading-on-dark | `#f6f4ec` | Headings on dark backgrounds |
| Cream / page | `#f4f2ea` | Light section background (about, projects, skills) |
| Cream / card | `#fbfaf4` | Card background on light sections (research cards) |
| White / card | `#ffffff` | Company cards, skill chips |
| Ink | `#16241d` | Headings/text on light backgrounds |
| Ink / body | `#2c3b33` | Body paragraph text on light |
| Ink / muted | `#45554c` | Secondary body text on light |
| Sage / muted-on-dark | `#9fb3a8` | Body/muted text on dark |
| Sage / soft-on-dark | `#b7c8bf` | Slightly brighter muted text on dark |
| Sage / faint | `#8ba093` · `#7d9587` | Mono labels / tertiary text on dark |
| Sage-ink (light) | `#5f7a6c` · `#8a9a90` | Muted text/labels on light |
| **Gold (primary accent)** | `#c2a05c` | Eyebrows, accents, primary buttons, hover, borders |
| Gold / bright | `#d6b870` · `#d4b878` | Button hover, active nav link |
| Positive (up) | `#2f6b4e` (on light) · `#86b39a` (on dark) | Overweight call, upside, ticker up |
| Negative (down) | `#a8503f` (on light) · `#cf8a7e` (on dark) | Underweight call, downside, ticker down |
| Call badge bg — Overweight | `rgba(134,179,154,.18)` | with fg `#2f6b4e` |
| Call badge bg — Underweight | `rgba(207,138,126,.18)` | with fg `#a8503f` |
| Border on dark | `rgba(255,255,255,.08)` – `.12` | hairlines / dividers |
| Border on light | `rgba(20,40,30,.1)` – `.14` | card borders / dividers |

### Typography
Three Google Fonts:
- **Newsreader** (serif) — all display headlines and serif body accents. Weights 300, 400, 500, 600 + italic. Optical-size axis `opsz 6..72`.
- **Archivo** (sans-serif) — default UI/body font, nav, buttons, chips. Weights 400, 500, 600, 700.
- **IBM Plex Mono** (monospace) — eyebrows, section numbers, data, ticker, tags, dates. Weights 400, 500, 600.

Google Fonts link:
```
https://fonts.googleapis.com/css2?family=Newsreader:ital,opsz,wght@0,6..72,300;0,6..72,400;0,6..72,500;0,6..72,600;1,6..72,300;1,6..72,400&family=Archivo:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&display=swap
```

Type scale (key styles):
| Role | Font | Size | Weight | Tracking / notes |
|---|---|---|---|---|
| Hero name (h1) | Newsreader | `clamp(46px, 8.5vw, 124px)` | 500 | line-height .96, letter-spacing −.022em, color `#f6f4ec` |
| Section title (h2) | Newsreader | `clamp(34px, 4.2vw, 52px)` | 400 | line-height 1.04, letter-spacing −.015em |
| Contact headline (h2) | Newsreader | `clamp(40px, 6vw, 84px)` | 400 | line-height 1.02, letter-spacing −.02em |
| Hero subtitle | Newsreader italic | `clamp(19px, 2.3vw, 27px)` | 300 italic | line-height 1.45, color `#b7c8bf` |
| About body | Newsreader | `clamp(19px, 1.7vw, 23px)` | 300 | line-height 1.62, `text-wrap: pretty`; key phrases weight 500 / color `#16241d` |
| Card title (h4) | Newsreader | 19–25px | 500 | line-height ~1.2 |
| Eyebrow / section number | IBM Plex Mono | 12px | 400/500 | letter-spacing .2em, uppercase, color `#c2a05c` (e.g. `01 — ABOUT`) |
| Nav links | Archivo | 12.5px | 500 | letter-spacing .03em |
| Buttons | Archivo | 13.5–14px | 600 | letter-spacing .02em |
| Skill chips / body small | Archivo | 13–16px | 400/500 | |
| Ticker / data | IBM Plex Mono | 11.5px | 400/500 | |

### Spacing & layout
- Content container: `max-width: 1180px; margin: 0 auto; padding: 0 40px;`
- Section vertical padding: `110px` top & bottom (`120px 0 100px` for contact).
- Section anchor offset: `scroll-margin-top: 80px` (for sticky-nav jump targets).
- Standard grid gaps: cards `22px`, company cards `14px`, two-column section splits `56–64px`.
- `box-sizing: border-box` globally; `html { scroll-behavior: smooth }`.
- `::selection { background:#c2a05c; color:#0a1611 }`.

### Borders, radius, shadow
- **No border-radius** anywhere — sharp corners are intentional (institutional feel). Buttons, cards, chips, badges are all square.
- Borders are 1px hairlines using the border tokens above.
- **No drop shadows.** Depth comes from the green/cream contrast and hairline borders, not shadows.
- Monogram "A" mark: 34px square, 1px gold border, Newsreader letter, gold.

---

## Screens / Views
Single scrolling page. Top → bottom:

### 0. Ticker bar (fixed at very top of page, scrolls away)
- Height 42px, bg `#0a1611`, bottom border `1px rgba(194,160,92,.22)`, `overflow:hidden`.
- A horizontal marquee: a flex row of items duplicated twice, animated `transform: translateX(0) → translateX(-50%)` over `48s linear infinite` (seamless loop).
- Each item: mono symbol (`#e9e6dc`) · mono value (`#7d9587`) · mono delta (green `#86b39a` up / red `#cf8a7e` down), separated by `border-right: 1px rgba(255,255,255,.07)`, padding `0 26px`.
- Items (illustrative market data + the candidate's real coverage): `EGX30 30,142.6 +0.84%`, `ARCC.CA PT 80 ▲ +43%`, `SWDY.CA PT 71 ▼ −22.3%`, `JUFO.CA PT 22 ▼ −21.7%`, `TASI 12,418.4 +0.31%`, `2280.SR Almarai ● Covered`, `AAPL NASDAQ ● Modeled`, `EGP/USD 48.62 ▼ −0.12%`. **Note:** index/FX levels are placeholders styled like a terminal; price targets are real. Replace with live data if desired.

### 1. Nav (sticky)
- `position: sticky; top: 0; z-index: 50`, bg `rgba(13,33,25,.92)` with `backdrop-filter: blur(14px)`, bottom border `1px rgba(255,255,255,.08)`. Height 66px.
- Left: monogram "A" (gold-bordered square) + `AWM` in mono, letter-spacing .22em.
- Right: links — About, Experience, Projects, Certifications, Skills, Education, Contact. Color `#9fb3a8`, hover `#f4f2ea`. **Active link** (scroll-spy) turns gold `#d6b870`.

### 2. Hero (`#top`)
- bg `#0d2119`. Two decorative overlays (pointer-events:none): a 64px subtle grid (`linear-gradient` lines at `rgba(255,255,255,.028)`) and a gold radial glow top-right (`radial-gradient(circle, rgba(194,160,92,.14), transparent 65%)`, 620px).
- Padding `96px 40px 78px`.
- Gold mono eyebrow: `INVESTMENT BANKING · PRIVATE EQUITY · EQUITY RESEARCH` (tracking .28em).
- h1: `Ahmed Wael` / `Metwally` (two lines).
- Italic serif subtitle: `M&A · Private Equity · Equity Research · Valuation · Financial Modeling — building institutional-grade models, one company at a time.`
- Two buttons: **Get in Touch** (gold fill `#c2a05c`, text `#0d2119`, padding `15px 28px`; hover bg `#d6b870` + `translateY(-2px)`) → `#contact`; **View Projects** (transparent, 1px `rgba(255,255,255,.24)` border, cream text; hover border gold) → `#projects`.
- Mono contact row: `Cairo, Egypt / ahmedwaelmetwally@gmail.com / +20 103 278 2667`.
- **Stats band**: 4-column grid, 1px gap, `rgba(255,255,255,.08)` background showing as hairlines, each cell bg `#0d2119`, padding `30px 26px`. Each: a big Newsreader gold number (`clamp(38px,5vw,58px)`) that **counts up** on load, + mono uppercase label. Values: **15** Companies Modeled · **3** Live Financial Engines · **3** Professional Certifications · **9** EGX Sectors Covered.

### 3. About (`#about`) — light
- bg `#f4f2ea`. Two-column grid `0.85fr 1.4fr`, gap 64px.
- Left: eyebrow `01 — ABOUT`, h2 `Who I Am`, 46×2px gold underline rule.
- Right: two large Newsreader paragraphs (weight 300, key phrases weight 500 ink) + one small mono-less sans note in `#5f7a6c`. Full copy in the source file; it covers: GSU Finance & Investment grad 2024, Financial Analyst at MCDR, CFA Level I Candidate, FMVC + FMVA, 15 companies modeled (12 EGX / 2 Tadawul / 1 NASDAQ), initiation research on Elsewedy & Juhayna, three live engines, target roles.

### 4. Experience (`#experience`) — dark
- bg `#0d2119`. Eyebrow `02 — EXPERIENCE`, h2 `Career History`.
- Two-column `0.8fr 1.5fr`, top border divider.
- Left: gold "● Current Role" tag (gold bg, dark text, mono uppercase), h3 `Financial Analyst`, gold link `MCDR — Misr for Central Clearing, Depository & Registry ↗` → https://www.mcsd.com.eg/en, mono dates `Nov 2024 – Present` / `Cairo, Egypt`, descriptive line.
- Right: 4 bullet rows, each `auto 1fr` grid: gold mono index (`01`–`04`) + paragraph, separated by `1px rgba(255,255,255,.09)` bottom borders.

### 5. Projects (`#projects`) — light, three sub-blocks
bg `#f4f2ea`. Eyebrow `03 — SELECTED WORK`, h2 `Built for Finance`, intro line.

**5a. Equity Research — Initiation of Coverage.** Header row + mono caption `DCF-anchored · PT vs. market`. 3-column grid of cards (bg `#fbfaf4`, 1px border). Each card:
- Mono ticker (top-left) + call badge (top-right, colored per Overweight/Underweight).
- Newsreader company name + sector caption.
- A 2-cell stat grid (hairline-separated): **Price Target** and **Current**, each label in tiny mono uppercase + big Newsreader value.
- A mono colored move line (e.g. `+43% Upside` green / `−22.3% Downside` red).
- Thesis paragraph (13.5px, `#45554c`).
- Footer links: `Report ↗` + `Slides ↗`.
- The three cards (exact data):
  - **Arabian Cement** (ARCC.CA, Building Materials & Cement) — **Overweight**, PT EGP 80, Current EGP 56.11, **+43% Upside**. Thesis: "Trading at a 43% discount to intrinsic value, with a net-cash balance sheet and a post-devaluation earnings step-change not yet in the share price." Report: https://ahmedwael.pages.dev/models/Arabian-Cement-ARCC-Equity-Research.pdf · Slides: https://ahmedwael.pages.dev/models/Arabian-Cement-ARCC-Equity-Research.pptx
  - **Elsewedy Electric** (SWDY.CA, Cables, Energy & EPC Infrastructure) — **Underweight**, PT EGP 71, Current EGP 91.19, **−22.3% Downside**. Thesis: "At 91 EGP the market prices in >12% perpetual FCF growth — above Egypt's nominal GDP; our DCF supports 71 EGP." Report: https://ahmedwael.pages.dev/models/Elsewedy-SWDY-Equity-Research.pdf · Slides: https://ahmedwael.pages.dev/models/Elsewedy-SWDY-Equity-Research.pptx
  - **Juhayna Food Industries** (JUFO.CA, Dairy & Beverage) — **Underweight**, PT EGP 22, Current EGP 28.09, **−21.7% Downside**. Thesis: "Input-cost pressure and a stretched multiple leave little margin of safety; our DCF lands at 22 EGP against a 28 EGP market price." Report: https://ahmedwael.pages.dev/models/Juhayna-JUFO-Equity-Research.pdf · Slides: https://ahmedwael.pages.dev/models/Juhayna-JUFO-Equity-Research.pptx

**5b. Valuation & 3-Statement Model Library.** Caption `15 companies · 3 markets · DCF + NAV`. Grouped by market, each group a gold mono label with a flex divider rule + count, then a 3-column grid of compact company cards (bg `#fff`, 1px border; hover: border gold + `translateY(-2px)`). Each card: Newsreader name + gold mono ticker, sector caption, footer links `Preview` + `Download ↓`.
  - **EGX — Cairo (12 companies · 9 sectors):** Arabian Cement (ARCC.CA, Materials/Cement), Oriental Weavers (ORWE.CA, Home Textiles/Carpets), Ibnsina Pharma (ISPH.CA, Healthcare/Distribution), Telecom Egypt (ETEL.CA, Telecom), E-finance (EFIH.CA, Fintech), Talaat Moustafa (TMGH.CA, Real Estate), Elsewedy Electric (SWDY.CA, Industrials), Fawry (FWRY.CA, Fintech), Cleopatra Hospital (CLHO.CA, Healthcare), Juhayna (JUFO.CA, Consumer Staples), Eastern Company (EAST.CA, Tobacco), Edita Food (EFID.CA, Consumer Staples).
  - **Tadawul — Riyadh (TASI) (2):** Almarai (2280.SR, Consumer Staples), Qassim Cement (3040.SR, Materials).
  - **NASDAQ — New York (1):** Apple (AAPL, Technology).
  - **Download URL pattern:** `https://ahmedwael.pages.dev/models/<File>.xlsx` (filenames listed in the source `co(...)` calls). **Preview URL:** `https://view.officeapps.live.com/op/view.aspx?src=<URL-encoded download URL>`.

**5c. Live Financial Engines.** Caption `Deployed & interactive`. 3-column grid of dark cards (bg `#0d2119`, full card is an `<a>`; hover `translateY(-4px)`). Each: a "● LIVE" mono tag with a **pulsing green dot** (`@keyframes pulseDot`), Newsreader name, description, `Open Engine →`.
  - Multi-Method Valuation Engine — https://wolf-valuation-engine.pages.dev/
  - M&A Modeling Engine — https://valor-ma-engine.pages.dev/
  - 3-Statement Model Engine — https://3-statement-model-engine.pages.dev/

### 6. Certifications (`#certifications`) — dark
- bg `#0d2119`. Eyebrow `04 — CREDENTIALS`, h2 `Certifications`. 3-column grid of bordered cards (1px `rgba(255,255,255,.12)`). Each: gold mono year, Newsreader name, sage issuer, optional gold `View Credential ↗` link.
  - **CFA Level I Candidate** — CFA Institute — *In Progress* (no link).
  - **Financial & Valuation Modeling (FMVC)** — Wall Street Prep — 2026 (no link).
  - **Financial Modeling & Valuation Analyst (FMVA)** — Corporate Finance Institute — 2025 — link http://credentials.corporatefinanceinstitute.com/96cc4829-968e-462b-b284-2556c7262a40

### 7. Skills (`#skills`) — light
- bg `#f4f2ea`. Eyebrow `05 — EXPERTISE`, h2 `Skills & Tooling`. 3-column grid; each column = mono uppercase title with bottom rule + wrap of chips (white bg, 1px border, `8px 14px`).
  - **Financial Modeling:** 3-Statement Modeling, DCF, LBO, Comparable Company Analysis, Precedent Transactions, Merger Model, Accretion / Dilution.
  - **Valuation & Analysis:** WACC, Terminal Value, Sensitivity & Scenario, Relative Valuation, NAV / RNAV, Dividend Discount Model.
  - **Tools:** Bloomberg Terminal, Capital IQ, Excel (Advanced), PowerPoint, Python.

### 8. Education (`#education`) — dark
- bg `#0d2119`. Eyebrow `06 — EDUCATION`, h2 `Academic Background`. Two-column `0.8fr 1.5fr`.
- Right: mono `2020 – 2024`, h3 `Bachelor of Finance & Investment`, gold link `Georgia State University, J. Mack Robinson College of Business ↗` → https://robinson.gsu.edu/, coursework line (Corporate Finance, Financial Statement Analysis, Investments, Financial Modeling & Valuation, Capital Markets, Econometrics).

### 9. Contact (`#contact`) — deepest green close
- bg `#0a1611`, gold radial glow bottom-left. Eyebrow `07 — CONTACT`, huge h2 `Let's build the / next deal together.`, supporting paragraph.
- Buttons: **Download CV** (gold fill) → https://ahmedwael.pages.dev/Ahmed%20Wael%20Metwally%20-%20CV.pdf ; **LinkedIn ↗** (outline) → https://www.linkedin.com/in/ahmedwaelmetwally ; **Email** (outline) → mailto:ahmedwaelmetwally@gmail.com.
- Mono row: `+20 103 278 2667 / Cairo, Egypt`.

### 10. Footer
- bg `#0a1611`, top hairline. Left: monogram + `Ahmed Wael Metwally © 2026`. Right: mono `M&A · PRIVATE EQUITY · EQUITY RESEARCH · VALUATION`.

---

## Interactions & Behavior
- **Smooth scroll** to anchors via `html { scroll-behavior: smooth }`; sections carry `scroll-margin-top: 80px` so the sticky nav doesn't overlap targets.
- **Sticky nav + scroll-spy:** on scroll, the link whose section straddles ~40% of the viewport height turns gold (`#d6b870`); others are `#9fb3a8`.
- **Ticker marquee:** infinite horizontal scroll; items rendered twice for a seamless loop.
- **Count-up stats:** the 4 hero numbers animate from 0 to their target (~1.5s, cubic ease-out) shortly after load.
- **Scroll reveal:** elements tagged for reveal slide up ~20px into place as they enter the viewport (`~0.85s`, cubic-bezier(.22,.61,.36,1)).
  - ⚠️ **Important implementation note:** the reveal animates **transform only — opacity is always 1**. Do NOT pre-hide elements with `opacity:0` and rely on a transition/animation to bring them back; if the animation clock fails to composite, the content stays blank. Keep content visible by default and treat motion as pure enhancement. In React, an `IntersectionObserver` adding a class that triggers a transform `@keyframes` (with `animation-fill-mode: both`) is the clean equivalent.
- **Hover states:** buttons lift `translateY(-2px)` and brighten gold; cards lift (`-2px` library / `-4px` engines) and border turns gold; links shift to gold/cream. Transitions ~.25s.
- **Pulsing "LIVE" dot:** `@keyframes pulseDot` (opacity + scale, 1.8s ease-in-out infinite).

## State Management
Minimal — this is a static content page. The only runtime state:
- Active nav section (derived from scroll position; no persistence needed).
- Count-up animation progress (transient, runs once on load).
No data fetching. If you later wire the ticker to live quotes, that's the only async addition.

## Responsive behavior
- The current prototype is desktop-first (1180px container, multi-column grids). For production, add breakpoints: collapse the 3-column grids to 2 then 1 column under ~900px / ~600px; collapse two-column section splits to single column; reduce section padding to ~64px on mobile; the `clamp()` type scales already handle fluid sizing. Nav should collapse to a menu on small screens.

## Assets
- **Fonts:** Newsreader, Archivo, IBM Plex Mono via Google Fonts (link above). No self-hosted assets required.
- **No images or icon libraries** — all "icons" are Unicode glyphs (→ ↗ ↓ ● ▲ ▼) and CSS shapes. The decorative grid and radial glows are pure CSS gradients.
- **External documents** (PDFs, PPTX, XLSX, CV) are hosted at `ahmedwael.pages.dev` — keep those links or repoint them to wherever the files live in the new deployment.

## Files
- `Ahmed Wael Metwally — Portfolio.dc.html` — the full design reference (markup + inline styles + the small amount of reveal/count-up/scroll-spy JS). Open it in a browser to see the live design and read exact inline style values for anything not captured above.
