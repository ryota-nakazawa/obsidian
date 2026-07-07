---
description: Health-check the wiki for broken links, metadata issues, orphans, and gaps
---

# Wiki Lint

Read `AGENTS.md` first.

Run a wiki health check.

Check:

1. Broken `[[wikilinks]]`.
2. Orphan pages with no inbound links.
3. Missing or malformed YAML frontmatter.
4. Important concepts referenced repeatedly but lacking concept pages.
5. Source pages older than six months where recency matters.
6. Contradictions or unresolved tensions across pages.

Fix low-risk structural issues automatically. Save the report to `wiki/outputs/lint-report-YYYY-MM-DD.md`, update the master index when useful, and append to `wiki/log.md`.

