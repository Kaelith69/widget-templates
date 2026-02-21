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

### Git Widgets
- **`commit-history.svg`**: A GitHub-style commit history graph with branch visualization.
- **`contribution-graph.svg`**: A GitHub-style contribution graph showing coding activity over time.

### Utility Widgets
- **`weather.svg`**: A weather widget with animated sun, clouds, and weather information.
- **`music-player.svg`**: A Spotify-style music player with animated equalizer bars and playback controls.
- **`calendar.svg`**: A monthly calendar widget with today's date highlighted.
- **`system-monitor.svg`**: A system monitoring widget showing CPU, RAM, disk usage, and network activity.
- **`time-zones.svg`**: A world clock widget displaying current time in different time zones.
- **`network-activity.svg`**: A network topology visualization with animated data packets.

### Social & Progress Widgets
- **`social-stats.svg`**: Social media statistics widget with follower counts and growth trends.
- **`progress-tracker.svg`**: Project progress tracker with animated progress bars and completion checkmarks.
- **`inspiration-quote.svg`**: Inspirational quote widget with animated sparkles and gradient background.

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

### 3. Setup Instructions

#### Step 1: Choose Your Widgets
1. Browse the available widgets above and select the ones that fit your style
2. Consider the theme (dark/light) and animation style that matches your profile
3. Think about the information you want to display (stats, activities, utilities, etc.)

#### Step 2: Upload to Repository
1. Create a new repository on GitHub (or use an existing one)
2. Upload the selected SVG files to your repository
3. Make sure the files are in the root directory or a dedicated folder

#### Step 3: Update Your README
1. Open your profile README.md file (create one if it doesn't exist)
2. Add the widget images using the markdown or HTML syntax shown above
3. Use `<p align="center">` tags for centered alignment
4. Adjust width percentages for responsive sizing (e.g., `width="80%"` for smaller widgets)

#### Step 4: Customize (Optional)
1. Open any SVG file in a text editor (VS Code recommended)
2. Look for `<text>` elements to change displayed text
3. Modify `fill="#..."` attributes to change colors
4. Adjust animation timings in the `<style>` section
5. Save and commit your changes

#### Step 5: Preview and Publish
1. Commit your changes and push to GitHub
2. Visit your profile to see the widgets in action
3. Make adjustments as needed for optimal display

## Customization Guide

### Text Customization
Most widgets contain customizable text. Look for `<text>` tags:
```xml
<text x="16" y="48">Your Custom Text Here</text>
```

### Color Customization
Change colors by modifying `fill` attributes:
```xml
<!-- Change text color -->
<text fill="#ff0000">Red Text</text>

<!-- Change background color -->
<rect fill="#000000">Black Background</rect>
```

### Animation Customization
Modify CSS animations in the `<style>` section:
```css
.my-animation {
  animation-duration: 2s;  /* Change speed */
  animation-delay: 0.5s;  /* Change delay */
}
```

### Size Customization
Adjust the `viewBox` and dimensions:
```xml
<svg viewBox="0 0 400 200" width="400" height="200">
```

## Widget Categories & Use Cases

### For Developers
- `code-editor.svg` - Show your coding environment
- `commit-history.svg` - Display recent Git activity
- `contribution-graph.svg` - Showcase coding consistency
- `system-monitor.svg` - Demonstrate technical skills

### For Productivity
- `calendar.svg` - Show current date and planning
- `progress-tracker.svg` - Track project milestones
- `time-zones.svg` - Display global collaboration

### For Personal Branding
- `github-stats.svg` - Highlight GitHub metrics
- `social-stats.svg` - Show social media presence
- `inspiration-quote.svg` - Share motivational content

### For Fun & Engagement
- `music-player.svg` - Show current listening
- `weather.svg` - Display local weather
- `joke.svg` - Add humor to your profile
- `existential.svg` - Add personality

## Tips for Best Results

- **File Size:** These SVGs are optimized and typically under 10KB each.
- **Browser Compatibility:** All modern browsers support SVG animations.
- **Performance:** Animations are CSS-based and won't impact page performance.
- **Accessibility:** Add appropriate `alt` text when embedding in HTML.
- **Responsiveness:** Use CSS `max-width: 100%` for responsive behavior.
- **Loading:** GitHub may cache images; use `?v=1` parameter to force refresh during development.
- **Organization:** Group related widgets together in your README layout.
- **Balance:** Mix static information with animated widgets for visual interest.

## Example Profile README

Check out [`example-profile-README.md`](example-profile-README.md) for a complete example of how to integrate these widgets into your GitHub profile README. It demonstrates proper placement, sizing, and organization of multiple widgets.
