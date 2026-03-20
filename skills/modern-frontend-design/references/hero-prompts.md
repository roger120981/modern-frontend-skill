# Hero Prompt Templates — v2.0

Six production-ready, MotionSites-style hero prompt templates.
Each is pixel-precise: tokens, component anatomy, animation spec, stack all defined upfront.
Copy, fill the bracketed values, and hand to any AI coding agent.

---

## Template 1 — AI SaaS (Dark, Indigo/Purple, Video Background)

**Best for**: AI writing tools, ML platforms, automation SaaS, LLM products

```
Build a cinematic AI SaaS hero section.
Stack: React + Vite + Tailwind CSS + Framer Motion

────────── DESIGN SYSTEM (:root in index.css) ──────────
--background:       260 87%  3%;
--surface:          240  6%  9%;
--foreground:        40  6% 95%;
--foreground-muted: 240  5% 65%;
--primary:          262 83% 58%;
--primary-hover:    262 83% 65%;
--border:           240  4% 18%;
--font-sans:        'Geist Sans', 'Inter', sans-serif;
--font-display:     'Cabinet Grotesk', sans-serif;
--radius:           0.75rem;
--dur-base:         250ms;
--ease-out:         cubic-bezier(0.22, 1, 0.36, 1);

────────── LIQUID GLASS UTILITY (index.css) ──────────
.liquid-glass {
  background: linear-gradient(135deg, rgba(255,255,255,0.08), rgba(255,255,255,0.02));
  backdrop-filter: blur(20px) saturate(180%);
  -webkit-backdrop-filter: blur(20px) saturate(180%);
  border: 1px solid rgba(255,255,255,0.12);
  box-shadow:
    inset 0 1px 0 rgba(255,255,255,0.15),
    0 8px 32px rgba(0,0,0,0.3),
    0 0 0 1px rgba(255,255,255,0.04);
  border-radius: var(--radius);
}

────────── FONTS ──────────
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');
Use Cabinet Grotesk from Fontshare for headlines if available, else Inter 800.

────────── GRAIN TEXTURE (index.css) ──────────
.grain::after {
  content: '';
  position: fixed;
  inset: 0;
  pointer-events: none;
  z-index: 100;
  opacity: 0.035;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)'/%3E%3C/svg%3E");
}

────────── NAVBAR ──────────
Position: fixed top-0 z-50 w-full
Style: liquid-glass px-6 py-4 flex items-center justify-between
Left: liquid-glass icon (indigo gradient square, 8×8, rounded-lg) + "Lumina" font-semibold text-foreground
Center: ["Features", "Pricing", "Changelog", "Docs"] text-foreground/60 text-sm gap-8 hidden md:flex
Right: ["Sign In" ghost text-sm] + ["Start free" primary button rounded-full px-4 py-2 text-sm
       bg-primary hover:bg-primary-hover glow-box-shadow]
Border-bottom: h-px bg-gradient-to-r from-transparent via-foreground/15 to-transparent

────────── HERO SECTION ──────────
Layout: relative min-h-screen flex flex-col overflow-hidden grain
Background: radial-gradient(ellipse at 50% 0%, hsl(var(--primary)/0.15) 0%, transparent 60%),
            radial-gradient(ellipse at 80% 80%, hsl(262 83% 45%/0.06) 0%, transparent 50%),
            hsl(var(--background))
Dot grid overlay: radial-gradient(circle, rgba(255,255,255,0.08) 1px, transparent 1px)
                  background-size: 32px 32px, opacity-30

Content: flex-1 flex flex-col items-center justify-center px-4 pt-24 pb-16 text-center

Elements:
1. EYEBROW BADGE (Framer: fade-in + y 8→0, 400ms, delay 0ms)
   liquid-glass rounded-full px-4 py-1.5 inline-flex items-center gap-2 mb-8
   Left: animated dot w-2 h-2 rounded-full bg-emerald-400 animate-pulse
   Text: "Introducing Lumina 2.0" text-foreground/70 text-sm font-medium
   Right: "→" arrow text-foreground/40

2. HEADLINE (Framer: fade-in + y 20→0, 600ms ease-out-expo, delay 100ms)
   font-display font-bold tracking-[-0.04em] leading-[0.92]
   text-[clamp(3rem,1rem+6vw,7rem)]
   Line 1: "Write faster." text-foreground
   Line 2: "Think deeper." — gradient: linear-gradient(135deg, hsl(var(--primary)), #a855f7, #ec4899)
   Apply via: bg-clip-text text-transparent

3. SUBHEADLINE (Framer: fade-in, 400ms, delay 250ms)
   max-w-xl mt-6 text-foreground/65 text-lg leading-8

4. CTA ROW (Framer: fade-in + y 8→0, 400ms, delay 400ms)
   flex items-center gap-3 mt-10
   Primary: "Start writing free" rounded-full px-7 py-3.5 font-semibold text-sm
            bg: hsl(var(--primary)) hover:hsl(var(--primary-hover))
            box-shadow: 0 0 24px hsl(var(--primary-glow)/0.4), 0 0 48px hsl(var(--primary-glow)/0.15)
   Ghost: "Watch demo →" rounded-full px-7 py-3.5 text-sm
          border border-foreground/15 text-foreground/70 hover:border-foreground/30

5. SOCIAL PROOF (Framer: fade-in, 400ms, delay 550ms)
   flex items-center gap-3 mt-8
   Avatar stack: 5 overlapping circles w-8 h-8 rounded-full bg-gradient-to-br from-primary to-purple-600
   Text: "Loved by 40,000+ writers" text-foreground/50 text-sm
   Stars: 5× ★ text-amber-400 text-xs

6. VISUAL SPACER h-24

────────── LOGO MARQUEE ──────────
pt-8 pb-16 overflow-hidden
Left label: "Trusted by teams at" text-foreground/35 text-xs uppercase tracking-widest mr-8
Scroll track: flex animate-marquee gap-8 (duplicate brands for seamless loop)
Brands (liquid-glass pills): Vortex, Nimbus, Kynder, Halcyn, Aethon, Solace, Driftly, Covalent

@keyframes marquee { from { transform: translateX(0) } to { transform: translateX(-50%) } }
.animate-marquee { animation: marquee 24s linear infinite; }

────────── ANIMATIONS (Framer Motion) ──────────
const fadeUp = { hidden: {opacity:0, y:16}, visible: {opacity:1, y:0} }
Wrap hero content in <motion.div variants={stagger} initial="hidden" animate="visible">
  staggerChildren: 0.1s, delayChildren: 0s
Each child: <motion.div variants={fadeUp} transition={{duration:0.5, ease:[0.22,1,0.36,1]}}>

────────── ANTI-SLOP ──────────
Zero hardcoded hex. All colors hsl(var(--token)).
Liquid glass on navbar + eyebrow + logo pills.
Fictional but believable brand names only.
Grain overlay for warmth.
```

