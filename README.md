# Widget Templates

A collection of animated, terminal-style SVG widgets designed to spice up your GitHub profile README or personal website. These widgets are lightweight, customizable, and require no external dependencies.

## Available Widgets

### Terminal-Style Widgets (Dark Theme)
- **`existential.svg`**: A matrix-style falling text animation with an existential crisis theme.
- **`github-stats.svg`**: A terminal window displaying mock GitHub statistics.
- **`joke.svg`**: A terminal window fetching and displaying a programming joke.
- **`rain.svg`**: A terminal window with a soothing ASCII rain animation.
- **`skills.svg`**: A terminal window displaying a "skill issue" progress bar chart.
- **`status.svg`**: A terminal window displaying a current status or activity.

### Code Editor Widget
- **`code-editor.svg`**: A VS Code-style editor window with syntax-highlighted Python code and a blinking cursor.

### File Explorer Widget
- **`file-explorer.svg`**: A macOS Finder-style file explorer with light theme and sliding animations.

### Git Widget
- **`commit-history.svg`**: A GitHub-style commit history graph with branch visualization.

### Utility Widgets
- **`weather.svg`**: A weather widget with animated sun, clouds, and weather information.
- **`music-player.svg`**: A Spotify-style music player with animated equalizer bars and playback controls.

## How to Use

### 1. GitHub Profile README

You can easily embed these widgets in your GitHub profile `README.md` file. First, upload the SVG files to your repository.

**Using Markdown:**
```markdown
![GitHub Stats](./github-stats.svg)
```

**Using HTML (Recommended for better alignment and sizing):**
```html
<p align="center">
  <img src="./github-stats.svg" alt="GitHub Stats" width="100%" />
</p>
```

*Note: Replace `./github-stats.svg` with the correct path to the SVG file in your repository.*

### 2. Personal Website

You can use these SVGs in your HTML projects just like any other image.

```html
<img src="path/to/skills.svg" alt="Skills" />
```

Alternatively, you can embed the SVG code directly into your HTML if you want to manipulate it further with CSS or JavaScript.

## Customization

These widgets are plain SVG files, which means you can easily customize them by opening the files in any text editor (like VS Code).

1. **Change Text:** Look for `<text>` tags to modify the displayed text. For example, in `github-stats.svg`, you can change the username, repository count, or top languages to match your actual stats.
2. **Change Colors:** Look for `fill="#..."` attributes to change the colors of text, progress bars, or the terminal background. The default colors are based on the GitHub Dark theme.
3. **Adjust Animations:** The animations are controlled by CSS within the `<style>` tag at the top of each SVG file. You can tweak the `@keyframes`, `animation-delay`, and `animation-duration` to your liking.

## Example: Customizing `github-stats.svg`

Open `github-stats.svg` in your editor and find this line:
```xml
<text x="16" y="48" class="mono row r1" font-size="11" fill="#484f58">$ ./fetch_stats.sh --user kaelith69</text>
```
Change `kaelith69` to your own GitHub username:
```xml
<text x="16" y="48" class="mono row r1" font-size="11" fill="#484f58">$ ./fetch_stats.sh --user yourusername</text>
```
Save the file, and the widget will now display your username!

## Tips for Best Results

- **File Size:** These SVGs are optimized and typically under 10KB each.
- **Browser Compatibility:** All modern browsers support SVG animations.
- **Performance:** Animations are CSS-based and won't impact page performance.
- **Accessibility:** Add appropriate `alt` text when embedding in HTML.
- **Responsiveness:** Use CSS `max-width: 100%` for responsive behavior.
