# Modern Frontend Design

A skill for coding agents that transforms vague UI requests into polished,
production-quality frontends. Instead of generating generic Bootstrap-looking
layouts, the agent thinks like a senior designer — analyzing the product, the
niche, the target users — and then builds something that looks like an
award-winning SaaS product.

## How It Works

When you ask your coding agent to "build me a landing page" or "create a
dashboard for my fintech app", the skill automatically kicks in. It follows a
**10-step Atom of Thought Design Process** — a structured reasoning framework
that ensures every UI decision is intentional:

1. **Understand the Product** — identifies product type, target audience, core
   value proposition, and conversion goal
2. **Visual Inspiration Research** — mentally references Awwwards-quality
   patterns: dark gradients, glassmorphism, bold typography, glow effects
3. **Visual System Planning** — establishes typography pairings, color palette,
   spacing scale, border radius language, and shadow system
4. **Layout Architecture** — maps section hierarchy before writing code
   (hero → social proof → features → pricing → CTA)
5. **UI Component System** — builds modular, prop-driven, reusable components
6. **Modern Interaction Design** — adds purposeful hover effects, scroll
   reveals, micro-animations, and staggered entrances
7. **Technology Stack** — picks the right tools (Next.js, Tailwind, shadcn/ui,
   Framer Motion — or whatever the user specifies)
8. **Backend Awareness** — designs with real data in mind: loading skeletons,
   error states, empty states, form validation
9. **Responsive System** — ensures pixel-perfect behavior on mobile, tablet,
   and desktop
10. **Visual Quality Validation** — runs a comprehensive design checklist before
    delivery

The result is a frontend that looks like it came from a well-funded startup's
design team, not a generic template with swapped colors.

## Installation

### Claude Code

```bash
npx skills add deveshpunjabi/modern-frontend-skill
```

### Cursor

Copy the `skills/modern-frontend-design/` folder into your project's
`.cursor/skills/` directory.

### Windsurf

Copy the `skills/modern-frontend-design/` folder into your project's
`.windsurf/skills/` directory.

### Cline

Copy the `skills/modern-frontend-design/` folder into your project's
`.cline/skills/` directory.

### Codex / OpenAI Agents

Copy `skills/modern-frontend-design/SKILL.md` into your project's
`.codex/skills/` or `.agents/skills/` directory.

### Aider

Add to your `.aider.conf`:
```
read: path/to/skills/modern-frontend-design/SKILL.md
```

### Gemini / Other Agents

Copy `skills/modern-frontend-design/SKILL.md` into your agent's
instruction or skill directory. The skill is agent-agnostic Markdown —
it works with any LLM-based coding agent that reads instruction files.

### Manual (Any Agent)

Copy `skills/modern-frontend-design/SKILL.md` into your agent's skills
directory. The skill is a single Markdown file — no dependencies required.

### Verify It Works

Start a new session and ask something like *"build me a modern landing page for
my AI startup"*. The agent should analyze the product, plan a design system,
and build a polished interface instead of jumping straight into generic code.

## What's Inside

### Skill

- **modern-frontend-design** — 10-step Atom of Thought design workflow: product
  analysis → visual research → system planning → layout architecture → component
  system → interaction design → tech stack → backend awareness → responsive
  system → quality validation. Includes niche-specific guidance for 12 industries,
  anti-pattern prevention, and premium design techniques (glassmorphism, gradient
  systems, glow effects).

### Design Reference

- **references/design-systems.md** — Complete design system quick reference with
  typography pairings, niche-specific color palettes, glassmorphism recipes,
  gradient/glow CSS, spacing scales, shadow systems, animation patterns, and
  responsive breakpoint strategies.

### Niche-Aware Design Table

