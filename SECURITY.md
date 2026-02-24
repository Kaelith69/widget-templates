# Security Policy

## Supported Versions

This project is a collection of static SVG files. There's no server, no authentication, no database, no user accounts. The attack surface is... very small.

That said, we take security seriously — even for a folder of animated SVGs — because the files end up embedded in people's GitHub profiles and personal websites.

| Version | Supported |
|---|---|
| latest (`main`) | ✅ |
| older commits | ❌ (just use the latest) |

---

## What Could Actually Go Wrong

Fair question. The main concerns for static SVG files in a web context:

- **Malicious inline scripts** — SVG files can technically contain `<script>` tags. GitHub strips them, but other embedding contexts might not. We don't include any scripts and you shouldn't add any to contributed widgets.
- **External resource references** — `<image>`, `<use>`, or CSS `url()` pointing to external URLs could be used for tracking or content injection. We don't do this. Don't add any.
- **SVG XML injection** — if someone were to dynamically generate SVG content from user input elsewhere, that's a concern — but that's not what this repo does.

---

## Reporting a Vulnerability

Found something that looks like a security issue? Here's what to do:

**Do:** Open a [GitHub Security Advisory](https://github.com/Kaelith69/widget-templates/security/advisories/new) — it's private, it goes straight to the maintainer, it's the right tool for this.

**Don't:** Open a public issue with the vulnerability details before it's been addressed. That gives bad actors a head start.

**What to include:**
- A description of the vulnerability
- Which file(s) are affected
- Steps to reproduce or proof of concept
- Your assessment of the impact
- (Optional) a suggested fix

**What to expect:**
- An acknowledgment within a few days (this is a solo-ish project, not a security team)
- A fix or mitigation as quickly as the issue warrants
- Credit in the CHANGELOG if you want it

---

## What We Will Never Do

- Add external URL references to widget files (fonts, images, scripts)
- Include JavaScript in SVGs (GitHub strips it anyway, but it's a principle)
- Phone home from any widget file

These aren't just security policies — they're what makes the widgets trustworthy enough for people to embed in their profiles. If a PR violates these, it won't be merged.

---

Thanks for keeping this project safe. It's much appreciated.
