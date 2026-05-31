# PLAN.md — Ecoscience Website

**Status:** Awaiting client approval before any code is written.

---

## 1. Executive Summary

We are replacing Ecoscience's existing coming-soon page with a complete, production-quality public-facing website built in Astro (static output), deployed to Hostinger Premium via a GitHub Actions CI pipeline. The site will carry the established brand identity — navy `#0A2E87`, brand green `#108439`, water-blue `#2585E1`, off-white `#FCFDFB`, Fraunces + Manrope + JetBrains Mono — into a multi-page experience structured around two product pillars (Membrane Solutions and Specialty Polymers), with supporting About, Team, News, and Contact pages. Structural and tonal reference is Notark (notark.com); visual personality is entirely Ecoscience's own — light, editorial, premium, molecular.

---

## 2. Design Direction Proposals

Three named directions are offered. All are faithful to the coming-soon page's brand identity. Pick one or ask to blend elements.

---

### Direction A — "Editorial Lab"

**Mood:** A science journal meets a premium material consultancy. Unhurried, spacious, deeply typographic.

**Color emphasis:** Off-white `#FCFDFB` dominates. Navy is reserved for body text and headings only. Green appears exclusively as an accent — italic Fraunces words, eyebrow line-pair strokes, hover underlines. Water-blue plays a supporting role for links and the occasional pull-quote. No solid color fills on section backgrounds (one exception: the footer, in very light `#F3F6FF`).

**Typography rhythm:** Fraunces at extreme optical sizes — display headings at 120–160px, section heads at 56–72px, with the italic variant used for one emotionally loaded word per heading (the same technique as the coming-soon `"Coming soon."` in italic green). Manrope at 17px/28px line-height for body. JetBrains Mono exclusively for eyebrow labels, stat callouts, and footer microtext.

**Motion philosophy:** Identical restraint to the coming-soon page. The three ambient orbs (green top-left, blue bottom-right, accent mid-right — lifted directly from the coming-soon CSS) persist as a fixed page layer. Scroll-triggered fade-rise on sections (the `@keyframes rise` pattern already established). No parallax. No element moves faster than 600ms.

**Notark patterns adapted:**
- The numbered-points block (01 / 02 / 03) for the "Who we are" section.
- The two-pillar product grid on the homepage.
- The full-width CTA strip before the footer.

**Homepage hero (in words):** Centered layout, matching the coming-soon page. Logo at top. Fraunces display headline in two lines: "Polymers that *purify*." on line one, "Materials that *endure*." on line two — italic words in green. Manrope subhead: "Innovating Polymers. Transforming Tomorrow." Below: two ghost-border CTAs (Explore Products / Contact Us). The ambient orb system is the only background motion.

**Best for:** A client who wants zero risk of the new site feeling jarring next to the coming-soon page. Safe, premium, universally readable.

---

### Direction B — "Scientific Atelier" *(Recommended)*

**Mood:** A research institute with the confidence to publish its results boldly. Dense enough to feel like it holds IP; airy enough to feel like design matters here.

**Color emphasis:** Off-white background, but with **one or two navy `#0A2E87` full-width feature strips** per page (the same technique Notark uses for dark section breaks). Within those strips, text inverts to `#FCFDFB`. Green leads all numerical call-outs and stat values (e.g. "4 Application Areas", "2 Product Pillars"). Water-blue handles all interactive elements (links, buttons, active nav). The result: three colors all earn their presence, instead of green disappearing into white space.

**Typography rhythm:** Same Fraunces/Manrope/JetBrains Mono triad, but with a tighter information hierarchy. JetBrains Mono numeric labels ("01 — Research / 02 — Process / 03 — Scale") are larger and bolder — they carry visual weight, not just label weight. Heading sizes are slightly more restrained than Direction A (80–120px display) to allow more dense content blocks.

**Motion philosophy:** Level 2 (what you selected). Scroll-triggered section reveals with a 30px upward slide + fade (extending the coming-soon `@keyframes rise`). Subtle stagger on card grids (each card reveals 80ms after the previous). Hover states on product cards: a thin green left-border slides in over 300ms. The molecular hex watermark in the hero has a slow, very subtle pulse/breathe cycle (separate from the orb drift).

