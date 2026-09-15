---
name: blog-author
description: >-
  Universal article pipeline: fact-check against project facts, SEO draft,
  locales if the site is multilingual, narrative rewrite, avoid-ai-writing,
  images, schema, then publish via the project's own CMS. Use when writing
  or publishing a blog post or long-form guide.
disable-model-invocation: true
---

# Article author

Pipeline for any site. Facts come from this project's [project-facts.md](project-facts.md). Do not invent product, prices, or integrations.

**Copy quality is required before publish:** the SEO draft (step 3) is a skeleton. Production needs steps 3c and 3d.

```
- [ ] 1. Ingest and fact-check
- [ ] 2. Keywords (if an SEO tool exists)
- [ ] 3. Draft in the source language
- [ ] 3e. Other site languages (if they exist)
- [ ] 3c. Connected prose — copywriting.md + narrative-rewrite.md
- [ ] 3d. No AI-isms — humanize.md + avoid-ai-writing
- [ ] 3b. Locale check (for ru — ru-locale-style.md)
- [ ] 4. Article skeleton from content-template.md
- [ ] 5. Images — image-style.md
- [ ] 6. Schema for visible content
- [ ] 7. Publish the project's way
- [ ] 8. E-E-A-T / audit, patches
- [ ] 9. Indexing — if the project already has it
```

## 1. Ingest and fact-check

1. Read the source in full.
2. Read [project-facts.md](project-facts.md). If empty, fill from site code and docs, not from memory.
3. Verify contested claims in the repo (API, i18n, README).
4. Fact-check table: claim → source → ok / drop / soften.

Forbidden: invented numbers, reviews, “guaranteed growth”, features that do not exist.

## 2. Keywords

If the project has SEO MCP or a keyword export, take up to 5 working queries per publish language. Seeds in the SERP language, not English seeds in a foreign database.

No tool — queries from the brief and common sense, no fake volumes.

Optional: [skills/seo-dataforseo/SKILL.md](skills/seo-dataforseo/SKILL.md).

## 3. Draft

Source language = the site’s primary language (often `html[lang]`). Structure — [content-template.md](content-template.md). Tone: teacher, not a sales reel.

Optional: [skills/seo-aeo-landing-page-writer/SKILL.md](skills/seo-aeo-landing-page-writer/SKILL.md) — structure only, not “buy now” landing tone if this is a guide.

## 3e. Locales

Write only languages the site actually serves. Meaning and facts match the source, not word-order calque. For `ru` — [ru-locale-style.md](ru-locale-style.md).

## 3c. Connected prose

[copywriting.md](copywriting.md) → [narrative-rewrite.md](narrative-rewrite.md). Each H2 is a finished thought. FAQ — 2–4 sentences. Mistakes — paragraphs, not fragments.

## 3d. Humanize

[humanize.md](humanize.md) and `rules/avoid-ai-writing.mdc`. Edit all user-facing article copy. Leave facts, prices, code, UI labels, brands.

## 5. Images

[image-style.md](image-style.md). Logo and domain from project facts, not invented.

## 6. Schema

JSON-LD only for what is on the page. HowTo if there are steps. FAQ if there is FAQ. Article/BlogPosting for every article.

Optional: [skills/seo-aeo-schema-generator/SKILL.md](skills/seo-aeo-schema-generator/SKILL.md).

## 7–9. Publish

File format, CMS, 404, sitemap, IndexNow — as in this repo. No tie to Supabase or one host.

Do not publish until there is a short note for 3c and 3d.

Audit: [skills/seo-content-auditor/SKILL.md](skills/seo-content-auditor/SKILL.md).
