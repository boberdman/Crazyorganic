# Crazy Organic — static site (GitHub Pages)

A single-page landing site for Crazy Organic. Built to be hosted free on GitHub Pages.
Copy is the approved subscribe-page voice; the visual system is a tasteful starting point
only — the real one is still TBD per the Operating Brief.

Files:
- `index.html` — the whole site (self-contained: HTML + CSS + a little JS, no dependencies)
- `CNAME` — the custom domain (`crazyorganic.com`). Delete this if you're not using a custom domain yet.

---

## What this site does and doesn't do

- ✅ Public landing page with the brand promise, "what you get," the honest-framing handshake,
  and the field-notes call to action.
- ⚠️ The email signup form is a **placeholder**. It does NOT collect emails yet. It shows a
  friendly "signups open soon" message instead of silently failing. Wire it to Mailchimp
  (steps below) when you're ready to start the list.

---

## Deploy to GitHub Pages (your steps — needs your GitHub account)

These touch your account, so they're yours to do:

1. Create a new GitHub repository.
   - For a user site at `https://<username>.github.io`, name the repo exactly
     `<username>.github.io`.
   - For a project site, any repo name works; the URL becomes
     `https://<username>.github.io/<repo>/`.
2. Upload `index.html` (and `CNAME` if using the custom domain) to the repo root.
3. In the repo: **Settings → Pages**. Under "Build and deployment," set Source to
   **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. Wait a minute, then visit the URL GitHub shows on that Pages screen.

## Custom domain — crazyorganic.com (your DNS, your call)

1. Keep the `CNAME` file in the repo root (it contains `crazyorganic.com`).
2. At your domain registrar's DNS settings, point the domain at GitHub Pages:
   - Apex domain `crazyorganic.com` → four A records to GitHub's IPs
     (`185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`),
     **and** an AAAA set if you want IPv6.
   - `www` → a CNAME record pointing to `<username>.github.io`.
   - Confirm current GitHub Pages IPs in their docs at deploy time — they can change.
3. Back in **Settings → Pages**, enter `crazyorganic.com` as the custom domain and tick
   **Enforce HTTPS** once the certificate is issued.

---

## Turn the signup on later (Mailchimp or similar)

The form in `index.html` is pre-wired so this is a 2-minute job:

1. In Mailchimp: **Audience → Signup forms → Embedded form**.
2. Copy the form's `action` URL.
3. In `index.html`, find `action="MAILCHIMP_ACTION_URL"` and paste the real URL in.
4. The email field is already named `EMAIL` (Mailchimp's default) — no change needed.
5. Paste Mailchimp's hidden anti-bot field where the comment marks it.
6. **Delete the `<script>` placeholder block at the bottom of `index.html`** so the form
   submits for real instead of showing the "coming soon" message.

Any email tool with an embeddable form (Buttondown, MailerLite, ConvertKit, Kit, etc.)
works the same way — paste its action URL, match the email field name, remove the placeholder script.

---

## Notes
- Edit copy directly in `index.html` — sections are clearly commented.
- The page is responsive and has no external requests (good for privacy and speed).
- When the brand's real visual system is set, swap the colors in the `:root` block near the top of the CSS.
