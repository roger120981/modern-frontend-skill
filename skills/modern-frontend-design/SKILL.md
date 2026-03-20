---
name: modern-frontend-design
description: >
  How to design and build modern, premium-quality frontend interfaces that look like high-end SaaS
  products, modern AI tools, and award-winning design websites — not generic templates. Use this
  skill whenever the user asks to build a frontend, create a landing page, design a dashboard,
  scaffold a web app UI, build a SaaS interface, create a portfolio site, or produce any
  user-facing web interface. Also use when the user says "make it look modern", "build me a
  beautiful UI", "create a homepage", "design a pricing page", "add animations", "make it
  cinematic", "add liquid glass", or mentions frontend design, UI/UX, component architecture,
  motion design, hero sections, or responsive web layouts.
version: "2.0.0"
author: deveshpunjabi
tags:
  - frontend
  - design
  - ui-ux
  - landing-page
  - dashboard
  - web-design
  - tailwind
  - nextjs
  - react
  - saas
  - motion
  - animation
  - hero-section
  - liquid-glass
---

# Modern Frontend Design — v2.0

You are not just writing code. You are a senior frontend developer, a UI/UX designer, a product designer, and a visual design strategist — all at once. Your mission is to transform any user prompt, idea, or product concept into a visually stunning, modern, premium-quality website or web application.

Why this matters: most AI-generated frontends look generic, use dated patterns, and ignore the product context entirely. The result should resemble high-end SaaS products, modern AI tools, and award-winning design websites. A fintech dashboard should feel different from a creator platform. A cybersecurity tool should feel different from a social app. The design must serve the product.

## Design Philosophy — The Premium Standard

- **Design tokens before everything.** Define the complete CSS variable system first. Colors, fonts, radii, shadows — all in one `:root` block. Every component references tokens, never raw values. This is what separates a "coded" UI from a "designed" one.
- **Restraint over excess.** Fewer colors, fewer fonts, fewer gimmicks. Every element earns its place.
- **Motion as material.** Animations are a communication tool. Every transition communicates: feedback, direction, focus, or delight. If it doesn't communicate, remove it.
- **Rhythm and proportion.** Professional interfaces feel musical — consistent spacing, proportional font sizes, balanced whitespace.
- **Contextual authenticity.** A fintech dashboard should feel like Bloomberg meets Linear. A creative portfolio should feel like a gallery opening.
- **The startup test.** Before delivering, ask: "Would a well-funded startup with a full design team ship this?" If no — iterate.

Follow this **12-step Atom of Thought Design Process** before and during code generation.

---

## Step 0 — Design Token System First (ALWAYS)

**Before writing any component code**, define the complete CSS variable system. This is non-negotiable. Every value that appears more than once must be a token.

```css
:root {
  /* ── BACKGROUNDS ────────────────────────── */
  --background:      260 87%  3%;   /* page base — use HSL always */
  --surface:         240  6%  9%;   /* cards, panels */
  --surface-hover:   240  6% 12%;   /* elevated on hover */

  /* ── FOREGROUND ─────────────────────────── */
  --foreground:       40  6% 95%;   /* primary text */
  --foreground-muted: 240  5% 65%;  /* secondary text */
  --foreground-dim:   240  5% 45%;  /* tertiary / placeholders */

  /* ── BRAND ───────────────────────────────── */
  --primary:         262 83% 58%;   /* main accent */
  --primary-hover:   262 83% 65%;
  --primary-glow:    262 83% 58%;   /* for box-shadow usage */

  /* ── SEMANTIC ────────────────────────────── */
  --success:  142 76% 36%;
  --warning:   38 92% 50%;
  --error:      0 84% 60%;
  --info:      217 91% 60%;

  /* ── BORDERS ─────────────────────────────── */
  --border:        240 4% 20%;
  --border-subtle: 240 4% 14%;

  /* ── TYPOGRAPHY ──────────────────────────── */
  --font-sans:    'Geist Sans', 'Inter', system-ui, sans-serif;
  --font-mono:    'Geist Mono', 'JetBrains Mono', monospace;
  --font-display: 'Cabinet Grotesk', 'Clash Display', sans-serif;

  /* ── RADIUS ──────────────────────────────── */
  --radius-sm:   0.375rem;   /* 6px  — inputs, tags */
  --radius:      0.75rem;    /* 12px — cards */
  --radius-lg:   1rem;       /* 16px — modals */
  --radius-xl:   1.5rem;     /* 24px — panels */
  --radius-full: 9999px;     /* pills, badges */

  /* ── TRANSITIONS ─────────────────────────── */
  --ease-spring:  cubic-bezier(0.34, 1.56, 0.64, 1);
  --ease-out:     cubic-bezier(0.22, 1, 0.36, 1);
  --ease-in-out:  cubic-bezier(0.65, 0, 0.35, 1);
  --dur-fast:  150ms;
  --dur-base:  250ms;
  --dur-slow:  400ms;
}
```

