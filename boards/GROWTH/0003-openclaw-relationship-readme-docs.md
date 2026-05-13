# Issue #3 — Clarify OpenClaw relationship in README and docs index

**Repo reviewed:** `ClawQueue/ClawQueue` at local commit `ed35069`  
**Deliverable type:** CMO copy review artifact, not an implementation commit  
**External-facing status:** Draft for human review before applying to README/docs  
**Revision note:** Updated after review feedback to make the OpenClaw main-agent intake advantage more explicit: a simple human prompt can become a full, scoped GitHub issue before CQ dispatches it.

## 1. Short diagnosis

The root `README.md` already mentions OpenClaw in the opening section, the at-a-glance table, use cases, the workflow diagram, and runner/backend sections. The relationship is broadly correct, but it is spread across the page and sometimes alternates between two roles without naming the distinction crisply:

- **OpenClaw as main-agent intake/context layer:** the assistant the human operator can prompt in plain language; OpenClaw reads repo/profile context and turns that rough intent into a full, scoped GitHub issue.
- **OpenClaw as runtime layer:** one of the local runner backends CQ can launch for specialist agents.

The docs landing page at `docs/index.md` is less clear. It says CQ launches “OpenClaw, Codex, Claude Code, or another configured local runner,” but the hero, feature cards, workflow, and final positioning mostly describe generic “agents” and “runners.” A new visitor can understand that CQ dispatches work, but may not understand that the default/full-harness path is powered by OpenClaw while CQ remains the GitHub-native queue/scheduler layer.

`docs/.vitepress/config.mts` does not need a navigation change. Its current nav is simple and ClawQueue-first. If anything changes there, the lowest-risk place is the footer message, but I recommend leaving it alone for now to avoid turning site chrome into OpenClaw promotion.

## 2. Recommended wording changes for `README.md`

### 2.1 Tighten the opening relationship sentence

**Current:**

```md
Combined with OpenClaw, CQ helps turn project context and operator intent into durable GitHub issues, then dispatches local agents to execute, report, and improve the work through reviewable GitHub history.
```

**Recommended:**

```md
Powered by OpenClaw for context-rich intake and, when configured, agent execution, CQ turns project context and operator intent into durable GitHub issues, then dispatches local workers to execute, report, and improve the work through reviewable GitHub history.
```

**Rationale:** This keeps the first impression ClawQueue-first while making the relationship explicit: OpenClaw powers the upstream context layer and can also be the runtime. It avoids sounding like CQ is merely a wrapper or an OpenClaw ad.

### 2.2 Clarify “What runs work?” in At a Glance

**Current:**

```md
| **What runs work?** | OpenClaw agents, Claude Code, or Codex backends |
```

**Recommended:**

```md
| **What runs work?** | CQ’s local scheduler launches the configured backend: OpenClaw agents by default/full-harness, or Claude Code/Codex direct CLI runners |
```

**Rationale:** The current line answers with backend names but hides CQ’s role. The revised line gives CQ ownership of scheduling while accurately crediting OpenClaw as the primary/default full-harness agent path.

### 2.3 Add one sentence after the “How CQ Fits” diagram intro or immediately before the numbered loop

**Recommended insertion:**

```md
In this model, the human operator can ask OpenClaw for help in plain language; OpenClaw uses project context to shape that rough intent into a full GitHub issue, and ClawQueue provides the GitHub-native queue, scheduler, policy, and reporting loop that carries the issue through execution and review.
```

**Rationale:** This is the clearest single-sentence mental model after review feedback. It makes the intake advantage concrete — OpenClaw turns a simple prompt into a complete issue — while still positioning CQ as the workflow product that queues, schedules, and preserves the work in GitHub.

### 2.4 Keep the existing “How Work Moves” backend clarification, but consider a small polish

**Current:**

```md
ClawQueue decides **which issue** gets picked and **which backend** launches it. OpenClaw is usually upstream as the context-rich intake/chief-of-staff layer; when using the `openclaw` backend, it is also the runtime that launches the named specialist agent. With `claudecode` or `codex`, the runner passes the full task prompt directly to that CLI.
```

**Recommended:**

```md
ClawQueue decides **which issue** gets picked, **which policy applies**, and **which backend** launches it. OpenClaw is usually upstream as the context-rich intake/chief-of-staff layer; when using the `openclaw` backend, it is also the runtime that launches the named specialist agent. With `claudecode` or `codex`, CQ passes the full task prompt directly to that CLI instead.
```

**Rationale:** This preserves the existing good explanation and adds one CQ-specific responsibility: policy. It also makes the direct-runner contrast slightly sharper.

## 3. Recommended wording changes for `docs/index.md` and docs index/navigation copy

### 3.1 Adjust hero tagline or keep hero tagline unchanged and add a trust bullet

