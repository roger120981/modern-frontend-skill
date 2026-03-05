# Skill Guide

How to use, customize, and extend the Modern Frontend Design skill.

## How the Skill Triggers

The skill activates automatically when a coding agent detects that you're
asking for frontend work. Trigger phrases include:

- "build me a landing page"
- "create a dashboard"
- "design a pricing page"
- "make it look modern"
- "scaffold a web app UI"
- Any request involving frontend design, UI/UX, or responsive web layouts

The agent reads the skill's YAML `description` field to decide whether to
activate. The description is intentionally broad to avoid under-triggering.

## Customizing the Skill

### Changing the Default Tech Stack

Open `skills/modern-frontend-design/SKILL.md` and edit the tech stack table in
**Step 7 — Technology Stack**. The skill already respects user
preferences ("use Vue" or "plain HTML only"), but you can change the defaults.

### Adding a New Niche

Add a row to the niche table in **Step 1 — Understand the Product → Niche-Aware
Design Adaptation**. Follow the pattern:

```markdown
| Your Niche | Design description — key visual traits, color tendencies, layout style |
```

### Adjusting Design Standards

The design quality checklist is in **Step 10 — Visual Quality Validation**.
You can adjust values like:

- Body text size (currently 16–18px)
- Section padding (currently 80–128px)
- Max container width (currently 1200–1440px)
- Transition duration (currently 150–300ms)

### Adding Reference Documents

For detailed guidance that would make SKILL.md too long, create a file in
`skills/modern-frontend-design/references/` and add a pointer from SKILL.md:

```markdown
For detailed color palette construction, see `references/color-systems.md`.
```

The agent loads reference files on demand — they don't count toward the 500-line
recommendation for SKILL.md.

## Extending with More Skills

This repo uses the standard skill format. To add another skill:

1. Create `skills/your-skill-name/SKILL.md`
2. Add YAML frontmatter with `name` and `description`
3. Write the instructions in Markdown
4. Add eval cases in `skills/your-skill-name/evals/evals.json`
5. Validate with `python scripts/validate_skill.py skills/your-skill-name/SKILL.md`

## Skill File Format

```yaml
---
name: skill-identifier
description: >
  What the skill does and when to trigger it. Be specific and slightly
  "pushy" — list concrete phrases and contexts so the agent doesn't
  under-trigger.
---

# Skill Title

Instructions in Markdown...
```

### Directory Structure

```
skill-name/
├── SKILL.md              # Required — core instructions
├── references/           # Optional — loaded on demand
│   └── topic.md
├── scripts/              # Optional — deterministic tasks
│   └── helper.py
├── assets/               # Optional — templates, icons
│   └── template.html
└── evals/                # Recommended — test cases
    └── evals.json
```