---

## Template 2 — Developer Tool (Dark, Green Terminal Aesthetic)

**Best for**: CLIs, APIs, code editors, DevOps platforms, observability tools

```
Build a developer tool hero section.
Stack: React + Vite + Tailwind CSS

────────── DESIGN SYSTEM ──────────
--background:       220 40%  4%;
--surface:          220 20%  8%;
--foreground:        90  5% 95%;
--foreground-muted: 220 10% 60%;
--primary:          142 76% 45%;   /* terminal green */
--primary-dim:      142 76% 36%;
--border:           220 15% 15%;
--font-sans:        'JetBrains Mono', 'Fira Code', monospace;
--font-ui:          'Inter', sans-serif;
--radius:           0.5rem;        /* sharper for dev tools */

────────── LIQUID GLASS (darker tint) ──────────
.liquid-glass {
  background: linear-gradient(135deg, rgba(255,255,255,0.05), rgba(255,255,255,0.01));
  backdrop-filter: blur(16px);
  border: 1px solid rgba(255,255,255,0.08);
  box-shadow: inset 0 1px 0 rgba(255,255,255,0.08), 0 4px 16px rgba(0,0,0,0.4);
  border-radius: var(--radius);
}

────────── NAVBAR ──────────
liquid-glass sticky top-0 z-50 px-6 py-3 flex items-center justify-between
Left: ">" text-primary font-mono mr-2 + "axiom" text-foreground font-mono font-bold
Center: ["Docs", "API", "Pricing", "Blog"] font-mono text-sm text-foreground/55 gap-8
Right: ["$ npm install axiom" liquid-glass pill font-mono text-xs text-primary px-3 py-1.5]
       + ["Get started →" primary-colored text-sm font-mono]

────────── HERO ──────────
Background: hsl(var(--background))
Scanline overlay: repeating-linear-gradient(0deg, transparent, transparent 2px,
                  rgba(255,255,255,0.01) 2px, rgba(255,255,255,0.01) 4px)
Radial glow: radial-gradient(ellipse at 50% 40%, hsl(var(--primary)/0.06) 0%, transparent 60%)

Content: flex flex-col items-center justify-center min-h-screen px-4 pt-20 text-center

Elements:
1. Terminal badge: liquid-glass rounded px-3 py-1 font-mono text-xs text-primary
   "$ v3.0.0 now available ↗"

2. HEADLINE: font-mono font-bold tracking-tight text-[clamp(2.5rem,5vw,5.5rem)] leading-[1.05]
   "Ship observability." line-break "Not complexity."
   "observability" — text-primary (no gradient, clean terminal green)

3. SUBHEAD: font-ui text-foreground/60 text-lg max-w-lg leading-8 mt-6

4. TERMINAL BLOCK (signature feature):
   liquid-glass rounded-lg p-4 font-mono text-sm text-left max-w-lg w-full mt-8
   Title bar: 3 dots (red, amber, green) + "~/project" text-foreground/30 text-xs text-center
   Lines with typing animation:
     $ npm install @axiom/sdk     ← text-foreground/70
     ✓ Installed in 0.4s          ← text-primary
     $ axiom init                 ← text-foreground/70
     ✓ Connected to Axiom Cloud   ← text-primary animate-blink-cursor

5. CTA row: "Start for free" primary + "Read the docs →" ghost, font-mono text-sm

────────── LOGO MARQUEE ──────────
Brands: Supabase, PlanetScale, Railway, Render, Fly, Neon, Turso, Upstash
Each: liquid-glass rounded px-3 py-1.5 font-mono text-xs text-foreground/50

────────── ANIMATIONS ──────────
Terminal lines: reveal one by one, 400ms stagger, cursor blink on last line
Hero elements: standard fade-up, 400ms ease-out-expo, 100ms stagger
```

