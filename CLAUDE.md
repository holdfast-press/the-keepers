# CLAUDE.md — the-keepers

Claude Code context for the manuscript, worldbuilding, and series reference repository for *The Keepers*.

## What this repo is

This is the creative home of *The Keepers* — a character-driven contemporary fantasy series published under Holdfast Press. It holds the working manuscript, series reference material, character bibles, outlines, branding, and all creative assets for the series. The protagonist group are Microsoft MVPs who discover they are the reincarnated survivors of a 9th-century Norse village, bound together by something older than memory.

**Tone:** Galaxy Quest's heart + LOTR's weight + Stephen R. Lawhead's ley-line realism + the everyday texture of the modern tech-conference circuit.
**Theme:** *What we choose to carry, carries us.*

## ADO

| Field | Value |
|---|---|
| Organization | https://dev.azure.com/hybridcloudsolutions |
| Project | Holdfast Press |
| Area path | Holdfast Press\The Keepers |
| Commit format | `type(scope): description AB#<id>` |

## Repo structure

```
the-keepers/
├── CLAUDE.md
├── README.md
├── ref/                  — canonical series reference (deduplicated, latest versions only)
├── manuscript/
│   └── book-one/         — chapter files for Book One
├── outline/              — working outlines (separate from ref/canonical)
├── branding/             — cover art, typography, visual identity assets
├── assets/               — images, maps, diagrams
├── marketing/
│   └── press-kit/        — synopsis, author bio, back-cover copy, pitch materials
└── site/                 — content exported to holdfast-press.github.io
```

## Agents

| Agent | Model | Purpose |
|---|---|---|
| hp-writer | opus | Drafts new prose aligned with the series voice — mythic, grounded, character-first |
| hp-editor | sonnet | Developmental and copy editing passes |
| hp-lore-keeper | opus | Continuity, worldbuilding consistency, Norse/Celtic/ley-line accuracy |
| hp-planner | sonnet | Plans multi-chapter arcs and structural work — read-only |
| hp-reviewer | sonnet | Reviews prose quality, pacing, and adherence to series standards |

## Slash commands

| Command | Skill | Purpose |
|---|---|---|
| `/draft <scene or chapter>` | workstream-draft | Draft new prose: planner → hp-writer → hp-reviewer → human approve |
| `/edit <file or passage>` | workstream-edit | Edit existing prose: hp-editor → hp-reviewer → human approve |
| `/lore-check <claim or chapter>` | workstream-lore | Continuity audit: hp-lore-keeper → findings → human decides |

## Writing voice — non-negotiable

When drafting or editing prose in this repo, the voice must embody all three of these:

- **C.S. Lewis** — clarity that never condescends, wonder that never embarrasses, theology worn lightly into the fabric of ordinary things
- **J.R.R. Tolkien** — weight of history, languages of the land, myth as the deeper grammar of reality; grief and beauty inseparable
- **Stephen R. Lawhead** — ley-line realism (the sacred geography of Britain and the North), Celtic and Norse sacred tradition rendered with scholarly affection, heroes who are broken people carrying something they do not yet understand

The modern setting (tech conferences, MVP community, Seattle/Amsterdam/Edinburgh geography) is not in tension with myth — it IS the myth, just wearing a different coat. The humor is real, the friendship is load-bearing, and the darkness is earned.

## Hard rules

- Reviewer model family must differ from writer/editor model family
- No secret values ever committed — not tokens, not credentials, not subscription IDs
- All prose commits reference an ADO work item: `AB#<id>`
- Do not rewrite large existing passages without the author's explicit approval
- When continuity conflicts arise, the canonical ref/ documents take precedence over working drafts

## What Claude may do autonomously

- Read, search, and grep any file in this repo
- Write and edit manuscript, outline, ref, and marketing files
- Run git add, git commit, git push (normal pushes)
- Suggest edits with tracked-change comments in markdown

## Always confirm before

- Deleting or overwriting any file in ref/ (canonical documents)
- Committing to main branch without a work item reference
- Major structural changes to the outline or character bible
- Publishing or exporting content to holdfast-press.github.io

## Runtime structure

```
.claude/
├── agents/           — hp-writer, hp-editor, hp-lore-keeper, hp-planner, hp-reviewer
├── commands/         — /draft, /edit, /lore-check
├── skills/           — workstream-draft, workstream-edit, workstream-lore
├── hooks/            — block-secrets, validate-path, log-tokens, summarize-session
├── logs/             — sessions.jsonl, tokens.jsonl
└── settings.json     — Claude Code settings
```
