---
name: external-brain-vault
description: Operate the user's Obsidian-style external brain vault. Use when the user asks to ingest sources, organize raw/wiki/daily/ops/qa notes, add or prune wikilinks, create weekly reports, save Q&A, separate work and admin domains, check empty links, or maintain the knowledge graph in `/Users/ryota/Desktop/dev/外部脳` or a cloned copy of that vault.
---

# External Brain Vault

## Core Rule

Treat the vault as a personal knowledge graph, not a file dump. Preserve the distinction between:

- `raw/` - external source material
- `wiki/` - synthesized knowledge and concept pages
- `daily/` - daily logs, diary, emotion, work traces
- `ops/` - reusable procedures and checklists
- `qa/` - durable answers to user questions
- `inbox/` - unsorted notes

Read the vault's `AGENTS.md` first when present.

## Domain Separation

Support multiple knowledge domains. Do not assume all sources are about AI evals.

Use frontmatter and indexes to separate domains:

```yaml
domain: work | admin | personal | research | other
area: "broad area, e.g. content, accounting, legal, learning"
project: "specific project or blank"
topic: "short topic name"
```

Recommended meaning:

- `work` - business, projects, clients, deliverables, professional learning
- `admin` - paperwork, accounting, subscriptions, household/office operations
- `personal` - diary, emotions, health-adjacent reflections, private life logs
- `research` - external learning sources and synthesized knowledge

Keep folders simple. Prefer domain metadata over creating many top-level folders.

Use `area` and `project` when one domain contains multiple streams. Example: `domain: work`, `area: content`, `project: ai-evals-article`; or `domain: admin`, `area: accounting`, `project: monthly-closing`.

## Workflows

### Ingest Sources

When the user adds unrelated or new-domain sources to `raw/`:

1. Identify each source's domain and topic.
2. Create or update a source summary in `wiki/sources/` or a relevant `wiki/` page.
3. Create concept pages in `wiki/concepts/` only for reusable concepts.
4. Link across domains only when the relationship is useful and explicit.
5. Update an index when the new source changes navigation.
6. Append to `wiki/log.md`.

### Link Daily Notes

For `daily/` notes:

1. Preserve the user's wording and emotional nuance.
2. Add only high-signal links: projects, procedures, reusable concepts, repeated emotional patterns.
3. Do not link every noun.
4. If a repeated daily pattern suggests a procedure, propose or create an `ops/` note.
5. If a repeated daily pattern suggests a concept, propose or create a `wiki/concepts/` note.

### Save Q&A

When a response is reusable:

1. Save it to `qa/YYYY-MM-DD-short-slug.md`.
2. Link to relevant `wiki/`, `ops/`, and `daily/` notes.
3. Mark `domain` and `topic` in frontmatter.

### Weekly Reports

Read the requested week's `daily/`, relevant `qa/`, `ops/`, and touched `wiki/` notes. Output:

1. 成果
2. 進捗
3. 詰まり
4. 学び
5. 感情・コンディション傾向
6. opsへ反映する改善点
7. 来週やること
8. 関連リンク

### Empty Links

Empty links are acceptable when they are deliberate placeholders for useful future concepts. Handle them as:

- Ignore: one-off names, weak concepts, accidental links.
- Stub: repeated or central concepts.
- Remove: noisy links that will not be useful.

Use the helper reference for specific policy: `references/link-policy.md`.

## Safety

Do not add secrets, passwords, API keys, bank details, national IDs, or sensitive personal data to the vault. If the user wants to store work-sensitive or private material in a public GitHub repo, warn that the repo should be private or the material should be excluded.
