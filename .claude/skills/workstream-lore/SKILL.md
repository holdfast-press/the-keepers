---
name: workstream-lore
description: Continuity and historical accuracy audit pipeline for The Keepers.
---

## Pipeline

1. **hp-lore-keeper** — reads the target passage or claim, cross-references canonical ref/ documents, performs historical research as needed, and produces a findings report with PASS/WARN/FAIL items.
2. Present findings to human — lore checks are informational; the author decides how to respond.
3. If author approves corrections: route to workstream-edit for hp-editor to address FAIL items.
4. If author accepts WARNs as intentional creative choices: document the decision in a comment in the relevant ref/ document.

## Output format

hp-lore-keeper findings should be structured as:
- Summary: overall assessment
- PASS items: listed briefly
- WARN items: listed with explanation and suggested approach
- FAIL items: listed with canonical source, the conflict, and recommended resolution
