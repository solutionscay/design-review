# Typography & Visual Layout Reference

Read this file when making typography decisions, pairing fonts, establishing type scales, or building grid-based layouts.

---

## Typography Fundamentals

### Why Typography Matters More Than You Think

Typography is the interface. In most apps, 80%+ of the content is text. Bad typography doesn't just look wrong — it actively harms comprehension, creates fatigue, and signals "this wasn't made with care." Good typography is invisible in the best way: users read effortlessly and trust the content.

### The Type Scale

Don't pick font sizes arbitrarily. Use a modular scale — a set of sizes derived from a ratio. Common ratios:

- **1.2 (Minor Third)** — Subtle steps, good for dense UIs and data-heavy interfaces
- **1.25 (Major Third)** — The sweet spot for most apps and web interfaces
- **1.333 (Perfect Fourth)** — More dramatic hierarchy, good for marketing and editorial
- **1.5 (Perfect Fifth)** — Very pronounced steps, best for presentations and hero content

Given a base size of 16px and a 1.25 ratio:
- 10px (small caption)
- 13px (caption/label)
- 16px (body)
- 20px (subhead)
- 25px (heading)
- 31px (large heading)
- 39px (display)

Pick your ratio and stick with it. Every font size in your app should come from the scale. If you're reaching for a size "between" two scale steps, you probably have a hierarchy problem, not a size problem.

### Line Height (Leading)

Body text: 1.4–1.6x the font size. Tighter than 1.4 feels cramped. Looser than 1.6 disconnects lines from each other.

Headings: 1.1–1.3x. Headings are shorter, so they need tighter leading to hold together as a unit. Large display text (32px+) can go as tight as 1.0–1.1.

The rule: as text gets larger, line-height ratio gets smaller. As text gets smaller, line-height ratio gets larger.

### Line Length (Measure)

The optimal reading line length is 45–75 characters for body text. On the web, this means max-width on text containers — never let body text span the full width of a wide viewport.

For mobile: 35–50 characters. For captions and secondary text: shorter is fine.

If your text feels "hard to read" and you can't figure out why, check the line length first. It's the most commonly overlooked typography variable.

### Letter Spacing (Tracking)

Body text: leave it alone. The type designer already optimized it.

All-caps text: add 2–5% tracking. Uppercase letters are designed to appear next to lowercase — without extra spacing, all-caps words feel jammed together.

Large display text (40px+): tighten tracking slightly (-1 to -2%). At large sizes, the default spacing feels too loose.

Small text (12px and below): open tracking slightly (+1%). Helps legibility at small sizes.

---

## Font Pairing

### The Two-Font Rule

Most interfaces need exactly two typefaces: one for headings, one for body. Adding a third is almost always unnecessary and fragments visual consistency.

### Pairing Strategies

**Contrast pairing** — Combine a serif with a sans-serif or a display face with a text face. The key is meaningful contrast: the two fonts should look intentionally different, not accidentally different. Good: geometric sans headings + humanist serif body. Bad: two similar sans-serifs that just look like a mistake.

**Superfamily pairing** — Use a type family that includes both serif and sans-serif variants designed to work together (e.g., Source Sans/Source Serif, IBM Plex Sans/Plex Serif, Noto Sans/Noto Serif). This is the safest option — guaranteed harmony.

**Weight contrast** — If using one font family, create hierarchy through weight contrast. A bold weight for headings and regular for body within the same family is always harmonious. Make sure the weights are distinct enough — semibold headings over regular body doesn't create enough contrast.

### What Makes a Good Body Font
- Large x-height (the height of lowercase letters relative to capitals) for readability at small sizes
- Open counters (the enclosed spaces in letters like "e", "a", "o")
- Even color (consistent visual density across a paragraph)
- Available in multiple weights (at minimum: regular, medium/semibold, bold)

### What Makes a Good Heading Font
- Distinctive character — it should set the tone
- Good at large sizes — details and quirks become features, not problems
- Works in the weights you need (often just bold or semibold)

### Fonts to Consider (not an exhaustive list, but proven choices)

**Body (sans):** Inter is overused but functional. Alternatives: Geist, Söhne, Untitled Sans, GT Walsheim, DM Sans, Satoshi, General Sans, Switzer, Cabinet Grotesk, Plus Jakarta Sans

**Body (serif):** Literata, Lora, Newsreader, Spectral, Crimson Pro, Libre Baskerville

**Display/Heading:** Clash Display, Cabinet Grotesk, Space Grotesk, Outfit, Syne, Bricolage Grotesque, Instrument Serif, Fraunces, Playfair Display

**Monospace:** JetBrains Mono, Berkeley Mono, Fira Code, IBM Plex Mono, Geist Mono

---

## Grid Systems

### Müller-Brockmann's Core Insight

The grid is not a constraint — it's a communication tool. Alignment creates invisible connections between elements. When everything sits on a grid, users can predict where information will be. When something breaks the grid, it signals importance.

### Building a Grid

**Columns:** 12-column grids offer the most flexibility (divisible by 2, 3, 4, 6). For simpler layouts, 4 or 6 columns work. Mobile: 4 columns. Tablet: 8 columns. Desktop: 12 columns.

**Gutters:** The space between columns. 16–24px for mobile, 24–32px for desktop. Gutters should be consistent. Varying gutter widths creates visual noise.

**Margins:** The space between the grid and the edge of the viewport. On mobile: 16–20px. On desktop: proportional to viewport width, often 5–10%.

### The 8pt Grid

Use 8px as your base unit for all spacing: padding, margins, gaps, and component sizing. This creates a consistent rhythm across the interface.

- 4px — hairline spacing (between icon and label)
- 8px — tight spacing (between related elements)
- 16px — standard spacing (between form fields, list items)
- 24px — comfortable spacing (between groups)
- 32px — section spacing
- 48px — large section breaks
- 64px — major section divisions

Everything snaps to these values. When spacing looks "off," it's usually because values are inconsistent — 13px here, 17px there. The 8pt grid eliminates that drift.

### Breaking the Grid

Intentional grid breaks create focal points. A full-bleed image in an otherwise contained layout draws the eye. An element that spans more columns than its neighbors signals importance. But every break should be deliberate — accidental grid violations just look sloppy.

---

## Color & Typography Interaction

### Contrast for Hierarchy
- Primary text: highest contrast (near-black on white, or near-white on dark)
- Secondary text: reduced contrast (gray tones) — but never below WCAG AA (4.5:1)
- Tertiary text (captions, timestamps): further reduced, but still readable
- Interactive text (links, buttons): distinguished by color, not just contrast

### Dark Mode Typography
Light text on dark backgrounds appears heavier than the inverse. On dark backgrounds, consider reducing font weight by one step (medium instead of semibold) or increasing letter spacing slightly. Pure white (#fff) text on pure black (#000) creates excessive contrast and visual vibration — use off-white on near-black instead.

### Color as Signifier
Reserve your accent color for interactive and important elements. If everything is your brand color, nothing stands out. Tufte's principle applies: color should carry information, not just decoration.
