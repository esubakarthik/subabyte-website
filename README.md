# SUBABYTE website

Static company site for **SUBABYTE LTD**, hosted on GitHub Pages at [subabyte.co.uk](https://subabyte.co.uk).

The **GitHub repo should be private**. The live website is still public on the internet (required for App Store privacy/support URLs).

## Pages

| URL | Purpose |
|-----|---------|
| `/` | Company home |
| `/play-with-krypto.html` | Play with Krypto project |
| `/nightowl-responders.html` | NightOwl Responders product page |
| `/topic-chat.html` | Redirect → NightOwl Responders (old name) |
| `/support.html` | App Store support URL |
| `/privacy.html` | App Store privacy policy URL |
| `/terms.html` | Terms of Use (incl. NightOwl subscriptions) |

## Local preview

```bash
cd subabyte-website
python3 -m http.server 8080
```

Open http://localhost:8080

## GitHub setup (private repo)

1. Create a **private** repo on GitHub (e.g. `subabyte-website`).
   - Do **not** tick “Add a README” — push this folder instead.
2. Push from your machine:

```bash
cd /Users/subakarthikelangovan/Developer/subabyte-website
git commit -m "Initial SUBABYTE company site"
git remote add origin git@github.com:esubakarthik/subabyte-website.git
git push -u origin main
```

Or with GitHub CLI:

```bash
gh repo create subabyte-website --private --source=. --remote=origin --push
```

3. Repo → **Settings** → **Pages** → Source: **GitHub Actions**.
4. After the workflow runs: **Custom domain** → `subabyte.co.uk` → Save → **Enforce HTTPS**.

### Private repo + GitHub Pages

GitHub Pages from a **private** repo requires **GitHub Pro** (or a paid organisation plan) on personal accounts. On the free plan, Pages only deploys from **public** repos.

Your options:

| Option | Repo visibility | Cost |
|--------|-----------------|------|
| Private repo + GitHub Pro | Private | ~$4/mo |
| Public repo | Public (source visible; site URL unchanged) | Free |

The deployed site at `https://subabyte.co.uk` is public either way — only the source code visibility differs.

## GoDaddy DNS (subabyte.co.uk)

Point the domain at GitHub Pages. Keep existing **MX** records for email.

| Type | Name | Value |
|------|------|--------|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `esubakarthik.github.io` |

## App Store Connect

### Play with Krypto
- Privacy Policy: `https://subabyte.co.uk/privacy.html`
- Support URL: `https://subabyte.co.uk/support.html`

### NightOwl Responders
- Privacy Policy: `https://subabyte.co.uk/privacy.html#nightowl` (or `/privacy.html`)
- Support URL: `https://subabyte.co.uk/support.html#nightowl` (or `/support.html`)
- Terms of Use (EULA): `https://subabyte.co.uk/terms.html`
- Marketing: `https://subabyte.co.uk/nightowl-responders.html`
