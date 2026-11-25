<div align="center">
   
# HELIXERA

### Biology, rewritten with intent.

**A modern, fully interactive landing page for a fictional synthetic biology company — built with zero frameworks, zero dependencies, and a lab-bench aesthetic.**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white&style=flat-square)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white&style=flat-square)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6%2B-F7DF1E?logo=javascript&logoColor=black&style=flat-square)
![Dependencies](https://img.shields.io/badge/dependencies-none-brightgreen?style=flat-square)
![Size](https://img.shields.io/badge/single--file-%7E60KB-blue?style=flat-square)
![Motion](https://img.shields.io/badge/reduced--motion-respected-orange?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-acid?style=flat-square)

[Live Demo](https://khdxsohee.web.app/projects/helixera-bioworks.html) · [Report Bug](https://github.com/khdxsohee/helixera-bioworks/issues) · [Request Feature](https://github.com/khdxsohee/helixera-bioworks/issues)

</div>

---

## 📖 Table of Contents

- [About the Project](#-about-the-project)
- [Key Features](#-key-features)
- [Interactive Modules](#-interactive-modules)
- [Design System](#-design-system)
- [Motion & Micro-interactions](#-motion--micro-interactions)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [Customization Guide](#-customization-guide)
- [Browser Support](#-browser-support)
- [Accessibility](#-accessibility)
- [Performance](#-performance)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)

---

## 🧬 About the Project

**Helixera** (a portmanteau of *Helix* + *Era*) is a fictional synthetic biology company landing page built as a single, self-contained HTML file. It was designed from day one to **not look like a template** — no centered hero trio, no gradient headlines, no rows of identical cards, no glassmorphism soup.

Instead, the page borrows the visual language of an actual biotech lab: specimen frames, monospace instrument readouts, live incubator telemetry, pipeline disclosure tables, and a fully functional **Sequence Inspector** that performs real bioinformatics calculations in the browser.

> *"Every program shares the same backbone: computational design, automated construction, and closed-loop testing."*

**What makes this different from a typical landing page:**

- 🧪 **Real working tools** — the DNA analyzer computes genuine molecular biology metrics, not placeholders
- 📡 **Live data simulation** — lab status bar with drifting temperature, pH, humidity and a UTC clock
- 🎨 **Opinionated design identity** — bone-paper + ink + acid-green palette with a three-typeface system
- ⚙️ **Zero dependencies** — no React, no Tailwind, no build step. One file, double-click, done
- ♿ **Respectful of user preferences** — every animation honors `prefers-reduced-motion`

<img width="1351" height="639" alt="image" src="https://github.com/user-attachments/assets/47b27f9a-059c-40b4-b7a9-305773420b81" />

---

## ✨ Key Features

| Feature | Description |
|---|---|
| 🧬 **Animated DNA Helix** | Real-time canvas-rendered double helix with depth-shaded strands, rungs, and a live base-pair readout |
| 🔬 **Sequence Inspector** | Full DNA analysis tool — GC%, Tm, MW, reverse complement, translation, ORF detection |
| 📊 **Pipeline Filters** | Interactive program table filterable by therapeutic area with staged progress indicators |
| 📡 **Live Lab Telemetry** | Simulated incubator temperature, pH, and humidity values drifting realistically every 2.5s |
| 🔢 **Animated Counters** | Stat numbers count up with cubic ease-out when scrolled into view |
| 📝 **Validated Forms** | Sample request form with per-field validation and a generated request ID on success |
| 📰 **Newsletter Signup** | Inline email validation with success/error feedback |
| 🍔 **Mobile Menu** | Full-screen clip-path reveal menu with staggered link animation |
| ⬆️ **Scroll Utilities** | Reading progress bar, active nav highlighting, back-to-top button |
| 🔠 **Scramble Decode** | Hero headline decodes through random `A/C/G/T` glyphs on load |
| 🎞️ **Scroll Reveals** | Line-mask headline reveals and staggered fade-ins via IntersectionObserver |
| 🖼️ **Image Treatment** | Grayscale + luminosity blend duotone images with slow zoom breathing |
| 📋 **Copy to Clipboard** | One-click reverse-complement copying with toast feedback |
| 🔔 **Toast Notifications** | Contextual feedback for every user action |

---

## 🧪 Interactive Modules

### 1. Sequence Inspector

The centerpiece of the page. Paste (or load a sample) DNA sequence and get instant, **locally-computed** analysis — nothing leaves the browser.

**Computed metrics:**

| Metric | Method |
|---|---|
| **Length** | Nucleotide count in base pairs |
| **GC Content** | `(G + C) / N × 100` |
| **Melting Temp (Tm)** | Wallace rule `2(A+T) + 4(G+C)` for < 14bp; salt-adjusted `64.9 + 410×(GC−16.4)/N` for longer sequences |
| **Molecular Weight** | `Σ(A×313.21 + C×289.18 + G×329.21 + T×304.19) + 79 Da` (single-stranded) |
| **Base Composition** | Proportional stacked bar of A/C/G/T/N |
| **Reverse Complement** | Full 5′→3′ reverse complement, copyable to clipboard |
| **Frame-1 Translation** | Standard genetic code codon table (64 codons), `N` → `X` |
| **ORF Detection** | Scans all 3 forward frames for ATG→stop open reading frames ≥ 150 bp |

**Input handling:**

- Accepts only `A`, `C`, `G`, `T`, `N` (case-insensitive)
- Invalid characters are auto-stripped with a visible warning count
- Debounced analysis (280ms) with an "ANALYZING…" LED state
- Three built-in sample sequences: **Human Insulin CDS (333 bp)**, **GFP N-terminal (99 bp)**, and a seeded **Random 240 bp** generator

### 2. Pipeline Table

Eight disclosed programs (of a fictional 42) with:

- Filter chips: `All` · `Therapeutics` · `Agriculture` · `Industrial` · `Diagnostics`
- Four-stage progress dots (Discovery → Lead → Preclinical → Clinical) with a pulsing active stage
- Status badges: `ENROLLING` · `ACTIVE` · `SCREENING`
- Responsive collapse into labeled cards on mobile
- Staggered row re-entry animation on filter change

### 3. Sample Request Form

- Per-field inline validation (name, email format, organization, area select, brief length)
- Error states with monospace messages, cleared on re-input
- On success: animated SVG checkmark (stroke-dash draw), a generated request ID in the format `HX-YYMM-XXXX` (ambiguity-free alphabet), and a re-submit option

### 4. Method Accordion

Four-stage Design → Build → Test → Learn loop with `grid-template-rows: 0fr → 1fr` expansion animation and italic outline numerals that fill on open.

---

## 🎨 Design System

### Palette

| Token | Hex | Usage |
|---|---|---|
| `--ink` | `#0C1613` | Primary dark / text |
| `--ink-2` | `#122019` | Dark surfaces, inputs |
| `--paper` | `#F3F0E7` | Primary light background |
| `--paper-2` | `#EAE6D7` | Alternate section background |
| `--acid` | `#B5E62E` | Signature accent — fills, LEDs, highlights |
| `--acid-deep` | `#8FBC1E` | Accent text on light backgrounds |
| `--moss` | `#1F4A38` | Image duotone base |
| `--amber` | `#E2A63D` | Warnings, screening badges |
| `--red` | `#D0502A` | Validation errors |

### Typography

| Typeface | Role | Weights |
|---|---|---|
| **Fraunces** | Display — headlines, numerals, wordmark | 300–700 + italic, variable optical size |
| **Space Grotesk** | Body copy, buttons, labels | 300–700 |
| **IBM Plex Mono** | Instrument readouts, eyebrows, metadata | 400–500 |

### Signature Details

- **Film grain overlay** — fixed SVG `feTurbulence` noise at 5.5% opacity across the entire page
- **Offset hard shadows** — `8px 8px 0` ink shadows on cards and the instrument panel (print-press feel)
- **Duotone imagery** — grayscale images over moss-green with `mix-blend-mode: luminosity`
- **Specimen framing** — corner `+` registration marks on the hero canvas
- **Section numbering** — monospace `SEC. 01 / 02 / 03…` eyebrows with leading rules

---

## 🎞️ Motion & Micro-interactions

| Element | Technique |
|---|---|
| Hero headline | Scramble-decode through `ACGT*#` glyphs → `DECODED ✓` tag |
| DNA helix | `requestAnimationFrame` canvas loop, paused off-screen via IntersectionObserver |
| Sequence ticker | Infinite CSS marquee (content duplicated), pauses on hover |
| Section headlines | Line-mask reveals (overflow-hidden + translateY), staggered |
| Stat counters | rAF count-up with cubic ease-out, triggered once |
| Program cards | Hover lift + hard shadow; slow zoom on imagery |
| Team cards | Scattered rotations (`nth-child` variance), straighten + lift on hover |
| Lab vitals | Random-walk drift (temp ±0.05°C, pH ±0.012, RH ±0.8%) |
| Pipeline rows | Staggered `rowIn` re-animation on filter |
| Form success | SVG stroke-dashoffset checkmark draw |
| Scroll | Top progress bar, sticky header state, back-to-top reveal |

> ⚠️ **Every one of these is disabled or reduced to an instant state change when `prefers-reduced-motion: reduce` is active.**

---

## 🛠️ Tech Stack

| Layer | Choice |
|---|---|
| Markup | Semantic HTML5, single file |
| Styling | Hand-written CSS3 — custom properties, grid, clamp(), color-mix fallbacks |
| Logic | Vanilla ES6+ JavaScript (IIFE, strict mode, zero libraries) |
| Fonts | Google Fonts (Fraunces, Space Grotesk, IBM Plex Mono) |
| Images | picsum.photos seeds with CSS duotone treatment |
| Icons | None — pure typography and CSS |
| Build | None — no bundler, no compiler, no node_modules |

---

## 🚀 Getting Started

### Prerequisites

A modern browser. That's it.

### Option 1 — Run Locally

```bash
# Clone the repository
git clone https://github.com/khdxsohee/helixera-bioworks.git

# Enter the directory
cd helixera-bioworks

# Open the file (macOS)
open index.html

# Windows
start index.html

# Linux
xdg-open index.html
```

Or simply **double-click `index.html`** — no server required.

### Option 2 — Deploy to GitHub Pages

1. Fork or push this repo to your GitHub account
2. Go to **Settings → Pages**
3. Set Source to `Deploy from a branch`, branch `main`, folder `/ (root)`
4. Your site will be live at:
   ```
   https://khdxsohee.github.io/helixera-bioworks/
   ```

### Option 3 — Serve with any static server

```bash
npx serve .
# or
python -m http.server 8000
```

---

## 📁 Project Structure

```
helixera-bioworks/
├── index.html        # Everything — markup, styles (~1000 lines), logic (~450 lines)
├── README.md         # You are here
└── LICENSE           # MIT
```

> The single-file architecture is intentional: trivially portable, instantly deployable, zero dependency surface. Internal sections are clearly demarcated with `/* ============ SECTION ============ */` comment banners.

---

## ✏️ Customization Guide

### Change the brand name

Search for `Helixera` and `HELIXERA` in `index.html` (logo, title, footer, status bar). The asterisk `*` is part of the identity — keep it.

### Change the palette

All colors live in `:root` at the top of the `<style>` block:

```css
:root{
  --ink:#0C1613;   /* dark */
  --paper:#F3F0E7; /* light */
  --acid:#B5E62E;  /* accent */
  /* ... */
}
```

### Add a pipeline program

Add a `<tr data-area="...">` row inside `#pipeRows` following the existing structure — the filter logic picks it up automatically.

### Add a team member

Copy an `<article class="tcard">` block and update the image seed, code, name, role, and bio.

### Swap placeholder images

Replace any `https://picsum.photos/seed/...` URL with your own. Keep the duotone by leaving the `.p-img`/`tint` classes intact.

### Extend the Sequence Inspector

The codon table (`CODONS` object) and all formulas are plain JS constants near the top of the script — adding e.g. extinction coefficient or primer validation is a matter of extending `analyze()`.

---

## 🌐 Browser Support

| Browser | Version |
|---|---|
| Chrome / Edge | Latest 2 |
| Firefox | Latest 2 |
| Safari | 15.4+ |
| Mobile Safari | iOS 15+ |
| Chrome Android | Latest |

> `color-mix()` is used with safe fallbacks (`rgba`) for critical borders. `backdrop-filter` degrades gracefully. Canvas uses `devicePixelRatio`-aware rendering capped at 2× for performance.

---

## ♿ Accessibility

- Semantic landmarks (`header`, `main`, `nav`, `footer`, `section`)
- `aria-expanded` on the menu toggle and accordion buttons
- `aria-label` on icon-only controls (copy, back-to-top, menu)
- `role="status"` + `aria-live="polite"` on the toast
- Visible `:focus-visible` outlines throughout
- Labels bound to all form inputs
- `prefers-reduced-motion` disables: canvas loop, marquee, image zoom, scramble, LED blink, counters (set instantly), smooth scrolling
- Contrast-checked palette (acid used only as fill/accent, never as body text on light)

---

## ⚡ Performance

- **Zero network dependencies** beyond fonts and placeholder images
- Canvas helix **pauses when off-screen** (IntersectionObserver) and on tab hide
- Counters and reveals are **one-shot observers** (unobserved after firing)
- All scroll handlers are `passive`
- Image zoom and ticker are pure CSS (compositor-only)
- No layout thrash — single read/write passes, `transform`/`opacity` animations only
- Debounced sequence analysis (280 ms)

---

## 🗺️ Roadmap

- [ ] 6-frame translation with frame selector
- [ ] Restriction site detection
- [ ] Primer design helper (Tm matching)
- [ ] JSON export of analysis results
- [ ] Dark "night bench" theme toggle
- [ ] Multi-page split for real deployment (Careers, Platform deep-dive)
- [ ] Lighthouse 100/100 pass with self-hosted fonts

---

## 🤝 Contributing

Contributions are what make the open-source community great. Any contributions you make are **greatly appreciated**.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'feat: add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

Distributed under the **MIT License**. See [`LICENSE`](LICENSE) for more information — the fictional company data, copy, and design identity are included for demonstration purposes.

```
MIT License

Copyright (c) 2026 khdxsohee

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
```

---

## 👤 Author

**khdxsohee**

- GitHub: [@khdxsohee](https://github.com/khdxsohee)
- Project: [helixera-bioworks](https://github.com/khdxsohee/helixera-bioworks)

---

<div align="center">

**Built with intent — like the biology.**

`ATG GCA TTA CCG GAA TTC GGC TAA` — *a start is just a sequence.*

⭐ Star this repo if you found it useful

</div>
