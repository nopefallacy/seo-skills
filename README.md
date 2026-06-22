# seo-skills

A small collection of independent [Claude](https://claude.com/claude-code) **skills** for SEO and landing-page work. Each skill is self-contained — drop in just the one you need.

| Skill | Trigger | What it does |
|-------|---------|--------------|
| [`seo-audit`](skills/seo-audit) | `/seo-audit` | Runs a comprehensive technical SEO audit (16 categories, 148 rules) on a site using the `seomator` CLI, then returns prioritized, actionable fixes. |
| [`seo-optimize`](skills/seo-optimize) | `/seo-optimize` | Data-driven SEO optimization using **Google Search Console** — finds striking-distance keywords, fixes low-CTR pages, detects keyword cannibalization, and executes content optimizations backed by real search data. |
| [`site-launch-kit`](skills/site-launch-kit) | — | Clones an inspiration site and customizes it section-by-section into a conversion-ready landing page, deployed live. |

## Install

These are **skills**, not a plugin — install whichever you want individually.

**Per-user (available in every project):**

```bash
# clone, then copy the skill(s) you want into your Claude skills dir
git clone https://github.com/nopefallacy/seo-skills.git
cp -R seo-skills/skills/seo-audit      ~/.claude/skills/seo-audit
cp -R seo-skills/skills/seo-optimize   ~/.claude/skills/seo-optimize
cp -R seo-skills/skills/site-launch-kit ~/.claude/skills/site-launch-kit
```

**Per-project (checked into a single repo):**

```bash
mkdir -p .claude/skills
cp -R seo-skills/skills/seo-audit .claude/skills/seo-audit
```

Restart Claude Code (or run `/doctor`) and the skills will be picked up automatically. Invoke with `/seo-audit` or `/seo-optimize`, or just describe the task — Claude triggers the matching skill from its description.

## Requirements

- **`seo-audit`** — installs `@seomator/seo-audit` (npm) on first run; optional Playwright/Chromium for Core Web Vitals.
- **`seo-optimize`** — Google Search Console access (service-account API key, browser extraction, or CSV export).
- **`site-launch-kit`** — a `GEMINI_API_KEY` for image generation; deploys to Vercel.

## License

[MIT](LICENSE) © nopefallacy
