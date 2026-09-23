---
name: daigou-korea-ops
description: Operate and maintain the local 代购韩国 project, including WorkBuddy imports, product cleanup, image prompts and assets, website synchronization, frontend or dashboard changes, and verification. Use only for this project and its product or marketing workflows.
---

# 代购韩国项目运营

Use `/Users/liming/Desktop/共享文件夹/代购韩国项目` as the only source-of-truth workspace.

Before changing anything:

1. Read the root `AGENTS.md` and the relevant files under `codex-memory/`.
2. Check Git status and preserve unrelated user changes.
3. When entering `frontend-ui/` or `hankoo-dashboard/`, read that directory's `AGENTS.md`. Their Next.js version may differ from remembered conventions; consult the installed documentation before changing framework APIs.

Route the request using [references/project-map.md](references/project-map.md).

## Invariants

- WorkBuddy is an upstream collector. Local code cleans and normalizes data, creates Chinese copy and image prompts, imports approved assets, and synchronizes them to the site.
- Product claims must remain traceable to the source. Never invent sales, review counts, effects, materials, colors, sizes, or model gender.
- Do not reuse or imitate an origin site's detail-page layout. Preserve facts and original image links; create new Chinese commerce layouts and assets.
- Treat `data/products.json`, site assets, generated reports, and database backups as business data. Inspect schemas and callers before changing them.
- Do not expose or commit API keys, payment secrets, recovery codes, or production tokens.
- Publishing, production data mutation, account actions, and paid image generation require the user's current authorization.

## Working method

- Inspect the smallest relevant files and existing scripts before writing new automation.
- Prefer existing pipeline, audit, synchronization, and build commands over one-off rewrites.
- For product-data changes, verify category, price, options, image paths, source fields, and detail-page fields before synchronization.
- For frontend changes, run the relevant lint/build check and, when practical, open the local page to verify rendering and interactions.
- Finish with the files changed, commands run, validation result, and any production step still pending.
