# Uplands brand kit

Shared branding for web apps at **The International School of Penang (Uplands)**: colours, typography, components and the school crest, in one place, so every site looks and feels the same.

> **Uplands** · *Respect for Self. Respect for Others.*

Current version: **1.1.0** (see [Changes](#changes)).

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
| `@1.1.0/brand.css` | Exactly version 1.1.0, never changes | Sites that must never change by surprise |

A **2.0.0** release is only used by sites that switch their link to `@2`, so breaking changes never reach a site unannounced.

---

## Colours

Use the variable (`var(--ul-green)`), never the hex code.

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
| `--ul-hover` | `#FAFCFB` | Row hover and alternate rows *(1.1)* |
| `--ul-ink` | `#2B3430` | Headings and body text |
| `--ul-text` | `#4E5954` | Secondary text, menu items |
| `--ul-muted` | `#6B7570` | Labels and captions |
| `--ul-faint` | `#9AA3A0` | Past or disabled items only, never essential text *(1.1)* |
| `--ul-border` | `#E3E8E5` | Borders |
| `--ul-divider` | `#EEF1EF` | Hairlines |
| `--ul-warning` | `#E8A33A` | Warnings, heavy load |
| `--ul-danger` | `#C0392B` | Errors, very heavy load |

### Status colours *(1.1)*

For messages, highlighted boxes and badges. Each state has a pale background, a border and a text colour; the text meets 4.5:1 on its background and on white.

| State | Background | Border | Text |
|---|---|---|---|
| Success | `--ul-success-tint` `#EEF9F2` | `--ul-success-border` `#BFE5CF` | `--ul-success-text` `#2F5D45` |
| Warning | `--ul-warning-tint` `#FDF1DC` | `--ul-warning-border` `#F2D49B` | `--ul-warning-text` `#8A5300` |
| Error / danger | `--ul-danger-tint` `#FBE3E3` | `--ul-danger-border` `#EDB4B4` | `--ul-danger-text` `#9E2A20` |

Always say the state in words ("Saved", "Heavy week", "Couldn't save"). Colour backs the words up; it never carries the meaning alone.

**Load scale** (for workload views): `--ul-load-0` none, `--ul-load-1` light, `--ul-load-2` normal, `--ul-load-heavy` amber, `--ul-load-very-heavy` red. Heavy weeks also get a small white dot, so they never rely on colour alone.

## Typography

- **Source Serif 4** (`--ul-font-serif`): the "Uplands" wordmark, the motto, occasional headings.
- **Geist** (`--ul-font-sans`): everything else, including app names, labels, tables and buttons.
- brand.css loads both fonts. Don't add your own Google Fonts link.

## Components

| Class | What it is |
|---|---|
| `ul-shell`, `ul-sidebar`, `ul-main`, `ul-topbar`, `ul-content` | App layout: sidebar on the left, top bar, content area |
| `ul-brand`, `ul-brand__crest`, `ul-brand__name`, `ul-brand__subtitle` | Crest, "Uplands" and app name, with a hairline underneath |
| `ul-nav`, `ul-nav__item` (+ `is-active`) | Sidebar menu; the active item is a green gradient pill |
| `ul-btn`, `ul-btn--primary`, `ul-btn--outline` | Pill buttons |
| `ul-btn--danger` *(1.1)* | Red outline button for Remove / Delete |
| `ul-input`, `ul-select` | Pill-shaped form fields |
| `ul-textarea` *(1.1)* | Multi-line text box |
| `ul-field`, `ul-label`, `ul-hint`, `ul-field-error` *(1.1)* | A labelled field with hint and error text |
| `is-invalid` or `aria-invalid="true"` on a field *(1.1)* | Red border for a field with an error |
| `ul-segmented`, `ul-segmented__item` (+ `is-active`) | Pill toggle group, for example All / Year 10 / Year 11 |
| `ul-card`, `ul-card__header` | White rounded card |
| `ul-stat`, `ul-stat__label`, `ul-stat__value`, `ul-stat__note` | Summary number card |
| `ul-badge`, `ul-status` | Small green pill; "Synced" status with a dot |
| `ul-badge--neutral`, `--warning`, `--danger` *(1.1)* | Grey, amber and red badges |
| `ul-notice`, `ul-notice--success`, `--warning`, `--error` *(1.1)* | Message banner |
| `ul-empty` *(1.1)* | "Nothing here" / "Loading…" message inside a card |
| `ul-table` (+ `tr.is-selected`) | Data table |
| `ul-table--hover`, `--striped`, `--compact` *(1.1)* | Optional table extras |
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

Example notice and form field *(1.1)*:

```html
<div class="ul-notice ul-notice--success" role="status"><strong>Saved.</strong> Changes apply when the page reloads.</div>

<div class="ul-field">
  <label class="ul-label" for="email">Email</label>
  <input class="ul-input" id="email" type="email" aria-describedby="email-hint">
  <span class="ul-hint" id="email-hint">Your @uplands.org address</span>
  <span class="ul-field-error"></span>   <!-- put the error text here; it hides itself when empty -->
</div>

<div class="ul-empty"><strong>No students match "Smith".</strong>Check the spelling, or search by ID.</div>
```

Use `role="alert"` on a notice only for errors the person must act on; use `role="status"` for everything else.

## Crest and wording

- Files: `logo/uplands-crest.png` (full size), `uplands-crest-256.png` and `uplands-crest-128.png` (solid green, crisp at small sizes).
- Use the **128** file for headers (shown at about 36–44 px tall) and the **256** file for larger placements.
- Don't stretch, recolour, rotate or add effects to the crest. Keep clear space around it of at least a quarter of its width.
- School name: **Uplands**. Full name: **The International School of Penang (Uplands)**. Motto: **Respect for Self. Respect for Others.**
- The crest belongs to the school and is included here only for Uplands sites.

## Asking for something new

If your app needs a colour or component the kit doesn't have, don't invent one in your app. Comment on the **Uplands Brand Kit** Google Doc. Approved additions are released as the next 1.x version and reach every app automatically.

## Releasing a new version

1. Edit the files on GitHub and commit.
2. Go to **Releases → Draft a new release**, create a tag such as `v1.1.0` (small changes) or `v2.0.0` (changes that could break existing pages), and publish it.
3. Sites linking to `@1` pick up `v1.x` releases automatically. The CDN can take a while to refresh; to speed it up, open `https://purge.jsdelivr.net/gh/uplandsschool/uplands-brand@1/brand.css` in a browser.

## Rules for this repo

- It's **public**, so the CDN can serve it. **Never** add passwords, API keys, tokens or any student or staff data.
- Keep changes in `brand.css` backwards-compatible within a major version (1.x).

## Changes

### 1.1.0 (October 2026)

Additions only; no 1.0.0 rule changed. One visible effect on existing pages: fields that are already `disabled` now look greyed out.

- Status colours: tint, border and text for success, warning and danger.
- `--ul-hover` for row hover and alternate rows; `--ul-faint` for past or disabled items.
- Notices: `ul-notice` with success, warning and error.
- Form fields: `ul-field`, `ul-label`, `ul-hint`, `ul-field-error`, `ul-textarea`, error and disabled styles.
- `ul-empty` for empty and loading messages.
- Badges: `ul-badge--neutral`, `--warning`, `--danger`.
- `ul-btn--danger` for Remove / Delete.
- Tables: optional `ul-table--hover`, `--striped`, `--compact`.

### 1.0.0 (October 2026)

First release.
