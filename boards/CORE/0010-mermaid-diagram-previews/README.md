# Mermaid Diagram Improvement Previews

Issue: https://github.com/ClawQueue/ClawQueue/issues/10

Status: revised draft preview for human approval. No ClawQueue source files have been changed.

## Diagnosis

The current README Mermaid diagram explains the system, but it is doing too much in one vertical chain:

- intake, queueing, dispatch, runners, artifacts, and review all sit at the same visual weight
- runner options branch late, which makes the central CQ control loop less obvious
- OpenClaw appears both as intake and as one runner, but the difference is not visually explained
- runner colors previously grouped OpenClaw, Codex, and Claude together even though they represent different approved execution paths
- human review previously looked like an output state instead of a human approval actor
- the diagram is readable on desktop, but it is tall and less scannable in narrow views

The docs homepage currently uses a custom HTML flow instead of Mermaid. That is visually cleaner, but it loses some architecture clarity from the README.

## Retry Feedback Addressed

The second pass keeps the first-pass structure but fixes color semantics:

- both OpenClaw nodes now use the same blue treatment, whether OpenClaw is shaping intake or running a specialist agent
- human operator and human review now share the same purple treatment
- Codex uses a distinct blue treatment
- Claude Code uses a light orange treatment
- GitHub and ClawQueue remain separate neutral/brand-blue anchors so the durable work contract and local scheduler are easy to scan

## Recommendation

Approve **Variant A, revised** as the primary replacement for the README Mermaid diagram. It keeps the strongest story:

1. OpenClaw/operator context shapes the work.
2. GitHub owns the durable queue.
3. CQ dispatches locally by policy and labels.
4. Agents/runners return reviewable output to GitHub.

Use **Variant B, revised** only if we want a more technical architecture diagram later in the operator docs.

## Variant A - Control Loop

Best for README and public docs because it is compact and narrative-first.

Preview:

![Variant A control loop](variant-a-control-loop.svg)

```mermaid
flowchart LR
    H[Human operator] --> OC1[OpenClaw intake]
    P[Project docs and repo context] --> OC1
    OC1 --> GH[GitHub issue and project queue]

    GH --> CQ[ClawQueue local scheduler]
    CQ --> R{Labels and profile policy}

    R --> OC2[OpenClaw specialist agent]
    R --> COD[Codex CLI]
    R --> CLA[Claude Code CLI]

    OC2 --> OUT[Comment, artifact, branch, or PR]
    COD --> OUT
    CLA --> OUT

    OUT --> HR[Human review in GitHub]
    HR --> GH

    classDef human fill:#F3E8FF,stroke:#7E22CE,stroke-width:2px,color:#2E1065;
    classDef context fill:#F8FAFC,stroke:#64748B,stroke-width:1.5px,color:#0F172A;
    classDef openclaw fill:#E0F2FE,stroke:#317AE8,stroke-width:2px,color:#0B2E5F;
    classDef github fill:#FFFFFF,stroke:#24292F,stroke-width:2px,color:#24292F;
    classDef cq fill:#DBEAFE,stroke:#317AE8,stroke-width:2.5px,color:#0B2E5F;
    classDef codex fill:#DCEBFF,stroke:#0A66C2,stroke-width:2px,color:#073763;
    classDef claude fill:#FFE8C7,stroke:#C46A1D,stroke-width:2px,color:#7C2D12;
    classDef output fill:#DCFCE7,stroke:#16A34A,stroke-width:2px,color:#14532D;

    class H,HR human;
    class P context;
    class OC1,OC2 openclaw;
    class GH github;
    class CQ,R cq;
    class COD codex;
    class CLA claude;
    class OUT output;
```

## Variant B - Three-Lane System View

Best for operator docs because it separates human/GitHub/local-runtime responsibilities and exposes the approved runner choices.

Preview:

![Variant B swimlane](variant-b-swimlane.svg)

```mermaid
flowchart TB
    subgraph Intake["Human + OpenClaw intake"]
        H1[Human operator]
        H2[Project context]
        O1[OpenClaw intake]
        H1 --> O1
        H2 --> O1
    end

    subgraph GitHub["GitHub durable workflow"]
        G1[Issue]
        G2[Labels]
        G3[Project status: Todo]
        G4[Comments, artifacts, PRs]
        G1 --> G2 --> G3
    end

    subgraph Local["Local ClawQueue runtime"]
        C1[Scheduler scan]
        C2[Policy and locks]
        C3[Mode and runner selection]
        C1 --> C2 --> C3
    end

    subgraph Runners["Approved local runners"]
        O2[OpenClaw specialist agent]
        COD[Codex CLI]
        CLA[Claude Code CLI]
    end

    O1 --> G1
    G3 --> C1
    C3 --> O2
    C3 --> COD
    C3 --> CLA
    O2 --> G4
    COD --> G4
    CLA --> G4
    G4 --> HR[Human review]
    HR --> G1

    classDef human fill:#F3E8FF,stroke:#7E22CE,stroke-width:2px,color:#2E1065;
    classDef context fill:#F8FAFC,stroke:#64748B,stroke-width:1.5px,color:#0F172A;
    classDef openclaw fill:#E0F2FE,stroke:#317AE8,stroke-width:2px,color:#0B2E5F;
    classDef github fill:#FFFFFF,stroke:#24292F,stroke-width:2px,color:#24292F;
    classDef local fill:#DBEAFE,stroke:#317AE8,stroke-width:2px,color:#0B2E5F;
    classDef codex fill:#DCEBFF,stroke:#0A66C2,stroke-width:2px,color:#073763;
    classDef claude fill:#FFE8C7,stroke:#C46A1D,stroke-width:2px,color:#7C2D12;

    class H1,HR human;
    class H2 context;
    class O1,O2 openclaw;
    class G1,G2,G3,G4 github;
    class C1,C2,C3 local;
    class COD codex;
    class CLA claude;
```

## Before / After Notes

- Before: all runner options shared one color, so OpenClaw looked unrelated to the upstream OpenClaw intake step. After: OpenClaw intake and OpenClaw specialist execution share one color.
- Before: human review used a green output style, which made it look like an artifact rather than an approval actor. After: human operator and human review share one actor color.
- Before: Codex and Claude Code were visually collapsed into the same runner category. After: Codex is blue and Claude Code is light orange, making direct runner choices easier to distinguish without adding extra nodes.
- Before: Variant B hid runner choices inside a generic agent execution step. After: Variant B exposes the three approved local runner paths while keeping GitHub and CQ as the central workflow anchors.

## Approval Choice

- **Approve A**: apply revised Variant A to the README and optionally reuse it in docs.
- **Approve B**: use revised Variant B for operator docs, not the homepage.
- **Request second pass**: ask CMO to create a more visual/brand-forward version that uses VitePress HTML instead of Mermaid.

## Follow-up Implementation Issue

Title: `[dev] Apply approved Mermaid diagram improvements`

Labels: `dev`, `cq:change`, `documentation`

Body:

```md
## Goal

Apply the approved Mermaid diagram from #10 to ClawQueue docs/source.

## Source artifact

Use the approved preview artifact, including the revised color semantics from the retry pass:
https://github.com/ClawQueue/ClawQueue-reports/tree/main/boards/CORE/0010-mermaid-diagram-previews

## Task

- Replace the current README Mermaid diagram with the approved variant.
- If Manos approved reuse in docs, update `docs/index.md` or the relevant operator docs page too.
- Preserve existing positioning and links.

## Acceptance criteria

- Mermaid renders correctly on GitHub.
- Docs build passes locally.
- PR includes before/after notes and verification.
- Do not merge until Manos approves the PR.
```