I recommend **leaving the hero tagline unchanged** because it is strong and ClawQueue-first:

```yaml
tagline: Keep the contract in GitHub. Run the workers locally.
```

Then update the signal row instead.

**Current signal row:**

```html
<span>Local-first</span>
<span>GitHub-native</span>
<span>Markdown-configurable</span>
<span>PR-reviewable</span>
<span>Built for one operator + their agents</span>
```

**Recommended:**

```html
<span>Local-first</span>
<span>GitHub-native</span>
<span>Powered by OpenClaw</span>
<span>Markdown-configurable</span>
<span>PR-reviewable</span>
```

**Rationale:** The signal row is designed for quick positioning. “Powered by OpenClaw” gives visible credit without spending hero headline space or changing the core promise. Dropping “Built for one operator + their agents” is acceptable because that idea appears elsewhere on the page and the row should stay short.

### 3.2 Add a short OpenClaw boundary sentence after the first docs index paragraph

**Current section:**

```md
## GitHub is the durable work contract. Your machine runs the workers.

ClawQueue keeps source-of-truth work in GitHub Issues and Projects, then uses a local scheduler to pick eligible work, resolve labels into the right mode, launch the configured runner, and report the result back to the issue.
```

**Recommended:**

```md
## GitHub is the durable work contract. Your machine runs the workers.

ClawQueue keeps source-of-truth work in GitHub Issues and Projects, then uses a local scheduler to pick eligible work, resolve labels into the right mode, launch the configured runner, and report the result back to the issue.

OpenClaw supplies the context-rich assistant layer: a human can ask the OpenClaw main agent for help in plain language, and OpenClaw can use project context to turn that rough prompt into a full GitHub issue. With the default `openclaw` backend, it can also run the specialist agents CQ dispatches.
```

**Rationale:** This is the most important docs-index change. It explains “powered by OpenClaw” in plain architectural language while keeping the section led by GitHub/CQ. It also advertises the specific OpenClaw advantage requested in review: the operator can start with a simple human prompt, and OpenClaw’s context turns it into a real issue before CQ dispatches. It still cleanly handles both OpenClaw roles without implying Claude Code/Codex support is gone.

### 3.3 Update one feature card: “Local scheduler”

**Current:**

```yaml
- title: Local scheduler
  details: Your machine picks eligible issues, applies policy, and launches the configured local runner.
```

**Recommended:**

```yaml
- title: Local scheduler
  details: Your machine picks eligible issues, applies policy, and launches the configured runner — usually OpenClaw for full agent context, or direct CLI backends when configured.
```

**Rationale:** This makes OpenClaw visible in the feature scan, but only as the common/default runner path. It does not overtake the product framing.

### 3.4 Update the workflow labels to show OpenClaw intake before CQ dispatch

**Current:**

```html
<span>GitHub Issue</span>
<b>→</b>
<span>CQ Scheduler</span>
<b>→</b>
<span>Agent Mode</span>
<b>→</b>
<span>Local Runner</span>
<b>→</b>
<span>Worklog / PR / Comment</span>
```

**Recommended:**

```html
<span>Human Prompt</span>
<b>→</b>
<span>OpenClaw Main Agent</span>
<b>→</b>
<span>Full GitHub Issue</span>
<b>→</b>
<span>CQ Scheduler</span>
<b>→</b>
<span>Mode + Policy</span>
<b>→</b>
<span>OpenClaw / Local Runner</span>
<b>→</b>
<span>Worklog / PR / Comment</span>
```

**Rationale:** This directly addresses the review feedback. The current diagram starts after the valuable OpenClaw step has already happened, so it misses the strongest “powered by OpenClaw” story: an operator can give the OpenClaw main agent a simple request, OpenClaw uses context to create a full issue, and then CQ takes over as the durable scheduler/execution loop. The revised diagram adds that intake step without making CQ look secondary; CQ still owns queueing, policy, dispatch, and reporting.

### 3.5 Update the “How it works” steps to advertise the OpenClaw intake advantage

**Current:**

```html
<div><strong>1. Issue created</strong><br/>A task lands in GitHub Issues or Projects.</div>
<div><strong>2. Labels define intent</strong><br/>Labels map work to modes and safety policies.</div>
<div><strong>3. CQ picks eligible work</strong><br/>Scheduler checks status, locks, attempts, and policy.</div>
<div><strong>4. Runner executes locally</strong><br/>CQ launches OpenClaw, Codex, Claude Code, or another configured local runner.</div>
<div><strong>5. Results return to GitHub</strong><br/>Comments, artifacts, branches, PR links, and next steps are written back to the issue.</div>
```

**Recommended:**

