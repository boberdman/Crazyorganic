# Crazy Organic — static site (GitHub Pages)

Field-guide static site for Crazy Organic. Hosted free on GitHub Pages at crazyorganic.com.
Look follows **Visual System — Crazy Organic** (Drive): herbarium-earth palette, Fraunces /
Inter / IBM Plex Mono, and the signature epistemic-stamp device. Framework is plain static
HTML with one shared stylesheet — no build step.

## Files
```
index.html                                  homepage
issues/index.html                           the archive (all issues)
issues/how-life-got-sorted-into-boxes.html  Series A · Ep. 1
issues/TEMPLATE.html                         copy this to add a new issue
styles.css                                  shared styling for every page
.nojekyll                                   serve files as-is (no Jekyll processing)
CNAME                                       custom domain (crazyorganic.com)
```

## Local preview
Open `index.html` in a browser. Web fonts load from Google Fonts; everything else is local.
(Internal links use relative paths, so previewing from the file system works.)

## Add a new issue
1. Copy `issues/TEMPLATE.html` to `issues/<url-slug>.html`.
2. Fill the `<!-- FILL: ... -->` markers (title, series/episode/pillar/date, body, sources).
3. Mark claims with the epistemic stamp, e.g.
   `<span class="stamp inline stamp--established">Established</span>`
   Rungs: `established` `contested` `preliminary` `philosophy` `speculation` `folklore`.
4. Add a card for it in `issues/index.html` (copy the existing `<li>` block).
5. Optionally update the "From the field journal" teaser on `index.html`.

## Signup form
The subscribe block (on the homepage and every issue page) wraps your existing **Google Form**
embed, which writes to your Google Sheet. Copy is honest: it promises dispatches when ready,
not an instant download (there's no email-sending system or lead-magnet PDF yet).

- To change the form, edit it in Google Forms — the embed updates automatically. The embed
  URL is the one provided; it appears identically in `index.html`, `issues/index.html`,
  `issues/how-life-got-sorted-into-boxes.html`, and `issues/TEMPLATE.html`.
- Optional upgrade (not done, by choice): a custom on-brand form posting to the same Google
  Form `formResponse` endpoint would look seamless, but it can't confirm success and could
  silently drop signups if the form changes — risky for the email list. The iframe is
  bulletproof. Say the word if you'd rather have the prettier version.

## Deploy (your steps — your GitHub account)
1. Commit and push to `https://github.com/boberdman/Crazyorganic.git` (main).
2. Repo **Settings → Pages**: Source = Deploy from a branch, `main` / root.
3. Custom domain + HTTPS: `CNAME` already holds `crazyorganic.com`; confirm the domain and
   tick "Enforce HTTPS" in Settings → Pages once the certificate issues.

## Notes / flags
- **Web fonts** load from Google Fonts (Google sees visitors' IPs). Standard for a marketing
  site; system-font fallbacks are in place if it's ever blocked. Can be self-hosted later.
- The homepage was restyled to match the Visual System doc (fonts, exact palette, stamp
  device). Structure and content are unchanged from the live site.