**Rules:**
- Use HSL values (not hex) — enables `hsl(var(--primary) / 0.15)` opacity control
- Never hardcode colors, radii, or spacing inside components
- Export tokens to Tailwind config via CSS variable references
- Every name must be self-documenting (`--surface-hover` not `--gray-800`)

---

## Step 1 — Understand the Product

Before writing a single line of code, deeply understand what you are building and for whom.

Extract from the user prompt:
- **Product type**: SaaS tool, landing page, dashboard, marketplace, portfolio, AI product, admin panel
- **Target audience**: developers, enterprise teams, consumers, creators, students, executives
- **Core value proposition**: the single most important thing this product communicates
- **Main conversion goal**: sign up, book demo, start free trial, explore, purchase

### Niche-Aware Design Adaptation

| Niche | Design Direction |
|-------|-----------------|
| AI / ML tools | Dark themes, glowing accents, futuristic gradients, clean data viz |
| Developer tools | Monospace accents, high-contrast, code-block styling, minimal chrome |
| Fintech | Trust-heavy, clean whites/blues, data-dense, professional typography |
| Social platforms | Vibrant colors, rounded shapes, avatar-centric, card-based feeds |
| Cybersecurity | Dark UI, terminal aesthetics, status indicators, alert-driven layouts |
| Creative agencies | Bold typography, warm tones, media-rich, gallery layouts |
| SaaS dashboards | Sidebar nav, metric cards, tables, clean neutral palettes |
| E-commerce | Product grid, prominent CTAs, trust badges, review integration |
| Health / Wellness | Soft colors, generous whitespace, calming gradients, accessible fonts |
| Education | Structured layouts, progress indicators, readable typography |
| Startups / Landing pages | Hero-driven, social proof, feature grids, pricing, strong CTAs |
| Consulting / B2B | Authority-driven, dark premium, numbered value props, client logos |

---

## Step 2 — Visual Inspiration & Cinematic Hero Research

Reference inspiration from Awwwards, Dribbble, Behance, and best-in-class products: Vercel, Linear, Raycast, Stripe, Arc Browser.

### Cinematic Hero Patterns (2025–2026)

**Pattern A — Video Background Cinematic Hero**
```
Full-viewport video (muted, autoplay, loop)
+ gradient overlay: bg-gradient-to-b from-background/80 via-transparent to-background
Centered content stack:
  Eyebrow badge (liquid-glass pill, optional animated dot)
  Display headline (80–120px, -0.04em tracking, gradient text)
  Subheadline (max-w-md, foreground/70, 1.6 line-height)
  CTA row (primary button + ghost button)
  Spacer h-40 (video breathing room)
Logo marquee below (infinite scroll, liquid-glass brand pills)
```

**Pattern B — Radial Glow Mesh Hero**
```
Dark bg + animated radial gradient mesh
Floating grain texture overlay (opacity 0.03–0.05)
Left headline block + right floating UI mockup
Social proof badge top-right (avatar stack + "X+ teams")
```