---

## Template 3 — Fintech (Light, Professional Blue, Trust-Heavy)

**Best for**: payment platforms, banking apps, expense tools, investment SaaS

```
Build a fintech/financial SaaS hero section.
Stack: Next.js 14 + Tailwind CSS

────────── DESIGN SYSTEM ──────────
--background:       220 20% 98%;
--surface:            0  0% 100%;
--foreground:       220 40% 10%;
--foreground-muted: 220 15% 50%;
--primary:          217 91% 45%;   /* professional blue */
--primary-hover:    217 91% 38%;
--accent-green:     142 76% 36%;   /* positive delta */
--accent-red:         0 84% 55%;   /* negative delta */
--border:           220 13% 91%;
--font-sans:        'Inter', system-ui, sans-serif;
--radius:           0.625rem;

────────── GLASS (light mode) ──────────
.liquid-glass {
  background: rgba(255, 255, 255, 0.80);
  backdrop-filter: blur(20px) saturate(180%);
  border: 1px solid rgba(0, 0, 0, 0.08);
  box-shadow: 0 1px 3px rgba(0,0,0,0.06), 0 8px 24px rgba(0,0,0,0.04);
  border-radius: var(--radius);
}

────────── NAVBAR ──────────
liquid-glass border-b border-black/6 fixed top-0 z-50 w-full px-6 py-4
Left: blue square icon (bg-primary) + "Clearpath" font-semibold text-foreground
Center: ["Product", "Security", "Pricing", "Enterprise"] text-foreground/65 text-sm gap-8
Right: ["Log in" text-sm text-foreground/70] + ["Request demo" primary btn px-4 py-2 rounded-lg text-sm]

────────── HERO ──────────
Background: hsl(var(--background))
Subtle dot grid: radial-gradient(circle, hsl(var(--primary)/0.1) 1px, transparent 1px) 24px 24px
Radial highlight: radial-gradient(ellipse at 60% 50%, hsl(var(--primary)/0.05) 0%, transparent 70%)

Content: two-column layout (left: text, right: floating dashboard card)
Left (text):
  1. Trust badge: liquid-glass rounded-full px-3 py-1 inline-flex items-center gap-2 mb-6
     "SOC 2 Type II Certified" — shield icon text-primary + text text-foreground/70 text-sm

  2. Headline: text-[clamp(2.5rem,4vw,4rem)] font-bold text-foreground tracking-tight leading-[1.1]
     "Financial infrastructure for modern teams."
     No gradient — professional, clean, trustworthy

  3. Subhead: text-foreground/60 text-lg leading-8 max-w-md mt-4

  4. CTA row:
     Primary: "Get started" bg-primary text-white rounded-lg px-6 py-3 font-semibold
     Secondary: "Talk to sales →" text-primary text-sm font-medium

  5. Trust row: flex items-center gap-6 mt-10
     Items: "256-bit encryption", "99.99% uptime", "PCI DSS Level 1"
     Each: checkmark icon text-accent-green + label text-foreground/55 text-sm

Right (dashboard card):
  liquid-glass rounded-2xl p-6 shadow-2xl max-w-xs
  Balance: "$284,931.40" text-3xl font-bold text-foreground
  Delta: "+$12,430 (4.6%)" text-accent-green text-sm font-medium
  Mini sparkline SVG (5 points, smooth curve, stroke = primary, fill = primary/10)
  3 recent transactions (avatar + name + amount + category chip)

────────── LOGO BAR ──────────
"Trusted by finance teams at" — logos of fictional enterprises in grayscale:
Vantara, Meridian Group, Nexus Capital, Solvex, Arclight

────────── ANIMATIONS ──────────
Left content: stagger fade-up, 80ms intervals, 400ms duration
Dashboard card: fade-in + scale(0.97→1), 600ms ease-spring, delay 200ms
Balance counter: count-up animation from 0, 1200ms ease-out, delay 400ms
Sparkline: stroke-dasharray draw animation, 800ms ease-out, delay 600ms
```

