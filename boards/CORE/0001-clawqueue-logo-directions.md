# ClawQueue logo direction exploration

**Issue:** ClawQueue/ClawQueue#1  
**Date:** 2026-05-10  
**Status:** Internal concept exploration, not a final/public brand decision.

## Goal

Propose a small set of logo directions for ClawQueue based on the current README, design system, and repo presentation, so a human can choose which route is worth visual exploration next.

## Evidence reviewed

- `README.md` positions ClawQueue as a **local GitHub issue dispatcher for one operator and their agents**.
- The core framing is intentionally narrow and operator-controlled: **GitHub is the control plane, the machine runs the workers, and policy stays in editable markdown/config**.
- The README repeatedly emphasizes durable work contracts, GitHub Issues/Projects, local execution, audit trail, review history, profile-specific agents, and human review.
- The warning block makes the trust boundary explicit: CQ shells out to local CLIs and expects a trusted operator.
- The repo presentation already has a dark, operational visual language: deep navy `#07111E`, blue `#317AE8`, amber/claw accent `#F59E0B`, mono-heavy labels, terminal density, and a current lightning/claw-like seed mark in `docs/banner.svg` and `preview/brand.html`.
- Voice/tone examples in `preview/brand.html` favor direct, precise, operational copy over vague AI-marketing language.

## Product personality and visual cues

**Personality:** precise, local-first, durable, inspectable, agentic but not magical, trusted-operator oriented, GitHub-native, safety-conscious, and intentionally small.

**Tone:** operational, sober, slightly technical, explicit about boundaries, anti-hype, friendly to builders/operators who want control.

**Positioning cues:** CQ is not trying to be a broad SaaS PM layer or an “AI company OS” brand. It is closer to a dispatch switchboard / queue runner / control loop that sits between GitHub issues and local agent runners.

**Visual cues already present:** dark control-plane background, amber activity/accent, blue system/control color, dense UI metadata, sharp-radius cards, monospace labels, and a compact CQ short-name convention.

## Logo direction criteria

A strong CQ logo should:

1. Work as a tiny GitHub/avatar/favicon mark as well as a README wordmark.
2. Signal dispatch, queueing, local control, or human-agent handoff without becoming a generic robot logo.
3. Preserve the current dark/amber/blue operational system.
4. Avoid overclaiming autonomy or magic.
5. Stay simple enough to render in SVG/CSS and to sit comfortably inside GitHub documentation.

---

## Direction 1: **Dispatch Claw**

**Concept label:** A refined version of the current lightning/claw seed mark.

**Rationale:** This direction keeps continuity with the existing banner and design system while making the symbol more ownable. The current amber bolt already implies agent activity, dispatch, and fast execution. By shaping it slightly more like a claw stroke or hooked path, the mark can carry both “Claw” and “dispatch” without adding new metaphors.

**Brand feel:** energetic, compact, agent-active, familiar to current repo presentation, closest to the existing seed brand.

**Rough visual description:** A rounded square app tile in deep navy or translucent amber. Inside: a single angular amber stroke, somewhere between a lightning bolt, terminal cursor path, and claw slash. Wordmark uses `Claw` in light foreground and `Queue` in amber, with the icon left-aligned.

**Works well for:**

- README banner and badges
- GitHub org/repo avatar
- Favicon/app icon
- Existing dark-mode design system
- “Agent dispatched” moments in UI

**Might fail when:**

- The lightning shape feels too generic or too much like “speed/energy” rather than durable workflow.
- It over-indexes on “Claw” and under-explains “Queue”.
- It resembles existing automation/devtool marks if not customized enough.

---

## Direction 2: **Issue Switchboard**

**Concept label:** GitHub issues routed through a local control node.

**Rationale:** CQ’s clearest product truth is routing issue work into agent runs. A switchboard/router mark would express the product more literally than a claw. It can visually connect GitHub issue cards, labels, and runner endpoints while staying sober and operational.

**Brand feel:** trustworthy, infrastructural, system-level, precise, less flashy than the claw mark.

**Rough visual description:** A compact node-and-path icon: three small queue dots/cards on the left converge into a central amber dispatch node, then split toward one or two runner outputs. The mark could be drawn as circuit-like lines or GitHub-project column paths inside a rounded square. Amber marks the active dispatch node; blue marks the system paths.

**Works well for:**

- Explaining the product at a glance to new operators
- Architecture diagrams and docs
- Enterprise/internal tooling contexts
- Visualizing “GitHub control plane → local runners”

**Might fail when:**

- At favicon size, routing lines may become too detailed.
- It could feel like generic infrastructure/network software.
- It is less emotionally distinctive than a claw/animal-inspired mark.

---

## Direction 3: **Queue Bracket**

**Concept label:** A typographic CQ mark built from brackets, queue slots, and terminal rhythm.

**Rationale:** The README and design system are mono-heavy and operator-centric. A bracket-based logo could emphasize markdown/config, local CLIs, issue contracts, and inspectable workflows. This is the most “developer-native” direction.

**Brand feel:** technical, restrained, terminal-native, inspectable, precise.