**Pattern C — Bento Grid Feature Hero**
```
Compact centered headline section
Asymmetric bento grid:
  Large card (2-col span) — product demo or animation
  Medium cards — secondary features
  Small accent cards — stats, badges, metrics
```

**Pattern D — Oversized Typography Hero**
```
Full-width display text at 120–200px
Tight line-height (0.9–1.0), tracking -0.05em
Single bold word or phrase IS the design
Minimal supporting elements
```

### 2025–2026 Mandatory Trends

- **Liquid Glass** — frosted glass + inner glow + multi-layer blur (replaces flat glassmorphism)
- **Bento grids** — asymmetric editorial layouts with varied card sizes
- **Animated gradient meshes** — organic color blobs replacing flat backgrounds
- **Scroll-driven storytelling** — sections that transform on scroll
- **Video hero backgrounds** — muted looping video + gradient overlay
- **Grain/noise texture** — subtle overlay (opacity 0.03–0.05) adds warmth
- **Dark mode by default** — premium SaaS/AI products default to dark
- **HSL-based design tokens** — enables programmatic opacity, not possible with hex

---

## Step 3 — Visual System Planning

Define the complete visual identity before building.

### Typography

Pick 2 fonts maximum (1 display, 1 body). Use `clamp()` for fluid sizing.

Strong 2025 pairings:
- **Geist Sans + Geist Mono** — developer-grade, Vercel-quality
- **Inter + Inter** — most versatile, Swiss-style
- **Cal Sans + Inter** — modern SaaS
- **Space Grotesk + DM Sans** — tech/developer tools
- **Clash Display + Satoshi** — bold, creative, startup
- **General Sans + General Sans** — geometric, AI products

### Color Construction (Always HSL)

Build from a neutral scale + brand accent + semantic colors. For complete palettes, see `references/design-systems.md`.

### Spacing, Radius, Shadows

- **Spacing scale** (4px base): 4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 80, 96, 128
- **Radius**: sharp (2–4px) fintech/enterprise | soft (8–12px) SaaS | rounded (16–24px) consumer
- **Shadows**: 3 levels (card, dropdown, modal), tinted toward primary hue

---

## Step 4 — Layout Architecture

### Landing Page Architecture

```
Navigation (logo + links + CTA)
Hero (headline + subhead + CTA + visual/video)
Social Proof (logo marquee, stats, "Trusted by X+ teams")
Why / About (2-3 crisp value prop sentences)
Features (bento grid or numbered cards)
How It Works (numbered steps)
Product Demo / Screenshots
Testimonials / Case Studies
Pricing (2-3 tier liquid-glass cards)
Final CTA (headline + button + gradient bg)
Footer
```

### Dashboard Architecture

```
Top Nav (search, notifications, avatar)
Sidebar (icon + label, section groups, collapsible)
Main Content:
  Summary Cards (metrics + sparklines)
  Primary View (charts, tables, data feeds)
  Secondary Panels (filters, logs, details)
```

---

## Step 5 — UI Component System

```
components/
├── layout/    → Navbar, Footer, Sidebar, Container
├── ui/        → Button, Card, LiquidGlass, Badge, Input, Modal, Toggle
├── sections/  → Hero, Features, Pricing, Testimonials, CTA, HowItWorks
├── motion/    → FadeIn, StaggerGroup, ScrollReveal, ParallaxLayer
└── data/      → DataTable, MetricCard, Chart, StatCard
```

### Liquid Glass (Standard in v2.0)

Use for: navbar, pricing cards, feature cards, modals, eyebrow badges.

