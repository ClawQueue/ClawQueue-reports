# ClawQueueHQ Worklog

This repository stores **generated ClawQueue artifacts** for ClawQueue operating on itself.

It exists so CQ can use the same artifact/worklog discipline it recommends to others, without mixing generated reports into the main code/profile pull-request flow.

## What belongs here

Examples:
- product and workflow reviews
- architecture notes
- launch/readiness checklists
- issue/board artifacts
- PR review summaries
- triage notes for public issues/comments
- handoff docs and other durable generated deliverables

Typical paths:

```text
boards/<board>/<issue-number>-<slug>.md
boards/<board>/<issue-number>-<slug>/README.md
boards/<board>/BOARD_GUIDANCE.md
boards/<board>/HANDOFF.md
```

## What does *not* belong here

Do not use this repo for:
- ClawQueue source code
- tracked product/profile configuration
- normal code-review changes
- long-term canonical docs that belong in the main repo

Those belong in the main ClawQueue repo.

## Why this repo exists

Generated artifacts are useful institutional memory, but they make normal PRs noisy and conflict-prone when mixed into the same branch used for code and profile work.

So the rule is simple:

> durable generated artifacts go here; code and profile changes go in the main repo.
