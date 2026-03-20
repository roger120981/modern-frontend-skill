# Modern Frontend Skill

A skill for coding agents that transforms vague UI requests into polished,
production-quality frontends. Instead of generating generic Bootstrap-looking
layouts, the agent thinks like a senior designer **and** a MotionSites-level prompt engineer
— planning a complete token system, building Liquid Glass components, and
specifying every animation with pixel-precise detail.

## What's New in v2.0

| Feature | v1.0 | v2.0 |
|---------|------|------|
| Design system | Optional | **Mandatory CSS :root tokens (Step 0)** |
| Color format | Hex values | **HSL tokens (opacity manipulation)** |
| Glass effect | Glassmorphism | **Liquid Glass (inner glow, multi-layer)** |
| Hero patterns | Generic | **4 cinematic patterns (video, mesh, bento, oversized type)** |
| Animation spec | General guidance | **Per-element: property + duration + easing + delay** |
| Prompt templates | None | **6 MotionSites-quality hero prompt templates** |
| Eval cases | 5 cases, 66 assertions | **7 cases, 135 assertions** |
| Steps | 11-step process | **12-step process (Step 0 = tokens first)** |

## How It Works

When you ask your coding agent to "build me a landing page" or "create a dashboard", the skill
automatically kicks in. It follows a **12-step Atom of Thought Design Process**:

0. **Design Token System** — defines complete `:root` CSS variables (HSL format) before any component
1. **Understand the Product** — extracts type, audience, value prop, conversion goal
2. **Visual Inspiration** — references cinematic hero patterns and 2025–2026 trends
3. **Visual System Planning** — typography pairings, HSL palette, spacing scale, radius language
4. **Layout Architecture** — section hierarchy mapped before coding
5. **UI Component System** — modular, prop-driven, liquid-glass-aware components
6. **Motion & Interaction Design** — per-element animation specs with easing curves
7. **Technology Stack** — right tools for the project
8. **Backend Awareness** — loading, error, empty states; realistic data
9. **Responsive System** — pixel-perfect at 375px, 768px, and 1440px
10. **Visual Quality Validation** — checklist including token compliance audit
11. **Hero Prompt Engineering** — MotionSites-style precise prompt spec output
12. **Final Testing** — build verification, lint, runtime smoke test, component scan

## What's Inside

### Core Skill
- **SKILL.md** — 698-line, 12-step process with full liquid glass recipes, HSL token system,
  cinematic hero patterns, and hero prompt engineering guide

### Design References
- **references/design-systems.md** — 978-line reference: typography, palettes, gradients, liquid glass,
  HSL tokens, logo marquee implementation, video hero implementation, animation patterns
- **references/hero-prompts.md** *(new)* — 6 production-ready MotionSites-style hero prompt templates:
  1. AI SaaS (dark, indigo/purple, video background)
  2. Developer Tool (dark, green terminal, code block)
  3. Fintech (light, professional blue, dashboard mockup)
  4. Creative Agency (warm dark, editorial typography)
  5. Wellness App (soft light, phone mockup, blob background)
  6. SaaS Pricing Page (dark, interactive monthly/yearly toggle)

### Evaluations
- **evals/evals.json** — 7 test cases, 135 total assertions covering:
  token compliance, liquid glass, hero patterns, motion spec, niche-specific design

## Niche-Aware Design Table

| Niche | Design Direction |
|-------|-----------------|
| AI / ML tools | Dark, glowing indigo/purple accents, video or mesh hero |
| Developer tools | Dark green terminal aesthetic, monospace, code blocks |
| Fintech | Light, professional blue, trust-heavy, two-column hero |
| Cybersecurity | Dark, terminal-style, alert-driven, status indicators |
| Creative agencies | Warm dark, editorial typography, grain texture, Awwwards-level |
| SaaS dashboards | Sidebar nav, metric cards, neutral palette, token-compliant |
| E-commerce | Product grids, prominent CTAs, light mode, trust badges |
| Social platforms | Vibrant, rounded, avatar-centric, card feeds |
| Health / Wellness | Soft light, sage palette, phone mockup, blob backgrounds |
| Education | Structured, friendly, progress indicators, accessible |
| Startups / Landing | Hero-driven, social proof, bento features, pricing |
| Consulting / B2B | Authority-driven, dark premium, numbered value props |

