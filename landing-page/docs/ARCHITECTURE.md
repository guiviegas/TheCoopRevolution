# Technical Architecture

## Overview

Pure HTML/CSS/JS implementation with no build step. Designed for simplicity, performance, and easy maintenance.

## Technology Choices

### Why No Framework?
- Simple content site (no complex state)
- Maximum performance
- Easy to edit by anyone
- No dependencies to maintain
- Direct Vercel deployment

### Fonts
- **Space Grotesk** - Modern geometric sans-serif for headings and body
- **JetBrains Mono** - Monospace for labels, tags, and technical elements

### Hosting
- **Vercel** - Free tier, auto-deploy from GitHub, global CDN
- **Domain:** thecooprevolution.com (pending)

## File Structure

```
landing-page/
├── index.html              # Landing page
│   ├── CSS (inline <style>)
│   ├── HTML structure
│   └── JS (inline <script>)
│
├── whitepaper.html         # Whitepaper
│   ├── CSS (inline <style>)
│   ├── Sidebar navigation
│   ├── Content sections
│   └── JS (language, navigation)
│
├── vercel.json             # Vercel config
├── .gitignore
├── CLAUDE.md               # AI assistant instructions
└── docs/                   # Documentation
```

## Landing Page Architecture

### Layout: Full-Page Scroll
```
┌────────────────────────────┐
│  [EN] [ES] [PT]            │  Language switcher (fixed)
├────────────────────────────┤
│                            │
│         PAGE 1             │  scroll-snap-align: start
│         (Hero)             │
│                            │
├────────────────────────────┤
│                            │
│         PAGE 2             │  scroll-snap-align: start
│       (The Model)          │
│                            │
├────────────────────────────┤
│         ...                │
└────────────────────────────┘
```

### CSS Features
- `scroll-snap-type: y mandatory` - Full page snap scrolling
- CSS custom properties for colors
- Responsive with clamp() for typography
- Mobile breakpoint at 768px

## Whitepaper Architecture

### Layout: Sidebar + Content
```
┌──────────┬─────────────────────────────┐
│          │              [EN] [ES] [PT] │
│  LOGO    ├─────────────────────────────┤
│          │                             │
│  NAV     │         CONTENT             │
│  - Start │         (scrollable)        │
│  - Princ │                             │
│  - How   │         max-width: 820px    │
│    - Net │                             │
│    - Coop│                             │
│    - Tok │                             │
│    ...   │                             │
│          │                             │
└──────────┴─────────────────────────────┘
```

### CSS Features
- Fixed sidebar (260px)
- Sticky header with language switcher
- Content optimized for reading (18px, 1.75 line-height)
- Responsive: sidebar becomes hamburger menu at 900px

### Typography Scale
```css
html { font-size: 18px; }
h1   { font-size: clamp(2rem, 4vw, 2.75rem); }
h2   { font-size: clamp(1.35rem, 2.5vw, 1.6rem); }
h3   { font-size: 1.15rem; }
p    { font-size: 1rem; line-height: 1.75; }
```

### Responsive Breakpoints
| Breakpoint | Changes |
|------------|---------|
| > 1400px | Content width: 900px |
| 1100px | Content width: 700px |
| 900px | Mobile layout, hamburger menu |
| 480px | Smaller padding, smaller headings |

## Language System

### Implementation
```html
<!-- Content tagged by language -->
<p data-lang="en">English text</p>
<p data-lang="es">Spanish text</p>
<p data-lang="pt">Portuguese text</p>

<!-- Navigation also tagged -->
<a href="#section" data-lang="en">Section Name</a>
<a href="#section" data-lang="es">Nombre de Sección</a>
<a href="#section" data-lang="pt">Nome da Seção</a>
```

### CSS Control
```css
/* Default: show English */
[data-lang] { display: none; }
[data-lang="en"] { display: block; }

/* Spanish mode */
.lang-es [data-lang="en"] { display: none; }
.lang-es [data-lang="es"] { display: block; }

/* Portuguese mode */
.lang-pt [data-lang="en"] { display: none; }
.lang-pt [data-lang="pt"] { display: block; }
```

### JavaScript
```javascript
function setLanguage(lang) {
    document.body.classList.remove('lang-en', 'lang-es', 'lang-pt');
    document.body.classList.add('lang-' + lang);
    document.documentElement.lang = lang;
}
```

## Component Patterns

### Principle Card
```html
<div class="principle">
    <div class="principle-number">01</div>
    <div class="principle-title">Title here.</div>
    <div class="principle-text">Description text.</div>
</div>
```

### Callout/Note
```html
<div class="callout">
    <div class="callout-title">Note</div>
    <p>Callout content here.</p>
</div>
```

### Table
```html
<div class="table-wrapper">
    <table>
        <tr><th>Header 1</th><th>Header 2</th></tr>
        <tr><td>Cell 1</td><td>Cell 2</td></tr>
    </table>
</div>
```

## Navigation

### Active Section Highlighting
Uses IntersectionObserver to highlight current section in sidebar:

```javascript
const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            // Update active nav link
        }
    });
}, { rootMargin: '-20% 0px -80% 0px' });
```

## Deployment

### Vercel Configuration
```json
{
  "$schema": "https://openapi.vercel.sh/vercel.json",
  "public": true
}
```

### Deploy Process
1. Push to `main` branch
2. Vercel auto-detects changes
3. Deploys static files to CDN
4. Available globally in seconds

## Performance

- No external JS libraries
- Fonts loaded with `preconnect`
- Inline CSS (no extra requests)
- Static HTML (instant load)
- Vercel CDN (global edge)

## Browser Support

- Modern browsers (Chrome, Firefox, Safari, Edge)
- CSS Grid and Flexbox
- scroll-snap (with fallback)
- IntersectionObserver