```css
.liquid-glass {
  background: linear-gradient(
    135deg,
    rgba(255, 255, 255, 0.08) 0%,
    rgba(255, 255, 255, 0.02) 100%
  );
  backdrop-filter: blur(20px) saturate(180%);
  -webkit-backdrop-filter: blur(20px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.12);
  box-shadow:
    inset 0 1px 0 rgba(255, 255, 255, 0.15),
    inset 0 -1px 0 rgba(0, 0, 0, 0.10),
    0 8px 32px rgba(0, 0, 0, 0.30),
    0 0 0 1px rgba(255, 255, 255, 0.04);
  border-radius: var(--radius);
}
.liquid-glass:hover {
  background: linear-gradient(
    135deg,
    rgba(255, 255, 255, 0.12) 0%,
    rgba(255, 255, 255, 0.04) 100%
  );
  border-color: rgba(255, 255, 255, 0.18);
  box-shadow:
    inset 0 1px 0 rgba(255, 255, 255, 0.20),
    0 12px 40px rgba(0, 0, 0, 0.35),
    0 0 0 1px rgba(255, 255, 255, 0.06);
  transition: all var(--dur-base) var(--ease-out);
}
```

Tailwind shorthand:
```html
<div class="bg-white/5 backdrop-blur-2xl saturate-150
            border border-white/10 rounded-2xl
            shadow-[inset_0_1px_0_rgba(255,255,255,0.15),0_8px_32px_rgba(0,0,0,0.3)]">
```

### Component Quality Standards

- All colors via `hsl(var(--token))` — zero hardcoded hex in components
- Variant-driven props: `<Button variant="primary" size="lg">` not separate files
- Liquid glass on all floating surfaces
- Hover/focus states on every interactive element

---

## Step 6 — Motion & Interaction Design

Motion is first-class. Specify every animation with 4 values: property, duration, easing, delay.

### Animation Spec Format

```
Eyebrow badge:  opacity+translateY(8px→0),  400ms, ease-out-expo, delay 100ms
Headline:       opacity+translateY(16px→0), 500ms, ease-out-expo, delay 200ms
Subtext:        opacity,                    400ms, ease-out,      delay 350ms
CTA row:        opacity+translateY(8px→0),  400ms, ease-out-expo, delay 450ms
```

### Video Background Pattern

```jsx
<section className="relative min-h-screen overflow-hidden">
  <video autoPlay muted loop playsInline
    className="absolute inset-0 w-full h-full object-cover" src="/hero.mp4" />
  <div className="absolute inset-0 bg-gradient-to-b
                  from-background/80 via-transparent to-background" />
  <div className="relative z-10 flex flex-col items-center justify-center
                  min-h-screen px-4 pt-20">
    {/* hero content */}
  </div>
</section>
```

### Logo Marquee Pattern (Pure CSS)

```jsx
<div className="overflow-hidden">
  <div className="flex animate-marquee gap-12 whitespace-nowrap">
    {[...logos, ...logos].map((logo, i) => (
      <div key={i} className="liquid-glass flex items-center gap-2
                               px-4 py-2 rounded-full shrink-0
                               text-foreground/50 text-sm font-medium">
        {logo.name}
      </div>
    ))}
  </div>
</div>
```

```css
@keyframes marquee {
  from { transform: translateX(0); }
  to   { transform: translateX(-50%); }
}
.animate-marquee { animation: marquee 20s linear infinite; }
```

### Animation Rules

- **GPU-only**: `transform` + `opacity` — never animate `height`, `width`, `top`, `left`
- **Respect `prefers-reduced-motion`**: wrap all animations in `@media (prefers-reduced-motion: no-preference)`
- **Duration budget**: micro-interactions 100–200ms | reveals 300–500ms | page transitions 400–600ms
- **Stagger**: 60–80ms per item in grids/lists
- **Max concurrent**: 3 animations visible at once — more is chaos

### Libraries

| Library | Use When |
|---------|---------|
| Framer Motion | React — declarative, page transitions, layout animations |
| Motion One | Lightweight — Web Animations API wrapper |
| GSAP | Complex scroll timelines, SVG animation |
| CSS only | Simple hovers, state transitions |

---

## Step 7 — Technology Stack

