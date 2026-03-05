# Examples

Real-world example prompts and the expected outputs when using the **modern-frontend-design** skill. These cover the most common project types an agent will encounter.

## Landing Pages

### AI SaaS Product (InkFlow)
**Prompt:** *"Build a landing page for an AI writing assistant called InkFlow with a dark theme, hero with demo preview, features showing different writing modes, 3-tier pricing, and testimonials. Use Next.js and Tailwind."*

**Expected:** Next.js + Tailwind dark-themed landing page with cohesive blue/purple palette, display-size hero typography with demo preview, social proof logos, feature grid, glassmorphism pricing cards (Free/Standard/Pro) with highlighted recommended tier, testimonial section, and responsive design.

### AI Customer Support (Orbita AI)
**Prompt:** *"Landing page for Orbita AI — 24/7 multilingual chat support for global teams. Hero with 'Always-On AI Support for a Global Customer Base', trusted-by logos (Atlassian, Microsoft, Notion, Shopify, Slack), 3 benefit cards, 4-step 'how it works', final CTA. Dark theme, green accents. React + Tailwind."*

**Expected:** Premium dark-themed landing page with green accent system, hero with globe/earth visual, logo bar, 3 benefit cards with icons, numbered 4-step process section, and strong final CTA. Resembles modern AI SaaS marketing pages.

### Developer Tool
**Prompt:** *"Create a homepage for a CLI tool that helps developers manage Docker containers. Minimal, dev-focused."*

**Expected:** High-contrast dark theme with monospace accents, terminal-style hero with code snippet demo, feature comparison section, one-line install CTA, and developer-focused copy.

---

## Dashboards

### Fintech Dashboard
**Prompt:** *"Build a dashboard for my fintech startup — expense tracking for small businesses. Main view: total spend, budget remaining, spend-by-category charts. Sidebar nav, transactions table with filters, top bar with search and profile. Clean and professional."*

**Expected:** Professional sidebar dashboard with icon+label nav, top bar (search + avatar), metric summary cards with trend arrows, category spend chart (donut/bar), filterable transactions table with realistic financial data, loading skeletons, and responsive layout.

### Analytics Dashboard
**Prompt:** *"Analytics dashboard for a social media scheduling app. Show post performance, engagement metrics, and a calendar view."*

**Expected:** Clean SaaS dashboard with top nav, metric cards (impressions, clicks, engagement rate), line/bar charts for trends, calendar grid with scheduled posts, and proper empty states.

---

## Pricing Pages

### SaaS Pricing (Forma AI)
**Prompt:** *"Pricing page for Forma AI design tool. Three plans: Free ($0), Standard ($9.99/m), Pro ($19.99/m) with monthly/yearly toggle. Dark background, glassmorphism cards. Each card lists specific features with checkmarks."*

**Expected:** Standalone pricing page with dark gradient background, 3 glassmorphism pricing cards, monthly/yearly toggle, feature checklists, prominent price typography, highlighted recommended tier, and 'Choose Plan' CTAs. Responsive — cards stack on mobile.

---

## Portfolios & Personal Sites

### Designer Portfolio
**Prompt:** *"Portfolio for freelance UI/UX designer Aria Chen. Project gallery grid, about section, contact form, blog listing. Bold typography, scroll animations. HTML/CSS/JS only. Warm colors, dark background."*

**Expected:** Single-page or multi-page site with display typography, scroll-triggered animations (Intersection Observer), gallery grid with hover effects, about section with personality, working contact form, blog listing, and warm copper/gold palette on dark background.

---

## How to Use These Examples

1. Load the skill into your agent (see installation instructions in README)
2. Copy any prompt above and paste it as your request
3. Compare the output against the expected result
4. The output should follow the 10-step Atom of Thought process and match the design quality described
5. If the output looks generic or template-like, the skill needs tuning
