# Architecture

> It's SVG files. But let's explain it properly anyway, because the details are interesting.

---

## The Big Picture

```
widget-templates/
│
├── [widget-name].svg     ← Each widget is one self-contained file
├── ...                   ← (20 total)
│
├── example-profile-README.md  ← Reference implementation
└── README.md                  ← Human-readable docs
```

No build system. No package manager. No compiled output. The files you see in the repo are the files users embed. That's it.

---

## What's Inside Each SVG

An SVG widget is a standard XML document with three main layers:

### 1. Structure — the SVG elements

```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 400 200" width="400" height="200">
  <!-- Background -->
  <rect width="400" height="200" fill="#1a1a2e"/>

  <!-- Content elements -->
  <text x="20" y="40" font-family="monospace" fill="#10B981">$ hello world</text>

  <!-- Animated elements -->
  <rect class="cursor" x="20" y="50" width="8" height="14" fill="#F59E0B"/>
</svg>
```

### 2. Styles — the CSS animations

```xml
<style>
  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }
  .cursor {
    animation: blink 1s step-start infinite;
  }
</style>
```

### 3. Definitions — reusable assets

```xml
<defs>
  <linearGradient id="bg" x1="0%" y1="0%" x2="100%" y2="100%">
    <stop offset="0%" style="stop-color:#1a1a2e"/>
    <stop offset="100%" style="stop-color:#16213e"/>
  </linearGradient>
  <filter id="glow">
    <feGaussianBlur stdDeviation="2" result="blur"/>
    <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
  </filter>
</defs>
```

---

## Animation Engine

All animations use CSS `@keyframes` inside the SVG's `<style>` block. This means:

- **No JavaScript required** — CSS handles everything
- **GitHub-safe** — GitHub strips `<script>` from SVGs; CSS animations survive
- **Performance-friendly** — CSS animations run on the compositor thread (GPU), not the main thread
- **Deterministic** — animations loop predictably; no state management, no bugs from async operations

Common animation patterns used across the widgets:

| Pattern | CSS technique | Used in |
|---|---|---|
| Blinking cursor | `steps()` timing + opacity | `code-editor.svg` |
| Falling text | `translateY` + staggered delays | `existential.svg`, `rain.svg` |
| Progress bars | `scaleX` from 0 to target width | `skills.svg`, `progress-tracker.svg` |
| Pulsing dots | `opacity` cycle | `status.svg`, hero banner |
| Equalizer bars | `scaleY` with staggered timing | `music-player.svg` |
| Sliding panels | `translateX` | `file-explorer.svg` |
| Animated packets | `translate` along path | `network-activity.svg` |
| Gradient shimmer | `background-position` shift | `inspiration-quote.svg` |

---

## Color Palette

The widgets use two aesthetic systems:

### Dark / Terminal Theme
Used by: `existential.svg`, `github-stats.svg`, `joke.svg`, `rain.svg`, `skills.svg`, `status.svg`, `commit-history.svg`, `contribution-graph.svg`, `system-monitor.svg`, `network-activity.svg`

| Role | Color |
|---|---|
| Background (deep) | `#0d1117` / `#1a1a2e` |
| Background (panel) | `#161b22` / `#1e293b` |
| Primary accent | `#F59E0B` (amber) |
| Secondary accent | `#2563EB` (blue) |
| Success / green | `#10B981` |
| Text (primary) | `#e6edf3` / `#cdd6f4` |
| Text (muted) | `#888` / `#555` |

### Light Theme
Used by: `file-explorer.svg`, `weather.svg`, `calendar.svg`

Standard light backgrounds (`#f8f9fa`, `#ffffff`) with colored accents.

---

## Embedding Model

```
┌─────────────────────────────────────────────────────┐
│ User's GitHub profile repository                    │
│                                                     │
│  README.md                                          │
│  └── ![Widget](./github-stats.svg)  ←── img ref    │
│                                                     │
│  github-stats.svg  ←── static file in repo          │
└─────────────────────────────────────────────────────┘
         │
         │  GitHub renders README.md
         ▼
┌─────────────────────────────────────────────────────┐
│ GitHub's markdown renderer                          │
│                                                     │
│  Fetches SVG → sanitizes it → renders inline        │
│  (strips scripts, keeps CSS animations)             │
└─────────────────────────────────────────────────────┘
         │
         ▼
┌─────────────────────────────────────────────────────┐
│ Visitor's browser                                   │
│                                                     │
│  Parses SVG XML + CSS → renders + animates          │
└─────────────────────────────────────────────────────┘
```

The key insight: GitHub's SVG sanitization removes `<script>` tags but preserves CSS, including `@keyframes`. This is why the "CSS-only animations" constraint is both a design choice and a practical requirement.

---

## What GitHub Does to Your SVG

When GitHub renders an SVG embedded in a README:

1. **Fetches** the raw SVG file from the repository
2. **Sanitizes** it — removes scripts, event handlers (`onclick`, etc.), external resource loads
3. **Wraps** it in an `<img>` element (or renders it inline depending on context)
4. **Caches** it via `camo` (GitHub's image proxy), which can cause a delay before updates appear

This means:
- `<script>` → stripped (we don't use it anyway)
- `onclick`, `onload`, etc. → stripped
- `@keyframes` CSS → **preserved** ✅
- `<style>` blocks → **preserved** ✅
- External `url()` references → may be blocked or stripped

---

## Why No External Dependencies?

Three reasons:

1. **Security** — External URLs in SVG files can be used for tracking. Users embedding these in their profiles shouldn't have to worry about that.
2. **Reliability** — External services go down. A widget that stops working because a CDN had an outage is a bad widget.
3. **GitHub compatibility** — GitHub's SVG sanitization may block or rewrite external resource references anyway.

Self-containment is a feature.
