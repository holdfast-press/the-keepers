---
name: workstream-edit
description: Editing pipeline for existing prose in The Keepers manuscript.
---

## Pipeline

1. **hp-editor** — reads the target passage and performs developmental or copy editing per the request. Marks changes with `[EDIT: reason]`. Flags major revisions with `[MAJOR REVISION PROPOSED: reason]` rather than making them unilaterally.
2. **hp-reviewer** — reviews the edited version against the original. Issues verdict.
3. If APPROVE: present to human for final approval before commit.
4. If REVISE BEFORE COMMIT: hp-editor addresses issues; hp-reviewer reviews again (max 2 cycles).
5. **Human approval** — author gives final approval; Claude commits with `fix(manuscript): <description> AB#<id>`.

## Major revision gate

If hp-editor proposes a major structural revision, STOP and present the proposal to the human author before proceeding. Do not implement major revisions without explicit author approval.
