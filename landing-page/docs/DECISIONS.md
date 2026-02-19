# Design Decisions Log

This document records the key decisions made during the project development.

---

## 2026-02-13: Whitepaper Design Session

### Decision: Separate Whitepaper Page
**Options considered:**
- A) Single page with landing + whitepaper
- B) Separate page for whitepaper

**Chosen:** B - Separate page (`/whitepaper.html`)

**Reasoning:** Whitepaper needs different layout optimized for reading, while landing page is optimized for impact and conversion.

---

### Decision: Sidebar Navigation
**Options considered:**
- A) Top navigation menu
- B) Sidebar navigation

**Chosen:** B - Sidebar navigation

**Reasoning:** Better for long-form content, allows always-visible table of contents, familiar pattern from documentation sites.

---

### Decision: Content Tone
**Options considered:**
- A) Technical/formal
- B) Conversational with technical sections when needed

**Chosen:** B - Conversational as default

**Reasoning:** Aligns with movement's values (accessible, inclusive), technical depth available when needed but not the default.

---

### Decision: Content Structure
**Options considered:**
- Initial proposal: Technical categories (Token, Governance, Infrastructure...)
- User feedback: "muito chato" (too boring)

**Chosen:** Narrative flow with questions
- Start Here (2 minutes)
- The Principles
- How It Works (progressive depth)
- How to Participate
- Deep Dive (technical details)
- Join Us

**Reasoning:** Reader journey from curiosity to understanding to action. Technical depth comes later, after context is established.

---

### Decision: 9 Principles Tone
**Evolution:**
- v1-5: Progressive refinement
- v6: More "punk"/irreverent tone
- User feedback: "Ah não gostei, o modelo anterior estava melhor"
- v7: Return to balanced tone

**Final decision:** Direct and clear, but not irreverent. Personality without being edgy.

---

### Decision: No Emojis
**Reasoning:** Maintains professional, serious tone. Visual design carries the personality instead.

---

## 2026-02-13: Typography Optimization

### Decision: Reading-Optimized Typography
**Problem:** Initial text was hard to read

**Changes made:**
- Base font: 16px → 18px
- Line height: 1.5 → 1.75
- Content width: 680px → 820px (900px on large desktop)

**References:** Stripe docs, ENS DAO basics, Optimism docs

---

### Decision: Responsive Breakpoints
```
> 1400px  : Large desktop (900px content)
< 1100px  : Tablet (700px content)
< 900px   : Mobile (hamburger menu)
< 480px   : Small mobile (reduced padding)
```

---

## Technical Decisions

### Decision: Pure HTML/CSS/JS
**Reasoning:**
- Simple content site, no complex state needed
- Maximum performance
- Easy maintenance
- No build step required
- Direct Vercel deployment

---

### Decision: Inline CSS/JS
**Reasoning:**
- Single file = simpler deployment
- No additional HTTP requests
- Easy to edit everything in one place
- Small enough that bundling adds no benefit

---

### Decision: Language System with data-lang
**Implementation:**
```html
<p data-lang="en">English</p>
<p data-lang="es">Spanish</p>
<p data-lang="pt">Portuguese</p>
```

**Reasoning:**
- All content in same file (easier to keep in sync)
- No JavaScript required for initial render
- CSS-only language switching
- Simple to add new languages

---

### Decision: ASCII Section IDs
**Problem:** Accented characters in IDs (e.g., `#princípios`) caused issues

**Solution:** Use ASCII-only IDs
- `#principios` instead of `#princípios`
- `#governanca` instead of `#governança`

---

## Content Decisions

### Decision: "Empty Center" Concept
The network DAO has an "empty center" - it doesn't govern, doesn't operate, doesn't make ongoing decisions. It only guards purpose and culture.

**Reasoning:** Avoids centralization trap while maintaining coherence.

---

### Decision: COOP Token as Non-Monetary
Token is for identity and signaling, NOT currency or voting power.

**Reasoning:**
- Avoids speculation
- Focus on participation, not profit
- Monetary aspect is secondary experiment

---

### Decision: Cooperative Shares Non-Transferable
Shares cannot be sold or traded, only burned on exit.

**Reasoning:** Prevents speculation, maintains cooperative nature.

---

### Decision: Coop-Franchising Concept
New model where collective brand is owned by all franchisees together.

**Reasoning:** Solves traditional franchise power imbalance while maintaining brand benefits.

---

### Decision: 5 Initial Cooperatives
Protocol, Bank, Cafe, Edu, Lab

**Reasoning:**
- Protocol: Essential infrastructure
- Bank: Financial independence
- Cafe: Physical presence, relatable
- Edu: Growth and education
- Lab: Research and evolution

---

## Pending Decisions

### To Revisit
- [ ] 9 Principles need deep review
- [ ] Entry criteria ("estrutura dorsal") needs refinement
- [ ] Protocol templates need detailed development
- [ ] Roadmap phases need concrete milestones
