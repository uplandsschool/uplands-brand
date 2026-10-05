# Uplands brand kit

Shared branding for web apps at **The International School of Penang (Uplands)**: colours, typography, components and the school crest, in one place, so every site looks and feels the same.

> **Uplands** · *Respect for Self. Respect for Others.*

---

## Use it in a site

Add one line inside `<head>`:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/uplandsschool/uplands-brand@1/brand.css">
```

The repo lives in the [uplandsschool](https://github.com/uplandsschool) GitHub organisation.

Then add `class="ul-app"` to the `<body>` (or the page's outer element) and use the `ul-` classes below.

The crest:

```html
<img src="https://cdn.jsdelivr.net/gh/uplandsschool/uplands-brand@1/logo/uplands-crest-128.png" alt="Uplands School crest">
```

### Which version to link

| Link ends with | What you get | Use for |
|---|---|---|
| `@1/brand.css` | The latest **1.x** release, picked up automatically | Most sites |
| `@1.0.0/brand.css` | Exactly version 1.0.0, never changes | Sites that must never change by surprise |

A **2.0.0** release is only used by sites that switch their link to `@2`, so breaking changes never reach a site unannounced.

---

## Colours

| Token | Value | Use |
|---|---|---|
| `--ul-green` | `#2E7D4F` | Primary: buttons, links, active states |
| `--ul-green-dark` | `#1F5A38` | Hover and pressed |
| `--ul-green-bright` | `#3E9B6B` | Gradient end, status dot |
| `--ul-crest-green` | `#2E5A46` | The crest's own green |
| `--ul-mist` | `#E6F2EB` | Selected rows, badges |
| `--ul-tint` | `#EEF3F0` | Table headers, segmented controls |
| `--ul-page` | `#F5F7F6` | Page background |
| `--ul-surface` | `#FFFFFF` | Cards, sidebar, top bar |
| `--ul-ink` | `#2B3430` | Headings and body text |
| `--ul-text` | `#4E5954` | Secondary text, menu items |
| `--ul-muted` | `#6B7570` | Labels and captions |
| `--ul-border` | `#E3E8E5` | Borders |
| `--ul-divider` | `#EEF1EF` | Hairlines |
| `--ul-warning` | `#E8A33A` | Warnings, heavy load |
| `--ul-danger` | `#C0392B` | Errors, very heavy load |

**Load scale** (for workload views): `--ul-load-0` none, `--ul-load-1` light, `--ul-load-2` normal, `--ul-load-heavy` amber, `--ul-load-very-heavy` red. Heavy weeks also get a small white dot, so they never rely on colour alone.

## Typography

- **Source Serif 4** (`--ul-font-serif`): the "Uplands" wordmark, the motto, occasional headings.
- **Geist** (`--ul-font-sans`): everything else, including app names, labels, tables and buttons.

## Components

| Class | What it is |
|---|---|
| `ul-shell`, `ul-sidebar`, `ul-main`, `ul-topbar`, `ul-content` | App layout: sidebar on the left, top bar, content area |
| `ul-brand`, `ul-brand__crest`, `ul-brand__name`, `ul-brand__subtitle` | Crest, "Uplands" and app name, with a hairline underneath |
| `ul-nav`, `ul-nav__item` (+ `is-active`) | Sidebar menu; the active item is a green gradient pill |
| `ul-btn`, `ul-btn--primary`, `ul-btn--outline` | Pill buttons |
| `ul-input`, `ul-select` | Pill-shaped form fields |
| `ul-segmented`, `ul-segmented__item` (+ `is-active`) | Pill toggle group, for example All / Year 10 / Year 11 |
| `ul-card`, `ul-card__header` | White rounded card |
| `ul-stat`, `ul-stat__label`, `ul-stat__value`, `ul-stat__note` | Summary number card |
| `ul-badge`, `ul-status` | Small green pill; "Synced" status with a dot |
| `ul-table` (+ `tr.is-selected`) | Data table |
| `ul-load`, `ul-load--1`, `--2`, `--heavy`, `--very-heavy` | Weekly load blocks |
| `ul-motto`, `ul-footer`, `ul-sidebar__footer` | Motto and footer lines |

Example sidebar header:

```html
<div class="ul-brand">
  <img class="ul-brand__crest" src="https://cdn.jsdelivr.net/gh/uplandsschool/uplands-brand@1/logo/uplands-crest-128.png" alt="Uplands School crest">
  <div class="ul-brand__text">
    <span class="ul-brand__name">Uplands</span>
    <span class="ul-brand__subtitle">Assessment Load Tracker</span>
  </div>
</div>
```

## Crest and wording

- Files: `logo/uplands-crest.png` (full size), `uplands-crest-256.png` and `uplands-crest-128.png` (solid green, crisp at small sizes).
- Use the **128** file for headers (shown at about 36–44 px tall) and the **256** file for larger placements.
- Don't stretch, recolour, rotate or add effects to the crest. Keep clear space around it of at least a quarter of its width.
- School name: **Uplands**. Full name: **The International School of Penang (Uplands)**. Motto: **Respect for Self. Respect for Others.**
- The crest belongs to the school and is included here only for Uplands sites.

## Releasing a new version

1. Edit the files on GitHub and commit.
2. Go to **Releases → Draft a new release**, create a tag such as `v1.1.0` (small changes) or `v2.0.0` (changes that could break existing pages), and publish it.
3. Sites linking to `@1` pick up `v1.x` releases automatically. The CDN can take a while to refresh; to speed it up, open `https://purge.jsdelivr.net/gh/uplandsschool/uplands-brand@1/brand.css` in a browser.

## Rules for this repo

- It's **public**, so the CDN can serve it. **Never** add passwords, API keys, tokens or any student or staff data.
- Keep changes in `brand.css` backwards-compatible within a major version (1.x).
