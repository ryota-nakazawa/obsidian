---
description: Answer a question using the compiled wiki and file the answer back
---

# Wiki Query

Read `AGENTS.md` first.

Answer the user's question using the wiki as the primary source.

Steps:

1. Read the master index.
2. Select the relevant wiki pages.
3. Read those pages before answering.
4. If the wiki is insufficient and the topic may have changed, browse current authoritative sources.
5. Produce a concise answer with `[[wikilink]]` citations where possible.
6. Save reusable answers to `wiki/outputs/{question-slug}.md`.
7. Update the master index if a durable output was created.
8. Append an entry to `wiki/log.md`.

