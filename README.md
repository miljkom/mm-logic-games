# MM Logic Games — Studio Site

Static landing page + privacy policy for the studio. Two HTML pages, one CSS file, one SVG favicon. No build step, no JavaScript, no dependencies.

```
studio-site/
├── index.html      # landing page
├── privacy.html    # privacy policy (required for Google Play)
├── style.css       # all styling
├── favicon.svg     # inline-character favicon
└── README.md       # this file
```

---

## Deploy to GitHub Pages (recommended — 5 minutes)

### Option A — Separate repo (cleaner URL, recommended)

1. Create a new public GitHub repo, e.g. `mm-logic-games`.
2. Copy the contents of this folder into that repo's root and push.
3. Repo → Settings → Pages → **Source: Deploy from a branch** → Branch: `main` / root.
4. Wait ~30 seconds. Your URL will be:
   `https://<your-github-username>.github.io/mm-logic-games/`
5. Paste that URL into the Google Play Console "Organization website" field.

### Option B — Subfolder of an existing repo

1. Push this `studio-site/` folder to your existing repo (already done if you're reading this here).
2. Repo → Settings → Pages → Source: `main` branch, folder: `/studio-site` (if available)
   *or* serve from the root and the URL becomes `.../studio-site/`.
3. URL: `https://<your-github-username>.github.io/shikakumac/studio-site/`

### Option C — User site (URL = `<username>.github.io`)

1. Create a repo named exactly `<your-github-username>.github.io`.
2. Push files to the root.
3. URL: `https://<your-github-username>.github.io/` — the cleanest possible URL.
4. Only works once per GitHub account.

---

## Custom domain (optional, later)

Buy a domain (e.g. `mmlogicgames.com` on Namecheap, ~$10/year) and:

1. Add a `CNAME` file to the repo root containing just: `mmlogicgames.com`
2. In your domain registrar's DNS panel, add:
   - `A` records pointing to GitHub's IPs: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` record for `www` → `<your-github-username>.github.io`
3. Wait for DNS to propagate (15 min – 24 h).
4. Repo → Settings → Pages → Custom domain → enter `mmlogicgames.com` → Enforce HTTPS.

---

## Local preview

No server needed — just open `index.html` in a browser. For nicer local serving:

```bash
cd studio-site
python3 -m http.server 8000
# then open http://localhost:8000
```

---

## Things to swap before going live

- **Contact email** — currently `miljkom99@gmail.com` in `index.html` and `privacy.html`. Search-and-replace to your preferred address.
- **Year in footer** — `© 2026 MM Logic Games`. Update in `index.html` and `privacy.html`.
- **Game card** — when the Shikaku build is live, add a real screenshot and replace the placeholder `桜` character (swap `<div class="game-art">桜</div>` with `<img src="..." />`).
- **Last updated date** in `privacy.html` — bump whenever you change the policy.

---

## Use this URL in Google Play Console

Once deployed, paste the URL in two places in Play Console:

1. **Account setup → Organization website** — the studio URL (`/`).
2. **App content → Privacy policy** — the full privacy URL (`/privacy.html`).
