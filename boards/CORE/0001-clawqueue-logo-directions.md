# ClawQueue Logo Direction Exploration

**Issue:** ClawQueue/ClawQueue#1  
**Date:** 2026-05-17  
**Status:** Retry-pass internal concept exploration for human selection. Not public launch guidance. No product/source files changed.

## Goal

Study the current ClawQueue README, product framing, docs tone, and current brand assets, then propose a small set of logo directions a human can choose from before any further visual generation or implementation work.

## Audience Or Segment

Primary audience: trusted operators, maintainers, and technical users who understand GitHub Issues/Projects and want local, reviewable agent work without adopting a hosted PM layer.

Secondary audience: contributors evaluating whether ClawQueue is a serious, inspectable workflow tool or just another broad agent-orchestration pitch.

## Evidence Reviewed

- Current root README.md, especially the framing: local human-agent workflow engine for GitHub, GitHub holds the durable work contract, your machine runs the workers, and policy stays in markdown/config.
- Current docs homepage copy and flow: Local GitHub issue dispatch for operator-controlled AI agents and Keep the contract in GitHub. Run the workers locally.
- COMPANY_CHARTER.md, which emphasizes evidence before claims, human accountability, small verifiable steps, and human approval before external commitments.
- Current design-system notes in docs/.vitepress/brand/README.md: full horizontal logo, mascot hero art, clean white docs surfaces, deep navy workflow panels, orange/red claw gradient CTAs, Space Grotesk/Inter typography.
- Current brand tokens: deep navy, ink navy, lobster orange/red, cyan/signal blue, ice blue, white, muted blue-gray.
- Current visual assets: horizontal wordmark, icon-with-queue, queue symbol, mascot-only art, favicons/app icons.

## Product Personality And Visual Cues

ClawQueue reads as:

- local-first and operator-controlled
- GitHub-native rather than a new PM surface
- inspectable, policy-driven, and markdown/config-friendly
- agentic, but explicitly not magical or fully autonomous
- pragmatic and safety-conscious, with human review as a core part of the loop
- friendly enough for docs and onboarding, but still a tool for trusted technical operators

The current brand pack already shifted the visual tone from the earlier dark terminal-only seed into a friendlier docs identity: clean white surfaces, navy/orange/cyan accents, rounded wordmark, and a robot/claw mascot. That is useful, but it creates a real decision: should the primary logo lead with the current friendly mascot energy, or should it tighten around the actual product behavior: queue, dispatch, local control, review?

## Logo Direction Criteria

A strong ClawQueue logo should:

1. Work at favicon/GitHub avatar size, not only as a large hero illustration.
2. Make queue and dispatch legible without becoming a literal architecture diagram.
3. Preserve the current orange/navy/cyan system unless there is a strong reason to reset it.
4. Avoid generic robot, AI sparkle, and autonomous-agent cliches.
5. Support the serious trust boundary: GitHub is the durable contract, humans approve, workers run locally.
6. Pair well with the current mascot without forcing the mascot to carry every logo use case.

## Direction 1: Queue Q Core

**Concept label:** The Q becomes the product mark: queue slots, dispatch arrow, and review loop in one simple glyph.

**Rationale:** The current assets already imply this route through the queue-symbol and icon-with-queue. It is the most direct bridge between the product name and the product behavior. It can become the core logo mark while the mascot remains supporting art.

**Brand feel:** clear, product-specific, technical but approachable, durable, less hype-driven than a mascot-first system.

**Rough visual description:** A bold rounded Q built from navy outline and orange active segment. Inside the counter: two or three short queue bars or issue slots. The tail of the Q becomes a dispatch arrow or claw-like movement stroke. Optional cyan dot marks the active runner, but the small-size version should work in one or two colors.

**Works well for:**

- GitHub org/repo avatar
- favicon/app icon
- README header next to the wordmark
- docs navigation
- monochrome or two-color uses
- explaining queue plus dispatch quickly

**Might fail when:**

- The internal queue bars become too small or decorative at 16px.
- The mark feels too close to a generic SaaS app icon if the tail is not distinctive.
- The Q carries the name well, but may not communicate Claw unless the dispatch tail has a subtle hook.

## Direction 2: Dispatch Claw

