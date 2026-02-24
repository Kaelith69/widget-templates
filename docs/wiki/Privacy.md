# Privacy

Short version: **these widgets collect absolutely nothing.**

Longer version below, for the skeptics.

---

## What Data Do the Widgets Collect?

Zero. None. Nada. The big donut.

These are static SVG files. An SVG file cannot:
- Set cookies
- Run JavaScript (GitHub strips it; we don't include it anyway)
- Make network requests (no `<script>` tags, no `fetch()`)
- Access `localStorage` or `sessionStorage`
- Call any API
- Know who is viewing it
- Phone home to any server

When someone views your GitHub profile and sees one of these widgets, the only network request is:
1. Their browser requests the SVG file from GitHub's servers
2. GitHub's servers send the file

That's it. The widget itself initiates nothing.

---

## What About GitHub?

When you upload these SVG files to a GitHub repository and embed them in a README, GitHub:
- Stores the file in your repository (like any other file)
- Serves it through their image proxy (`camo.githubusercontent.com`) when it's rendered in a markdown page
- May log the request in their standard server logs (as they do for all traffic)

This is the same as any image you upload to GitHub. It has nothing to do with the widgets themselves.

For information about how GitHub handles your data, see [GitHub's Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).

---

## External Resources

The widgets contain **no external resource references**. No:

| What | Example | Present in these SVGs? |
|---|---|---|
| External fonts | `@font-face { src: url('https://fonts.googleapis.com/...') }` | ❌ No |
| External images | `<image href="https://example.com/image.png"/>` | ❌ No |
| External scripts | `<script src="https://...">` | ❌ No |
| Tracking pixels | `<image href="https://tracker.example.com/pixel.gif"/>` | ❌ No |
| External CSS | `<?xml-stylesheet href="https://..."/>` | ❌ No |

All fonts used are system fonts (`monospace`, `'Courier New'`, `sans-serif`) — no web font loading.

All colors are inline hex values.

All animations are CSS `@keyframes` defined inline in the SVG's `<style>` block.

---

## Why Does This Matter?

If you embed a widget that makes an external network request:
1. Someone can track who views your profile (they see a request from each visitor's IP address)
2. If that external service goes down, your widget breaks
3. GitHub may sanitize or block the external resource anyway

By keeping everything self-contained, the widgets are:
- **Private** — no third party learns anything from visitors viewing your profile
- **Reliable** — no external dependencies that can fail
- **GitHub-compatible** — nothing to be stripped by GitHub's SVG sanitizer

---

## Contribution Policy

We enforce this in code review: **no PRs will be merged that introduce external resource references** of any kind. This isn't just a privacy preference — it's what makes these widgets trustworthy enough for people to embed in their profiles without having to audit each file.

If you're contributing a new widget, please review the [Architecture](Architecture) page to understand what's allowed and what isn't.

---

## Contact

If you believe a widget contains a privacy violation (external tracking, unexpected network call, etc.), please report it via [GitHub Security Advisory](https://github.com/Kaelith69/widget-templates/security/advisories/new) or open an issue. We take this seriously.
