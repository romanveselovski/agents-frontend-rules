# Agent: frontend of this site

Rules: `.cursor/rules/` or `web-ai-rules/rules/`. The user's request outranks any file.

**Chat language** — same language as the user's task. Code and site copy — product language.

**Code** — `karpathy-guidelines.mdc`. React/Next already in the repo — you may use `skills/frontend-developer/SKILL.md`. Do not invent a stack.

**UI build** — empty repo: `01-greenfield.mdc`. Visual: `14-design.mdc` + `frontend-design`. Behavior: `16-ux.mdc` (Google/Material interaction, not necessarily their look). Motion: `antigravity-design-expert` unless a flat mock exists. Components beat decoration. `prefers-reduced-motion` kills scenes.

**Copy** — `52-copy.mdc` + `avoid-ai-writing.mdc` (including `tsx`/`html`).

**Articles** — `53-content.mdc`, `skills/blog-author/SKILL.md`, facts from `project-facts.md`. Schema — `skills/seo-aeo-schema-generator/SKILL.md`. GEO — `skills/seo-geo/SKILL.md`.

**Measurement** — CWV on production. CI gate — `skills/frontend-lighthouse/SKILL.md` only if CI was requested.

**UI**
1. Reuse existing components and the shared header/footer first.
2. One toast, tooltip, form, modal, button per project.
3. Home logo is not a link. Clickable: hover + pointer + **pressed**. On mobile, a press state is required, not hover alone. Logo: pointer only.
4. Forms: label, error summary, do not clear values. No toast for form errors.
5. Data views: loading / empty / error / success.
6. WCAG 2.2 AA. Keyboard equals mouse. Light and dark themes from the first scaffold.
7. Custom 404 + HTTP 404 from the first scaffold.
8. No raw HTML from outside. No secrets in the client.

Before handoff: focus visible; no logo self-link; no blank screen; LCP not lazy; `noopener`; Esc closes overlays; scrollbar does not shift the page; text selection does not close the modal; a dead URL serves the custom 404; both themes; no AI-boilerplate copy.
