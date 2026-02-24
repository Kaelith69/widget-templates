# Contributing to widget-templates

Hey! You want to contribute? Genuinely didn't expect that, but I'm delighted. Pull up a chair. Let's do this.

---

## 🤔 Before You Start

Check the open issues first. If you have an idea for a new widget or spotted a bug, open an issue and let's talk about it before you spend three hours on a PR that conflicts with something already in progress. Communication: invented for a reason.

---

## 🌿 Branching Model

We keep it simple because this is a collection of SVG files, not the Linux kernel.

```
main                    ← stable, what people actually use
└── feature/your-widget ← your new widget or improvement
└── fix/animation-bug   ← fixing something broken
└── docs/improve-readme ← documentation improvements
```

**Rules:**
- Branch off `main`
- Name your branch descriptively: `feature/gruvbox-terminal-widget`, `fix/rain-animation-loop`, `docs/add-wiki-page`
- Open a PR to merge back into `main`
- Don't push directly to `main` (the repo will be disappointed in you)

---

## ✍️ Commit Style

We follow [Conventional Commits](https://www.conventionalcommits.org/) because it makes the changelog write itself (mostly).

```
feat: add catppuccin-themed terminal widget
fix: correct rain animation loop timing
docs: update installation guide
chore: clean up SVG whitespace
refactor: simplify music-player keyframe logic
```

Keep messages short and in present tense. "Add widget" not "Added widget" not "I added a widget and it was really hard."

---

## 🖼️ Adding a New Widget

1. Create a new `.svg` file in the root of the repo
2. Keep it self-contained — **no external URLs, no web fonts loaded from CDNs, no remote anything**
3. All animations must be CSS `@keyframes` inside a `<style>` block within the SVG
4. Target file size: **under 10KB** (most are well under this — don't go wild with path data)
5. Test it in a browser by just opening the file
6. Test it in a GitHub Markdown file by embedding it as `![test](./yourwidget.svg)` — GitHub has quirks
7. Add it to the widget table in `README.md`
8. Add it to `example-profile-README.md` if it fits naturally in a profile layout

---

## 🔧 Modifying an Existing Widget

- Keep the existing style/theme consistent
- Don't break backward compatibility (people have these in their live profiles)
- If you're changing colors or layout significantly, consider making a new variant file instead

---

## 📐 SVG Guidelines

- Use a sensible `viewBox` — most widgets use something like `viewBox="0 0 400 200"`
- Set explicit `width` and `height` attributes so GitHub renders them at a reasonable default size
- Use `font-family="monospace"` or `font-family="'Courier New', monospace"` for terminal-style text — these are safe system fonts
- Use `text-anchor="middle"` for centered text
- Avoid JavaScript inside SVGs — GitHub strips it anyway and it breaks the "zero JS" vibe
- Avoid `<image>` tags that reference external URLs

---

## ✅ PR Checklist

Before submitting your pull request, make sure:

- [ ] The SVG opens correctly in a browser
- [ ] The SVG renders in a GitHub markdown file (test in a fork or gist)
- [ ] File is under 10KB
- [ ] No external URL references in the SVG
- [ ] README.md updated if you added a new widget
- [ ] Commit messages follow Conventional Commits format
- [ ] You have not introduced any tracking pixels, analytics, or external dependencies (yes, even "just a font")

---

## 🐛 Reporting Bugs

Open an issue with:
- Which widget is broken
- What browser/OS you're on
- A screenshot or description of what you expected vs. what happened
- Bonus points: the fix already included

---

## 💬 Code of Conduct

Be cool. This is a fun project about SVG widgets, not a place to have arguments. Treat people with respect. Don't be the person who makes open source unfun.

---

Thanks for contributing. You're making profile READMEs everywhere slightly more interesting, and that matters. Sort of.