## Anti-Patterns Prevented

| Anti-Pattern | Fix |
|-------------|-----|
| Hardcoded hex in components | All `hsl(var(--token))` — zero exceptions |
| Flat glassmorphism (2021-era) | Liquid Glass: inner glow, multi-layer blur |
| Rainbow soup | Primary + neutral + 1-2 accents maximum |
| Wall of cards | Bento layout, varied sizes, visual weight |
| Generic Bootstrap look | Design from the token system up |
| Vague animations | Per-element: property + duration + easing + delay |
| Lorem ipsum | Realistic product copy, always |
| Typography neglect | Display → h1 → h2 → body hierarchy enforced |

## Project Structure

```
modern-frontend-skill/
├── skills/
│   └── modern-frontend-design/
│       ├── SKILL.md                          # 12-step process, 698 lines
│       ├── references/
│       │   ├── design-systems.md             # 978-line reference guide
│       │   └── hero-prompts.md               # 6 MotionSites-style templates
│       └── evals/
│           └── evals.json                    # 7 test cases, 135 assertions
├── examples/
│   ├── README.md
│   ├── landing-page.json
│   ├── dashboard.json
│   ├── ai-support-landing.json
│   └── pricing-page.json
├── scripts/
│   ├── validate_skill.py
│   └── run_evals.py
├── tests/
│   ├── test_validate_skill.py
│   └── test_evals.py
├── docs/
│   └── SKILL-GUIDE.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Installation

### Claude Code

```
npx skills add deveshpunjabi/modern-frontend-skill
```

### Cursor

Copy the `skills/modern-frontend-design/` folder into your project's `.cursor/skills/` directory.

### Windsurf / Cline / Codex

Copy the `skills/modern-frontend-design/` folder into the equivalent skills directory.

### Aider

```yaml
# .aider.conf
read: path/to/skills/modern-frontend-design/SKILL.md
```

### Any Agent

Copy `skills/modern-frontend-design/SKILL.md` into your agent's skill/instruction directory.
Optionally include `references/` for deeper reference material.

### Verify It Works

Start a new session and ask:

> "Build me a cinematic landing page for my AI startup 'Nimbus'. Dark theme, video background hero, indigo/purple palette."

The agent should: define `:root` HSL tokens → implement liquid glass utility → build the hero with video background + animated marquee → specify per-element animation timing → validate token compliance before finishing.

## Test Cases

| # | Scenario | Stack | Key Checks |
|---|---------|-------|-----------|
| 1 | AI SaaS landing (Lumina) | React + Framer | Tokens, video hero, liquid glass, marquee, gradient text |
| 2 | Dev tool hero (Axiom) | React + Tailwind | Terminal aesthetic, code block, green primary, monospace |
| 3 | Fintech landing (Clearpath) | Next.js | Light mode, two-column, dashboard card, trust signals |
| 4 | Wellness app (Bloom) | React + Framer | Soft palette, phone mockup, blobs, warm copy |
| 5 | SaaS pricing page (Forma AI) | React | Toggle animation, liquid glass cards, FAQ accordion |
| 6 | Creative agency (Forma Studio) | React | Editorial type, warm dark, grain texture, Awwwards-level |
| 7 | Dashboard homepage | Next.js | Full token audit, sidebar, charts, loading states |

7 test cases · 135 total assertions

## Philosophy

- **Tokens-first** — design system defined before any component code
- **HSL over hex** — enables opacity manipulation; `hsl(var(--primary) / 0.15)` is the norm
- **Liquid Glass** — the standard floating surface treatment in 2025+
- **Motion as material** — per-element animation specs, not vague "add animations"
- **Cinematic heroes** — video backgrounds, oversized type, logo marquees are first-class
- **Niche-aware** — every industry has visual conventions; violating them breaks trust
- **Prompt engineering** — the skill teaches agents to output MotionSites-quality prompt specs
- **Framework-agnostic** — the thinking matters more than the tools
- **Backend-ready** — loading states, error handling, real data integration

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

1. Fork the repository
2. Create a branch for your changes
3. Follow the token-first patterns in the existing skill
4. Run `python -m pytest tests/ -v` to verify
5. Submit a PR

## License

MIT — see [LICENSE](LICENSE)
