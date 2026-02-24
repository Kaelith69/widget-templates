# Usage

Everything you need to know about actually using these widgets. From "drop it in and forget it" to "I want to change literally everything."

---

## The Basics

### Embedding a widget

```markdown
![Widget Alt Text](./widget-name.svg)
```

That's the whole thing. Everything else is optimization.

### Centering a widget (recommended)

```html
<p align="center">
  <img src="./github-stats.svg" alt="GitHub Stats" width="100%" />
</p>
```

### Two widgets side by side

```html
<p align="center">
  <img src="./music-player.svg" alt="Music Player" width="49%" />
  <img src="./weather.svg" alt="Weather" width="49%" />
</p>
```

---

## Widget-by-Widget Notes

### `existential.svg`
Matrix-style falling text animation. Works best at full width. The falling characters are CSS-animated; just embed and it runs.

### `github-stats.svg`
Displays mock GitHub statistics in a terminal window. The stats are hardcoded in the SVG — if you want different numbers, open the file and find the `<text>` elements containing the stat values.

### `joke.svg`
Shows a programming joke in a terminal window. The joke is hardcoded. To change it, find the `<text>` elements with the joke content and edit them.

### `rain.svg`
ASCII rain animation. Very meditative. Works best at medium-to-full width. Just embed it.

### `skills.svg`
Progress bar chart with a "skill issue" theme. Skill names and percentages are in `<text>` elements. The bar widths are in `<rect>` elements' `width` attributes or CSS transform values. Customizable.

### `status.svg`
Shows a status message in a terminal window. Find the `<text>` element with the status message and change it to whatever you're actually working on.

### `code-editor.svg`
VS Code-style editor showing Python code with a blinking cursor. The code content is in `<text>` elements. You can change the language label and code lines. Colors use the VS Code dark+ theme palette.

### `file-explorer.svg`
macOS Finder-style file browser with a light theme and sliding animations. File names are in `<text>` elements — change them to reflect your actual project structure if you want.

### `commit-history.svg`
GitHub-style commit history graph. Branch names and commit messages are editable `<text>` elements.

### `contribution-graph.svg`
The famous green grid. Square colors are `fill` attributes on `<rect>` elements — tweak them to match your actual activity level (or your desired activity level 👀).

### `weather.svg`
Animated weather widget. Temperature, condition text, and location are all editable `<text>` elements.

### `music-player.svg`
Spotify-style player with animated equalizer bars. Track title, artist, and album are `<text>` elements. The equalizer animation is pure CSS.

### `calendar.svg`
Monthly calendar with today highlighted. The month/year and today's date cell are hardcoded — update them when the month changes (or accept the timestamp as art).

### `system-monitor.svg`
CPU, RAM, disk, and network gauges. Values are hardcoded. Change the numbers in `<text>` elements and bar/arc widths in the geometry to reflect whatever looks good (or accurate).

### `time-zones.svg`
World clock showing multiple time zones. City names and time values are `<text>` elements. All editable.

### `network-activity.svg`
Network topology with animated data packets. Node labels are `<text>` elements. The packet animation paths are CSS-driven.

### `social-stats.svg`
Follower counts and trends for social platforms. Numbers and platform names are `<text>` elements.

### `progress-tracker.svg`
Project progress bars. Task names and completion percentages live in `<text>` elements; bar lengths are geometry values. Edit to match your actual projects.

### `inspiration-quote.svg`
Quote text and attribution are in `<text>` elements. The gradient and sparkle animation are CSS. Swap in your favorite quote.

---

## Customization Guide

### Changing Text

Open the SVG in a text editor. Find `<text>` elements:

```xml
<text x="20" y="60" font-family="monospace" font-size="14" fill="#e6edf3">
  currently writing docs
</text>
```

Change the content between the tags. Save. Done.

### Changing Colors

Find `fill="#..."` or `stroke="#..."` attributes and swap the hex value:

```xml
<!-- Original -->
<text fill="#10B981">success green text</text>

<!-- Changed to blue -->
<text fill="#2563EB">now it's blue</text>
```

For gradient colors, find `<stop>` elements inside `<linearGradient>`:

```xml
<linearGradient id="myGrad">
  <stop offset="0%" style="stop-color:#F59E0B"/>   <!-- start color -->
  <stop offset="100%" style="stop-color:#2563EB"/>  <!-- end color -->
</linearGradient>
```

### Changing Animation Speed

Find the `<style>` block in the SVG. Locate the `animation` property or `animation-duration`:

```css
/* Original: 2 second blink */
.cursor { animation: blink 2s step-start infinite; }

/* Slower: 3 second blink */
.cursor { animation: blink 3s step-start infinite; }

/* Faster: 0.8 second blink */
.cursor { animation: blink 0.8s step-start infinite; }
```

### Changing Widget Size

Modify the `width` and `height` attributes on the root `<svg>` tag. The `viewBox` defines the internal coordinate system — you usually don't need to change it.

```xml
<!-- Original: 400×200 -->
<svg viewBox="0 0 400 200" width="400" height="200">

<!-- Larger: 600×300 (scales up proportionally) -->
<svg viewBox="0 0 400 200" width="600" height="300">
```

Or just use the `width` attribute in your HTML/markdown and let it scale:

```html
<img src="./widget.svg" width="500" />
```

### Disabling an Animation

Set `animation: none` on the element's class in the `<style>` block:

```css
/* Original */
.rain-drop { animation: fall 3s linear infinite; }

/* Disabled */
.rain-drop { animation: none; }
```

---

## Example Profile Layout

Check `example-profile-README.md` in the repo root for a complete working example of how to combine multiple widgets in a GitHub profile README. It covers:

- Side-by-side widget pairs
- Full-width widgets
- Section headers
- Badge integration
- Overall layout structure

---

## Tips

- **Cache busting:** GitHub caches SVG files. After updating a widget, append `?v=2` (then `?v=3`, etc.) to the image URL in your README to force a refresh: `![Stats](./github-stats.svg?v=2)`
- **Accessibility:** Add descriptive `alt` text to all your image embeds
- **Dark mode:** Most widgets are already dark-themed and look great in GitHub's dark mode. The light-themed ones (`file-explorer.svg`, etc.) still render fine but look a bit bright.
- **Mobile:** GitHub profile READMEs are responsive. `width="100%"` widgets will scale down on mobile correctly. `width="49%"` side-by-side pairs may get tight on small screens — that's a trade-off to be aware of.