**Concept label:** A single orange claw/arrow stroke that signals grabbing, routing, and sending work.

**Rationale:** This keeps the strongest metaphor from the name. It can be more ownable and energetic than a pure Q, while staying simpler than the mascot. It also aligns with the orange/red claw gradient already used for CTAs.

**Brand feel:** fast, active, memorable, slightly aggressive, strong as a badge or sticker.

**Rough visual description:** A deep navy rounded square or transparent mark containing one angular orange/red stroke. The stroke should combine a claw hook, dispatch arrow, and terminal/action pulse. Pair it with the existing wordmark or a cleaned-up ClawQueue lockup.

**Works well for:**

- avatar and favicon where simplicity matters
- launch graphics and stickers
- worker dispatched moments in UI
- retaining some continuity with the current claw/mascot language

**Might fail when:**

- It can read as generic speed/lightning rather than durable work routing.
- It underplays GitHub, queueing, and review.
- If too sharp, it may clash with the current friendly rounded wordmark.

## Direction 3: Operator Switchboard

**Concept label:** GitHub issue queue routes through a local control node into approved runners.

**Rationale:** This is the most literal product-positioning route. It says ClawQueue is a control loop, not a mascot or generic AI tool. It is especially strong for docs, architecture diagrams, and operator trust.

**Brand feel:** infrastructural, sober, precise, control-plane oriented.

**Rough visual description:** Three small issue cards or dots enter from the left, converge into one orange dispatch node, then route out through two blue lines. A small return path or check node suggests review. The icon should be aggressively simplified: one node, two paths, no miniature full diagram.

**Works well for:**

- technical docs
- diagrams and system explanations
- enterprise/internal-tool contexts
- landing-page sections about GitHub in, local work out

**Might fail when:**

- It may be too complex for favicon size.
- It can feel generic, like networking or workflow automation.
- It has less emotional memorability than the claw or mascot routes.

## Direction 4: Mascot Companion System

**Concept label:** Keep the robot/claw mascot as the memorable brand character, but do not make it the only logo.

**Rationale:** The current mascot is distinctive and approachable. It helps soften an otherwise technical, trust-boundary-heavy product. But the mascot has too much detail to carry favicon, README badge, or serious control-plane use alone.

**Brand feel:** friendly, playful developer tool, memorable, community-friendly.

**Rough visual description:** Use the current mascot in hero art, social preview, stickers, empty states, and launch posts. Create a simplified mascot head/claw silhouette for large app-icon uses. Pair with Queue Q Core or Dispatch Claw as the primary small mark.

**Works well for:**

- docs homepage hero
- social preview art
- community/sticker assets
- making ClawQueue feel more human and less sterile

**Might fail when:**

- It can make the product feel toy-like if overused in serious docs.
- It loses legibility quickly at small sizes.
- Robot imagery risks blending into generic AI-tool branding.

## Direction 5: Terminal Queue Badge

**Concept label:** A compact CLI/control badge that makes local execution and inspectability the main signal.

**Rationale:** The README repeatedly emphasizes local machine execution, shelling out, markdown/config policy, and trusted operator control. A terminal badge could foreground that difference from hosted SaaS or opaque agent platforms.

**Brand feel:** developer-native, restrained, inspectable, practical.

**Rough visual description:** A rounded terminal window or badge with CQ and two queue bars. An orange prompt/cursor or active job dot marks the dispatch moment. The wordmark can stay friendly, while the badge signals that ClawQueue is a local operator tool.

**Works well for:**

- CLI docs
- installation/setup pages
- technical audiences
- monochrome README contexts

**Might fail when:**

- It may look like any other CLI tool.
- It underuses the Claw name.
- It is less flexible for public brand/website use than Queue Q Core.

## Recommendation And Decision Aid

### Selection Matrix

Scores are directional, not final design judgment. They are meant to help Manos choose which route deserves visual exploration first.

