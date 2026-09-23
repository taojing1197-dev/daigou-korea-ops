# Project map

## Canonical paths

- Root: the user-supplied project workspace
- Cross-session context: `AGENTS.md`, `codex-memory/`
- Store data and assets: `data/`, `dist/`
- Product processing CLI: `scraper/`
- Collection and image workspace: `product-page-generator/`
- Customer frontend: `frontend-ui/`
- Operations dashboard: `hankoo-dashboard/`
- Mini-program/H5: `小程序-H5/`
- Established maintenance automation: `tools/`
- Xiaohongshu workflows: `marketing/`

Documents copies are historical, not working directories.

## Product workflow

From `scraper/`, the installed CLI supports:

```bash
hankoobuy status
hankoobuy process <slug>
hankoobuy process --all
hankoobuy url <URL>
hankoobuy prompts
hankoobuy images import <slug> <directory>
```

The pipeline is WorkBuddy/raw source → translation → normalization → copy and prompts → approved images → store output. Keep source fields so each claim can be audited.

From `product-page-generator/`:

```bash
npm run dev
npm run generate:assets
npm run resume:images
npm run sync:site
npm run lint
npm run build
```

Use `resume:images` when `image_generation_pending.json` exists. Do not discard pending state merely because an API was rate-limited or out of credit.

## Frontend and dashboard

Both `frontend-ui/` and `hankoo-dashboard/` expose `dev`, `lint`, and `build` scripts. Read the local `AGENTS.md` before editing and use the installed Next.js documentation for framework behavior.

## Existing automation

Search `tools/` before implementing data imports, audits, normalization, image synchronization, database backup, or publishing. Useful entry points include:

- `tools/sync_collector_to_site.py`
- `tools/audit_product_source_consistency.py`
- `tools/auto_data_guard.py`
- `tools/backup_database.py`
- `tools/verify_database_backup.py`
- `tools/build_static_frontend.py`
- `tools/site_publish.py`

Read a script's arguments and side effects before running it. A filename is not authorization to publish or mutate production.
