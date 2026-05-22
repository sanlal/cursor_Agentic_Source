# Cursor: The Agentic Way
Link: https://sanlal.github.io/cursor_Agentic_Source/

An interactive teaching site about Cursor (the AI code editor) plus an optional slide deck for video recording. Dark hand-drawn neon theme. All artwork is original SVG &mdash; no copyright risk for YouTube or any other use.

## What's inside

```
cursor-agentic-deck/
  index.html          - the main teaching page (open this first)
  slides.html         - optional 10-slide deck for YouTube recording
  learn.css           - styles for the teaching page
  style.css           - styles for the slide deck
  narration.md        - per-slide voiceover script for the deck
  assets/             - 10 original SVG illustrations
    01-title.svg
    02-what-is-cursor.svg
    03-chat-vs-agent.svg     (4-ways-to-talk illustration)
    04-agent-deep-dive.svg   (@-references illustration)
    05-agent-mode.svg
    05-plan-mode.svg
    06-subagents.svg
    07-tdd-cycle.svg
    08-model-selection.svg
    09-pro-tips.svg
    10-cheat-sheet.svg
```

## Two ways to use this

### 1. As a teaching page (the main one)

`index.html` is a full interactive guide. 10 lessons from beginner to advanced, each as an expandable card with TL;DR, explanation, code examples, "Try this" and "Common mistakes" callouts, and a key takeaway. Share the link, and your audience learns at their own pace.

- Click any lesson title to expand it.
- Use **Expand all** / **Collapse all** in the top bar.
- Code blocks have a **Copy** button on hover.
- Reading-progress bar at the very top.
- Mobile-friendly (responsive layout, touch-friendly tap targets).

### 2. As a slide deck for video

`slides.html` is the same content arranged as a Reveal.js slide deck with speaker notes. Open it, press **F** for fullscreen, advance with arrow keys, press **S** for speaker notes. Use it for YouTube/Loom recording.

The voiceover script is in [`narration.md`](narration.md).

## Quick start (run locally)

Just double-click `index.html`. For a local server (recommended &mdash; some browsers limit `file://` access):

```bash
# Python 3 (pre-installed on most systems)
python -m http.server 8000
# then open http://localhost:8000
```

```powershell
# Windows / PowerShell
start index.html
```

## Deploying to GitHub Pages (get a shareable link)

The whole project is static HTML/CSS/SVG, so it deploys to GitHub Pages in two minutes.

```bash
# from this folder
git init
git add .
git commit -m "Initial cursor-agentic teaching site"

# create an empty repo on github.com, then:
git branch -M main
git remote add origin https://github.com/<your-username>/cursor-agentic-deck.git
git push -u origin main
```

Then on github.com:

1. **Settings** &rarr; **Pages**.
2. Source: **Deploy from a branch**.
3. Branch: **main**, folder: **/ (root)**, **Save**.
4. ~30 seconds later your live URL appears at the top:

   `https://<your-username>.github.io/cursor-agentic-deck/`

That's your shareable link. The teaching page is at the root, the slide deck is at `/slides.html`.

### Updating after edits

```bash
git add .
git commit -m "tweak lesson 4"
git push
```

GitHub Pages re-deploys automatically within ~30 seconds.

## Editing

| You want to change... | Edit this file |
|--|--|
| Lesson wording, examples, code blocks | `index.html` |
| Teaching-page colours, padding, fonts | `learn.css` |
| Slide deck wording | `slides.html` |
| Slide deck colours / layout | `style.css` |
| Video voiceover script | `narration.md` |
| An illustration | `assets/NN-*.svg` &mdash; open in any text editor or Figma/Inkscape |

### Tweaking the hand-drawn wobble

Each SVG has a `<filter id="wN">` block near the top. The wobble is controlled by:

- `baseFrequency` on `feTurbulence` &mdash; higher = noisier strokes.
- `scale` on `feDisplacementMap` &mdash; higher = wobblier.

## Recording the YouTube video (slide deck workflow)

1. Open `slides.html`, press **F** for fullscreen.
2. Open `narration.md` on a second monitor (or print it).
3. Start your recorder (OBS, Loom, ShareX, Windows Game Bar, etc).
4. Read each slide's *On-screen* / *Main beat* / *Transition* block.
5. Press **Right arrow** between slides for a clean fade transition.

Tips:

- Record at 1920x1080 or 2560x1440. SVGs scale infinitely, so any resolution looks crisp.
- The script aims for ~14 minutes. Trim the "On-screen" lines if you want a tighter ~10-min cut.

## Using the SVGs elsewhere

The illustrations are standalone files. Drop any `assets/NN-*.svg` into:

- Microsoft PowerPoint 2016+ (Insert &rarr; Picture supports SVG)
- Google Slides (Insert &rarr; Image &rarr; Upload)
- Canva (Upload &rarr; drag the `.svg`)
- Notion, Obsidian, any markdown editor

All artwork is original and royalty-free for YouTube videos, courses, blog posts &mdash; anywhere.

## License

Do whatever you want with the site, the slides, the artwork, and the script. No attribution required (but always appreciated).
