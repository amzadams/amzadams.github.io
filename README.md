# amzadams.github.io

Personal academic website for Abdul-Manan Zakari Adams.

## Structure

```
index.html              homepage
css/style.css           all styles
js/main.js              nav toggle, active links, scroll
pages/
  research.html         research projects (clickable, detailed)
  publications.html     publication list with links
  teaching.html         TA roles and presentations
  cv.html               full CV with PDF download placeholder
  misc.html             learning, side projects, private items
_config.yml             GitHub Pages config (disables default theme)
```

## Deploying to GitHub Pages

1. Clone or copy these files into your `amzadams/amzadams.github.io` repo root.
2. Commit and push to the `main` branch.
3. GitHub Pages will serve the site at `https://amzadams.github.io`.

No build step is required. The site is plain HTML, CSS, and JavaScript.

## Private items (misc page)

The misc page uses a passphrase to show private cards. The current default
passphrase is `amz2026`. To change it:

1. Open your browser console on any page.
2. Run:
   ```js
   crypto.subtle.digest('SHA-256', new TextEncoder().encode('yournewpassword'))
     .then(b => [...new Uint8Array(b)].map(x=>x.toString(16).padStart(2,'0')).join(''))
     .then(console.log)
   ```
3. Copy the resulting hash.
4. Open `pages/misc.html` and replace the value of `PASSPHRASE_HASH` near the bottom.

This is client-side only: the private items are in the HTML source, just visually
hidden. Do not put anything genuinely sensitive here. For truly confidential
material, keep it offline or behind a real backend.

## Adding content

- New research project: copy a `.research-card` block in `pages/research.html`.
- New publication: copy a `.pub-entry` block in `pages/publications.html`.
- New misc item: copy a `.misc-card` block in `pages/misc.html`.
  Add `class="misc-card private"` to hide it behind the passphrase.

## CV PDF

Replace the `#` href on the Download PDF button in `pages/cv.html` with the
relative path to your PDF once you add it to the repo, e.g. `../cv.pdf`.