| Direction | Product clarity | Tiny-size potential | Distinctiveness | Fit with current assets | Risk |
|---|---:|---:|---:|---:|---|
| Queue Q Core | High | High | Medium | High | Can become generic if the Q tail is not ownable |
| Dispatch Claw | Medium | High | High | Medium-high | Can read as speed/lightning instead of queue/review |
| Operator Switchboard | High | Low-medium | Medium | Medium | Too diagrammatic at small sizes |
| Mascot Companion System | Medium | Low | High | High | Too playful/detailed as the primary logo |
| Terminal Queue Badge | Medium | Medium | Low-medium | Medium | Generic CLI-tool feel |

### Approval-Ready Decision

Recommended approval decision: **approve Queue Q Core for the next visual refinement pass**, with **Dispatch Claw as the comparison route**. Keep the mascot in the brand system, but treat it as supporting art until small-size tests prove otherwise.

The next artifact should not be another strategy memo. It should be a visual comparison sheet with:

- Queue Q Core and Dispatch Claw side by side
- icon-only, horizontal wordmark, monochrome, and dark/light background variants
- 16px, 32px, 128px, and README-header previews
- one short scorecard for readability, product clarity, distinctiveness, and current-brand fit

### Strongest route: Queue Q Core

Choose **Queue Q Core** as the primary logo direction to refine. It best matches the current state of the brand pack and the README truth: ClawQueue is about queueing durable GitHub work and dispatching it locally. It can be made small, product-specific, and serious enough for GitHub while still pairing with the friendly mascot.

Recommended refinement brief: simplify the current queue-symbol/icon-with-queue into a crisp primary mark. Prioritize small-size legibility, a distinctive Q tail, and a two-color version using navy plus orange/red.

### Strong alternate: Dispatch Claw

Keep **Dispatch Claw** as the best alternate if Manos wants more energy and memorability. It is stronger emotionally, but weaker at explaining the product. It should be tested next to Queue Q Core in tiny sizes, README header use, and social preview use.

### Supporting system: Mascot Companion

Keep the mascot, but treat it as supporting brand art rather than the main logo mark. It is useful for warmth and recall; it should not be forced into every small or official surface.

## Suggested Follow-Up Prompt Set

Use these after choosing the route. These are internal exploration prompts, not public approval.

### Prompt A: Queue Q Core

> Create 8 rough logo mark explorations for ClawQueue, a local GitHub issue dispatch tool for operator-controlled AI agents. Core idea: a bold, simple Q that contains queue slots and a dispatch arrow or subtle claw-tail. Style: clean developer tooling, readable at favicon size, not glossy, not generic AI. Palette: deep navy #07162B, lobster orange #FF4A12, signal blue #158BFF, white. Show icon-only, wordmark lockup, monochrome, and tiny 16px preview.

### Prompt B: Dispatch Claw

> Create 8 rough logo mark explorations for ClawQueue. Core idea: a single simple orange/red claw stroke that also reads as a dispatch arrow moving work through a queue. Brand feel: local-first, GitHub-native, operator-controlled, energetic but not hypey. Must work as favicon and README wordmark. Avoid robots, sparkles, glossy 3D, and complex diagrams. Palette: deep navy, lobster orange/red, small cyan accent only if needed.

### Prompt C: Mascot Support System

> Create a compact brand sheet for ClawQueue showing how the existing robotic claw mascot can support, but not replace, a primary Q queue logo. Include: primary icon, mascot hero use, GitHub avatar, favicon, README header, social preview. Keep the mascot friendly but reduce detail for small sizes. Style: clean docs product, not toy-like, not enterprise bland.

### Prompt D: Comparison Sheet

> Create a black/white and color comparison sheet for two logo directions: 1) Queue Q Core, a Q with queue bars and dispatch tail; 2) Dispatch Claw, a single claw/arrow action stroke. Show each at 16px, 32px, 128px, horizontal wordmark, and monochrome. Score each for readability, distinctiveness, product clarity, and fit with the current ClawQueue docs brand.

## Success Metric

This artifact succeeds if Manos can choose one of three next actions without more strategy work:

- approve Queue Q Core for visual refinement
- request a Dispatch Claw comparison pass
- keep the current mascot/wordmark system and only refine small-size marks

The next measurable signal should be a visual comparison sheet with small-size previews and a human approval decision.

## Human Approval Note

This is internal brand exploration only. Any public logo change, README asset replacement, GitHub social preview update, or docs brand-system update needs explicit human approval before implementation.
