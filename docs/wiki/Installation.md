# Installation

Look, "installation" is a strong word for "copy a file." But let's walk through all the ways you might want to do this.

---

## Prerequisites

- A GitHub account (for the profile README use case)
- A text editor (VS Code, Neovim, Notepad, a rock and chisel — whatever works)
- The ability to upload a file somewhere

That's it. No Node.js. No Python. No Docker. No Kubernetes. Nothing.

---

## Option 1: GitHub Profile README (Most Common)

This is the main use case. You have a GitHub profile. You want it to look good. Here's the full flow.

### Step 1: Get the widget file(s)

**Option A — Download directly:**
Go to the repository, click the SVG file you want, click the download button. Done.

**Option B — Clone the repo:**
```bash
git clone https://github.com/Kaelith69/widget-templates.git
```
Then copy the SVG files you want to your own project.

**Option C — Raw URL:**
Right-click on a file in the repo → Copy link → Download with curl:
```bash
curl -O https://raw.githubusercontent.com/Kaelith69/widget-templates/main/github-stats.svg
```

### Step 2: Upload to your profile repository

Your GitHub profile README lives in a special repository named `<your-username>/<your-username>`. If it doesn't exist yet, create it — GitHub will recognize it automatically.

Upload the SVG files to that repository. You can:
- Drag and drop them in the GitHub web UI
- Push them via git:

```bash
cd your-username/
cp /path/to/github-stats.svg .
git add github-stats.svg
git commit -m "feat: add github stats widget"
git push
```

### Step 3: Reference in README.md

In your `README.md`:

```markdown
![GitHub Stats](./github-stats.svg)
```

Or with HTML for more control:

```html
<p align="center">
  <img src="./github-stats.svg" alt="GitHub Stats" width="100%" />
</p>
```

### Step 4: Commit and push

```bash
git add README.md
git commit -m "docs: add widget-templates widgets"
git push
```

Visit your GitHub profile. Your widget should be there, doing its little animation.

---

## Option 2: Personal Website

If you're embedding in a plain HTML file:

```html
<!-- As an img tag (simplest) -->
<img src="./path/to/skills.svg" alt="Skills" style="max-width: 100%;" />

<!-- Inline SVG (paste SVG content directly into your HTML) -->
<!-- Allows CSS/JS interaction from outside the SVG -->
<div class="widget-container">
  <!-- paste SVG file contents here -->
</div>
```

For inlining, just open the `.svg` file, copy everything, paste it into your HTML where you want it.

---

## Option 3: Any Markdown File

These work in any markdown renderer that supports image embedding:

```markdown
![Widget Name](./widget-name.svg)
```

This includes:
- GitHub READMEs, wikis, issue templates
- GitLab markdown
- Most static site generators (Jekyll, Hugo, Gatsby, etc.)
- Notion (sort of — Notion doesn't render SVG animations, but the static version will show)
- Any `README.md` in any repo

---

## Sizing Tips

GitHub renders images at their `width`/`height` attributes by default. To control sizing:

```html
<!-- Responsive full width -->
<img src="./widget.svg" width="100%" />

<!-- Fixed pixel width -->
<img src="./widget.svg" width="400" />

<!-- Side by side (49% each with a small gap) -->
<img src="./widget-a.svg" width="49%" />
<img src="./widget-b.svg" width="49%" />
```

Most widgets have a natural width between 300–500px. GitHub profile READMEs are about 800px wide, so `width="100%"` for single widgets and `width="49%"` for two side-by-side works well.

---

## Troubleshooting Installation

**Widget not showing up?**
- Make sure the SVG file is actually committed and pushed to the repo
- Check the file path in the markdown is correct (case-sensitive!)
- GitHub caches images via camo proxy — wait a minute or try appending `?v=2` to force-refresh

**Widget showing as broken image?**
- The SVG file might have an XML error — open it in a browser to check
- Make sure the file is in the repository (not just on your local machine)

**Animation not playing?**
- GitHub renders SVGs in a sandboxed `<img>` context — animations should still work
- If you're on Safari, some animation types may render differently
- Try opening the SVG file directly in a browser tab to confirm the animation works

More help in [Troubleshooting](Troubleshooting).