| Niche | Design Direction |
|-------|-----------------|
| AI / ML tools | Dark themes, glowing accents, futuristic gradients |
| Developer tools | Monospace accents, high-contrast, minimal chrome |
| Fintech | Trust-heavy, clean whites/blues, professional typography |
| Cybersecurity | Dark UI, terminal aesthetics, alert-driven layouts |
| Creative agencies | Bold typography, warm tones, personality-forward |
| SaaS dashboards | Sidebar nav, metric cards, neutral palettes |
| E-commerce | Product grids, prominent CTAs, trust badges |
| Social platforms | Vibrant colors, rounded shapes, card-based feeds |
| Health / Wellness | Soft colors, generous whitespace, calming gradients |
| Education | Structured layouts, progress indicators, friendly |
| Startups / Landing pages | Hero-driven, social proof, strong CTAs |
| Consulting / B2B | Authority-driven, dark premium, numbered value props |

### Anti-Patterns Prevented

The skill teaches agents to recognize and avoid common AI-generated UI failures:

| Anti-Pattern | What Goes Wrong |
|-------------|----------------|
| Rainbow soup | Too many unrelated colors |
| Wall of cards | Identical cards, no visual hierarchy |
| Button overload | Multiple competing CTAs |
| Fake depth | Shadows and gradients on everything |
| Giant hero, empty page | Massive hero, thin content below |
| Bootstrap syndrome | Default template look with swapped colors |
| Typography neglect | Same size/weight for everything |
| Spacing chaos | Random margins, no system |
| Inconsistent radius | Mixing sharp + rounded randomly |
| Stock photo blanket | Generic photos unmatched to product |

## Project Structure

```
modern-frontend-skill/
├── skills/
│   └── modern-frontend-design/
│       ├── SKILL.md                       # Core skill (369 lines, 10-step process)
│       ├── references/
│       │   └── design-systems.md          # Design system reference guide
│       └── evals/
│           └── evals.json                 # 5 test cases, 66 assertions
├── examples/
│   ├── README.md                          # Example prompts & expected outputs
│   ├── landing-page.json                  # AI SaaS landing page (InkFlow)
│   ├── dashboard.json                     # Fintech expense dashboard
│   ├── ai-support-landing.json            # AI support product (Orbita AI)
│   └── pricing-page.json                  # SaaS pricing page (Forma AI)
├── scripts/
│   ├── validate_skill.py                  # Validate SKILL.md structure
│   └── run_evals.py                       # Print eval summary
├── tests/
│   ├── test_validate_skill.py             # Skill validator tests (6 tests)
│   └── test_evals.py                      # Eval integrity tests (7 tests)
├── docs/
│   └── SKILL-GUIDE.md                     # How to customize or extend
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Test Cases

| # | Scenario | Stack | Key Checks |
|---|----------|-------|------------|
| 1 | AI writing tool landing page (InkFlow) | Next.js + Tailwind | Dark theme, hero + demo, glassmorphism pricing, social proof |
| 2 | Fintech expense dashboard | Any framework | Sidebar nav, metric cards, charts, filterable table |
| 3 | Designer portfolio (Aria Chen) | HTML/CSS/JS only | Bold typography, scroll animations, warm palette |
| 4 | AI support landing page (Orbita AI) | React + Tailwind | Dark + green accents, logo bar, benefit cards, 4-step process |
| 5 | SaaS pricing page (Forma AI) | Any modern stack | Glassmorphism cards, monthly/yearly toggle, feature checklists |

5 test cases with 66 total verifiable assertions.

## Scripts

```bash
# Validate SKILL.md structure and frontmatter
python scripts/validate_skill.py skills/modern-frontend-design/SKILL.md

# View eval summary
python scripts/run_evals.py skills/modern-frontend-design/evals/evals.json

# Run all tests (13 tests)
python -m pytest tests/ -v
```

## Philosophy

- **Design-first** — understand the product before writing code
- **Niche-aware** — every industry has visual conventions; respect them
- **Systematic** — design system before components, components before pages
- **Premium quality** — glassmorphism, gradients, glow effects, bold typography
- **Framework-agnostic** — the thinking matters more than the tools
- **Backend-ready** — loading states, error handling, real data integration

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

The short version:

1. Fork the repository
2. Create a branch for your changes
3. Follow the patterns in the existing skill
4. Run `python -m pytest tests/ -v` to verify nothing breaks
5. Submit a PR

## License

MIT — see [LICENSE](LICENSE)
