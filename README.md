# FC Mother — Email Preview Gallery

Public-facing static-HTML gallery of all 45 lifecycle and AOTW campaign email
variants, rendered with sample merge-tag data (Paulo · Honor Week · Veteran
tier). Used for internal stakeholder review and Notion embed previews.

**Open `index.html` locally** to navigate the full gallery. Once deployed to
GitHub Pages, the live gallery URL is:

```
https://drpauloignacio.github.io/fcm-email-previews/
```

Each variant lands at:

```
https://drpauloignacio.github.io/fcm-email-previews/<filename>.html
```

## Two-command deploy (GitHub Pages)

This directory is meant to live as its **own public repo** —
`fcm-email-previews` — separate from the platform monorepo. Move it out of the
platform folder first if you haven't already, then:

```bash
# From inside the email-previews/ directory
cd /Users/pauloignaciojr./WCH_Platform/fcm-email-previews

# 1. Initialize the repo (if not already)
git init -b main
git add .
git commit -m "Initial gallery: 45 variants for Honor Week launch review"

# 2. Create the public repo and push (requires gh CLI)
gh repo create fcm-email-previews --public --source=. --push

# 3. Enable GitHub Pages from the main branch
gh api -X POST /repos/drpauloignacio/fcm-email-previews/pages \
  -f source.branch=main -f source.path=/
```

If you don't have `gh` installed, you can:

1. Create the repo manually at https://github.com/new (public, no template).
2. `git remote add origin https://github.com/drpauloignacio/fcm-email-previews.git`
3. `git push -u origin main`
4. In Settings → Pages, set Source to "Deploy from branch" → `main` → `/ (root)` → Save.

GitHub Pages takes ~30–60 seconds to publish after enabling. Once live, every
HTML file is reachable at the URL pattern above.

## Updating after the first deploy

When variants change, just commit and push. GitHub Pages republishes
automatically:

```bash
cd /Users/pauloignaciojr./WCH_Platform/fcm-email-previews
# overwrite the changed HTML files (or copy fresh ones from the platform repo)
git add .
git commit -m "Update <variant name>"
git push
```

## What's in here

- **`index.html`** — The gallery landing page, grouped by template family.
- **45 variant HTMLs** — see breakdown below.
- **`README.md`** — this file.

### Template family breakdown

| Family | Variants | Coverage |
|---|---|---|
| AOTW Sunday Teaser | 4 | base, with-partner, nonuser-base, nonuser-with-partner |
| AOTW Monday Launch | 9 | base, with-quote, with-partner, with-sweepstakes, full, canonical, nonuser × 3 |
| AOTW Wednesday Chase | 5 | with-rank, no-rank, canonical, nonuser-default, nonuser-no-convert |
| AOTW Friday Final-Call | 7 | base, with-quote, with-partner, full, canonical, nonuser × 2 |
| Onboarding Arc | 8 | welcome × 2, primer, first-assist × 5 |
| Week-1 Recap | 2 | default, with-aotw |
| Assist Confirmation | 4 | default, with-quote, no-aotw, with-quote-no-aotw |
| Milestone Celebration | 4 | cumulative × 2, rank × 2 |
| Near-Miss Milestone | 2 | base, with-aotw |
| **Total** | **45** | |

## Notion embed integration

After deployment, each card in the FC Mother HQ Notion gallery page can embed
the live URL via Notion's `<embed>` block. Notion renders any public URL as a
live iframe — meaning the actual HTML email renders inline in Notion, not just
a static screenshot.

## Source of truth

Variant routing rules and template specs live in the platform monorepo at
`docs/brand/templates/`:

- `aotw-sunday-teaser.md`
- `aotw-monday-launch.md`
- `aotw-wednesday-chase.md`
- `aotw-friday-final.md`
- `aotw-arc-nonuser-variants.md`
- `aotw-campaign-schedule.md`
- `milestone.md`
- `near-miss-milestone.md`
- `operations-handbook.md`

Updates to those specs cascade here only when the rendered HTMLs are
re-generated and re-committed.

---

Internal review only · Do not share publicly. v1.0 · 2026-05-01
