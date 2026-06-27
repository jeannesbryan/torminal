# > TORMINAL CSS_ 📟
**The Zero-JS, Tor-Friendly Terminal UI Framework**

![CSS3](https://img.shields.io/badge/CSS3-Pure-1572B6?style=for-the-badge&logo=css3)
![Zero JS](https://img.shields.io/badge/JavaScript-0%25-F7DF1E?style=for-the-badge)
![Tor Friendly](https://img.shields.io/badge/Tor-Optimized-7D4698?style=for-the-badge&logo=tor)
![No Dependencies](https://img.shields.io/badge/Dependencies-None-00ff66?style=for-the-badge)

Torminal CSS is a lightweight, dependency-free CSS framework for building terminal-inspired interfaces that work cleanly in privacy-first environments such as Tor Browser. It uses native HTML and CSS only: no frontend JavaScript, no remote assets, no webfont downloads, and no build step.

Torminal is used as the UI foundation for DeadDrop, but it is designed to be reusable in other small PHP/static apps that need low-resource, keyboard-friendly, mobile-ready interfaces.

---

## Design Goals

- **Zero JavaScript:** interactive patterns rely on native HTML or CSS-only mechanisms such as `:checked`, `:target`, and `<details>`.
- **Tor-friendly:** no external fonts, no remote CSS, no tracking dependencies, and a conservative default `monospace` stack.
- **Low-resource:** small plain CSS file, no bundler, no runtime framework.
- **Readable on mobile:** responsive containers, flex utilities, touch-friendly buttons, and stack-on-mobile helpers.
- **Accessible by default:** visible keyboard focus, reduced-motion support, and CSS-only toggles that can remain screen-reader/keyboard accessible.
- **Reusable:** shared utility classes and modules replace page-level inline CSS.

---

## Quick Start

Drop `torminal.css` into your project and link it from the page header:

```html
<link rel="stylesheet" href="assets/torminal.css">
```

Enable the CRT overlay by adding `.t-crt` to the body:

```html
<body class="t-crt">
    <div class="t-container t-box-md mt-4">
        <h1 class="t-glow t-page-title">&gt; HELLO_WORLD_</h1>
        <a href="#" class="t-btn active">[ EXECUTE ]</a>
    </div>
</body>
```

The CRT effect is optional. For a calmer UI, use a plain `<body>` without `.t-crt`.

---

## Core Utilities

Torminal includes a small utility layer inspired by Bootstrap-style naming, but intentionally much smaller:

- Layout: `.d-flex`, `.flex-wrap`, `.flex-column`, `.flex-fill`, `.justify-content-between`, `.align-items-center`, `.gap-1` to `.gap-4`
- Spacing: `.m-*`, `.mt-*`, `.mb-*`, `.p-*`, `.pt-*`, `.pb-*`, `.px-*`, `.py-*`
- Sizing: `.w-25`, `.w-50`, `.w-75`, `.w-100`, `.w-auto`
- Text: `.text-center`, `.text-right`, `.text-muted`, `.text-success`, `.text-danger`, `.text-warning`, `.text-info`, `.text-private`
- Borders: `.t-border`, `.t-border-top`, `.t-border-bottom`, `.border-private`, `.border-info`, `.border-soft`
- Accessibility: `.t-sr-only`, `:focus-visible`, `prefers-reduced-motion`

---

## Components

### Buttons

```html
<a class="t-btn active" href="#">[ TIMELINE ]</a>
<a class="t-btn private outline" href="#">[ INBOX ]</a>
<a class="t-btn info outline" href="#">[ RADAR ]</a>
<a class="t-btn danger outline" href="#">[ LOCK ]</a>
```

Variants:

- `.active` / `.is-active`
- `.danger`
- `.warning`
- `.info`
- `.private`
- `.ghost`
- `.outline`
- `.t-btn-sm`
- `.t-btn-block`

### Forms

```html
<label class="t-form-label">Master Key</label>
<input class="t-input t-input-center" type="password" placeholder="Insert Master Key...">
<textarea class="t-textarea" placeholder="Type payload..."></textarea>
<select class="t-input t-input-sm">
    <option>TTL: Forever</option>
</select>
```

Useful form helpers:

- `.t-input-center`
- `.t-input-sm`
- `.t-input-xs`
- `.t-input-micro`
- `.t-input-peer-url`
- `.t-input-alias`
- `.t-input-alias-sm`
- `.border-private`
- `.border-info`

### Cards and Alerts

```html
<div class="t-card">
    <div class="t-card-title">[ Broadcast Station ]</div>
    <p>Terminal card content.</p>
</div>

<div class="t-card private">
    <div class="t-card-title private">[ Secure Drop Channel ]</div>
</div>

<div class="t-alert danger">[!] Authentication failed.</div>
```

Card variants:

- `.private`
- `.info`
- `.danger`
- `.warning`
- `.dashed`

### Lock / Vault Panels

```html
<div class="t-lock-panel private">
    <h1 class="t-vault-title t-glow text-private">[ 🔒 CLASSIFIED VAULT ]</h1>
    <div class="t-vault-subtitle">Authentication required.</div>
    <form class="t-lock-form" method="post">
        <input class="t-input t-input-center border-private" type="password">
        <button class="t-btn private w-100 font-bold">[ UNLOCK ]</button>
    </form>
</div>
```

### Timeline / Inbox Posts

```html
<div class="t-post private">
    <div class="t-post-header fs-small">
        <a class="t-badge private outline t-post-author" href="#">@alias</a>
        <span class="text-muted">ID: abc123</span>
    </div>

    <div class="t-quote private">
        <span class="t-quote-author">&gt; Replying to @node:</span>
        Previous signal preview...
    </div>

    <div class="t-post-content private">
        Decrypted message content...
    </div>

    <div class="t-post-footer">
        <span class="fs-small text-muted">2026-06-27 UTC</span>
    </div>
</div>
```

Post variants:

- `.local` / `.local-node`
- `.private` / `.inbox`
- `.burner`
- `.deleted` / `.tombstone`

### Radar / Inspector Helpers

```html
<div class="t-dotted-row">
    <div class="t-ellipsis flex-fill">
        <a class="t-link-underline t-glow font-bold" href="#">@peer</a>
        <br>
        <span class="fs-small text-muted">http://example.onion/deaddrop</span>
    </div>
</div>
```

Useful helpers:

- `.t-fingerprint` for long identifiers, onion URLs, hashes, and keys
- `.t-kv` for key/value inspector panels
- `.t-metric-grid` and `.t-metric` for status counters
- `.t-ellipsis` for compact radar rows
- `.t-badge-btn` for tiny button-like badges

### CSS-only Components

Torminal includes:

- CSS-only dropdowns using checkbox toggles
- CSS-only tabs using radio inputs
- CSS-only modals using `:target`
- Native accordions using `<details>` and `<summary>`
- Toggle switches
- Range sliders
- Empty states
- Terminal windows
- Splash screens

---

## CSS-only Tabs Example

```html
<div class="t-tabs-wrapper">
    <input class="t-tab-radio" id="tab1" name="tabs" type="radio" checked>
    <label class="t-tab-label" for="tab1">Timeline</label>

    <input class="t-tab-radio" id="tab2" name="tabs" type="radio">
    <label class="t-tab-label" for="tab2">Inbox</label>

    <div class="t-tab-content-css" id="content1">Timeline content...</div>
    <div class="t-tab-content-css" id="content2">Inbox content...</div>
</div>
```

---

## CSS-only Modal Example

```html
<a href="#help" class="t-btn outline">[ OPEN HELP ]</a>

<div id="help" class="t-modal">
    <div class="t-modal-content">
        <a href="#" class="t-modal-close-btn">X</a>
        <h2 class="t-card-title">[ Help ]</h2>
        <p>No JavaScript required.</p>
    </div>
</div>
```

---

## Privacy Notes

Torminal is designed to avoid unnecessary fingerprinting surface:

- Do not load remote fonts.
- Do not import third-party CSS.
- Do not add analytics snippets.
- Prefer native HTML controls over custom JavaScript widgets.
- Keep animation optional and honor `prefers-reduced-motion`.

The `.t-crt` overlay is aesthetic. It can be disabled if readability or performance is more important.

---

## DeadDrop Integration Notes

DeadDrop v10 pages should avoid page-level `<style>` blocks and inline `style="..."` rules. Use Torminal modules instead:

- `post-card` → `.t-post`
- `media-attachment` → `.t-media-attachment`
- `thread-quote` → `.t-quote`
- unlock panels → `.t-lock-panel` / `.t-vault-title` / `.t-lock-form`
- page navigation → `.t-toolbar`
- pagination → `.t-pagination`, `.t-page-link`, `.t-page-current`
- long IDs/onion URLs → `.t-fingerprint`

Backward-compatible aliases such as `.post-card` and `.media-attachment` remain available, but new pages should prefer the `t-*` classes.

---

## Contributing

Torminal welcomes CSS-only components and utility improvements. The rule of thumb remains:

> If it requires `<script>`, it does not belong in Torminal core.

Keep it simple, local, reusable, and Tor-friendly.
