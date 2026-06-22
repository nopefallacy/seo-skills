# seo-skills

A small collection of independent [Claude](https://claude.com/claude-code) **skills** for SEO and landing-page work. Each skill is self-contained — drop in just the one you need.

| Skill | Trigger | What it does |
|-------|---------|--------------|
| [`seo-audit`](skills/seo-audit) | `/seo-audit` | Runs a comprehensive technical SEO audit (16 categories, 148 rules) on a site using the `seomator` CLI, then returns prioritized, actionable fixes. |
| [`seo-optimize`](skills/seo-optimize) | `/seo-optimize` | Data-driven SEO optimization using **Google Search Console** — finds striking-distance keywords, fixes low-CTR pages, detects keyword cannibalization, and executes content optimizations backed by real search data. |
| [`site-launch-kit`](skills/site-launch-kit) | — | Clones an inspiration site and customizes it section-by-section into a conversion-ready landing page, deployed live. |

## Install

These are standard [`SKILL.md`](https://code.claude.com/docs/en/skills) skills, so they work across any agent that reads them — Claude Code, Codex, Cursor, Antigravity, Copilot, and others.

### Recommended: `npx skills` (cross-runtime)

The [`skills`](https://github.com/vercel-labs/skills) CLI installs into whichever agents you have, auto-detecting them. No clone needed.

```bash
# all three skills, project-level (./.claude/skills, ./.cursor/skills, ...)
npx skills add nopefallacy/seo-skills

# global — available in every project (~/.claude/skills, ...)
npx skills add nopefallacy/seo-skills -g

# target specific runtimes
npx skills add nopefallacy/seo-skills -a claude-code -a cursor -a codex

# just one skill
npx skills add https://github.com/nopefallacy/seo-skills/tree/main/skills/seo-audit
```

### Manual

```bash
git clone https://github.com/nopefallacy/seo-skills.git
cp -R seo-skills/skills/seo-audit ~/.claude/skills/seo-audit   # per-user
# or, per-project:
mkdir -p .claude/skills && cp -R seo-skills/skills/seo-audit .claude/skills/seo-audit
```

Restart your agent (or run `/doctor` in Claude Code). Invoke with `/seo-audit` or `/seo-optimize`, or just describe the task — the agent triggers the matching skill from its description.

## Requirements

- **`seo-audit`** — installs `@seomator/seo-audit` (npm) on first run; optional Playwright/Chromium for Core Web Vitals.
- **`seo-optimize`** — Google Search Console access (service-account API key, browser extraction, or CSV export).
- **`site-launch-kit`** — a `GEMINI_API_KEY` for image generation; deploys to Vercel.

## License

[MIT](LICENSE) © nopefallacy
