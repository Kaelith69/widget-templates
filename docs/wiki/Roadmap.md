# Roadmap

Where widget-templates is going. Or might go. Or wants to go, circumstances permitting.

These aren't promises. They're ideas on a whiteboard. If something here resonates with you, open an issue or a PR — that's the fastest way to make it happen.

---

## 🟢 Done (v1.0.0)

- [x] 20 core widgets across 5 categories (terminal, code/file, git, utility, social/progress)
- [x] CSS-only animations (no JavaScript dependency)
- [x] Self-contained SVG files (zero external resources)
- [x] GitHub markdown compatible
- [x] Example profile README (`example-profile-README.md`)
- [x] README documentation

---

## 🟡 Up Next (Near-term)

These are things that are pretty clearly worth doing and not hugely complex:

- [ ] **`prefers-reduced-motion` support** — add `@media (prefers-reduced-motion: reduce)` to all widget styles so people with motion sensitivity get a static version instead of animations. This is an accessibility must-have.

- [ ] **Dark/light theme variants** — some widgets are dark-only; some are light-only. Give all of them both. Naming convention: `weather-dark.svg` / `weather-light.svg` or a `theme` attribute approach.

- [ ] **More terminal color schemes** — the current terminal widgets use a custom dark palette. Variants in gruvbox, catppuccin mocha, solarized dark, and Tokyo Night would make a lot of people happy.

- [ ] **SVG linting / validation in CI** — a GitHub Actions workflow that validates SVG syntax on every PR. Catches broken XML before it lands in `main`. Would use a tool like `xmllint` or a custom validator.

- [ ] **Contribution graph: accurate date rendering** — the current `contribution-graph.svg` has a hardcoded date grid. A script to generate an accurate version (or documentation on how to update the date labels) would be useful.

---

## 🔵 Medium-term Ideas

Things that would meaningfully expand what the project can do:

- [ ] **Widget preview page** — a simple `preview.html` in the repo that renders all widgets side by side in a browser. No server needed, just open the file locally. Would make it much easier to browse widgets without reading the README.

- [ ] **More language snippets for `code-editor.svg`** — currently shows Python. Variants or a customization guide for JavaScript, Rust, Go, TypeScript, and other popular languages.

- [ ] **`calendar.svg` auto-date** — the calendar currently has a hardcoded date. Either a build script to regenerate it, or a note in the docs about updating it monthly, would help.

- [ ] **Animated text variants** — some widgets (like `status.svg`) have static text. A version with a typewriter animation effect for the text would look great.

- [ ] **Accessibility audit** — add `role`, `aria-label`, and `title` elements to all widgets so screen readers can describe them meaningfully.

---

## 🟣 Bigger Ideas (Long-term / Experimental)

These are more ambitious and may involve trade-offs:

- [ ] **Optional JavaScript widgets (clearly labeled)** — JavaScript would allow widgets with real-time data (actual time, actual date, randomized content). These would work on personal websites but not in GitHub's SVG sandbox. Clear labeling (`widget-name.js.svg` or a separate `/interactive` folder) would keep the distinction clear.

- [ ] **Widget generator CLI or web tool** — a simple tool where you enter your preferences (username, color scheme, stats) and it outputs a customized SVG. This is a bigger project than it sounds.

- [ ] **More widget categories** — potential new widget types:
  - Language stats bar (like wakatime but static)
  - Reading list / currently reading widget
  - Minimal ASCII art portraits
  - Terminal-style "today I learned" widget
  - Project card widget (name, description, language, stars)

- [ ] **Theming system** — a way to apply a color theme to multiple widgets at once. Probably implemented as a set of CSS custom properties with a theme file that overrides defaults.

---

## 💡 Community Suggestions

Got an idea? [Open an issue](https://github.com/Kaelith69/widget-templates/issues/new) with the label `enhancement`. Describe the widget, what it would show, and why it belongs in the collection. Best ideas get built.

The only constraint: anything new must be self-contained, CSS-only animation, and work in GitHub's SVG sandbox. That's the bar. Clear it and you're in.

---

## What's Not on the Roadmap

To set expectations:

- **Real-time data fetching from external APIs** — would require JavaScript and a server. Out of scope for this repo.
- **A full SaaS product with user accounts and dashboards** — nope.
- **React/Vue/Svelte components** — this repo is intentionally framework-free.
- **Widgets that require a build step to use** — defeats the purpose.

The magic of this project is that it's simple. The roadmap keeps it simple while making it better.