**Rough visual description:** A monogram-like `CQ` or `[CQ]` mark where the `Q` becomes a queued item or circular status loop. Possible variants: `[C→Q]`, `CQ>` with a tiny amber cursor, or three stacked queue bars nested inside a `Q`. The wordmark could use Barlow for warmth but keep the icon in JetBrains Mono.

**Works well for:**

- CLI docs and terminal surfaces
- GitHub README/favicon contexts
- Developer/operator trust
- Monochrome applications

**Might fail when:**

- It may feel too cold or too generic as a product brand.
- `CQ` alone may not communicate enough to new users.
- The bracket/cursor language may overlap many devtool identities.

---

## Direction 4: **Human-in-the-Loop Queue**

**Concept label:** A queue lane with a human approval/checkpoint built into the flow.

**Rationale:** The README is explicit that CQ does not remove humans: issues become durable contracts, workers report results, and humans review before accepting or publishing. A mark that shows a queue passing through a deliberate checkpoint would distinguish CQ from “autonomous agent” hype.

**Brand feel:** safe, deliberate, review-oriented, calm, governance-friendly.

**Rough visual description:** Three small stacked issue cards or queue bars move left-to-right through a central checkpoint/hand-off symbol. The checkpoint could be a small amber gate, check, or pause/control glyph. The right side resolves into a completed issue card or comment bubble. The shape should remain geometric, not illustrative.

**Works well for:**

- Communicating trust boundaries and review flow
- Operator workflow docs
- Larger header art or onboarding pages
- Teams concerned about agent safety/auditability

**Might fail when:**

- It may become too explanatory and not iconic enough.
- The human-review concept is harder to compress into a tiny mark.
- If drawn too literally, it could look like generic process-management software.

---

## Direction 5: **Local Control Plane**

**Concept label:** A compact “machine + GitHub board” control-plane emblem.

**Rationale:** CQ’s differentiated promise is local execution with GitHub as durable state. This direction leans into the local-machine/operator boundary rather than the agent or queue metaphor alone.

**Brand feel:** grounded, secure, local-first, control-oriented, infrastructure-grade.

**Rough visual description:** A minimal terminal/window rectangle containing a small queue column and an amber active runner dot. Optional outer rounded-square frame implies a local machine. A tiny branch/issue path could enter from the top-left and exit as a comment/artifact line.

**Works well for:**

- Trust-boundary messaging
- Docs about setup, private config, and local runners
- Operators who care about “not SaaS” positioning
- Dark UI surfaces

**Might fail when:**

- It may look more like a generic dashboard/app icon than a distinctive logo.
- It may underplay the memorable “Claw” name.
- It could be visually busy unless heavily simplified.

---

## Recommendation

### Strongest direction: **Dispatch Claw**

This is the best first route because it preserves the existing seed identity while giving it more intentional meaning. It is distinctive enough for an icon, already compatible with the current palette, and can be refined without changing the design system. It also gives CQ a memorable visual hook without drifting into robot/AI clichés.

Recommended refinement brief: make the current lightning/claw mark more ownable by combining three ideas in one simple stroke: **claw slash + dispatch arrow + terminal energy**.

### Strong alternate: **Issue Switchboard**

This is the best strategic alternate if the team wants the mark to explain the product more directly. It is less distinctive than Dispatch Claw, but it anchors the identity in CQ’s real behavior: GitHub issues routed through local policy into workers, then back to review.

Recommended exploration: create a simplified switchboard mark that can collapse to one amber dispatch node and two blue paths at small sizes.

## Suggested follow-up image/logo generation prompts

Use these only after choosing a direction. Keep outputs exploratory and internal.

### Prompt A — Dispatch Claw

> Design 6 rough logo mark concepts for “ClawQueue”, a local GitHub issue dispatcher for human-agent teams. Visual style: dark navy operator tooling, amber activity accent, precise developer UI, not SaaS-marketing. Core symbol: a single simple mark combining a claw slash, dispatch arrow, and lightning-like agent activity. Must work as a tiny GitHub avatar/favicon and as a README wordmark. Avoid robots, mascots, glossy 3D, and generic AI sparkles. Palette: #07111E navy, #317AE8 blue, #F59E0B amber, #E8EDF5 foreground.

### Prompt B — Issue Switchboard

> Design 6 rough logo mark concepts for “ClawQueue”, a GitHub-native issue dispatch tool. Core symbol: GitHub issue queue items routed through a local dispatch/switchboard node into agent runners, then back to review. Style: minimal SVG-like geometry, dark-mode developer tooling, precise and trustworthy. Use amber only for the active dispatch point, blue for system paths, deep navy background. Avoid complex diagrams; each mark must remain legible at favicon size.

### Prompt C — Comparison sheet

> Create a black-background concept sheet comparing two logo directions for “ClawQueue”: 1) Dispatch Claw, a single amber claw/arrow/bolt stroke; 2) Issue Switchboard, a minimal routing-node mark. Show icon-only, horizontal wordmark, monochrome, and tiny favicon versions. Brand feel: local-first, GitHub-native, operator-controlled, durable work queue, human review. No mascots, no robots, no glossy gradients.

## Human approval note

All directions above are internal exploratory concepts. Any public logo selection should go through human review, small-size checks, basic similarity checks against neighboring devtool logos, and at least one pass as plain SVG on the existing README/design-system surfaces.
