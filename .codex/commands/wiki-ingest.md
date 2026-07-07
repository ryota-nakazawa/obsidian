---
description: Process new raw sources into the compiled wiki
---

# Wiki Ingest

Read `AGENTS.md` first.

Process new files in `raw/` into the compiled wiki.

Steps:

1. List all markdown files in `raw/`.
2. List existing source summaries in `wiki/sources/` and source-style pages in `wiki/`.
3. Identify raw files that do not appear to have been processed.
4. For each new source:
   - Create a source summary in `wiki/sources/`.
   - Identify key concepts and entities.
   - Create or update relevant pages in `wiki/concepts/` and `wiki/entities/`.
   - Add useful `[[wikilinks]]`.
5. Update the master index.
6. Append an entry to `wiki/log.md`.
7. Report files processed, pages created, pages updated, and unresolved issues.

