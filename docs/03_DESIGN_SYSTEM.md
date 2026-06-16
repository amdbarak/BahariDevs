# 03 — Design System

## 1. Direction

BahariDevs should feel **premium, trustworthy, and innovative** without looking like a generic neon technology template.

Inspiration websites may inform:
- strong hierarchy;
- clear service positioning;
- polished case-study presentation;
- conversion-focused calls to action;
- restrained, purposeful motion;
- editorial whitespace and confident typography.

Do not copy their layouts, copy, artwork, animation sequences, code, or distinctive brand expression.

## 2. Avoid

- excessive glowing gradients;
- generic circuit-board imagery;
- cliché hooded-hacker cybersecurity imagery;
- overused glass cards on every surface;
- tiny body text;
- perpetual marquees;
- autoplay sound/video;
- scroll hijacking;
- custom cursor dependency;
- decorative motion that delays content;
- fake client-logo walls;
- fake counters or testimonials;
- crowded mega menus;
- stock imagery with no business relevance.

## 3. Color tokens

Core brand:
- `navy-950`: `#021526`
- `cyan-300`: `#72DBF1`
- `cyan-500`: `#07A0DD`
- accent gradient: `#72DBF1` → `#07A0DD`

Create complete accessible ramps for:
- neutral/slate;
- brand navy;
- cyan accent;
- success;
- warning;
- danger;
- information.

Do not use accent cyan as small text on white unless contrast passes. Define semantic tokens for backgrounds, surfaces, borders, text, focus, and states in both themes.

## 4. Themes

- Dark is default for first visit.
- Light theme toggle is persistent.
- Respect `prefers-color-scheme` only when no explicit choice is stored.
- No flash of incorrect theme.
- Both themes must meet WCAG 2.2 AA contrast.

## 5. Typography

Preferred self-hosted font: Satoshi, only after licence and files are supplied.

Fallback until then:
```css
font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
```

Do not download or redistribute proprietary font files.

Guidelines:
- body default 18px on desktop, 16–18px on smaller screens;
- 20px may be used for lead paragraphs, not every dense interface;
- large display headings use fluid `clamp()` sizing;
- body line height approximately 1.6;
- headings approximately 1.05–1.2;
- readable content width 60–75 characters;
- tabular numerals for commercial/analytics values.

## 6. Layout

- mobile-first;
- 12-column desktop grid;
- max content width about 1280–1440px;
- generous but consistent section spacing;
- spacing based on a 4px foundation;
- responsive breakpoints aligned with Tailwind 4 defaults unless design review changes them;
- application layouts prioritize density and clarity over marketing drama.

## 7. Components

Required reusable primitives:
- buttons and links;
- form controls;
- field groups and error summaries;
- cards;
- badges/status chips;
- alerts/toasts;
- dialogs and drawers;
- tabs;
- accordions;
- breadcrumbs;
- pagination;
- tables and responsive data lists;
- timeline;
- file uploader;
- empty/loading/error states;
- theme switch;
- service card;
- industry/solution card;
- case-study card;
- testimonial component, disabled until real content exists;
- CTA band;
- quote/invoice document shell.

Define variants, states, focus behavior, disabled behavior, and dark/light behavior before page-specific duplication.

## 8. Motion

- subtle reveal, elevation, and page transition only where it aids orientation;
- duration generally 150–350ms;
- reduced-motion users receive no nonessential animation;
- no content remains hidden if JavaScript fails;
- animate transform/opacity rather than expensive layout properties;
- avoid simultaneous motion across many elements.

## 9. Imagery

Until original assets exist:
- use abstract brand-owned geometric compositions generated in code/CSS or approved placeholder blocks;
- do not present stock photos as BahariDevs staff or projects;
- CMS requires alt text and focal/crop metadata;
- use responsive images and modern formats;
- lazy-load below-fold imagery;
- decorative images use empty alt text.

## 10. Accessibility

Target WCAG 2.2 AA:
- visible focus;
- keyboard-complete navigation;
- skip link;
- semantic landmarks;
- one page-level H1;
- correct heading order;
- accessible menu/dialog behavior;
- labels and descriptions;
- error summary plus field errors;
- touch target sizing;
- no color-only meaning;
- live regions for async status;
- accessible table alternatives on mobile;
- motion and contrast controls.

## 11. Page experience

Public pages should answer:
1. What does BahariDevs do?
2. Who is it for?
3. Why trust the company?
4. What evidence exists?
5. What is the next low-friction action?

Authenticated/admin pages should answer:
1. What requires attention?
2. What am I allowed to do?
3. What changed?
4. What happens next?
5. Is the action reversible/audited?
