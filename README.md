<p align="center">
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 860 180" width="860" height="180">
  <defs>
    <linearGradient id="heroBg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a1a2e"/>
      <stop offset="100%" style="stop-color:#16213e"/>
    </linearGradient>
    <linearGradient id="titleGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#F59E0B"/>
      <stop offset="50%" style="stop-color:#2563EB"/>
      <stop offset="100%" style="stop-color:#10B981"/>
    </linearGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <style>
      @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.5} }
      @keyframes slideIn { from{opacity:0;transform:translateX(-20px)} to{opacity:1;transform:translateX(0)} }
      .dot1{animation:pulse 2s ease-in-out infinite}
      .dot2{animation:pulse 2s ease-in-out 0.3s infinite}
      .dot3{animation:pulse 2s ease-in-out 0.6s infinite}
      .tagline{animation:slideIn 1s ease-out 0.5s both}
    </style>
  </defs>
  <rect width="860" height="180" rx="14" fill="url(#heroBg)"/>
  <rect x="0" y="0" width="860" height="36" rx="14" fill="#0d0d1a"/>
  <rect x="0" y="22" width="860" height="14" fill="#0d0d1a"/>
  <circle cx="28" cy="18" r="7" fill="#FF5F57" class="dot1"/>
  <circle cx="50" cy="18" r="7" fill="#FFBD2E" class="dot2"/>
  <circle cx="72" cy="18" r="7" fill="#28CA41" class="dot3"/>
  <text x="430" y="22" font-family="monospace" font-size="12" fill="#888" text-anchor="middle">widget-templates — zsh</text>
  <text x="430" y="100" font-family="'Courier New', monospace" font-size="48" font-weight="bold"
        fill="url(#titleGrad)" text-anchor="middle" filter="url(#glow)">widget-templates</text>
  <text x="430" y="138" font-family="monospace" font-size="14" fill="#10B981"
        text-anchor="middle" class="tagline">✦ animated SVG widgets that make your GitHub profile go brrr ✦</text>
  <rect x="350" y="152" width="160" height="20" rx="10" fill="#F59E0B" opacity="0.15"/>
  <text x="430" y="166" font-family="monospace" font-size="11" fill="#F59E0B"
        text-anchor="middle">20 widgets · zero dependencies · pure SVG</text>
</svg>
</p>

---