---

## Template 4 — Creative Agency (Warm Dark, Bold Typography)

**Best for**: design studios, creative agencies, portfolios, photography, brand consultancies

```
Build a creative agency hero section.
Stack: React + Vite + Tailwind CSS + GSAP ScrollTrigger

────────── DESIGN SYSTEM ──────────
--background:        22 15%  6%;   /* warm near-black */
--surface:           22 12% 10%;
--foreground:        40  8% 95%;
--foreground-muted:  30  6% 65%;
--primary:           28 85% 55%;   /* warm copper/amber */
--primary-hover:     28 85% 62%;
--border:            22  8% 18%;
--font-display:      'Playfair Display', Georgia, serif;
--font-sans:         'Satoshi', 'Inter', sans-serif;
--radius:            0.5rem;

────────── LIQUID GLASS (warm tint) ──────────
.liquid-glass {
  background: linear-gradient(135deg, rgba(255,200,120,0.06), rgba(255,200,120,0.01));
  backdrop-filter: blur(20px) saturate(150%);
  border: 1px solid rgba(255,200,120,0.12);
  box-shadow: inset 0 1px 0 rgba(255,200,120,0.1), 0 8px 32px rgba(0,0,0,0.4);
  border-radius: var(--radius);
}

────────── NAVBAR ──────────
fixed top-0 z-50 w-full px-8 py-5 flex items-center justify-between
(transparent bg — no glass on scroll start)
Left: "FORMA" letter-spacing-[0.3em] text-xs font-semibold text-foreground/80
Right: ["Work", "Studio", "Journal"] text-foreground/55 text-sm gap-8
      + ["Let's talk →" border border-primary/30 text-primary rounded-full px-5 py-2 text-sm]

────────── HERO ──────────
Layout: min-h-screen flex flex-col px-8 pt-32 pb-16
Background: hsl(var(--background))
Radial glow: radial-gradient(ellipse at 20% 80%, hsl(var(--primary)/0.08) 0%, transparent 50%)
Grain: subtle SVG grain overlay opacity-4

Top section:
  Row 1: "CREATIVE" font-display italic text-foreground/30 text-[clamp(4rem,10vw,10rem)]
          tracking-tight leading-none — LEFT aligned
  Row 2: "STUDIO" font-display font-bold text-foreground text-[clamp(4rem,10vw,10rem)]
          tracking-[-0.03em] leading-none — with inline image (portrait crop, 80×120px rounded-lg)
  Row 3: "SINCE 2019" font-sans text-foreground/40 text-sm tracking-widest uppercase
         + right-aligned "40+ Projects Shipped" liquid-glass pill text-xs

Middle section (spacer with decorative element):
  Horizontal rule: h-px bg-gradient-to-r from-transparent via-foreground/20 to-transparent my-16
  Two-column: Left: "We design brands that people remember." font-sans text-foreground/70 text-lg max-w-xs leading-8
              Right: "scroll to explore ↓" text-foreground/40 text-xs uppercase tracking-widest

Bottom row:
  Services: ["Brand Identity", "Web Design", "Motion", "Art Direction"]
  Each: text-foreground/50 text-sm + "·" separator

────────── ANIMATIONS (GSAP) ──────────
On load: staggered character reveal on "CREATIVE" + "STUDIO" — each word fades + clips up
Scroll: inline image parallax (GSAP ScrollTrigger, y: 0→-40px)
Cursor: custom cursor (32px circle, mix-blend-mode: difference)
```

