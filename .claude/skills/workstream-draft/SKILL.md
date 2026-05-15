---
name: workstream-draft
description: Full draft pipeline for new prose in The Keepers series.
---

## Pipeline

1. **hp-planner** — reads canonical ref/ and existing manuscript; produces a scene plan with constraints, open questions, and risk flags. Stops for human approval if open questions exist.
2. **Human approval** — author reviews plan and answers open questions before prose is drafted.
3. **hp-writer** — drafts the scene per the approved plan, channeling Lewis/Tolkien/Lawhead voice.
4. **hp-reviewer** — reviews the draft for voice, continuity, and craft. Issues verdict.
5. If APPROVE or APPROVE WITH MINOR REVISIONS: present to human for final approval before commit.
6. If REVISE BEFORE COMMIT: hp-editor addresses flagged issues, then hp-reviewer reviews again (max 2 cycles).
7. **Human approval** — author gives final approval; Claude commits with `feat(manuscript): <description> AB#<id>`.

## Escalation

If hp-reviewer requests more than 2 revision cycles, surface to human with full context — do not continue looping.