> You know that feeling when your GitHub profile is just... a wall of text? Yeah. This fixes that.
> **widget-templates** is a collection of 20 hand-crafted, animated SVG widgets you can drop straight into any GitHub profile README or personal website — no npm, no build step, no existential dread (well, there's one widget for that).

---

## Badges

<p align="center">

![Widgets](https://img.shields.io/badge/widgets-20-F59E0B?style=for-the-badge&logo=svg&logoColor=white)
![Dependencies](https://img.shields.io/badge/dependencies-0-10B981?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-2563EB?style=for-the-badge)
![Platform](https://img.shields.io/badge/platform-GitHub%20%7C%20Web-6366F1?style=for-the-badge)
![Format](https://img.shields.io/badge/format-SVG-orange?style=for-the-badge&logo=svg)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-10B981?style=for-the-badge)

</p>

---

## 🎬 Live Demo

> **Place demo GIF here:** `assets/demo.gif`

![Demo](assets/demo.gif)

*The GIF should show:*
- *Scrolling through several widgets rendered in a browser or GitHub profile*
- *The animations playing (falling text in `existential.svg`, equalizer bars in `music-player.svg`, rain in `rain.svg`)*
- *A quick side-by-side of the dark terminal widgets vs. the light file-explorer widget*
- *Optional: a terminal showing the copy-paste workflow (open SVG → paste in README → push → profit)*

---

## 🧠 System Overview

This isn't a framework, a SaaS, or a startup with a YC badge. It's a folder of SVGs that are really good at being SVGs.

Each widget is:
- A **single `.svg` file** — self-contained, no external resources
- Animated entirely with **inline CSS `@keyframes`**
- Themed around either a **dark terminal aesthetic** or a **light macOS/web aesthetic**
- Embeddable with one line of markdown

Think of it as a widget vending machine. You pick one, you drop it in your README, done. The widget does its little animation dance forever and you look like you spent three weekends on your profile when it was actually 30 seconds.

---

## ✨ Features

### Terminal-Style Widgets (Dark Theme 🖤)
| Widget | What it does |
|---|---|
| `existential.svg` | Matrix-style falling text. For when you want your profile to ask the hard questions. |
| `github-stats.svg` | Mock GitHub stats in a terminal window. Very official looking. |
| `joke.svg` | A programming joke widget. Humor as a service. |
| `rain.svg` | ASCII rain animation. Therapeutic. Actually calming. |
| `skills.svg` | "Skill issue" progress bar chart. Self-aware. Accurate. |
| `status.svg` | Current status/activity display. What are you even doing right now. |

### Code & File Widgets 📁
| Widget | What it does |
|---|---|
| `code-editor.svg` | VS Code-style editor with syntax-highlighted Python and a blinking cursor. You look productive. |
| `file-explorer.svg` | macOS Finder-style file explorer with slide animations. Light theme gang. |

### Git Widgets 🌿
| Widget | What it does |
|---|---|
| `commit-history.svg` | GitHub-style commit history with branch visualization. |
| `contribution-graph.svg` | That green contribution grid. But make it widget. |

### Utility Widgets 🛠️
| Widget | What it does |
|---|---|
| `weather.svg` | Animated sun, clouds, weather info. Vibes. |
| `music-player.svg` | Spotify-style player with animated equalizer bars. Currently playing: lo-fi. |
| `calendar.svg` | Monthly calendar, today highlighted. Time is a construct but at least it's animated. |
| `system-monitor.svg` | CPU, RAM, disk, network. For the sysadmin in all of us. |
| `time-zones.svg` | World clock for multiple time zones. For when you collaborate globally and forget what time it is. |
| `network-activity.svg` | Network topology with animated data packets. It looks like you understand networking. |

### Social & Progress Widgets 📊
| Widget | What it does |
|---|---|
| `social-stats.svg` | Social media follower counts and growth trends. |
| `progress-tracker.svg` | Project progress bars with animated checkmarks. You're almost done. |
| `inspiration-quote.svg` | Inspirational quote with sparkles and gradient. It's fine. We're fine. |

---

## 🗺️ Capability Visualization

<p align="center">
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 740 360" width="740" height="360">
  <defs>
    <style>
      @keyframes fadeIn { from{opacity:0} to{opacity:1} }
      .cap-card { animation: fadeIn 0.8s ease both }
    </style>
  </defs>
  <rect width="740" height="360" rx="12" fill="#0d1117"/>
  <text x="370" y="32" font-family="monospace" font-size="13" fill="#888" text-anchor="middle">// capability map</text>

  <rect x="30" y="50" width="200" height="130" rx="8" fill="#161b22" stroke="#F59E0B" stroke-width="1.5" class="cap-card" style="animation-delay:0.1s"/>
  <text x="130" y="72" font-family="monospace" font-size="11" fill="#F59E0B" text-anchor="middle" font-weight="bold">TERMINAL WIDGETS</text>
  <text x="50" y="94" font-family="monospace" font-size="10" fill="#ccc">▸ existential.svg</text>
  <text x="50" y="110" font-family="monospace" font-size="10" fill="#ccc">▸ github-stats.svg</text>
  <text x="50" y="126" font-family="monospace" font-size="10" fill="#ccc">▸ joke.svg</text>
  <text x="50" y="142" font-family="monospace" font-size="10" fill="#ccc">▸ rain.svg</text>
  <text x="50" y="158" font-family="monospace" font-size="10" fill="#ccc">▸ skills.svg  ▸ status.svg</text>

  <rect x="270" y="50" width="200" height="130" rx="8" fill="#161b22" stroke="#2563EB" stroke-width="1.5" class="cap-card" style="animation-delay:0.2s"/>
  <text x="370" y="72" font-family="monospace" font-size="11" fill="#2563EB" text-anchor="middle" font-weight="bold">CODE &amp; FILE</text>
  <text x="290" y="94" font-family="monospace" font-size="10" fill="#ccc">▸ code-editor.svg</text>
  <text x="290" y="110" font-family="monospace" font-size="10" fill="#ccc">▸ file-explorer.svg</text>
  <text x="290" y="134" font-family="monospace" font-size="11" fill="#4ade80">Git Widgets</text>
  <text x="290" y="152" font-family="monospace" font-size="10" fill="#ccc">▸ commit-history.svg</text>
  <text x="290" y="168" font-family="monospace" font-size="10" fill="#ccc">▸ contribution-graph.svg</text>

  <rect x="510" y="50" width="200" height="130" rx="8" fill="#161b22" stroke="#10B981" stroke-width="1.5" class="cap-card" style="animation-delay:0.3s"/>
  <text x="610" y="72" font-family="monospace" font-size="11" fill="#10B981" text-anchor="middle" font-weight="bold">UTILITY WIDGETS</text>
  <text x="530" y="94" font-family="monospace" font-size="10" fill="#ccc">▸ weather.svg</text>
  <text x="530" y="110" font-family="monospace" font-size="10" fill="#ccc">▸ music-player.svg</text>
  <text x="530" y="126" font-family="monospace" font-size="10" fill="#ccc">▸ calendar.svg</text>
  <text x="530" y="142" font-family="monospace" font-size="10" fill="#ccc">▸ system-monitor.svg</text>
  <text x="530" y="158" font-family="monospace" font-size="10" fill="#ccc">▸ time-zones.svg</text>

  <rect x="30" y="210" width="200" height="110" rx="8" fill="#161b22" stroke="#a855f7" stroke-width="1.5" class="cap-card" style="animation-delay:0.4s"/>
  <text x="130" y="232" font-family="monospace" font-size="11" fill="#a855f7" text-anchor="middle" font-weight="bold">SOCIAL &amp; PROGRESS</text>
  <text x="50" y="254" font-family="monospace" font-size="10" fill="#ccc">▸ social-stats.svg</text>
  <text x="50" y="270" font-family="monospace" font-size="10" fill="#ccc">▸ progress-tracker.svg</text>
  <text x="50" y="286" font-family="monospace" font-size="10" fill="#ccc">▸ inspiration-quote.svg</text>
  <text x="50" y="302" font-family="monospace" font-size="10" fill="#ccc">▸ network-activity.svg</text>

  <rect x="270" y="210" width="440" height="110" rx="8" fill="#161b22" stroke="#F59E0B" stroke-width="1" stroke-dasharray="4 2" class="cap-card" style="animation-delay:0.5s"/>
  <text x="490" y="232" font-family="monospace" font-size="11" fill="#F59E0B" text-anchor="middle" font-weight="bold">CORE PROPERTIES (all widgets)</text>
  <text x="290" y="256" font-family="monospace" font-size="10" fill="#10B981">✓ Zero external dependencies</text>
  <text x="290" y="272" font-family="monospace" font-size="10" fill="#10B981">✓ Pure SVG + CSS animations</text>
  <text x="290" y="288" font-family="monospace" font-size="10" fill="#10B981">✓ Embeds in GitHub markdown</text>
  <text x="510" y="256" font-family="monospace" font-size="10" fill="#10B981">✓ Text editor customizable</text>
  <text x="510" y="272" font-family="monospace" font-size="10" fill="#10B981">✓ Under 10KB each</text>
  <text x="510" y="288" font-family="monospace" font-size="10" fill="#10B981">✓ Browser compatible</text>
  <text x="370" y="345" font-family="monospace" font-size="12" fill="#555" text-anchor="middle">20 widgets total — pick your poison</text>
</svg>
</p>

---

## 🏗️ Architecture

> It's not that complicated. That's the point.

<p align="center">
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 740 320" width="740" height="320">
  <defs>
    <marker id="arrowA" markerWidth="8" markerHeight="8" refX="4" refY="4" orient="auto">
      <path d="M0,0 L8,4 L0,8 Z" fill="#555"/>
    </marker>
  </defs>
  <rect width="740" height="320" rx="12" fill="#0d1117"/>
  <text x="370" y="28" font-family="monospace" font-size="13" fill="#888" text-anchor="middle">// architecture diagram</text>

  <rect x="300" y="44" width="140" height="44" rx="8" fill="#1e293b" stroke="#F59E0B" stroke-width="1.5"/>
  <text x="370" y="61" font-family="monospace" font-size="11" fill="#F59E0B" text-anchor="middle">👤 User</text>
  <text x="370" y="78" font-family="monospace" font-size="9" fill="#888" text-anchor="middle">picks a widget SVG</text>

  <line x1="370" y1="88" x2="370" y2="112" stroke="#555" stroke-width="1.5" marker-end="url(#arrowA)"/>

  <rect x="220" y="112" width="300" height="44" rx="8" fill="#1e293b" stroke="#2563EB" stroke-width="1.5"/>
  <text x="370" y="129" font-family="monospace" font-size="11" fill="#2563EB" text-anchor="middle">📁 widget-templates repo</text>
  <text x="370" y="146" font-family="monospace" font-size="9" fill="#888" text-anchor="middle">20 × .svg files (static, self-contained)</text>

  <line x1="370" y1="156" x2="370" y2="180" stroke="#555" stroke-width="1.5"/>
  <line x1="200" y1="180" x2="540" y2="180" stroke="#555" stroke-width="1.5"/>
  <line x1="200" y1="180" x2="200" y2="204" stroke="#555" stroke-width="1.5" marker-end="url(#arrowA)"/>
  <line x1="540" y1="180" x2="540" y2="204" stroke="#555" stroke-width="1.5" marker-end="url(#arrowA)"/>

  <rect x="80" y="204" width="240" height="44" rx="8" fill="#1e293b" stroke="#10B981" stroke-width="1.5"/>
  <text x="200" y="221" font-family="monospace" font-size="11" fill="#10B981" text-anchor="middle">🐙 GitHub Profile README</text>
  <text x="200" y="238" font-family="monospace" font-size="9" fill="#888" text-anchor="middle">![Widget](./widget.svg)</text>

  <rect x="420" y="204" width="240" height="44" rx="8" fill="#1e293b" stroke="#a855f7" stroke-width="1.5"/>
  <text x="540" y="221" font-family="monospace" font-size="11" fill="#a855f7" text-anchor="middle">🌐 Personal Website / HTML</text>
  <text x="540" y="238" font-family="monospace" font-size="9" fill="#888" text-anchor="middle">&lt;img src="widget.svg" /&gt;</text>

  <line x1="200" y1="248" x2="200" y2="268" stroke="#555" stroke-width="1.5"/>
  <line x1="540" y1="248" x2="540" y2="268" stroke="#555" stroke-width="1.5"/>
  <line x1="200" y1="268" x2="540" y2="268" stroke="#555" stroke-width="1.5"/>
  <line x1="370" y1="268" x2="370" y2="278" stroke="#555" stroke-width="1.5" marker-end="url(#arrowA)"/>

  <rect x="280" y="278" width="180" height="30" rx="8" fill="#1e293b" stroke="#F59E0B" stroke-width="1.5"/>
  <text x="370" y="298" font-family="monospace" font-size="11" fill="#F59E0B" text-anchor="middle">🌍 Browser renders SVG</text>

  <text x="680" y="200" font-family="monospace" font-size="9" fill="#555" text-anchor="middle">no server</text>
  <text x="680" y="214" font-family="monospace" font-size="9" fill="#555" text-anchor="middle">no runtime</text>
  <text x="680" y="228" font-family="monospace" font-size="9" fill="#555" text-anchor="middle">no magic</text>
  <text x="680" y="242" font-family="monospace" font-size="9" fill="#555" text-anchor="middle">just files</text>
</svg>
</p>

---

## 🌊 Data Flow

<p align="center">
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 740 200" width="740" height="200">
  <defs>
    <marker id="arrowB" markerWidth="8" markerHeight="8" refX="4" refY="4" orient="auto">
      <path d="M0,0 L8,4 L0,8 Z" fill="#F59E0B"/>
    </marker>
    <style>
      @keyframes flow {
        0% { stroke-dashoffset: 20; }
        100% { stroke-dashoffset: 0; }
      }
      .flow-line { stroke-dasharray: 6 4; animation: flow 1s linear infinite; }
    </style>
  </defs>
  <rect width="740" height="200" rx="12" fill="#0d1117"/>
  <text x="370" y="24" font-family="monospace" font-size="12" fill="#888" text-anchor="middle">// data flow — from widget to your screen</text>

  <rect x="20" y="60" width="120" height="80" rx="8" fill="#1e293b" stroke="#F59E0B" stroke-width="1.5"/>
  <text x="80" y="96" font-family="monospace" font-size="10" fill="#F59E0B" text-anchor="middle">1. SVG File</text>
  <text x="80" y="112" font-family="monospace" font-size="9" fill="#888" text-anchor="middle">static asset</text>
  <text x="80" y="128" font-family="monospace" font-size="9" fill="#888" text-anchor="middle">on disk</text>

  <line x1="140" y1="100" x2="175" y2="100" stroke="#F59E0B" stroke-width="1.5" marker-end="url(#arrowB)" class="flow-line"/>

  <rect x="175" y="60" width="140" height="80" rx="8" fill="#1e293b" stroke="#2563EB" stroke-width="1.5"/>
  <text x="245" y="96" font-family="monospace" font-size="10" fill="#2563EB" text-anchor="middle">2. README.md</text>
  <text x="245" y="112" font-family="monospace" font-size="9" fill="#888" text-anchor="middle">markdown img ref</text>
  <text x="245" y="128" font-family="monospace" font-size="9" fill="#888" text-anchor="middle">![w](./w.svg)</text>

  <line x1="315" y1="100" x2="350" y2="100" stroke="#F59E0B" stroke-width="1.5" marker-end="url(#arrowB)" class="flow-line"/>

  <rect x="350" y="60" width="140" height="80" rx="8" fill="#1e293b" stroke="#10B981" stroke-width="1.5"/>
  <text x="420" y="96" font-family="monospace" font-size="10" fill="#10B981" text-anchor="middle">3. GitHub CDN</text>
  <text x="420" y="112" font-family="monospace" font-size="9" fill="#888" text-anchor="middle">caches &amp; serves</text>
  <text x="420" y="128" font-family="monospace" font-size="9" fill="#888" text-anchor="middle">raw SVG bytes</text>

  <line x1="490" y1="100" x2="525" y2="100" stroke="#F59E0B" stroke-width="1.5" marker-end="url(#arrowB)" class="flow-line"/>

  <rect x="525" y="60" width="140" height="80" rx="8" fill="#1e293b" stroke="#a855f7" stroke-width="1.5"/>
  <text x="595" y="88" font-family="monospace" font-size="10" fill="#a855f7" text-anchor="middle">4. Browser</text>
  <text x="595" y="104" font-family="monospace" font-size="9" fill="#888" text-anchor="middle">parses SVG + CSS</text>
  <text x="595" y="120" font-family="monospace" font-size="9" fill="#888" text-anchor="middle">runs animations</text>
  <text x="595" y="136" font-family="monospace" font-size="9" fill="#888" text-anchor="middle">renders frames</text>

  <text x="370" y="180" font-family="monospace" font-size="10" fill="#555" text-anchor="middle">zero network calls from the widget itself · all animation logic is inline CSS</text>
</svg>
</p>

---

## 📦 Installation

No `npm install`. No `pip install`. No `brew install`. The audacity of it all.

### Option A: GitHub Profile README (most common)

**Step 1:** Copy or download the SVG file(s) you want.

**Step 2:** Upload them to your GitHub profile repository (the one named `<your-username>/<your-username>`).

**Step 3:** Reference them in your `README.md`:

```markdown
![GitHub Stats](./github-stats.svg)
```

Or with HTML for alignment control:
```html
<p align="center">
  <img src="./github-stats.svg" alt="GitHub Stats" width="100%" />
</p>
```

### Option B: Personal Website / HTML project

```html
<!-- Drop-in as an image -->
<img src="path/to/skills.svg" alt="Skills" style="max-width: 100%;" />

<!-- Or inline the SVG directly in your HTML for CSS/JS control -->
<!-- Just paste the SVG file contents right into your HTML -->
```

### Option C: Clone the whole repo

```bash
git clone https://github.com/Kaelith69/widget-templates.git
cd widget-templates
# Pick your widgets, copy them, customize, go
```

---

## 🚀 Usage

### Basic embed

```markdown
![Existential Crisis](./existential.svg)
```

### Centered layout (recommended)

```html
<p align="center">
  <img src="./github-stats.svg" alt="GitHub Stats" width="49%" />
  <img src="./contribution-graph.svg" alt="Contributions" width="49%" />
</p>
```

### Customizing text

Open any SVG in a text editor (VS Code works great), find `<text>` tags, change the content:

```xml
<!-- Before -->
<text x="16" y="48">skill issue</text>

<!-- After -->
<text x="16" y="48">i know what i'm doing</text>
```

### Customizing colors

Find `fill="#..."` attributes and swap them out:

```xml
<!-- Change a color -->
<text fill="#10B981">was green, now whatever you want</text>
<rect fill="#1a1a2e"/>
```

### Customizing animations

Find the `<style>` block inside the SVG and tweak `animation-duration`, `animation-delay`, etc.:

```css
.my-animation {
  animation-duration: 3s;   /* slower = more chill */
  animation-delay: 0.2s;
}
```

### Sizing

Adjust `viewBox` and `width`/`height` on the root `<svg>` tag:

```xml
<svg viewBox="0 0 400 200" width="400" height="200">
```

---

## 📂 Project Structure

```
widget-templates/
├── existential.svg          # Matrix rain + existential vibes
├── github-stats.svg         # Terminal: mock GitHub stats
├── joke.svg                 # Terminal: programming joke
├── rain.svg                 # Terminal: ASCII rain animation
├── skills.svg               # Terminal: skill progress bars
├── status.svg               # Terminal: current status
├── code-editor.svg          # VS Code-style Python editor
├── file-explorer.svg        # macOS Finder-style explorer
├── commit-history.svg       # GitHub-style commit graph
├── contribution-graph.svg   # GitHub contribution grid
├── weather.svg              # Animated weather widget
├── music-player.svg         # Spotify-style player
├── calendar.svg             # Monthly calendar
├── system-monitor.svg       # CPU/RAM/disk/network stats
├── time-zones.svg           # World clock
├── network-activity.svg     # Network topology viz
├── social-stats.svg         # Social media stats
├── progress-tracker.svg     # Project progress bars
├── inspiration-quote.svg    # Quotes with sparkles
├── example-profile-README.md # Full example README layout
└── README.md                # You are here
```

---

## 📊 Performance Stats

<p align="center">
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 740 200" width="740" height="200">
  <rect width="740" height="200" rx="12" fill="#0d1117"/>
  <text x="370" y="28" font-family="monospace" font-size="13" fill="#888" text-anchor="middle">// performance profile</text>

  <rect x="20" y="44" width="160" height="120" rx="8" fill="#161b22" stroke="#F59E0B" stroke-width="1"/>
  <text x="100" y="74" font-family="monospace" font-size="28" fill="#F59E0B" text-anchor="middle" font-weight="bold">&lt;10KB</text>
  <text x="100" y="94" font-family="monospace" font-size="10" fill="#888" text-anchor="middle">per widget</text>
  <text x="100" y="130" font-family="monospace" font-size="9" fill="#555" text-anchor="middle">small enough to</text>
  <text x="100" y="144" font-family="monospace" font-size="9" fill="#555" text-anchor="middle">fit in a tweet (almost)</text>

  <rect x="200" y="44" width="160" height="120" rx="8" fill="#161b22" stroke="#2563EB" stroke-width="1"/>
  <text x="280" y="74" font-family="monospace" font-size="28" fill="#2563EB" text-anchor="middle" font-weight="bold">0ms</text>
  <text x="280" y="94" font-family="monospace" font-size="10" fill="#888" text-anchor="middle">JS runtime</text>
  <text x="280" y="130" font-family="monospace" font-size="9" fill="#555" text-anchor="middle">CSS animations only.</text>
  <text x="280" y="144" font-family="monospace" font-size="9" fill="#555" text-anchor="middle">zero JS executed.</text>

  <rect x="380" y="44" width="160" height="120" rx="8" fill="#161b22" stroke="#10B981" stroke-width="1"/>
  <text x="460" y="74" font-family="monospace" font-size="28" fill="#10B981" text-anchor="middle" font-weight="bold">0</text>
  <text x="460" y="94" font-family="monospace" font-size="10" fill="#888" text-anchor="middle">dependencies</text>
  <text x="460" y="130" font-family="monospace" font-size="9" fill="#555" text-anchor="middle">no node_modules.</text>
  <text x="460" y="144" font-family="monospace" font-size="9" fill="#555" text-anchor="middle">no supply chain anxiety.</text>

  <rect x="560" y="44" width="160" height="120" rx="8" fill="#161b22" stroke="#a855f7" stroke-width="1"/>
  <text x="640" y="74" font-family="monospace" font-size="28" fill="#a855f7" text-anchor="middle" font-weight="bold">20</text>
  <text x="640" y="94" font-family="monospace" font-size="10" fill="#888" text-anchor="middle">widgets</text>
  <text x="640" y="130" font-family="monospace" font-size="9" fill="#555" text-anchor="middle">for every mood,</text>
  <text x="640" y="144" font-family="monospace" font-size="9" fill="#555" text-anchor="middle">aesthetic, and identity crisis.</text>
</svg>
</p>

---

## 🔒 Privacy

These widgets are static files. They phone home to exactly **nobody**.

- No analytics, no tracking pixels, no "we use cookies" banners
- No API calls, no external CDN dependencies
- No user data collected, stored, or sold to fund someone's Series A
- The only network request is GitHub (or your web server) serving the `.svg` file itself

The most private thing about these widgets is that they will never know who's looking at them. Philosophical, really.

---

## 🔭 Future Roadmap

*Things that would be cool to have (no promises, no Jira tickets):*

- [ ] Dark/light theme variants for all widgets
- [ ] More terminal widget themes (gruvbox, solarized, catppuccin)
- [ ] Interactive SVG widgets with JavaScript (opt-in, clearly labeled)
- [ ] More language support for `code-editor.svg` (JS, Rust, Go snippets)
- [ ] A widget picker / preview tool (a simple HTML page in the repo)
- [ ] Automated testing to catch broken SVG animations
- [ ] GitHub Actions to auto-validate SVG syntax on PRs
- [ ] A "random widget" showcase in the README
- [ ] Accessibility improvements (ARIA labels, reduced-motion support)

---

## 📄 License

MIT — see [LICENSE](LICENSE) for the full legal monologue.

TL;DR: do whatever you want with these, just don't sue me.
