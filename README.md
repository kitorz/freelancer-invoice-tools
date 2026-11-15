# Freelancer Finance Lookup — tool site (skeleton + content, local only)

Static site, plain HTML + one shared CSS file, no build step, no framework.
English throughout. Niche: freelancer finance (invoice / quote / late-payment chasing).

## Files

- `index.html` — home: what the site is, index of tools/guides, links to the free sample and full kit.
- `calculators.html` — working calculators (vanilla JS): late-fee calculator (overdue days, annual rate, grace period) and invoice-total calculator (dynamic line items, discount %, fixed discount, tax/VAT).
- `chase-guide.html` — the 5-email chase cadence (3 days before due / Day 1 / Day 7 / Day 14 / Day 30) and the weekly 10-minute routine, described not reproduced.
- `quote-guide.html` — how to write a freelancer quote/estimate, what to include, pricing by replacement cost.
- `styles.css` — shared styles. Palette: paper #F3EDE4, ink #1E1E1E, tan #A68A64.
- `sitemap.xml`, `robots.txt` — SEO files.

## Monetization (only links, no affiliate programs)

- Free sample (tracker + Day 1 email, $0): https://kitkit2.gumroad.com/l/rjaklp
- Full kit ($29): https://kitkit2.gumroad.com/l/wztca

No affiliate links anywhere — affiliate programs are unverified for PayPal CN settlement.
No paid product contents are reproduced on the site; the 5-email cadence is described, not quoted.

## Before launch (NOT done — prep only)

1. **Domain is set.** `sitemap.xml` and `robots.txt` already point to https://kitorz.github.io/freelancer-invoice-tools/ (set 2026-11-16). If the repo name changes, update both files to match.
2. **Pick a deploy target.** See "Deploy options" below.
3. **Verify the calculators in a real browser** (they were tested headlessly with node — see `verify/` notes in the build report — plus a local HTTP serve check). No deployment was performed.

## Deploy options (checked 2026-11-16, read-only)

- **GitHub Pages — feasible, needs one user step.** `git` 2.43.0 is installed and `gh` CLI is installed, but `gh` is **not logged in** (`gh auth status`: "You are not logged into any GitHub hosts"). To deploy: user runs `gh auth login` once, then create a repo, push this folder, enable Pages (or `gh-pages` branch). No cost for a public repo.
- **Cloudflare Pages — feasible, needs setup.** `wrangler` is **not installed** on this machine (`command not found`), though `node` is available, so `npm install -g wrangler` would work. Also needs a Cloudflare account + API token login (`wrangler login`). The user already has a Cloudflare account (used for the cloud-mail project) but wrangler/API access from this machine was hanging as of 2026-11-15 — recheck before choosing this path.
- **Recommendation:** GitHub Pages is the simpler first deploy (one login, no build step, static files as-is). Cloudflare Pages is the fallback if the team wants Cloudflare hosting later. Either way, nothing has been created, pushed, or deployed.

## Local preview

```bash
cd ~/workspace/autonomous-earn/tool-site
python3 -m http.server 8000
# open http://localhost:8000/
```
