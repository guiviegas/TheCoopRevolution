# CLAUDE.md - Project Instructions

## Project Overview

THE COOP Revolution - Landing page and whitepaper for a network of cooperatives powered by DAO technology.

## Tech Stack

- **Pure HTML/CSS/JS** - No frameworks, no build step
- **Fonts:** Space Grotesk (headings/body) + JetBrains Mono (labels/code)
- **Hosting:** Vercel (auto-deploy from GitHub)
- **Languages:** EN/ES/PT with `data-lang` attribute system

## Project Structure

```
landing-page/
├── index.html          # Landing page (full-page scroll)
├── whitepaper.html     # Navigable whitepaper (sidebar layout)
├── vercel.json         # Vercel configuration
├── CLAUDE.md           # This file
├── .gitignore
└── docs/
    ├── README.md           # Project documentation
    ├── ARCHITECTURE.md     # Technical details
    ├── DECISIONS.md        # Design decisions log
    ├── CONTENT.md          # Content structure
    └── plans/
        └── 2026-02-13-whitepaper-design.md
```

## Design System

### Colors
- `--black: #0a0a0a` (whitepaper) / `#000000` (landing)
- `--white: #FFFFFF`
- `--gray: rgba(255,255,255,0.75)` (body text)

### Typography
- Base font: 18px (whitepaper), 16px (landing)
- Line height: 1.75 (whitepaper), 1.4 (landing)
- Content max-width: 820px (900px on large desktop)

### Visual Style
- Minimalist black/white
- No emojis
- Conversational tone in content
- Technical when necessary

## Language System

All text uses `data-lang` attributes:
```html
<p data-lang="en">English text</p>
<p data-lang="es">Spanish text</p>
<p data-lang="pt">Portuguese text</p>
```

CSS controls visibility:
```css
[data-lang] { display: none; }
[data-lang="en"] { display: block; }
.lang-es [data-lang="en"] { display: none; }
.lang-es [data-lang="es"] { display: block; }
```

## Key Concepts

### The Network (DAO)
- "Empty center" - no central governance
- Guards purpose and culture only
- Cooperatives are sovereign

### COOP Token
- Soulbound (non-transferable)
- Identity + signaling, NOT currency
- Experimental

### Cooperatives
- 5 initial: Protocol, Bank, Cafe, Edu, Lab
- 3 levels: Franchise, Network Member, Independent
- Entry criteria ("estrutura dorsal")

### Value Flows
1. Within each coop
2. Between cooperatives
3. Coops → Protocol (cloud subscription)
4. Voluntary contributions
5. Franchises → Collective brand

## Commands

```bash
# Local development
python3 -m http.server 8000
# Visit http://localhost:8000

# Deploy
git add . && git commit -m "message" && git push
# Vercel auto-deploys from main branch
```

## URLs

- **Production:** https://thecooprevolution.com (or Vercel URL)
- **GitHub:** https://github.com/guiviegas/TheCoopRevolution
- **Local:** http://localhost:8000

## Content Guidelines

- Conversational as default
- Technical when necessary
- No emojis
- Direct, clear, with personality
- "We believe...", "We're building..."

## Important Notes

- Always maintain 3 languages in sync
- Section IDs should be ASCII (no accents)
- Test responsive design (mobile menu at 900px)
- Portuguese/Spanish accents are critical - verify carefully

## References

- ENS DAO Basics: https://basics.ensdao.org/
- Optimism Docs: https://docs.optimism.io/
- Stripe Docs: https://docs.stripe.com/