---

## Template 5 — Health / Wellness App (Soft Light, Calming)

**Best for**: mental health apps, fitness trackers, meditation platforms, nutrition tools

```
Build a health/wellness app hero section.
Stack: React + Vite + Tailwind CSS + Framer Motion

────────── DESIGN SYSTEM ──────────
--background:       160 30% 97%;
--surface:            0  0% 100%;
--foreground:       160 25% 15%;
--foreground-muted: 160 10% 55%;
--primary:          162 60% 42%;   /* sage green */
--primary-hover:    162 60% 35%;
--accent-warm:       28 80% 65%;   /* peach accent */
--border:           160 15% 88%;
--font-sans:        'Nunito Sans', 'DM Sans', sans-serif;
--font-display:     'Sora', 'Inter', sans-serif;
--radius:           1rem;          /* extra soft for wellness */

────────── GLASS (light/soft) ──────────
.liquid-glass {
  background: rgba(255, 255, 255, 0.75);
  backdrop-filter: blur(24px) saturate(160%);
  border: 1px solid rgba(0, 0, 0, 0.06);
  box-shadow: 0 2px 8px rgba(0,0,0,0.04), 0 16px 40px rgba(0,0,0,0.06);
  border-radius: var(--radius);
}

────────── HERO ──────────
Background: hsl(var(--background))
Blobs: two soft blurred circles (CSS radial-gradient, not actual blobs):
  blob-1: 600px circle at -10% 20%, hsl(var(--primary)/0.12)
  blob-2: 500px circle at 110% 70%, hsl(var(--accent-warm)/0.10)
Both: filter blur(80px), pointer-events-none, absolute

Content: two-column (left text, right phone mockup)

Left:
  1. Eyebrow: "🌿 Over 2M people sleeping better" liquid-glass rounded-full text-foreground/65 text-sm px-4 py-2

  2. Headline: font-display font-bold text-[clamp(2.5rem,4vw,3.75rem)] text-foreground leading-[1.15]
     "Sleep better." line break "Feel stronger." line break "Live lighter."
     "stronger" — text-primary

  3. Subhead: font-sans text-foreground/60 text-lg leading-8 max-w-md mt-5

  4. CTA row: "Start your free trial" primary rounded-full px-8 py-4 font-semibold
              "Already a member? Sign in" text-foreground/50 text-sm ml-4

  5. App store badges: App Store + Google Play liquid-glass pills

Right:
  Phone mockup: 375×750px rounded-[3rem] overflow-hidden border border-foreground/8
  liquid-glass shadow-2xl
  Screen: gradient bg, sleep score "92/100" in large font, ring/arc progress, "Tonight's plan" section

────────── LOGO BAR ──────────
"Featured in:" — Forbes, Women's Health, Wired, Product Hunt #1
All grayscale, small, tasteful

────────── ANIMATIONS ──────────
Blobs: slow float animation, 8s ease-in-out infinite alternate (translateY ±20px)
Phone: gentle bob, 4s ease-in-out infinite (translateY ±8px)
Score counter: count up to 92, 1000ms ease-out, delay 600ms
Stagger: all text elements, 80ms, fade-up
```

---

## Template 6 — SaaS Pricing Page (Dark, Interactive Toggle)

**Best for**: any SaaS product pricing page — works standalone or as a section

