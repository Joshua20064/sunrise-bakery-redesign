# Sunrise Bakery: Website UI Redesign

A before/after case study. A dated small-business website is audited against core UI principles, then rebuilt as a clean, responsive page in plain HTML and CSS (no build step).

```
before/index.html   the original, intentionally dated baseline
after/index.html    the redesign
after/styles.css    design tokens + styles
```

Open either `index.html` in a browser to compare. To publish the redesign, enable GitHub Pages on the repository and serve the `after/` folder.

> Note: the "before" page is a representative legacy small-business site written for this case study, not a scraped copy of a real company's site.

## 1. Audit: what was wrong

| Area | Problem in the original | Principle broken |
|---|---|---|
| **Layout** | Fixed 900px column, boxed sections with heavy ridge borders, everything the same visual weight | Hierarchy, responsiveness |
| **Color** | Yellow, orange, brown, red, green and blue all competing; yellow text on orange; red button with green text | Contrast (WCAG AA), restraint |
| **Typography** | Comic Sans title, 12–13px body in low-contrast brown, 1.1 line-height | Readability, consistency |
| **Navigation** | 11 links in one cramped row (Products, Cakes, Bread, Pastry overlap), blue default link color, no clear primary action | Hick's law, clarity |
| **Content** | One run-on welcome paragraph; "CLICK HERE" button with no destination or meaning | Scannability, clear CTAs |
| **Menu** | Unstyled 4-column table, prices easy to misread | Proximity, alignment |
| **Mobile** | Fixed width forces horizontal scrolling, tiny tap targets | Responsive design, accessibility |
| **Accessibility** | No `lang`, no viewport meta, no focus styles, no landmarks | Semantics, inclusion |

## 2. Redesign decisions

- **Structure:** one page with a clear story: hero → menu → about → custom orders → visit info.
- **Navigation:** reduced from 11 links to 3 sections plus one primary button ("Order a cake"). The sticky header keeps it reachable.
- **Color:** a warm neutral base with a single accent (terracotta `#b4491b`). White on the accent is 5.4:1, body text on cream is 14.8:1, muted text is 5.9:1 (all pass WCAG AA).
- **Type:** Fraunces (headings, personality) with Inter (body, legibility). 17px base, 1.6 line-height, fluid heading sizes via `clamp()`.
- **Spacing:** an 8px scale held consistently, so sections breathe and align.
- **Components:** reusable cards, pill buttons (primary/secondary), a menu list with right-aligned prices.
- **Responsive:** 3-column grids collapse to one column below 860px; mobile keeps the CTA in the header.
- **Accessibility:** semantic landmarks, `lang`, skip-friendly structure, visible focus rings, `tel:`/`mailto:` links, reduced-motion support.

## 3. Before vs after

| | Before | After |
|---|---|---|
| Nav items | 11 | 3 + 1 CTA |
| Colors in use | 8+ | 1 accent + neutrals |
| Body text size | 13px | 17px |
| Mobile support | none | fully responsive |
| Primary action | "CLICK HERE" | "Order a custom cake" |
