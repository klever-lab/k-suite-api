# AGENTS.md

K Suite API is a small Go HTTP service that provides the API-first core for the K Suite tools.

## Documentation (read/write)

- **Read first:** For how this repo works, start at `docs/README.md`, then open only the topic files you need. Do not re-derive behavior from filenames alone when a doc covers it.
- **Before non-trivial changes:** Check the relevant doc so you match existing patterns.
- **After behavior changes:** Update the **one** topic file under `docs/` that owns that fact. Do not copy the same detail into AGENTS.md, README.md, or multiple docs.
- **Regenerate vs patch:** `docs/README.md` records the commit it was generated from; `git diff <sha>..HEAD --stat` shows what changed since. Prefer the `generate_docs` skill when docs are broadly stale or many topics shifted; for small, targeted edits, patch the single topic file (and `docs/README.md` if you add/remove a topic).
- `CLAUDE.md` is a symlink to this file.

Do not put implementation detail in this file — it lives under `docs/`.
