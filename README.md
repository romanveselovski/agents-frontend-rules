# agents-frontend-rules

This is a drop-in pack of `AGENTS.md`, Cursor `.mdc` rules, and skills for people who let an agent build or edit a website. You copy the files into the project once. Cursor, Claude Code, Codex, Copilot, and Windsurf all read `AGENTS.md`. Cursor also loads `.cursor/rules/*.mdc`.

The pack does not choose a stack. HTML and CSS are fine. So are React, Vue, Svelte, and Astro. If you ask for something else in chat, that request wins.

<p align="center">
  <a href="https://github.com/romanveselovski/agents-frontend-rules/stargazers"><img src="https://img.shields.io/github/stars/romanveselovski/agents-frontend-rules?style=for-the-badge" alt="GitHub stars"></a>
  <img src="https://img.shields.io/badge/AGENTS.md-included-0f172a?style=for-the-badge" alt="AGENTS.md included">
  <img src="https://img.shields.io/badge/Cursor-.mdc_rules-000?style=for-the-badge" alt="Cursor mdc rules">
  <img src="https://img.shields.io/badge/WCAG-2.2_AA-0052cc?style=for-the-badge" alt="WCAG 2.2 AA">
</p>

## Why this exists

Agents on default settings keep shipping the same page. You get a purple-blue first screen, Inter, a fake user count, and a homepage that says “Unlock the future.” There is only a light theme. The 404 is whatever the host serves. Inputs have no labels. It looks fine on a laptop and falls apart on a phone. There is no `lang`, no canonical URL, and schema markup for content that is not on the page.

Once the pack is in the repo, the agent has to do the boring work first. Thesis and design tokens come before the first section. Product copy goes through `avoid-ai-writing`. Light and dark both exist from the first scaffold. The custom 404 returns HTTP 404. Forms keep labels, an error summary, and the values you typed. Layout starts from the phone, inputs stay at 16px, and JSON-LD only describes what is visible.

The checks follow WCAG 2.2 (W3C), Core Web Vitals (web.dev), Google Search Central, ARIA APG Dialog, and OWASP CSP.

## Install

Run the commands from the project root. macOS and Linux share one snippet. PowerShell is separate. If you would rather not clone, copy the files by hand.

**macOS / Linux**

```bash
git clone --depth 1 https://github.com/romanveselovski/agents-frontend-rules.git /tmp/agents-frontend-rules
mkdir -p .cursor/rules .cursor/skills
cp /tmp/agents-frontend-rules/rules/*.mdc .cursor/rules/
cp /tmp/agents-frontend-rules/AGENTS.md ./
cp -R /tmp/agents-frontend-rules/skills/. .cursor/skills/
rm -rf /tmp/agents-frontend-rules
```

**Windows (PowerShell)**

```powershell
git clone --depth 1 https://github.com/romanveselovski/agents-frontend-rules.git $env:TEMP\agents-frontend-rules
New-Item -ItemType Directory -Force -Path .cursor\rules, .cursor\skills | Out-Null
Copy-Item $env:TEMP\agents-frontend-rules\rules\*.mdc .cursor\rules\
Copy-Item $env:TEMP\agents-frontend-rules\AGENTS.md .\
Copy-Item $env:TEMP\agents-frontend-rules\skills\* .cursor\skills\ -Recurse -Force
Remove-Item $env:TEMP\agents-frontend-rules -Recurse -Force
```

**By hand**

1. Copy `rules/*.mdc` into `<project>/.cursor/rules/`
2. Copy `AGENTS.md` to the site root, or merge it into the one you already have
3. Leave this README behind if the project already has one
4. Copy folders from `skills/` into `.cursor/skills/` (rules point at `skills/<name>/SKILL.md`)
5. For blog work, take `skills/blog-author/` and fill in `project-facts.md`

The files the agent actually follows sit in `rules/*.mdc`. This README and `AGENTS.md` only tell you what lives where.

## Rule files

Each `.mdc` file is a constraint, not a tutorial. The table is the index. Rows marked “Always on” load in every chat.