**Notark patterns adapted:**
- Dark navy feature strip mid-page for the "Why Ecoscience" benefit cluster — mirrors Notark's darkened section.
- Product card grid on homepage with eyebrow + product name + one-line description — same structure, entirely new visual treatment.
- Legacy/credibility paragraph block (Notark's "emerging from Kraton" beat) → Ecoscience's own origin paragraph, same structural position.
- Numbered 01/02/03 "Who we are" points in the About page.

**Homepage hero (in words):** Left-aligned (not centered, departing from the coming-soon page). Left column: JetBrains Mono eyebrow "Advanced Polymer Science — Pune, India", then two-line Fraunces headline "Clean *water*." / "Pure *hydrogen*." — italic accent words in green. Right column: a 2×1 product pillar tile stack (Membrane Solutions / Specialty Polymers) with a subtle animated hex-cluster graphic behind it. The ambient orbs anchor top-left and bottom-right as in the coming-soon page.

**Best for:** Matching the quality register of Notark while giving Ecoscience a clearly differentiated visual personality. The light/green/navy contrast system is more immediately legible than Direction A and will age better as content density increases.

**This is my recommendation.** It is the most direct structural parallel to Notark (which is the stated reference), it exercises all three brand colors meaningfully, and the navy strips create visual rhythm that makes long pages scannable — essential for product-heavy content.

---

### Direction C — "Precision Field"

**Mood:** Architectural precision meets organic chemistry. The molecular hexagon motif is no longer a whisper — it becomes a genuine compositional element.

**Color emphasis:** Same palette, but the **molecular hex cluster from the coming-soon SVG** is extracted and used as a large, semi-opaque hero graphic (think: a full right-half of the viewport filled with a slowly breathing hex network). Green plays a stronger role in border-accents on numbered sections (a 3px left border in `#108439` on each numbered point block). Water-blue is strictly interactive only.

**Typography rhythm:** A strong underlying grid (8-column on desktop). Section dividers use a thin navy rule with a JetBrains Mono label flush-right — echoing the eyebrow line pattern from the coming-soon page, but extended to full-section separators. Heading sizes similar to Direction B, but with more aggressive letter-spacing on display text (-0.05em).

**Motion philosophy:** Level 2, but more architectural. Sections slide in from slightly left rather than from below (a lateral reveal). The hex cluster in the hero slowly rotates at ~0.5rpm. The green left-border on numbered blocks draws itself downward on scroll-entry (a CSS height animation from 0 to full).

**Notark patterns adapted:**
- The two-pillar product architecture on homepage.
- Benefit grid for "Why choose us."
- Cross-link blocks between product sub-pages.

**Homepage hero (in words):** Split 50/50. Left: nav-aligned Fraunces headline "Engineering the *molecular* future." with subhead and two CTAs below. Right: large animated SVG hex-cluster network, slowly breathing, in navy + green with soft glow — the same motif from the coming-soon page watermark, scaled up and animated.

**Best for:** Maximum visual differentiation. Creates the most distinctive brand signature, but requires the most SVG/animation work and carries the highest risk of feeling heavy on lower-end devices. Reduce-motion support is non-negotiable here.

---

## 3. Sitemap & Information Architecture

| Route | Page | Purpose |
|---|---|---|
| `/` | Home | Full marketing homepage. Brand intro, two product pillars, numbered points, benefit grid, CTA. |
| `/about` | About Us | Brand origin story, founding narrative, mission/values, Sustainable Solutions woven into the purpose statement. |
| `/products` | Products Overview | Landing page for both pillars. Large pillar cards link down to each pillar. |
| `/products/membrane-solutions` | Membrane Solutions (Pillar 1) | Pillar overview: intro paragraph, numbered points, benefit grid, links to sub-pages. |
| `/products/membrane-solutions/water-filter-membranes` | Water Filter Membranes | Detail: features, applications, technical claims, cross-link to Hydrogen Membranes. |
| `/products/membrane-solutions/hydrogen-membranes` | Hydrogen Membranes | Detail: features, applications, technical claims, cross-link to Water Filter Membranes. |
| `/products/specialty-polymers` | Specialty Polymers (Pillar 2) | Pillar overview + Sustainable Solutions woven into purpose statement. Numbered points, benefit grid. |
| `/team` | Team | Placeholder cards (name, title, photo) for team members. |
| `/news` | News & Insights | Index of articles. 3 placeholder posts at launch. |
| `/news/[slug]` | Article detail | Individual news/insight article page. |
| `/contact` | Contact | Web3Forms contact form + contact details (email, location). |

**Total: 10 routes** (12 counting the two dynamic routes `/news/[slug]` and the Astro static generation for each post).

---

## 4. Component Inventory

Every reusable piece the site will need, organized by type.

### Layout
| Component | Description |
|---|---|
| `BaseLayout.astro` | `<head>` with all meta, font loading, design-token CSS, Open Graph, page title slot |
| `PageLayout.astro` | Wraps `BaseLayout` + `Nav` + `Footer`; accepts a `title` and `description` prop |
| `Nav.astro` | Top navigation: wordmark logo left, Products dropdown (with pillar links), right-side "Contact Us" CTA button. Mobile: hamburger → slide-down drawer |
| `Footer.astro` | Three-column footer: company info + Quick Links + Products columns, bottom bar with copyright and email/web links (matching coming-soon footer pattern) |

### Background & Atmosphere
| Component | Description |
|---|---|
| `AmbientOrbs.astro` | The three-orb system from the coming-soon page, adapted as a fixed-position layer. Accepts a `variant` prop (default / muted / none) |
| `MolecularWatermark.astro` | The hex-cluster SVG motif as a configurable background layer. Accepts `opacity`, `position`, `size` props |

### Typography & UI Primitives
| Component | Description |
|---|---|
| `SectionEyebrow.astro` | JetBrains Mono label with gradient accent lines left and right (the eyebrow pattern from the coming-soon hero) |
| `PageHeader.astro` | Interior page hero: eyebrow + large Fraunces heading + optional subhead. Used on every non-home page |
| `PillBadge.astro` | The pill badge with pulsing green dot (from the coming-soon `top` bar), reused wherever a status/category label is needed |

### Section Blocks
| Component | Description |
|---|---|
| `HeroHome.astro` | Full homepage hero (layout differs by chosen design direction) |
| `NumberedPoints.astro` | The 01/02/03 block. Accepts an array of `{ number, title, body }` objects |
| `BenefitGrid.astro` | 2×3 or 3×2 grid of benefit cards. Each card: icon + title + one-line description |
| `CTAStrip.astro` | Full-width call-to-action band. Accepts `headline`, `body`, `primaryCTA`, `secondaryCTA`. Has a navy variant (for Direction B feature strips) |
| `PillarCard.astro` | Large card for the two product pillars on the homepage and `/products` overview. Eyebrow + name + description + link |
| `ProductCard.astro` | Smaller card for individual product lines within a pillar |
| `FeatureList.astro` | Vertically stacked feature/spec list with green check icons |

### People & Content
| Component | Description |
|---|---|
| `TeamMember.astro` | Card: circular photo placeholder, name, title, optional one-liner |
| `NewsCard.astro` | Horizontal or vertical card: category label + date + headline + excerpt + read-more link |

### Forms
| Component | Description |
|---|---|
| `ContactForm.astro` | Web3Forms-powered form with fields: Name, Email, Company, Message. Includes honeypot field, success/error state, accessible labels |

---

## 5. Content Outline Per Page

Legend: **[DRAFT]** = AI will write placeholder copy you'll edit later. **[CLIENT]** = real content needed from you before this section can go live.

---

### Home `/`

| # | Section | Content | Source |
|---|---|---|---|
| 1 | Nav | Links + CTA | Component |
| 2 | Hero | Headline, subhead, 2 CTAs, ambient background | **[DRAFT]** |
| 3 | Brand statement | 2–3 sentence "what we do" paragraph | **[DRAFT]** |
| 4 | Product pillars | Pillar name + one-line description for each pillar | **[DRAFT]** |
| 5 | Numbered points | 3 points: who we are / what drives us / how we work | **[DRAFT]** |
| 6 | Benefit grid | 4–6 benefits of working with Ecoscience | **[DRAFT]** |
| 7 | CTA strip | Headline + 1–2 CTAs | **[DRAFT]** |
| 8 | Footer | Email, location, links | Component |

### About `/about`

| # | Section | Content | Source |
|---|---|---|---|
| 1 | Page header | Eyebrow + heading | **[DRAFT]** |
| 2 | Origin story | 3–4 paragraph founding narrative (placeholder until **[CLIENT]** provides real story) | **[DRAFT]** |
| 3 | Mission & values | Numbered points: 3 values | **[DRAFT]** |
| 4 | Sustainable Solutions | Woven into the mission section as the company's "why" | **[DRAFT]** |
| 5 | Team preview | "Meet the people behind Ecoscience" → CTA to /team | **[DRAFT]** |
| 6 | CTA strip | "Ready to work with us?" | **[DRAFT]** |

### Products Overview `/products`

| # | Section | Content | Source |
|---|---|---|---|
| 1 | Page header | | **[DRAFT]** |
| 2 | Pillar 1 card | Membrane Solutions overview | **[DRAFT]** |
| 3 | Pillar 2 card | Specialty Polymers overview | **[DRAFT]** |
| 4 | CTA strip | | **[DRAFT]** |

### Membrane Solutions `/products/membrane-solutions`

| # | Section | Content | Source |
|---|---|---|---|
| 1 | Page header | | **[DRAFT]** |
| 2 | Pillar intro | 2-paragraph intro paragraph | **[DRAFT]** |
| 3 | Sub-product cards | Water Filter + Hydrogen cards | **[DRAFT]** |
| 4 | Numbered points | 3 points specific to membrane technology | **[DRAFT]** |
| 5 | Benefit grid | Why Ecoscience membranes | **[DRAFT]** |
| 6 | CTA strip | | **[DRAFT]** |

### Water Filter Membranes `/products/membrane-solutions/water-filter-membranes`

| # | Section | Content | Source |
|---|---|---|---|
| 1 | Page header | | **[DRAFT]** |
| 2 | Product intro | What these membranes do and why it matters | **[DRAFT]** |
| 3 | Key features | Feature list (placeholder specs) | **[DRAFT]** → **[CLIENT]** for real specs |
| 4 | Applications | Where they're used (municipal water, industrial, etc.) | **[DRAFT]** |
| 5 | Cross-link | → Hydrogen Membranes | Component |
| 6 | CTA strip | | **[DRAFT]** |

### Hydrogen Membranes `/products/membrane-solutions/hydrogen-membranes`

Same pattern as Water Filter Membranes page. **[DRAFT]** throughout, **[CLIENT]** for real specs.

### Specialty Polymers `/products/specialty-polymers`

| # | Section | Content | Source |
|---|---|---|---|
| 1 | Page header | | **[DRAFT]** |
| 2 | Pillar intro + Sustainable Solutions angle | Combines specialty polymers + sustainability narrative | **[DRAFT]** |
| 3 | Numbered points | 3 points on polymer engineering approach | **[DRAFT]** |
| 4 | Benefit grid | Why Ecoscience polymers | **[DRAFT]** |
| 5 | CTA strip | | **[DRAFT]** |

### Team `/team`

| # | Section | Content | Source |
|---|---|---|---|
| 1 | Page header | | **[DRAFT]** |
| 2 | Team grid | 6 placeholder cards (gray avatar, "Team Member", "Title") | Scaffold — **[CLIENT]** to fill |
| 3 | "Join us" CTA | | **[DRAFT]** |

### News & Insights `/news`

| # | Section | Content | Source |
|---|---|---|---|
| 1 | Page header | | **[DRAFT]** |
| 2 | Featured post | First placeholder article | **[DRAFT]** |
| 3 | Article grid | 2 more placeholder articles | **[DRAFT]** |

### Contact `/contact`

| # | Section | Content | Source |
|---|---|---|---|
| 1 | Page header | | **[DRAFT]** |
| 2 | Contact form | Name, Email, Company, Message — Web3Forms | Component |
| 3 | Contact details | Email: support@ecoscience.in / Location: Pune, Maharashtra, India | Fixed |
| 4 | Footer | | Component |

---

## 6. Tech Architecture

### Stack

| Layer | Choice | Rationale |
|---|---|---|
| Framework | **Astro 4.x** (static output mode) | Component reuse, zero JS by default, Lighthouse ≥ 95 is trivial, `dist/` is a flat file folder ready for Hostinger |
| Styling | **Plain CSS** with design tokens as CSS custom properties | No build-time CSS overhead, matches the coming-soon page's architecture, full token control |
| Content layer | **Astro Content Collections** (Markdown/MDX) | News posts as `.md` files; no CMS needed for v1 |
| Contact form | **Web3Forms** | Free, unlimited submissions on free plan, no redirect required, AJAX-capable |
| Icons | **Inline SVG** (no icon font, no external library) | Performance, accessibility, full color control |
| Images | Astro's built-in `<Image />` component | Automatic AVIF/WebP output + lazy loading |
| Fonts | Google Fonts via `<link>` with `display=swap` | Matches coming-soon page; add `<link rel="preconnect">` for both origins |

### Design Tokens (CSS Custom Properties)

Carried directly from `ecoscience_coming_soon.html`:

```css
:root {
  /* Colors */
  --bg:          #FCFDFB;
  --ink:         #0A2E87;
  --ink-soft:    #4A5B7A;
  --ink-mute:    #8B96A8;
  --green:       #108439;
  --green-soft:  #4FA94F;
  --green-light: #D5EBD8;
  --water:       #2585E1;
  --water-soft:  #6FB7E8;
  --water-light: #D6EAF8;
  --rule:        #E5E8EF;
  --navy-strip:  #0A2E87; /* for Direction B feature strips */

  /* Spacing scale */
  --space-xs:  4px;
  --space-s:   8px;
  --space-m:   16px;
  --space-l:   32px;
  --space-xl:  64px;
  --space-2xl: 128px;

  /* Type scale */
  --text-xs:   11px;  /* JetBrains Mono eyebrows */
  --text-s:    14px;
  --text-body: 17px;
  --text-lg:   20px;
  --text-xl:   28px;
  --text-2xl:  40px;
  --text-3xl:  56px;
  --text-4xl:  80px;
  --text-hero: clamp(64px, 10vw, 140px);

  /* Border radius */
  --radius-s: 6px;
  --radius-m: 12px;
  --radius-pill: 999px;

  /* Shadows */
  --shadow-card: 0 4px 24px rgba(10, 46, 135, 0.08);
  --shadow-logo: 0 16px 36px rgba(10, 46, 135, 0.14); /* from coming-soon */

  /* Transitions */
  --ease-out: cubic-bezier(0.2, 0.7, 0.2, 1); /* from coming-soon @keyframes rise */
  --duration-fast: 200ms;
  --duration-base: 350ms;
  --duration-slow: 600ms;
}
```

### File & Folder Structure

```
ecoscience/
├── public/
│   ├── favicon.ico
│   ├── favicon-32.png
│   ├── favicon-180.png          # Apple touch icon
│   ├── og-default.jpg           # 1200×630 Open Graph image
│   ├── robots.txt
│   └── sitemap.xml              # Auto-generated by @astrojs/sitemap
├── src/
│   ├── styles/
│   │   ├── tokens.css           # All CSS custom properties above
│   │   ├── reset.css            # Minimal reset (box-sizing, margin: 0)
│   │   └── global.css           # Body, type, link, focus defaults
│   ├── components/
│   │   ├── layout/
│   │   │   ├── Nav.astro
│   │   │   └── Footer.astro
│   │   ├── ambient/
│   │   │   ├── AmbientOrbs.astro
│   │   │   └── MolecularWatermark.astro
│   │   ├── ui/
│   │   │   ├── SectionEyebrow.astro
│   │   │   ├── PageHeader.astro
│   │   │   ├── PillBadge.astro
│   │   │   ├── NumberedPoints.astro
│   │   │   ├── BenefitGrid.astro
│   │   │   ├── CTAStrip.astro
│   │   │   ├── PillarCard.astro
│   │   │   ├── ProductCard.astro
│   │   │   ├── FeatureList.astro
│   │   │   ├── TeamMember.astro
│   │   │   ├── NewsCard.astro
│   │   │   └── ContactForm.astro
│   │   └── sections/
│   │       └── HeroHome.astro
│   ├── layouts/
│   │   ├── BaseLayout.astro
│   │   └── PageLayout.astro
│   ├── pages/
│   │   ├── index.astro
│   │   ├── about.astro
│   │   ├── team.astro
│   │   ├── contact.astro
│   │   ├── products/
│   │   │   ├── index.astro
│   │   │   ├── membrane-solutions/
│   │   │   │   ├── index.astro
│   │   │   │   ├── water-filter-membranes.astro
│   │   │   │   └── hydrogen-membranes.astro
│   │   │   └── specialty-polymers/
│   │   │       └── index.astro
│   │   └── news/
│   │       ├── index.astro
│   │       └── [...slug].astro
│   └── content/
│       ├── config.ts            # Astro content collection schema
│       └── news/
│           ├── placeholder-1.md
│           ├── placeholder-2.md
│           └── placeholder-3.md
├── .github/
│   └── workflows/
│       └── deploy.yml           # GitHub Actions → FTP to Hostinger
├── astro.config.mjs
├── package.json
├── tsconfig.json
└── PLAN.md
```

### Dependencies

```json
{
  "dependencies": {},
  "devDependencies": {
    "astro": "^4.x",
    "@astrojs/sitemap": "^3.x"
  }
}
```

No other packages. No React, no Tailwind, no icon libraries. The entire UI is built in Astro + plain CSS.

### Build & Deploy Pipeline

**Local build:**
```bash
npm run build   # outputs to dist/
npm run preview # local preview of dist/
```

**CI/CD (GitHub Actions → Hostinger FTP):**
```yaml
# .github/workflows/deploy.yml
on:
  push:
    branches: [main]
jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: 20 }
      - run: npm ci
      - run: npm run build
      - uses: SamKirkland/FTP-Deploy-Action@v4.3.5
        with:
          server: ${{ secrets.FTP_HOST }}
          username: ${{ secrets.FTP_USER }}
          password: ${{ secrets.FTP_PASS }}
          local-dir: ./dist/
          server-dir: /public_html/
```

Secrets (`FTP_HOST`, `FTP_USER`, `FTP_PASS`) are set in the GitHub repo Settings → Secrets. I will write the exact workflow file during Phase 2.1. **I will need these three values from you** before that phase.

**No hardcoded absolute URLs.** All internal links use Astro's root-relative paths (`/about`, `/products`, etc.). A single `site` value in `astro.config.mjs` drives the canonical URL and sitemap.

---

## 7. Phased Build Plan

### Phase 2.1 — Foundation
**Deliverables:** Repo scaffolded, Astro installed, design tokens file, `BaseLayout`, `PageLayout`, `Nav`, `Footer`, `AmbientOrbs`, `MolecularWatermark`, empty shell for every page, GitHub Actions workflow wired to Hostinger, live empty shell deployed to `www.ecoscience.com`.

**Milestone:** A blank but styled site is live at the domain. Navigation works. Deploy pipeline is confirmed end-to-end.

**Needs from you:** GitHub repo URL (to add Actions config), Hostinger FTP credentials (as repo secrets), Web3Forms access key.

---

### Phase 2.2 — Homepage
**Deliverables:** Full home page — hero, brand statement, pillar cards, numbered points, benefit grid, CTA strip. All placeholder copy. Scroll animations active.

**Milestone:** Homepage deployed and visually complete except for real copy/images.

**Needs from you:** Design direction approval (A, B, or C) before this phase starts.

---

### Phase 2.3 — About Page
**Deliverables:** Full About page with placeholder origin story, mission/values numbered points, Sustainable Solutions woven in, team-preview CTA.

**Milestone:** About page deployed.

**Needs from you:** Real origin story whenever you have it (can fill in after launch).

---

### Phase 2.4 — Products
**Deliverables:** Products overview + Membrane Solutions pillar page + Water Filter detail page + Hydrogen detail page + Specialty Polymers pillar page. All with placeholder copy.

**Milestone:** All product pages deployed and interlinked.

**Needs from you:** Real product specs/copy when available.

---

### Phase 2.5 — Team, News, Contact
**Deliverables:** Team page (6 placeholder cards), News index + 3 placeholder articles + article detail template, Contact page with working Web3Forms submission.

**Milestone:** All pages live; contact form tested end-to-end.

**Needs from you:** Web3Forms access key (can generate a free account at web3forms.com in under 2 minutes).

---

### Phase 2.6 — Polish Pass
**Deliverables:**
- Micro-interaction pass (hover states, focus rings, active states)
- Animation audit (all motion respects `prefers-reduced-motion`)
- Accessibility audit (axe DevTools — target zero critical/serious issues; WCAG 2.2 AA)
- Lighthouse audit — target Performance ≥ 95, Accessibility = 100, Best Practices = 100, SEO = 100
- Font loading optimization (subsetting if needed, `font-display: swap`, preconnect)
- Image optimization pass (all Astro `<Image />`, AVIF/WebP, proper `alt` text)
- Responsive QA at 360 / 390 / 768 / 1024 / 1440 / 1920px
- Cross-browser check (Chrome, Firefox, Safari desktop; Chrome and Safari mobile)

---

### Phase 2.7 — Launch Readiness
**Deliverables:**
- SEO metadata pass (unique `<title>` and `<meta description>` per page)
- Open Graph + Twitter card metadata per page
- `Organization` JSON-LD schema on home and contact pages
- `robots.txt` (allow all)
- `sitemap.xml` (auto-generated by `@astrojs/sitemap`)
- Favicon set (32px, 180px Apple touch, SVG favicon)
- Social share image (1200×630, `og-default.jpg`)
- Redirect: the existing coming-soon `index.html` is simply **replaced** by the new Astro `dist/index.html` — no redirect needed, same domain, same `/public_html/` root
- Final review pass

**Milestone:** Site is ready to go live. DNS cutover is your call.

---

## 8. Open Questions

| # | Question | Blocking? |
|---|---|---|
| OQ1 | **Design direction: A, B, or C?** Required before Phase 2.2 starts. | Yes — Phase 2.2 |
| OQ2 | **GitHub repo URL.** Needed to configure the Actions workflow. | Yes — Phase 2.1 |
| OQ3 | **Hostinger FTP credentials** (host, username, password). Added as GitHub secrets — never stored in code. | Yes — Phase 2.1 |
| OQ4 | **Web3Forms access key.** Sign up free at web3forms.com, copy the access key. | Yes — Phase 2.5 |
| OQ5 | **Origin story.** Founding narrative for About page. Can be placeholder at launch. | No |
| OQ6 | **Real team bios and photos.** Can be placeholder at launch. | No |
| OQ7 | **Real product specs.** Can be placeholder at launch. | No |
| OQ8 | **Favicon / brand assets.** Do you have the logo as an SVG file, or should I extract it from the coming-soon HTML? | Phase 2.1 |

---

## 9. Risks & Assumptions

| Risk | Likelihood | Mitigation |
|---|---|---|
| Coming-soon HTML contains the logo as an inline SVG (very large file — 165k+ tokens). Extracting and cleaning it is a one-time cost. | High (near-certain) | Extract logo SVG in Phase 2.1 as a standalone file; optimize with SVGO. |
| Hostinger Premium FTP may have rate limits or connection restrictions for automated deploys. | Low | Use SamKirkland's FTP Deploy Action (battle-tested with Hostinger); fall back to lftp if needed. |
| Real content (copy, specs, photos) arrives late or piecemeal. | High (you indicated this) | All placeholder copy is written to be structurally correct — swapping in real copy requires only text edits, not layout changes. |
| Web3Forms free tier changes its limits. | Low | 250 submissions/month on free tier is ample for a B2B contact page. Paid plan is $10/month if needed. |
| Molecular hex watermark SVG may not be accessible to screen readers. | Certain | It is `aria-hidden="true"` in the coming-soon page — we carry this forward. |
| `prefers-reduced-motion` not respected on ambient orbs and scroll animations. | Certain if not handled | All animation CSS is wrapped in a `@media (prefers-reduced-motion: no-preference)` block from day one. |

---

*This document is the single source of truth for the build. All changes to scope, design direction, or architecture should be reflected here before code changes are made.*
