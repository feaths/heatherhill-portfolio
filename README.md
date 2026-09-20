# Heather Hill — Portfolio

Static portfolio site for [heatherhill.co](https://heatherhill.co). Plain HTML5, CSS3, and vanilla JavaScript — no build step, no framework, no dependencies.

## Structure

```
/
  index.html            Homepage (hero, throughline, project cards, about, CTA)
  /css/styles.css        All styling (design tokens, layout, components)
  /js/main.js             Mobile nav toggle + smooth scroll
  /projects/              One page per case study
    hello-brain.html
    at-your-ledger.html
    ai-guides.html
    capaci.html
  /img/                   Image assets, one folder per project
  vercel.json             Vercel deployment config
```

## Design system

- **Colors** are defined as CSS custom properties at the top of `css/styles.css` (`--coral`, `--hot-pink`, `--wine`, `--mustard`, `--forest`, `--lavender`, `--espresso`, `--cream`). Change a value there to re-theme the whole site.
- **Type**: Playfair Display (700 / 700 italic) for headlines, Inter (400 / 500) for body copy. Both load from Google Fonts.
- Each project page sets its own accent color via an inline `--accent` custom property on `<body>`, so section numbers, the hero eyebrow, and the "next project" link vary per page while staying inside the same system.

## Updating content

- **Homepage copy** (hero, throughline, about) is locked per the brief. Project card descriptions live in `index.html` inside `.project-card` blocks.
- **Project case studies**: each file in `/projects/` has four placeholder paragraphs marked `<!-- TEMPLATE: replace with the real project narrative -->`. Replace the `<p class="placeholder">` text with real copy and drop the `placeholder` class once it's final content.
- **Images**: each project has a folder under `/img/`. Drop a real image into the relevant folder and swap the `<div class="hero-image">` placeholder in that project's HTML for an `<img>` tag pointing at it.
- **LinkedIn URL**: currently set to `https://www.linkedin.com/in/heatherhill/` in the header, CTA, and footer of every page — update if the real profile URL differs.

## Local preview

No build step needed. Open `index.html` directly, or serve the folder locally:

```bash
npx serve .
```

## Deployment

Deploys to [Vercel](https://vercel.com) as a static site with zero configuration beyond `vercel.json` (security headers + long-cache headers for static assets).

```bash
vercel
```

Push to production:

```bash
vercel --prod
```
