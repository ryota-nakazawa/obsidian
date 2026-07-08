# Domain Policy

Use domain metadata before adding new top-level folders.

Use `area` and `project` when a domain has multiple streams:

```yaml
domain: work | admin | personal | research | other
area: "broad area"
project: "specific project or blank"
topic: "short topic"
```

## Domains

| domain | Use for |
|---|---|
| `work` | business, projects, professional output, clients, learning used for work |
| `admin` | paperwork, accounting, subscriptions, office/home operations |
| `personal` | diary, emotions, personal reflection |
| `research` | source-backed learning and synthesized knowledge |
| `other` | temporary fallback |

## Area and Project

Examples:

| domain | area | project | Use for |
|---|---|---|---|
| `work` | `content` | `ai-evals-article` | a specific article/project |
| `work` | `sales` | `client-a` | client or sales work |
| `admin` | `accounting` | `monthly-closing` | monthly admin procedure |
| `admin` | `contracts` | `vendor-renewal` | contract operations |
| `personal` | `reflection` | blank | daily emotional record |
| `research` | `ai` | `evals` | source-backed research |

## Folder Fit

- Put source material in `raw/`.
- Put synthesized concepts in `wiki/`.
- Put repeated procedures in `ops/`.
- Put daily logs and emotional records in `daily/`.
- Put durable questions and answers in `qa/`.
- Put unsorted material in `inbox/`.

## Cross-Domain Links

Cross-domain links are valuable when they explain a real relationship:

- `daily` mentions a blocker in a work project.
- `ops` captures a procedure learned from repeated admin mistakes.
- `wiki` explains a concept used in a work deliverable.
- `qa` answers a question that should update an operation.

Do not create cross-domain links just to make the graph denser.