```
Build a SaaS pricing page/section.
Stack: React + Vite + Tailwind CSS

────────── DESIGN SYSTEM ──────────
--background:    240 10%  4%;
--surface:       240  6%  8%;
--surface-alt:   240  6% 11%;
--foreground:     40  5% 95%;
--foreground-muted: 240 5% 60%;
--primary:       262 83% 58%;
--accent:        162 60% 45%;   /* green for "Popular" badge */
--border:        240  4% 16%;
--font-sans:     'Inter', system-ui, sans-serif;
--radius:        0.875rem;

────────── SECTION HEADER ──────────
text-center mb-16
Eyebrow: "Pricing" liquid-glass pill text-foreground/60 text-xs uppercase tracking-widest mb-4
Headline: "Simple, transparent pricing." text-[clamp(2rem,4vw,3.5rem)] font-bold tracking-tight
Subhead: text-foreground/60 text-lg mt-4

TOGGLE (Monthly / Yearly):
  liquid-glass rounded-full p-1 inline-flex mt-8
  Two pills: whichever active = bg-primary text-white rounded-full px-5 py-2 text-sm font-medium
             inactive = text-foreground/50 text-sm px-5 py-2
  "Save 20%" amber badge on "Yearly" option

────────── PRICING CARDS (3-column grid) ──────────

Card 1 — Starter:
  liquid-glass rounded-2xl p-8
  Plan name: "Starter" text-foreground/80 font-medium
  Price: "$0" text-5xl font-bold text-foreground + "/mo" text-foreground/40 text-lg
  Description: text-foreground/55 text-sm mt-2
  Divider: h-px bg-border my-6
  Features (8 items): checkmark icon text-accent + label text-foreground/70 text-sm gap-3
  CTA: "Get started free" border border-border rounded-xl py-3 text-sm text-foreground/80
       hover: border-foreground/30

Card 2 — Pro (FEATURED):
  DIFFERENT STYLE — gradient border:
  div wrapper: p-px rounded-2xl bg-gradient-to-b from-primary/40 to-purple-600/20
  Inner: bg-surface-alt rounded-[calc(var(--radius-lg)-1px)] p-8
  "Most Popular" badge: top-right absolute, liquid-glass px-3 py-1 text-xs text-primary
  Price: animated (switch between monthly/yearly with Framer layout animation)
  Feature list: more items than Starter, includes "Everything in Starter +"
  CTA: "Start Pro trial" full bg-primary rounded-xl py-3 font-semibold
       glow: box-shadow 0 0 24px hsl(var(--primary)/0.4)

Card 3 — Enterprise:
  liquid-glass rounded-2xl p-8
  Price: "Custom" text-5xl font-bold
  CTA: "Talk to sales →" text-primary text-sm font-medium (no button bg)
  Features include: "Custom contracts", "Dedicated support", "SLA guarantee"

────────── TOGGLE ANIMATION ──────────
Monthly↔Yearly: price numbers animate with Framer layoutId
Annual savings: "Save $240/year" fades in below Pro price when Yearly selected

────────── FAQ (below cards) ──────────
Accordion: liquid-glass rounded-xl divide-y divide-border
8 questions, smooth height animation on expand/collapse
```

---

## How to Use These Templates

1. **Pick the template** that matches your product niche
2. **Fill in bracketed values** — product name, copy, brand names
3. **Paste into your AI coding agent** as the full prompt
4. **The agent receives**: design tokens, component anatomy, animation spec, anti-patterns — all in one message
5. **Result**: a MotionSites-quality hero on first generation, not after 10 iterations

## Customization Tips

- **Swap the font pairing** in `--font-sans` and `--font-display` — this alone changes the entire personality
- **Adjust the primary HSL** to match your brand — the liquid glass and glow effects auto-adapt via `hsl(var(--primary)/opacity)`
- **Change `--radius`** — lower for fintech (0.375rem), higher for wellness (1.25rem)
- **Remove the video** from Template 1 and replace with a gradient mesh if no video asset exists
- **Combine patterns** — e.g. Template 1 typography style + Template 3 two-column layout

## Fictional Brand Name Bank

Use these when the prompt needs believable company names:

**Tech/AI**: Vortex, Nimbus, Kynder, Halcyn, Aethon, Luminal, Zephyr, Quark, Vertex, Axiom
**Enterprise**: Meridian, Clearpath, Vantara, Solace, Arclight, Nexus, Solvex, Covalent, Altos
**Consumer**: Driftly, Bloom, Soften, Gentle, Luma, Sage, Still, Grove, Calm, Halo
**Finance**: Clearpath, Vantara, Nexus Capital, Arclight, Meridian Group, Pinnacle