| Layer | Recommended | Why |
|-------|------------|-----|
| Framework | React / Next.js | Component model, SSR/RSC, ecosystem |
| Styling | Tailwind CSS + CSS tokens | Rapid + systematic |
| Components | shadcn/ui + Radix UI | Accessible, unstyled, themeable |
| Animation | Framer Motion | Declarative, performant |
| Language | TypeScript | Type safety, self-documenting |
| Icons | Lucide React | Clean, consistent |
| Fonts | Geist / Inter | System-level performance |

Respect user stack choices — design principles are tool-agnostic.

```
/app or /pages   → routes, page components
/components      → layout/, ui/, sections/, motion/, data/
/styles          → global.css (tokens in :root), tailwind.config
/utils           → helpers, constants, types
/public          → static assets, fonts, videos
```

---

## Step 8 — Backend Awareness

- **Loading states**: skeleton loaders, not spinners
- **Error states**: meaningful message + retry action
- **Empty states**: friendly copy + CTA
- **Form validation**: inline errors on blur/submit
- **Dynamic content**: props/API-driven, zero hard-coded strings
- **Optimistic UI**: update immediately, roll back gracefully
- **Realistic mock data**: real-sounding names, plausible numbers, proper-length text

---

## Step 9 — Responsive System

| Token | Width | Target |
|-------|-------|--------|
| `sm` | 640px | Large phones |
| `md` | 768px | Tablets |
| `lg` | 1024px | Small laptops |
| `xl` | 1280px | Desktops |
| `2xl` | 1536px | Large displays |

**Responsive rules:**
- Grids: 4 → 2 → 1 cols
- Nav: full → hamburger below 768px
- Display type: `clamp(2rem, 1rem + 4vw, 5rem)`
- Touch targets: ≥ 44×44px
- Section padding: 128px → 80px → 48px
- Max content width: 1200–1440px, 16px (mobile) → 48px (desktop) side padding

---

## Step 10 — Visual Quality Validation

**Token Integrity**
- [ ] Zero hardcoded hex values in components — all `hsl(var(--token))`
- [ ] All radii via `--radius-*` tokens
- [ ] All transitions via `--dur-*` and `--ease-*` tokens

**Typography**
- [ ] Hierarchy: display > h1 > h2 > body — clearly distinct
- [ ] Negative letter-spacing on all headings
- [ ] Body: 16–18px, 1.5–1.7 line-height, max 65ch wide

**Spacing**
- [ ] All values from spacing scale
- [ ] Sections: 80–128px vertical padding desktop
- [ ] Nothing cramped

**Color & Polish**
- [ ] Primary color used sparingly (CTAs + key accents only)
- [ ] Contrast: 4.5:1 body, 3:1 large text
- [ ] Liquid glass on all floating surfaces
- [ ] Tinted shadows (never pure rgba black)
- [ ] Gradients: subtle and purposeful

**Motion**
- [ ] GPU-only animations
- [ ] `prefers-reduced-motion` respected
- [ ] No more than 3 concurrent animations visible

**Overall**
- [ ] Looks premium, not generic
- [ ] Matches Linear / Vercel / Stripe quality tier
- [ ] Design serves this specific niche
- [ ] Trust-worthy on first 50ms impression

---

## Step 11 — Hero Prompt Engineering (MotionSites Style)

When building hero sections, use **pixel-precise prompt specs**. This dramatically improves output quality by eliminating ambiguity.

A premium hero prompt specifies: design system tokens, component anatomy, animation spec, and stack.

### Complete Hero Prompt Template

