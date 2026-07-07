# External Brain Agent Guide

## Overview

This vault is a personal external brain for AI agent evaluation and related AI engineering research. Raw source material lives in `raw/`. The compiled wiki lives in `wiki/`. The agent maintains wiki content, links, indexes, and research outputs while preserving raw sources as the source of truth.

## Directory Structure

- `raw/` - Source material. Treat as read-only unless the user explicitly asks to add or clean raw sources.
- `wiki/index.md` or `wiki/Master Index - AIエージェント評価.md` - Master index / map of content.
- `wiki/log.md` - Append-only operation log.
- `wiki/sources/` - One summary per raw source.
- `wiki/concepts/` - One article per concept.
- `wiki/entities/` - People, organizations, products, tools.
- `wiki/syntheses/` - Cross-source analyses and position papers.
- `wiki/outputs/` - Filed answers to user queries and lint reports.
- `templates/` - Markdown templates for recurring note types.
- `.codex/commands/` - Reusable command prompts for this vault.

Existing top-level files in `wiki/` are valid legacy wiki pages. Do not move them unless the user asks for reorganization.

## File Conventions

- Prefer Japanese for wiki output unless the user asks otherwise.
- Use kebab-case ASCII filenames for new system files where practical.
- Japanese filenames are acceptable for user-facing wiki notes when they improve readability.
- Every new wiki page should start with YAML frontmatter:

```yaml
---
title: "Page Title"
date_created: YYYY-MM-DD
date_modified: YYYY-MM-DD
summary: "One or two sentences describing this page."
tags: [ai-evals]
type: concept | entity | source | synthesis | output | index | log
status: draft | review | final
---
```

- Use `[[wikilinks]]` for internal references.
- Link only the first occurrence of a concept per section unless repeated links improve navigation.
- Trace claims to source pages or source URLs where possible.
- Do not leave important `[[wikilinks]]` unresolved if a short stub page would be useful.

## Operations

### INGEST: Process New Raw Sources

Use when the user adds files to `raw/` or asks to process new material.

1. List raw markdown files.
2. Compare against `wiki/sources/` and existing source notes in `wiki/`.
3. For each unprocessed source, create or update a source summary.
4. Identify concepts and entities.
5. Create concept/entity pages when a subject appears in 2+ sources, or a stub when it is important.
6. Update the master index.
7. Append a dated entry to `wiki/log.md`.

### QUERY: Answer From the Wiki

Use when the user asks a question about the vault topic.

1. Read the master index first.
2. Read relevant source, concept, and synthesis pages.
3. Answer with `[[wikilink]]` citations.
4. Save durable answers to `wiki/outputs/{question-slug}.md` when the answer adds reusable knowledge.
5. Update the index and log if new durable output is created.

### LINT: Health Check

Use when the user asks for a health check, link check, cleanup, or periodic maintenance.

1. Find broken `[[wikilinks]]`.
2. Find orphan pages with no inbound links.
3. Find missing or malformed frontmatter.
4. Identify stale source-derived content.
5. Flag contradictions across pages.
6. Fix low-risk structural issues automatically.
7. Save a report to `wiki/outputs/lint-report-YYYY-MM-DD.md`.
8. Append to `wiki/log.md`.

## Quality Standards

- Summaries should synthesize, not copy.
- Prefer source-grounded claims over generic explanation.
- Flag uncertainty explicitly.
- For high-stakes claims, use at least two independent sources or mark the claim as tentative.
- Keep `raw/` immutable so the compiled wiki can be regenerated or audited.

## Current Topic Scope

Primary scope: AI evals, AI agent evaluation, grader design, evaluation datasets, evaluation harnesses, production feedback loops, and operationalizing AI quality measurement.

