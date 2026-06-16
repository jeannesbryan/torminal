# > TORMINAL CSS_ 📟
**The Zero-JS, Tor-Friendly Terminal UI Framework**

![CSS3](https://img.shields.io/badge/CSS3-Pure-1572B6?style=for-the-badge&logo=css3)
![Zero JS](https://img.shields.io/badge/JavaScript-0%25-F7DF1E?style=for-the-badge)
![Tor Friendly](https://img.shields.io/badge/Tor-Optimized-7D4698?style=for-the-badge&logo=tor)

Torminal CSS is a lightweight, dependency-free CSS framework designed specifically to build cyberpunk, terminal-inspired user interfaces. It is heavily optimized for privacy-first environments like the Tor Browser, relying strictly on native HTML5 and CSS3 without a single line of JavaScript.

---

### ⚡ FEATURES
* **Zero JavaScript:** Interactive components (Modals, Tabs, Dropdowns, Accordions) are built entirely using advanced CSS hacks (`:checked`, `:target`).
* **Tor & Privacy Optimized:** Prevents browser fingerprinting by utilizing safe system font stacks and explicitly supporting `@media (prefers-reduced-motion: reduce)` for users on strict security settings.
* **CRT Aesthetic:** Built-in screen flickers, text glowing, and a subtle scanline overlay (`.t-crt`) to mimic vintage monitors.
* **Responsive Grid:** A lightweight flexbox and grid utility system tailored for minimal layouts.

### 🚀 QUICK START
Since Torminal is a standalone stylesheet, installation is as simple as dropping the file into your project.

1. Download `torminal.css`.
2. Link it in your `<head>` tag:
```html
<link rel="stylesheet" href="assets/torminal.css">
```
3. Add the `.t-crt` class to your `<body>` to enable the full terminal monitor effect.

```html
<body class="t-crt">
    <div class="t-container">
        <h1 class="t-glow">> HELLO_WORLD_</h1>
        <button class="t-btn">[ EXECUTE ]</button>
    </div>
</body>
```

### 🧩 INCLUDED COMPONENTS
* **Forms & Inputs** (Styled `.t-input`, `.t-textarea`, CSS-only Checkboxes)
* **CSS-Only Modals** (Using target pseudo-classes)
* **Native HTML5 Accordions** (Styled `<details>` and `<summary>`)
* **Terminal Windows & Cards** (`.t-window`, `.t-card`)
* **Splash Screens** (Auto-hiding via CSS animations)
* **Alerts & Badges**

### 🤝 CONTRIBUTING
This project is continuously developed. If you want to add new CSS-only components or alternative color schemes, feel free to submit a Pull Request.

> **Rule of thumb:** If it requires `<script>`, it does not belong here. Keep it raw, keep it CSS.