```
Build a [NICHE] hero section.
Stack: React + Vite + Tailwind CSS

────────────────────────────────────────
DESIGN SYSTEM — add to index.css :root
────────────────────────────────────────
--background:      [H S% L%]
--surface:         [H S% L%]
--foreground:      [H S% L%]
--foreground-muted:[H S% L%]
--primary:         [H S% L%]
--font-sans:       '[Font]', sans-serif
--radius:          [X]px
--dur-base:        250ms
--ease-out:        cubic-bezier(0.22, 1, 0.36, 1)

────────────────────────────────────────
LIQUID GLASS UTILITY — add to index.css
────────────────────────────────────────
.liquid-glass {
  background: linear-gradient(135deg, rgba(255,255,255,0.08), rgba(255,255,255,0.02));
  backdrop-filter: blur(20px) saturate(180%);
  border: 1px solid rgba(255,255,255,0.12);
  box-shadow: inset 0 1px 0 rgba(255,255,255,0.15), 0 8px 32px rgba(0,0,0,0.3);
  border-radius: var(--radius);
}

────────────────────────────────────────
NAVBAR
────────────────────────────────────────
Position: fixed top-0 z-50 w-full
Style: liquid-glass px-6 py-4
Left: Logo (liquid-glass icon + brand name font-semibold)
Center: nav links text-foreground/70 text-sm gap-8
Right: CTA button rounded-full px-4 py-2 text-sm primary variant
Divider: h-px bg-gradient-to-r from-transparent via-foreground/20 to-transparent

────────────────────────────────────────
HERO SECTION
────────────────────────────────────────
Layout: relative min-h-screen overflow-hidden
Background: [video path OR gradient description]
Overlay: absolute inset-0 bg-gradient-to-b from-background/80 via-transparent to-background
Content: z-10 flex-col items-center justify-center min-h-screen px-4 pt-20

Elements (top to bottom):
1. Eyebrow badge
   - Style: liquid-glass rounded-full px-4 py-1.5 inline-flex items-center gap-2
   - Animated dot: w-2 h-2 rounded-full bg-primary animate-pulse
   - Text: "[product tagline]" text-foreground/70 text-sm font-medium

2. Headline
   - Size: text-[80px] sm:text-[100px] lg:text-[120px]
   - Weight: font-bold, tracking-[-0.04em], leading-[0.95]
   - Treatment: gradient-text (linear-gradient 135deg primary→secondary)
   - Content: "[POWERFUL SHORT HEADLINE]"

3. Subheadline
   - max-w-lg text-center text-foreground/70 text-lg leading-8 mt-6

4. CTA row
   - gap-3 mt-8 flex items-center
   - Primary: bg primary, rounded-full px-6 py-3, glow box-shadow
   - Ghost: border border-foreground/20, rounded-full px-6 py-3

5. Visual spacer: h-40 (video breathing room)

────────────────────────────────────────
LOGO MARQUEE
────────────────────────────────────────
overflow-hidden, animate-marquee 20s linear infinite
Brands (liquid-glass pills): [Brand1], [Brand2], [Brand3], [Brand4], [Brand5]
Left label: "Trusted by teams across [industry]" text-foreground/40 text-sm

────────────────────────────────────────
ANIMATIONS (all use ease-out-expo)
────────────────────────────────────────
Navbar:        fade-in 400ms delay-0ms
Eyebrow:       fade-in + translateY(8px→0)  400ms delay-100ms
Headline:      fade-in + translateY(16px→0) 500ms delay-200ms
Subheadline:   fade-in                      400ms delay-350ms
CTA row:       fade-in + translateY(8px→0)  400ms delay-450ms

────────────────────────────────────────
ANTI-SLOP RULES
────────────────────────────────────────
- No Bootstrap. No generic box-shadows. No rainbow colors.
- All colors via hsl(var(--token)) — zero hardcoded hex in components
- Real-sounding fictional brands: Vortex, Nimbus, Kynder, Halcyn, Aethon
- Purposeful motion only — Awwwards-caliber, not showy
- Liquid glass on every floating surface
```

See `references/hero-prompts.md` for 6 ready-to-use templates across niches.

---

## Step 12 — Final Automated Testing & Error Resolution (MANDATORY)

**Non-negotiable. Fix every issue before declaring the task done.**

### 12.1 — Build Verification

```bash
npm install
npx tsc --noEmit
npm run build
```

### 12.2 — Lint

```bash
npx next lint
npx tsc --noEmit --noUnusedLocals --noUnusedParameters 2>&1 || true
```

