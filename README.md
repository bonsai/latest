# bonsai/latest

## Purpose

`bonsai/latest` is the **current active repository view** of the Bonsai organization.

It does not replace `bonsai/repos`.

- `bonsai/repos` = all repositories / organization index
- `bonsai/latest` = repositories that are most active and worth looking at now

## Principle

> Use only repositories that actually exist in `bonsai/*`.

No virtual repositories are created for organization modeling.

## Flow

```text
bonsai/*
   ↓
activity observation
   ↓
activity score
   ↓
bonsai/latest
   ↓
current working set
```

## Ranking signals

The first version should rank real repositories using observable GitHub activity:

- recent repository update
- recent commits
- recent pull requests
- recent issues
- development velocity
- repository health

The score should be reproducible from collected data rather than manually curated.

## Relationship to the organization

```text
                 bonsai/repos
                all repositories
                       │
                       ▼
                 activity analysis
                       │
                       ▼
                  bonsai/latest
                active working set
                       │
                       ▼
                 Coordinator / AW
                       │
                       ▼
                    Agents
                       │
                       ▼
                       pi
```

`latest` is therefore a **view into the existing organization**, not another organization.

## Initial scope

Start with the existing Bonsai repositories only. Do not invent or duplicate repositories.

The implementation can later publish machine-readable data such as `data/latest.json` and a static GitHub Pages dashboard.
