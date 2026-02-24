# Troubleshooting

When things go wrong with static SVG files (a genre of problem that shouldn't exist but somehow does), this page has you covered.

---

## 🖼️ Widget Not Showing / Broken Image Icon

**Symptom:** You see a broken image placeholder where the widget should be.

**Check these things, in order:**

1. **Is the file actually in the repository?**
   - Go to your repository on GitHub
   - Look for the SVG file in the file list
   - If it's not there, you need to commit and push it

2. **Is the path in your README correct?**
   - File paths are case-sensitive on GitHub
   - `./github-stats.svg` ≠ `./GitHub-Stats.svg`
   - If the file is in a subfolder: `./widgets/github-stats.svg`

3. **Did you push your changes?**
   - `git status` — do you see uncommitted changes?
   - `git push` — did the push succeed?

4. **Is there a syntax error in the SVG?**
   - Open the SVG file directly in a browser (drag & drop it onto a browser tab)
   - If the browser shows an error or blank page, the XML is broken
   - Common culprits: unclosed tags, unescaped `&` characters (should be `&amp;`), missing quotes on attributes

---

## 🎬 Animation Not Playing

**Symptom:** The widget shows up but it's just a static image — no animation.

**Possible causes:**

**GitHub camo proxy caching:** GitHub caches SVG files. If you just updated an animation, it might take a few minutes to refresh. Try appending `?v=2` to the filename in your README:
```markdown
![Stats](./github-stats.svg?v=2)
```

**Reduced motion preference:** If the OS has "Reduce Motion" enabled (macOS: System Settings → Accessibility → Motion), some browsers will suppress or slow animations.

**Browser-specific behavior:** Safari handles some CSS animation types differently. If the animation plays in Chrome/Firefox but not Safari, this is likely the cause. Test in multiple browsers to confirm.

**The animation actually has a finite duration:** Some animations are designed to play once and stop (using `animation-fill-mode: forwards` and no `infinite` keyword). This is intentional for some widgets. Check the CSS in the SVG's `<style>` block.

---

## 🐌 Widget Looks Stale / Old Content Showing

**Symptom:** You edited the SVG, pushed it, but GitHub still shows the old version.

**GitHub caches images via camo.** There's usually a delay of a few minutes to an hour before changes propagate.

**Force a refresh by:**
1. Appending or incrementing a version parameter: `./widget.svg?v=2`
2. Hard-refreshing the GitHub page: Ctrl+Shift+R / Cmd+Shift+R
3. Waiting. Patience is a virtue. GitHub's CDN will catch up.

---

## 📐 Widget Displaying at Wrong Size

**Symptom:** Widget is too big, too small, or the aspect ratio is wrong.

**Fix:**
- Add a `width` attribute to your `<img>` tag in the README:
  ```html
  <img src="./widget.svg" width="400" />
  ```
- For responsive sizing: `width="100%"` stretches to container width
- For side-by-side: `width="49%"` leaves a small gap between two widgets

The SVG has a `viewBox` that defines its internal coordinate system. Changing `width` in the embed scales the rendered size without distorting the content.

---

## 🔡 Wrong Font / Text Looking Weird

**Symptom:** Text in the widget looks different from the screenshots.

The widgets use system fonts (`monospace`, `'Courier New', monospace`, `sans-serif`). Different operating systems render these differently:
- macOS: Menlo or Monaco for monospace
- Windows: Courier New for monospace
- Linux: DejaVu Sans Mono or similar

This is expected behavior. There's no way to guarantee a specific font without loading an external web font — which we deliberately don't do (see [Privacy](Privacy)).

---

## 🌐 Widget Works Locally But Not on GitHub

**Symptom:** Opening the SVG in a browser shows animations, but embedded in a GitHub README it looks different or static.

**GitHub sanitizes SVGs.** It strips:
- `<script>` tags and JavaScript event handlers (`onclick`, `onload`, etc.)
- External resource references that GitHub's proxy can't or won't load

**CSS animations (`@keyframes`) are preserved.** If an animation works locally but not on GitHub, check if it relies on JavaScript. If it does, that's why it breaks on GitHub — and it means the widget isn't following the project's CSS-only animation constraint.

---

## 🔐 Security Warning / Widget Blocked

**Symptom:** GitHub shows a warning about the SVG content, or the widget is blocked.

This shouldn't happen with unmodified widgets from this repo. If you've modified a widget and it's being blocked:
- Check for any `<script>` tags you may have added
- Check for external URL references in `<image>`, CSS `url()`, or `@font-face`
- Check for event handler attributes (`onclick`, `onmouseover`, etc.)

Remove these and the block should clear.

---

## 📱 Widget Looks Bad on Mobile

**Symptom:** Widgets overlap, are too small, or the layout breaks on mobile.

GitHub profile READMEs don't have great mobile breakpoints for custom layouts. Options:
- Use `width="100%"` for single-column layouts on mobile
- Accept that side-by-side widgets (`width="49%"`) will be narrow on phones — most content still reads fine at 49% of ~380px
- Consider stacking widgets vertically for important content

---

## Still Stuck?

Open an [issue on GitHub](https://github.com/Kaelith69/widget-templates/issues). Include:
- Which widget is affected
- What browser and OS you're using
- A link to where you're embedding it (if it's a public profile)
- What you expected vs. what happened

The more context, the faster the fix.