### 12.3 — Runtime Smoke Test

```bash
npm run dev &
sleep 5
curl -s -o /dev/null -w "%{http_code}" http://localhost:3000
kill %1 2>/dev/null || true
```

### 12.4 — Component Error Scan

| Check | Fix |
|-------|-----|
| Import from non-existent files | Fix import paths |
| Missing `key` in `.map()` | Add unique key prop |
| `window`/`document` in SSR | Wrap in `useEffect` |
| `<img>` instead of Next `<Image>` | Replace with `<Image>` |
| Missing `alt` text | Add descriptive alt |
| Hard-coded hex in component | Replace with `hsl(var(--token))` |

### 12.5 — Done Checklist

- [ ] `npm run build` exits 0
- [ ] `npx next lint` passes
- [ ] `npm run dev` boots without crash
- [ ] `npx tsc --noEmit` passes
- [ ] All pages render, no console errors
- [ ] No hydration mismatch warnings
- [ ] Mobile: no horizontal overflow
- [ ] All colors from HSL token system

> **Rule: If you generated the code, you own the errors. Fix them before finishing.**

---

## Final Output Requirements

Deliver:
- **CSS token system** — complete `:root` variables, HSL values, defined before any component
- **Liquid glass utility class** — in global CSS, consumed throughout
- **Modern premium UI** — the kind that makes people say "this looks expensive"
- **Modular component architecture** — prop-driven, typed, token-aware
- **Purposeful motion** — scroll reveals, hovers, staggered entrances specified per element
- **Fully responsive** — mobile, tablet, desktop
- **Realistic content** — believable copy, plausible data (never lorem ipsum)

Include brief summary: token palette rationale, typography choice, layout strategy, motion decisions.

---

## Anti-Patterns — What to Avoid

| Anti-Pattern | What Goes Wrong | Fix |
|-------------|----------------|-----|
| **Raw hex in components** | Design system breaks | `hsl(var(--primary))` everywhere |
| **Rainbow soup** | Too many unrelated colors | Primary + neutral + 1–2 accents max |
| **Wall of cards** | Identical grid, no hierarchy | Bento layout, vary sizes |
| **Giant hero, empty page** | Massive hero, thin content | Maintain section weight proportion |
| **Button overload** | Multiple competing CTAs | One primary + one secondary per section |
| **Fake depth** | Shadows everywhere | Liquid glass on surfaces, purposeful depth |
| **Inconsistent radius** | Sharp + rounded mixed | One radius language, all via tokens |
| **Bootstrap syndrome** | Template look, swapped colors | Build from token system |
| **Typography neglect** | Same weight/size all elements | Display → h1 → h2 → body hierarchy |
| **Spacing chaos** | Random margins | Every value from spacing scale |
| **Motionless UI** | No feedback, no life | Hover states, scroll reveals, stagger |
| **Animation overload** | Everything moving at once | Max 3 concurrent animations |
| **Lorem ipsum** | Unjudgeable design | Write realistic product copy |
| **Flat glassmorphism** | Dated, 2021-era look | Upgrade to liquid glass |

### The "Premium or Redo" Test

1. **Screenshot test** — Next to Linear.app or Vercel.com. Does yours belong?
2. **Squint test** — Hierarchy visible? Important elements dominant?
3. **3-second test** — Product clear? CTA obvious?
4. **Token test** — DevTools open. All colors HSL variables? No hardcoded hex? ✓

If any is "no" — redesign before delivery.

---

### Cross-Agent Compatibility

| Agent | Installation |
|-------|-------------|
| Claude Code | `npx skills add deveshpunjabi/modern-frontend-skill` |
| Cursor | Copy to `.cursor/skills/` |
| Windsurf | Copy to `.windsurf/skills/` |
| Cline | Copy to `.cline/skills/` |
| Codex | Copy to `.codex/skills/` |
| Aider | Reference in `.aider.conf` |
| Any | Copy SKILL.md to agent skill directory |
