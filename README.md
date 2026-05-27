# RDC Design System

The visual and technical foundation for all Red Door Collaborative HTML output. Import one stylesheet and your HTML is on-brand by default.

**Live docs:** https://reddoorcollaborative.github.io/rdc-design-system/

---

## Quick start

Add these two blocks to the `<head>` of any HTML file:

```html
<!-- Google Fonts (DM Sans — web substitute for licensed Suisse Int'l) -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;0,9..40,600;0,9..40,700;1,9..40,300&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">

<!-- RDC Design System -->
<link rel="stylesheet" href="https://reddoorcollaborative.github.io/rdc-design-system/css/rdc.css">
```

That's it. All brand colors, typography, components, and layout utilities are now available.

---

## Using with Claude

Paste this at the start of any Claude conversation to get on-brand HTML output automatically:

```
You are creating an HTML deliverable for Red Door Collaborative (RDC). Apply the RDC design system precisely.

STYLESHEET — always include in <head>:
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;0,9..40,600;0,9..40,700;1,9..40,300&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://reddoorcollaborative.github.io/rdc-design-system/css/rdc.css">

BRAND COLORS:
  --coral: #FF4F58   CTAs, links, eyebrow labels
  --squid: #0D1724   Dark backgrounds, primary text
  --wine:  #7F0046   Secondary accent, gradient start
  --mist:  #ABDCE0   Soft accent — never a page background
  --gray:  #F3F3F3   Light backgrounds

COMPONENT CLASSES:
  .btn .btn-primary / .btn-dark / .btn-wine / .btn-outline-coral / .btn-ghost / .btn-sm / .btn-lg
  .badge .badge-coral / .badge-squid / .badge-wine / .badge-mist / .badge-success / .badge-warning
  .card / .doc-card / .content-card / .metric-card
  .form-label / .input-rdc / .select-rdc
  .alert .alert-coral / .alert-info / .alert-success / .alert-warning / .alert-banner
  .table-rdc
  .wrap / .wrap-narrow / .grid-2 / .grid-3 / .grid-4 / .grid-auto
  .page-header / .page-header-title / .page-header-desc / .header-meta
  .sidebar / .sidebar-content / .nav-link / .eyebrow / .divider

RULES:
  - All buttons use border-radius: 999px (pill) — handled by .btn class
  - Coral is always the primary CTA color
  - Page background is #F7F6F4 (set by rdc.css automatically)
  - Sentence case for all headings — never title case
  - Max 3 font weights per page
  - Logo minimum size: 85px wide, no drop shadows

DESIGN SYSTEM REFERENCE: https://reddoorcollaborative.github.io/rdc-design-system/
```

**Pro tip:** Add this as a Project instruction in Claude so it applies automatically to every conversation in that project.

---

## What's in this repo

```
rdc-design-system/
├── index.html              ← Live design system documentation (start here)
├── css/
│   └── rdc.css             ← The single importable stylesheet
└── templates/
    ├── hub.html            ← Portal / knowledge base index page
    ├── document.html       ← Long-form document with sidebar navigation
    ├── brief.html          ← Project brief / scoping document
    └── report.html         ← Metrics & performance report
```

---

## Brand tokens

### Colors

| Token | Hex | Use |
|-------|-----|-----|
| `--coral` | `#FF4F58` | Primary CTAs, links, eyebrow labels |
| `--squid` | `#0D1724` | Dark backgrounds, primary text |
| `--wine` | `#7F0046` | Secondary accent, gradient start |
| `--mist` | `#ABDCE0` | Soft accent — never page backgrounds |
| `--gray-100` | `#F3F3F3` | Light backgrounds, metric cards |
| `--page-bg` | `#F7F6F4` | Body background (set automatically) |

### Typography

| Role | Typeface | Source |
|------|----------|---------|
| Brand (print) | Suisse Int'l | Swiss Typefaces (licensed) |
| Brand (digital) | Proxima Nova | Adobe Fonts |
| HTML substitute | DM Sans | Google Fonts (free) |
| Monospace | DM Mono | Google Fonts (free) |

### Spacing (8pt base grid)

`--space-1: 4px` · `--space-2: 8px` · `--space-3: 12px` · `--space-4: 16px` · `--space-6: 24px` · `--space-8: 32px` · `--space-12: 48px` · `--space-16: 64px`

### Border radius

`--radius-sm: 4px` · `--radius-md: 8px` · `--radius-lg: 12px` · `--radius-xl: 18px` · `--radius-pill: 999px`

---

## Components at a glance

### Buttons
```html
<button class="btn btn-primary">Hire us</button>
<button class="btn btn-dark btn-sm">Learn more</button>
<a href="#" class="btn btn-outline-coral">View services</a>
```

### Cards
```html
<!-- Doc card (navigational link) -->
<a href="#" class="doc-card">
  <div class="doc-card-bar"></div>
  <div class="doc-card-body">
    <div class="eyebrow">Category</div>
    <h3>Card title</h3>
    <p>Description</p>
  </div>
</a>

<!-- Metric card -->
<div class="metric-card">
  <div class="metric-label">Projects</div>
  <div class="metric-value">48</div>
  <div class="metric-delta">↑ +12 this quarter</div>
</div>
```

### Dark hero header
```html
<div class="page-header">
  <div class="eyebrow">Red Door Collaborative</div>
  <h1 class="page-header-title">Page title</h1>
  <p class="page-header-desc">One-line description.</p>
</div>
```

### Alerts
```html
<div class="alert alert-coral">
  <div class="alert-dot"></div>
  <div class="alert-body">
    <div class="alert-title">Title</div>
    Supporting message text.
  </div>
</div>
```

---

## Logo rules (from brand guide v1.0)

- Minimum digital size: **85px wide**
- Minimum print size: **0.25 in wide**
- Clear space: equal to the logo's own bounding square on all four sides
- **Do not** stretch, rotate, skew, split colors, recolor, or add drop shadows
- Always use approved files from Box: `Red Door File Database → Red Door Guidelines and Assets → RDC 2025 Branding`

---

## Contributing

This is a living system. To update:

1. Edit `css/rdc.css` for token or component changes
2. Update `index.html` to reflect the change in the docs
3. Commit with a clear message describing what changed and why
4. Push to `main` — GitHub Pages auto-deploys

For new templates, follow the pattern in `templates/document.html`: import `../css/rdc.css`, use only documented class names, and add a link in `index.html` under the Templates section.