| File | What it forces |
| --- | --- |
| `00-core.mdc` | Your request wins. Reuse what exists. Do not invent the stack. Always on. |
| `01-greenfield.mdc` | First pass on an empty site: tokens, 404, both themes. Always on. |
| `karpathy-guidelines.mdc` | Small diffs. Always on. |
| `14-design.mdc` | Tokens, type, no stock AI-UI |
| `15-color-scheme.mdc` | Light and dark palettes, both required |
| `16-ux.mdc` | Nielsen plus Material interaction. Not a Google skin. |
| `avoid-ai-writing.mdc` | AI-ism audit for UI, HTML/TSX, and docs |
| `52-copy.mdc` | Short UI copy: buttons, title, 404 |
| `53-content.mdc` | Articles and blog. Details in `blog-author/` |
| `10-components.mdc` | One primitive per role. Screens from those primitives. |
| `11-layout-chrome.mdc` | Shared header/footer, landmarks, skip-link, custom 404 |
| `12-interactive-states.mdc` | Hover, pointer, pressed, focus, disabled |
| `13-navigation-logo.mdc` | Home logo is not a link to itself |
| `20-forms.mdc` | Labels, errors, submit states |
| `21-feedback.mdc` | One toast, one tooltip, one modal |
| `22-system-states.mdc` | Loading, empty, error, success |
| `30-accessibility.mdc` | WCAG 2.2 AA |
| `31-semantic-seo.mdc` | Semantics, crawl, schema, mobile parity |
| `40-responsive.mdc` | Mobile-first, touch, safe-area, `dvh` |
| `41-images-media.mdc` | CLS, lazy, srcset, video |
| `42-performance.mdc` | Core Web Vitals, mobile first |
| `50-security-privacy.mdc` | XSS, secrets, trackers, cookies |
| `51-i18n.mdc` | `lang`, locale, hreflang + x-default |

## Skills (`skills/`)

A skill is extra reading for a matching job. Do not change the project stack because a skill mentions React. If the repo already uses React or Next, `frontend-developer` is the right one to open.

| Skill | When |
| --- | --- |
| `frontend-design` | You are inventing UI from scratch and need an aesthetic thesis |
| `antigravity-design-expert` | Depth, glass, motion |
| `frontend-developer` | The repo already uses React or Next |
| `frontend-lighthouse` | Someone asked for a Lighthouse CI gate on production |
| `seo-aeo-schema-generator` | JSON-LD for content that is actually on the page |
| `seo-geo` | AI-search citations, robots for AI bots, `llms.txt` |
| `blog-author` | Writing an article |

## What this is not

Use this for frontend agent behavior. It will not stand in for a backend kit, a Next starter, a brand book, cookie-banner legal copy, or a paste of the Front-End Checklist, Opquast, or WCAG 3.

## Stars

GitHub ranks starred repositories higher in search. If the pack is in your project, star it here: [agents-frontend-rules](https://github.com/romanveselovski/agents-frontend-rules).

## Sources

I wrote most of the numbered files in `rules/`. A handful of skills and rules started in other public GitHub repos. Credit stays with those authors. What you see here may be a shorter copy, fitted to this folder layout.

| File here | Source |
| --- | --- |
| `rules/karpathy-guidelines.mdc` | [multica-ai/andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills), from [Andrej Karpathy’s notes](https://x.com/karpathy/status/2015883857489522876) on LLM coding mistakes |
| `rules/avoid-ai-writing.mdc`, `skills/blog-author/skills/avoid-ai-writing/` | [conorbronsdon/avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing) (MIT). Word list adapted from [brandonwise/humanizer](https://github.com/brandonwise/humanizer) |
| `skills/frontend-design/` | Public `frontend-design` skill (Apache 2.0). Also [anthropics/skills](https://github.com/anthropics/skills) |
| `skills/antigravity-design-expert/` | [sickn33/agentic-awesome-skills](https://github.com/sickn33/agentic-awesome-skills) |
| `skills/frontend-developer/` | Community React/Next skill, same family as [sickn33/agentic-awesome-skills](https://github.com/sickn33/agentic-awesome-skills) |
| `skills/frontend-lighthouse/` | [stareezy-1/frontend-architecture-skill](https://github.com/stareezy-1/frontend-architecture-skill) (MIT) |
| `skills/seo-geo/`, `skills/blog-author/skills/seo-dataforseo/` | [AgriciDaniel/claude-seo](https://github.com/AgriciDaniel/claude-seo) |
| `skills/seo-aeo-schema-generator/`, `skills/blog-author/skills/seo-aeo-*` | [mrprewsh/seo-aeo-engine](https://github.com/mrprewsh/seo-aeo-engine) |
| `skills/blog-author/skills/seo-content-auditor/` | Community SEO skill from the same circle |

If you wrote one of these and want a different line, or the file gone, open an issue.

## License

MIT for this pack, unless an upstream license still applies.

`skills/frontend-design/` stays [Apache 2.0](skills/frontend-design/LICENSE.txt). Files taken from other repos keep that repo’s license.