```html
<div><strong>1. Human asks OpenClaw</strong><br/>Start with a rough operator prompt, question, or desired outcome.</div>
<div><strong>2. OpenClaw creates the issue</strong><br/>The main agent uses repo/profile context to turn the prompt into a scoped GitHub issue with the details CQ needs.</div>
<div><strong>3. Labels define intent</strong><br/>Labels map work to modes and safety policies.</div>
<div><strong>4. CQ picks eligible work</strong><br/>Scheduler checks status, locks, attempts, and policy.</div>
<div><strong>5. OpenClaw or another runner executes locally</strong><br/>CQ usually launches an OpenClaw specialist agent; direct Codex or Claude Code runners can be configured when that is the approved path.</div>
<div><strong>6. Results return to GitHub</strong><br/>Comments, artifacts, branches, PR links, and next steps are written back to the issue.</div>
```

**Rationale:** The previous recommendation only clarified execution. This version also sells the front half of the loop: OpenClaw’s context turns rough human intent into a complete issue, which is exactly where the OpenClaw relationship creates visible user value. It remains ClawQueue-first because CQ still takes over once the issue exists and preserves the durable workflow in GitHub.

### 3.6 Optional docs config change: no nav change recommended

**Recommendation for `docs/.vitepress/config.mts`:** no change.

**Rationale:** The nav and footer should stay product-simple. Adding OpenClaw to navigation would be too heavy-handed for a docs index issue and could send users away before they understand CQ. The docs page itself is the better place to explain the relationship.

If Manos wants a tiny site-wide signal later, the least invasive option would be footer copy:

```ts
footer: {
  message: 'GitHub issues in. OpenClaw-powered agent work out.',
  copyright: 'MIT Licensed'
}
```

I do **not** recommend this as part of the first implementation pass because the current footer is cleaner.

## 4. Overall rationale

These changes make the OpenClaw relationship explicit at three reading depths:

1. **Skimmers:** “Powered by OpenClaw” appears in the docs index signal row.
2. **Evaluators:** the docs index explains the two-part advantage: OpenClaw turns rough human prompts into full, context-aware GitHub issues, then CQ carries those issues through a durable GitHub scheduler/reporting loop.
3. **Implementers/operators:** the README clarifies that CQ decides issue selection, policy, backend launch, and reporting; OpenClaw is the upstream main-agent intake path and the primary/full-harness agent runtime, but not the only supported backend.

The tone remains ClawQueue-first because every proposed sentence leads back to CQ’s job: GitHub work contract, scheduler, policy, local execution, reviewable output. OpenClaw is credited as the underlying assistant/runtime layer and the context advantage that makes issue creation better, not sold as the whole destination.

## 5. Proposed follow-up implementation issue body

```md
## Context

CMO reviewed the README and docs index copy in #3 and proposed a small ClawQueue-first clarification of the OpenClaw relationship. The artifact was revised after review feedback to make the OpenClaw main-agent intake advantage explicit: a human can start with a rough prompt, OpenClaw uses project context to create a full GitHub issue, and CQ then handles scheduling, policy, execution, and review history.

Accepted artifact:
- <link to accepted worklog artifact>

Dependency note:
- Follow-up implementation issue #4 already exists and is parked in CQ Growth / Inbox. Move it to Todo only after this artifact is accepted.

## Task

Apply the accepted wording changes from the artifact to:

- `README.md`
- `docs/index.md`

Do not change `docs/.vitepress/config.mts` unless the reviewer explicitly asks for the optional footer copy. The recommendation is no nav/config change in the first pass.

## Scope

Implement the copy changes only:

1. Update the README opening relationship sentence.
2. Clarify the README “What runs work?” At a Glance row.
3. Add the README one-sentence boundary explanation near the “How CQ Fits” diagram/loop.
4. Polish the README “How Work Moves” backend clarification.
5. Update the docs index signal row to include “Powered by OpenClaw.”
6. Add the docs index OpenClaw boundary sentence after the opening section paragraph.
7. Update the docs index Local scheduler feature card.
8. Update the docs index workflow labels so the flow begins with `Human Prompt → OpenClaw Main Agent → Full GitHub Issue` before CQ scheduling.
9. Update the docs index “How it works” steps so they advertise OpenClaw’s issue-creation/context advantage before CQ dispatch and local execution.

## Acceptance criteria

- Copy is applied with minimal interpretation from the accepted artifact.
- Tone remains ClawQueue-first: OpenClaw is clearly credited/explained as the context-rich main-agent intake/runtime layer, while CQ remains the GitHub-native queue/scheduler/policy/reporting layer.
- No unrelated docs/content changes.
- Docs build or relevant docs validation passes.
- PR includes before/after summary and links back to issue #3/artifact.

## Validation

Run the project’s docs validation/build command if available. If no docs build command is available, at minimum inspect the rendered Markdown/frontmatter for syntax errors and include that in the PR testing notes.
```
