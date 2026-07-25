---
title: "Feature Directions: From Research to Design"
area: product
file: research/product/feature-directions.md
tags: [feature-directions, synthesis, user-journey, capture, task-initiation, time-blindness, motivation, emotional-safety, ai]
related:
  - research/product/design-principles.md
  - research/product/anti-patterns.md
  - research/product/app-landscape.md
  - research/product/ux-design-for-adhd.md
  - research/product/ai-assistance-for-adhd.md
  - research/product/when-to-back-off.md
  - research/daily-life/task-initiation-and-paralysis.md
  - research/foundations/time-perception.md
  - research/foundations/memory-and-object-permanence.md
  - research/foundations/emotional-regulation-and-rsd.md
sources: 0
updated: 2026-07-25
summary: >
  Forty-five evidence-grounded feature directions for Klyr, organized by user journey stage
  (capture through return-after-absence) plus five cross-cutting layers. Not a spec and not a
  roadmap — the bridge from the research corpus to design work, with per-direction constraints,
  risks, and honest confidence grades.
---

# Feature Directions: From Research to Design

## TL;DR

- This doc translates the corpus into **45 small, composable feature directions** — not a spec, not a roadmap, and deliberately not a list of grand modules. Each direction names its problem, sketches an interaction, lists research constraints, names risks, and carries an honest confidence grade.
- Organization follows the user journey — **Capture → Clarify → Plan → Start → Focus and sustain → Transition and finish → Review and recover → Return after absence** — then five cross-cutting layers: **Time; Motivation and reward; Emotional safety; AI assistance; Integrations and ubiquity**.
- The strongest evidence-backed directions: **instant zero-decision capture**, **next-action extraction**, **if-then cue binding** (d ≈ 0.65 meta-analytic), **task shrinking**, **ready-to-resume bookmarks**, **visual time**, and **instant unconditional completion acknowledgment**.
- The market-defining direction is not a feature but a posture: Klyr is **the system that survives neglect** — elastic recurrence, overdue amnesty, automated review, and a restart ritual together make "miss two weeks, come back painlessly" the core loop, because the miss→shame→abandon step is where every competitor dies ([app-landscape](app-landscape.md)).
- Everything here inherits two universal rules: **capture and comeback must cost nearly nothing; pressure and novelty are user-owned dials, never house policy** ([ux-design-for-adhd](ux-design-for-adhd.md), [populations-and-variation](../foundations/populations-and-variation.md)).
- AI's place is **invisible infrastructure first, conversation only at stuck moments**, with a suggest→preview→undo trust ladder and a hard no-companion boundary ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).
- Recurring tensions are reconciled explicitly in the intro table: urgency-vs-anxiety, novelty-vs-stability, forgiveness-vs-momentum, resurfacing-vs-habituation, privacy-vs-recoverability, automation-vs-legibility.
- Confidence is graded honestly: roughly a quarter of directions are **evidence-backed**, most are **promising** (consistent community/market evidence or strong mechanism fit, no controlled trials), and a few are flagged **speculative** — bets Klyr would be validating, not implementing.
- Every direction must pass the corpus's cost test before design work starts: *what does this cost the user on their worst week?* ([adhd-overview](../foundations/adhd-overview.md))

## How to read this document

**What it is.** The bridge between the research corpus and design work: the set of product moves the evidence actually supports, sized small enough to design, test, and ship semi-independently. Directions are intentionally composable — several attack the same failure loop from different stages (e.g., amnesty, elastic recurrence, and the restart ritual are one strategy seen from three moments).

**What it is not.** Not a spec (no screens, no data models), not a roadmap (no sequencing, no effort estimates), and not a principles doc — the value hierarchy lives in [design-principles.md](design-principles.md), and the things Klyr must never build live in [anti-patterns.md](anti-patterns.md). Risks below reference anti-pattern themes by name.

**Confidence grades.**

| Grade | Meaning |
|---|---|
| **evidence-backed** | The core mechanism or harm has peer-reviewed (often meta-analytic) support, and the direction implements it directly. The *app delivery* may still be untested. |
| **promising** | Consistent community, clinical, or market evidence plus a coherent mechanism; no controlled tests. The corpus's "legitimate design material if labeled honestly" tier ([evidence-based-strategies](../strategies/evidence-based-strategies.md)). |
| **speculative** | A coherent bet from mechanism or thin/indirect evidence. Build to learn, not to rely on. |

**Tensions this doc had to reconcile.** Where corpus docs pull in opposite directions, the resolution is named here and applied throughout:

| Tension | Docs in conflict | Resolution used below |
|---|---|---|
| Urgency activates ADHD brains / urgency harms anxious, demand-sensitive users | [dopamine-and-motivation](../foundations/dopamine-and-motivation.md) vs. [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md), [motivation-and-gamification](../strategies/motivation-and-gamification.md) | Urgency is **opt-in equipment**, defaulted low, per-task adjustable; urgency about the task, never judgment about the person (direction 34) |
| Novelty sustains engagement / unannounced change harms AuDHD users | [evidence-based-strategies](../strategies/evidence-based-strategies.md) vs. [populations-and-variation](../foundations/populations-and-variation.md) | Novelty is **offered and previewed, never sprung**; stability is the default (direction 31) |
| Medication-window planning is real user practice / the product must never be medication-shaped | [task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md) vs. [time-perception](../foundations/time-perception.md), [privacy-and-data-ethics](privacy-and-data-ethics.md) | Neutral **"energy windows"** the user can privately mean anything by; sensitive-tier storage; the product never names medication (direction 9) |
| Forgiveness prevents shame-abandonment / forgiving everything dissolves the commitment device | [habits-and-routines](../daily-life/habits-and-routines.md) internal tension | **Forgiving by default, opt-in intensity**; instrument both (directions 32, 34) |
| Aggressive resurfacing is the memory prosthesis / repetition habituates and shames | [memory-and-object-permanence](../foundations/memory-and-object-permanence.md) internal tension | Budgeted, **form-shifting** resurfacing; three ignores = change strategy, not volume (direction 23) |
| E2E privacy / never-lose-anything trust contract | [privacy-and-data-ethics](privacy-and-data-ethics.md) vs. [memory-and-object-permanence](../foundations/memory-and-object-permanence.md) | Two-tier architecture: recoverable task graph, E2E-optional sensitive fields (directions 2, 9) |
| Automation removes maintenance burden / black-box automation breaks system trust | [planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md) internal tension | Every automated change is **legible and undoable**: visible reasoning, one-tap revert (directions 7, 22, 40) |

---

## Capture

The corpus is unanimous: thoughts evaporate in seconds, capture is the cheapest moment to help, and any decision demanded at capture time is a drop point ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md), [ux-design-for-adhd](ux-design-for-adhd.md)).

### 1. Instant capture with deferred clarification

**Problem.** Working memory in ADHD is a leaky scratchpad — uncaptured intentions decay in seconds, and an intrusive "must act on it now or lose it" thought (**distraction-by-anticipation**, corpus working term) derails the current task ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md), [attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)). Per-capture filing decisions are exactly how PARA-style systems die ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

**Direction.** A capture field reachable in under three seconds from anywhere — lock screen, widget, share sheet, voice, and a two-keystroke overlay *inside* Klyr that never navigates away from the current view. No required fields: no project, date, priority, or category. The item lands visibly ("got it") in a single inbox; all clarification is deferred to later, better moments (direction 4). Natural-language fragments and typos are accepted as-is; parsing is Klyr's job, not the user's (direction 40).

**Constraints from research.**
- Sub-3-second, zero-decision capture; every added tap or field is a documented drop point ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).
- Capture during a focus session must be an overlay that returns to the exact prior state — otherwise capture *is* the interruption ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).
- First capture within ~60 seconds of first open, before any account wall ([ux-design-for-adhd](ux-design-for-adhd.md), [app-landscape](app-landscape.md)).
- Sub-400 ms feedback; waiting is affectively costly, not just inconvenient ([ux-design-for-adhd](ux-design-for-adhd.md), [dopamine-and-motivation](../foundations/dopamine-and-motivation.md)).

**Risks.** Frictionless capture without the downstream triage engine (directions 4, 22, 23) manufactures a doom pile — the *overdue shame stacks* anti-pattern (AP-1, [anti-patterns.md](anti-patterns.md), [daily-life-impact](../daily-life/daily-life-impact.md)). Voice capture may be unusable in public; silent fast paths must be equal citizens ([ux-design-for-adhd](ux-design-for-adhd.md) open questions).

**Confidence: evidence-backed** — the working-memory and prospective-memory mechanisms are among the most replicated in the corpus; the exact 3-second threshold is a community heuristic, not a measured constant.

### 2. The nothing-is-ever-lost guarantee

**Problem.** The mind releases an open loop only when it trusts the external system to bring the item back; one silently dropped capture can collapse that trust permanently ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)). Klyr's own tidying features (amnesty, auto-archive) make this guarantee load-bearing.

**Direction.** A visible, queryable trust surface: "everything I ever captured" always works — one search box over every state including archived, parked, and amnestied items. Every automated tidy leaves a trace the user can inspect and reverse. Deletion exists only as an explicit user act (and as user-owned amnesty, direction 23); timeouts and sync failures never eat text ("that didn't save — we kept your words").

**Constraints from research.**
- No auto-archive without a visible trace; no expiring items; no captures that vanish into unsearchable states ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).
- Undo instead of confirmation, archive instead of delete, autosave everything ([ux-design-for-adhd](ux-design-for-adhd.md)).
- Recoverability beats maximal encryption for the task graph; E2E is reserved for the sensitive tier, with an honest tradeoff screen ([privacy-and-data-ethics](privacy-and-data-ethics.md)).

**Risks.** A browsable everything-archive can become a shame museum if it is ever *pushed* rather than pulled — the *overdue shame stacks* anti-pattern (AP-1, [anti-patterns.md](anti-patterns.md)); historical incompletions must be queryable by the user, never surfaced at them ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).

**Confidence: promising** — the trust mechanism (GTD's "trusted system," Zeigarnik framing) is conceptually strong and community-consistent; no direct studies of trust collapse and repair in task apps exist.

---

## Clarify

Planning — not retention, not execution — is the measurably broken step (d = 1.60 in the best adult component study; [memory-and-object-permanence](../foundations/memory-and-object-permanence.md)). Clarification is therefore work Klyr does *with* the user, in drips, never as a gate.

### 3. Next-action extraction

**Problem.** An item with no defined next physical action gets silently skipped on every list scan; task ambiguity is a silent blocker, and decomposing is itself the impaired executive function ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md), [executive-function](../foundations/executive-function.md)).

**Direction.** Every actionable item carries — or is one tap from generating — a concrete next physical action with a physical verb and single object ("call Dr. Ellis re: referral," not "sort out health stuff"). At capture-to-plan moments Klyr proposes the next action (AI-assisted, direction 39); the user edits or accepts in one tap. The next action, not the task title, is what lists, reminders, and widgets display first.

**Constraints from research.**
- The next action must be stored with the task, not reconstructed at initiation time ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).
- One visible sentence, zero taps to see it — covert self-speech is "weak as a source of stimulus control" ([executive-function](../foundations/executive-function.md)).
- Reminders must carry the action, not the task name: "Report" re-triggers the freeze; "Open report doc — one bad paragraph" is a launch instruction ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md), [memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).

**Risks.** Requiring a next action *at capture* would kill capture (*buried capture* anti-pattern, AP-20, [anti-patterns.md](anti-patterns.md)); extraction must be deferred and assisted. Machine-proposed actions that miss the point erode trust fast — apply the suggest→preview→undo ladder (direction 40).

**Confidence: evidence-backed** — chunking into concrete actions is a validated CBT ingredient and GTD's best-fitting mechanic for ADHD; the skip-ambiguous-items mechanism is well documented.

### 4. Drip-fed clarification at natural moments

**Problem.** Batch triage rituals (inbox zero, weekly processing) are boring, delayed-reward, EF-heavy — the exact task profile ADHD handles worst — and their lapse is how systems fill with accusing debris ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

**Direction.** Klyr never shows "47 unprocessed items." Instead it asks **one** clarifying question at a natural moment: when the user opens the day plan, finishes a task, or has declared a waiting gap — "You captured 'mom birthday' Tuesday. Want a next step, a date, or leave it parked?" One item, one tap-sized decision, skippable without consequence. Planning happens *with* the user: prompt for when/where/first-step, prefill defaults, attach the cue ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).

**Constraints from research.**
- One elaboration question at the right moment beats ten reminders later ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).
- Surfacing one stale item at a time as a single keep/kill/someday tap is the corpus's replacement for the weekly review ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).
- Skipping the question must be penalty-free and unrecorded — demand sensitivity turns obligatory prompts aversive ([motivation-and-gamification](../strategies/motivation-and-gamification.md)).

**Risks.** Too many micro-questions become nagging (notification carpet-bombing anti-pattern, [anti-patterns.md](anti-patterns.md)); prompt fatigue is documented in exactly this population ([outcomes-and-measurement](outcomes-and-measurement.md)). Budget clarification prompts as strictly as notifications.

**Confidence: promising** — built from two well-documented failure modes (per-capture filing and batch reviews both die); the drip cadence itself is untested.

### 5. If-then cue binding

**Problem.** Time-based intentions ("at 5pm") are the most reliably impaired prospective-memory channel in ADHD; event-based intentions ("when I get home") are relatively spared. Vague intentions without a cue mostly don't fire ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).

**Direction.** **Implementation intentions** as a first-class object, not a text note: when a user commits to a task, Klyr prompts for a cue — "after lunch," "when I close my laptop," "right after standup" — and stores the plan as if-then. Reminders fire *at the cue* (calendar-event end, location, task completion, device event), worded as the pre-made decision. When a user sets a bare time reminder, Klyr offers to convert it to an event anchor ("5pm — is that 'when you close your laptop'?").

**Constraints from research.**
- If-then planning: d = 0.65 across 94 tests, d ≈ 0.99 in clinical samples, with ADHD-sample replications — the best-evidenced portable technique in the corpus ([evidence-based-strategies](../strategies/evidence-based-strategies.md), [task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)).
- Cue anchors must be schedulable, triggerable entities in the data model ([executive-function](../foundations/executive-function.md)).
- Anchors themselves can be unreliable in ADHD lives; pair every anchor with a redundant external prompt and let users flag shaky anchors ([habits-and-routines](../daily-life/habits-and-routines.md)).

**Risks.** Geofencing is battery-hungry, imprecise, and privacy-sensitive ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md) open questions); location cues need graceful failure. Forcing cue selection on every task would be setup tax — offer, don't require.

**Confidence: evidence-backed** — the strongest effect size in the corpus; app-delivered versions still need decay testing.

---

## Plan

Planning features must assume the plan will break and make breakage cheap. Manual time blocking "collapses by 10am Monday"; what ADHD users love about auto-schedulers is guilt-free *re*-scheduling ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

### 6. The tiny day plan with a gentle WIP cap

**Problem.** Boom-phase planning is systematically inflated — capacity varies more than schedule does — and a 14-item day plan guarantees a visibly failed day ([daily-life-impact](../daily-life/daily-life-impact.md)). Strict priority ordering breaks on energy variance ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

**Direction.** Today is a short list by construction: 1–3 protected items plus an optional bench. Adding a fourth prompts an honest choice — "add it, and which of these moves to the bench?" — never a refusal. WIP limits on active tasks default on (2–3 in "doing"); starting beyond the cap offers finish-or-park. Overcommitment gets absorbed with capacity feedback ("yesterday-you scheduled 14 things; pick 3 protected ones"), never displayed as failure.

**Constraints from research.**
- WIP limits externally enforce finishing over starting — the strongest structural fit from Kanban ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).
- Never punish over-listing; absorb it gracefully ([executive-function](../foundations/executive-function.md)).
- Tiny-plan formats (MIT/1-3-5) fit ADHD capacity, but "most important" selection is the hard part — assist it (direction 13, direction 39).

**Risks.** A hard cap reads as the app bossing the user (demand-sensitivity backlash, [motivation-and-gamification](../strategies/motivation-and-gamification.md)); caps must be soft, negotiable, and framed as protection. Default WIP numbers are community folklore, not measured ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md) open questions).

**Confidence: promising** — strong community verdict and coherent mechanism; no controlled tests of caps in ADHD populations.

### 7. Self-healing schedules

**Problem.** One slipped block shatters a manually blocked day, and the wreckage triggers calendar anxiety and abandonment; guilt-free automatic rescheduling — not scheduling — is the most-loved auto-scheduler feature among ADHD users ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

**Direction.** When a block slips or a day derails, Klyr reflows the remaining plan automatically and quietly: the user never sees the wreckage of the old plan, only the current honest one. Every reflow shows one line of reasoning ("moved 'invoice' to 2pm — your 11am ran long") and offers one-tap undo. Rescheduling is never logged as failure and never accumulates a "rescheduled 6 times" trail on the task's face.

**Constraints from research.**
- Automation must stay legible: visible reasoning, notification restraint, one-tap undo — ADHD users demonstrably resent black-box calendar movers ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).
- Auto-reflow must respect transition buffers and never produce back-to-back stacking ([time-perception](../foundations/time-perception.md)).
- No silent writes to user data — reflow is an Act-tier operation: preview or undo always available ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).

**Risks.** Over-eager reflow becomes the *thrash* mode of the schedules-that-shatter-or-thrash anti-pattern (AP-19, [anti-patterns.md](anti-patterns.md)) — the external memory rearranging itself erodes the predictability that makes it trustworthy ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)). Whether self-healing actually extends system lifespan is unproven ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md) open questions).

**Confidence: promising** — product-grade evidence (Motion/Reclaim ADHD reviews), no published retention data.

### 8. Waiting-mode-aware day layout

**Problem.** **Waiting mode** (community term; essentially no direct research) — the inability to start anything before a scheduled event — regularly deletes entire half-days around a 3pm appointment ([time-perception](../foundations/time-perception.md)).

**Direction.** When the calendar shows a commitment later today, the day view reshapes: (a) plain-words usable time ("2h 10m before you need to leave"), (b) only tasks that fit that window with buffer are offered, (c) a guaranteed interrupt — "I'll tell you at 2:35; you can stop watching the clock." Pre-event slots draw from the waiting-sized bucket: tasks the user tagged (or Klyr learned) as short, low-stakes, interruptible.

**Constraints from research.**
- The guaranteed interrupt is the load-bearing piece: the mechanism behind waiting mode is plausibly fear of missing the event, so Klyr must visibly take over the vigil ([time-perception](../foundations/time-perception.md)).
- "Waiting-sized tasks" implements the most-repeated community coping strategy ([time-perception](../foundations/time-perception.md)).
- Fit calculations must use corrected durations, not user estimates (direction 28).

**Risks.** If Klyr's interrupt ever fails (OS kills the alarm), trust damage is severe — redundant delivery and an honest failure disclosure matter ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md) open questions on trust repair). Suggesting work during waiting can read as productivity-maximizing pressure; offering rest and "waiting-sized" leisure as equal options keeps it on the user's side ([when-to-back-off](when-to-back-off.md)).

**Confidence: promising** — near-universal community report, zero direct research; the corpus calls it a testable hypothesis with high expected value.

### 9. Energy windows, medication-window tagging, and chronotype-true day boundaries

**Problem.** Capability fluctuates within the day and across days — medication coverage, sleep debt, cycle phase, and plain EF variability — yet planners assume a flat, morning-anchored day. Up to ~78% of adults with ADHD show delayed sleep timing; morning-optimized defaults punish the majority ([adhd-overview](../foundations/adhd-overview.md), [daily-life-impact](../daily-life/daily-life-impact.md), [executive-function](../foundations/executive-function.md)).

**Direction.** The user can mark 1–2 daily **energy windows** for demanding work; Klyr routes cognitively heavy tasks into them and admin to the tails, and defaults "hard starts" inside windows ("hard starts before 3pm"). Windows are deliberately neutral — the user may privately mean "meds active," "post-coffee," or nothing — and the product never names medication. The day boundary itself is user-defined: plans don't fail at midnight, and review/plan prompts anchor to the user's actual evening, not 9am.

**Constraints from research.**
- Neutral windows, never medication-shaped; the product stores no health semantics ([time-perception](../foundations/time-perception.md)). This reconciles the tagging practice reported in [task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md) with the privacy line: correlated timing data is inference-rich, so windows live in the sensitive tier regardless ([privacy-and-data-ethics](privacy-and-data-ethics.md)).
- Never auto-schedule demanding items early; repeatedly snoozed morning items get offered a later home instead of a failure mark ([daily-life-impact](../daily-life/daily-life-impact.md)).
- Optional, user-declared cycle-aware adjustments only: never inferred from behavior, never required, always labeled emerging science ([populations-and-variation](../foundations/populations-and-variation.md), [habits-and-routines](../daily-life/habits-and-routines.md)).

**Risks.** Energy tagging can become its own maintenance burden ([daily-life-impact](../daily-life/daily-life-impact.md) open questions); windows must work set-once-and-forget, with passive inference offered later under consent. Any slip into wellness-y "your energy score" territory hits both the *uninvited state inference* anti-pattern (AP-22, [anti-patterns.md](anti-patterns.md)) and regulatory exposure ([when-to-back-off](when-to-back-off.md)).

**Confidence: promising** — circadian evidence is robust and the community practice (spoons, coverage planning) is widespread; the feature form is untested.

### 10. A life-admin lane with dread-aware defaults

**Problem.** Life admin has the highest dread-to-duration ratio of any domain — 20-minute forms and phone calls avoided for months behind shame that grows with delay — and bills/refills/appointments are the highest-dollar-consequence dropped items (~46% of ADHD prescriptions refilled on time; the **ADHD tax** is real money) ([daily-life-impact](../daily-life/daily-life-impact.md)).

**Direction.** Admin items get a differently-behaving home: capture "renew passport" and Klyr concretizes step one ("find where your passport is — that's the whole step"), attaches lead-time runway defaults for deadline species (refills, renewals, bookings), and offers a contained weekly **admin sprint** (15 minutes, 2–3 items, timer, done) instead of a mythical paperwork day. Money-adjacent wins are framed as tax avoided ("renewal caught 5 days early"), never waste incurred.

**Constraints from research.**
- Life domains behave differently and need differently-behaving homes; a generic task+date model loses exactly where ADHD costs the most ([daily-life-impact](../daily-life/daily-life-impact.md)).
- Moralizing-free money framing is mandatory; late fees are reducible system costs, never character data ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).
- Phone-call and form tasks deserve first-step scripts (direction 39's breakdown shines here).

**Risks.** Totting up what forgetting cost the user ends engagement — even "positive" money framings need testing ([daily-life-impact](../daily-life/daily-life-impact.md)). Domain sprawl (money, food, health in one app) risks overwhelm and a surveillance feel; ship lanes progressively ([app-landscape](app-landscape.md)).

**Confidence: promising** — the domain failure map is well documented; the lane treatment is a design response without trials.

### 11. Routines as menus with a minimum-viable floor

**Problem.** Routines collapse via rigidity, context resets, novelty decay, and — most commonly — all-or-nothing perfectionism: one rigid script snaps under real life and the whole practice is abandoned ([habits-and-routines](../daily-life/habits-and-routines.md)).

**Direction.** A Klyr routine is a menu, not a script: the user picks tonight's components, and every routine carries an explicit smallest version that still counts ("brush teeth" is a valid evening routine). Days render as full / minimum / missed, and minimum scores as success. Context variants (weekend, travel, sick-day) are pre-built so a changed context switches the routine instead of registering collapse. New habits start at a 30-second version; scaling up is opt-in.

**Constraints from research.**
- No routine may have an invalid partial state ([habits-and-routines](../daily-life/habits-and-routines.md)).
- Honest timelines only: no 21-day framing anywhere — median formation is ~66 days with an 18–254 day range ([habits-and-routines](../daily-life/habits-and-routines.md)).
- Externalize the cue at the point of performance; don't rely on the user remembering the stack ([habits-and-routines](../daily-life/habits-and-routines.md), [executive-function](../foundations/executive-function.md)).

**Risks.** Floors so low they feel patronizing ("confetti for brushing teeth") — celebration intensity must be user-calibrated (direction 38, [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md) open questions). Menu-building itself is setup; ship strong templates and harvest configuration from use ([ux-design-for-adhd](ux-design-for-adhd.md)).

**Confidence: promising** — clinical guidance plus habit-science mechanism; no ADHD trials of menu-based routine design.

---

## Start

Initiation is where executive, emotional, and reward systems fail simultaneously; once underway, a task supplies its own stimulation ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)). Everything in this stage shrinks the start.

### 12. Task shrinking: the 2-minute version on demand

**Problem.** Activation energy, not capability, is the barrier: all cost is now, all payoff is later, and the aversive first moment triggers mood-repair avoidance ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md), [dopamine-and-motivation](../foundations/dopamine-and-motivation.md)).

**Direction.** Every task collapses to a **2-minute version** on demand — one tap on any task, anywhere it appears, yields the smallest honest opener ("open the doc," "put one dish away"), AI-drafted and user-editable. A second shrink axis lowers *stakes* rather than size: **ugly-first-draft mode** marks a task draft-stakes, and its copy explicitly authorizes a bad version ("goal: a bad paragraph exists"). Completing the shrunk version counts — visibly — as a real start (direction 30).

**Constraints from research.**
- Shrinking the first step has the broadest mechanism support among starter tools; graded task assignment is a validated CBT ingredient ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md), [evidence-based-strategies](../strategies/evidence-based-strategies.md)).
- Fear of failure largely mediates perfectionist delay — stake-lowering attacks the actual mechanism ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)).
- Action precedes motivation (behavioral-activation evidence), so the offer should be "just the 2-minute version," never "get motivated first" ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)).

**Risks.** If the 2-minute version is silently treated as the whole task, trust in the task model erodes; the parent task must visibly retain its identity. Shrink offers on *every* stall can read as condescension — tie frequency to the deferral signal (direction 37), not to a timer.

**Confidence: evidence-backed** — chunking/graded-start mechanisms are validated; the on-demand app delivery is the untested part.

### 13. Momentum-aware ordering: warm-up task first

**Problem.** Initiation is the expensive step and every transition re-pays it; "eat the frog" is wrong for most ADHDers most of the time (7% do hardest-first; 68% say it depends on the day) ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md), [evidence-based-strategies](../strategies/evidence-based-strategies.md)).

**Direction.** When Klyr proposes a session or day order, it defaults to one small guaranteed-win first — a warm-up "appetizer" — then the priority task while the engine is warm; after any completion it immediately surfaces the next pre-chosen action so no re-decision gap opens. Ordering is state-based: a lightweight daily state signal (one tap: fired-up / okay / running-on-fumes) flips between frog-first and appetizer-first suggestions.

**Constraints from research.**
- Continuing is cheaper than starting; transitions are where momentum dies ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md), [attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).
- Ordering must be suggestion, not doctrine — state beats rules, and autonomy is protective ([evidence-based-strategies](../strategies/evidence-based-strategies.md), [motivation-and-gamification](../strategies/motivation-and-gamification.md)).
- The "next" surfaced after a completion should be pre-chosen at plan time, because choosing is the expensive act at execution time ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)).

**Risks.** A day of only appetizers quietly starves important-non-urgent work — the system must still protect one substantial item ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)). State check-ins can become prompt fatigue; make them skippable and infer from behavior over time ([outcomes-and-measurement](outcomes-and-measurement.md)).

**Confidence: promising** — mechanism-grounded and survey-consistent; no trials of ordering algorithms.

### 14. Launch rituals: countdowns and start affordances

**Problem.** The start moment lacks any external push; the gap between "decided" and "doing" is where paralysis lives ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)).

**Direction.** A **launch button** on any task: tap → 5-4-3-2-1 countdown with sound/haptic → the task opens in focus view with its first step displayed and the timer already running. Optional start sounds and a tiny "launch streak of one" celebration for the act of starting itself. Nearly free to build; treated as delight *and* activation.

**Constraints from research.**
- Matches a community-beloved pattern; ship as equipment the user reaches for, not an animation forced on every start ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)).
- Sound/haptic intensity respects the sensory panel defaults (direction 38; [populations-and-variation](../foundations/populations-and-variation.md)).
- Pairs with if-then cues: the countdown can fire *at the cue* as the pre-made decision (direction 5).

**Risks.** Ritual fatigue — the countdown's novelty will decay ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)); rotate forms (direction 31) rather than escalating intensity. Never auto-launch: an uninvited countdown is manufactured pressure (*fake urgency* anti-pattern, [anti-patterns.md](anti-patterns.md)).

**Confidence: promising** — community-validated, mechanism-plausible (arousal ramp + implementation intention), untested formally.

### 15. Overwhelm exit: collapse to one small action

**Problem.** Choice paralysis and overwhelm freeze are input problems — too many options, too much visible — and the exit is fewer options, ideally one (82% of surveyed ADHD adults report frequent decision difficulty; 58% weekly paralysis) ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)).

**Direction.** A permanently visible, judgment-free **"I'm stuck"** affordance. Tapping it collapses the entire UI to exactly one small next action — no list, no counts, no badges — chosen by Klyr from the day's plan (smallest, most concrete item; warm-up logic from direction 13). Two quiet alternatives sit beneath: "make it smaller" (direction 12) and "not now — pick for me later." Exiting the state restores the normal view unchanged.

**Constraints from research.**
- One thing, everything else out of sight: choice overload bites hardest under decision difficulty and uncertainty — precisely the ADHD profile ([ux-design-for-adhd](ux-design-for-adhd.md)).
- The stuck state must never be recorded as a failure event or surfaced in any recap ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).
- Copy is invitation-shaped, not command-shaped ([motivation-and-gamification](../strategies/motivation-and-gamification.md)).

**Risks.** If Klyr's one pick is wrong ("that's exactly the task I'm avoiding"), the rescue fails — always offer the one-tap swap. Naming the state clinically ("overwhelm detected") crosses the inference line ([when-to-back-off](when-to-back-off.md)); the *user* declares stuck, never the algorithm.

**Confidence: promising** — paralysis flavors are documented and the one-task pattern is market-loved; the rescue flow itself is untested.

---

## Focus and sustain

ADHD attention is dysregulated, not absent: internal distraction usually outweighs external, and a focus feature that only silences the phone solves half the problem ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).

### 16. Body-double and focus sessions

**Problem.** Starting and sustaining alone is the bottleneck users already pay humans to solve; **body doubling** — working alongside another person — is the community's flagship strategy (85% of 220 surveyed neurodivergent people said they're more likely to complete a task alongside someone; no RCTs yet) ([evidence-based-strategies](../strategies/evidence-based-strategies.md), [app-landscape](app-landscape.md)).

**Direction.** A focus session is one tap from any task: pick duration (or open-ended count-up), optional soundscape, and an optional presence layer with an intensity dial — silent ambient co-working (others' avatars quietly present) ↔ matched live sessions with goal declaration and a check-out. "Start together" invites let a user summon a friend into a session. Session screens show the current task and time shape, nothing else.

**Constraints from research.**
- Intensity must be a dial, not a mode: the continuum model says one intensity won't fit all ([evidence-based-strategies](../strategies/evidence-based-strategies.md)).
- Share *actions and progress*, never identity goals — announced identity intentions reduce follow-through ([motivation-and-gamification](../strategies/motivation-and-gamification.md)).
- Label honestly in copy: "many people find…" not "research shows…" ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).
- No public failure surfaces, ever; leaving a session early is unremarkable ([motivation-and-gamification](../strategies/motivation-and-gamification.md)).
- Instrument it — Klyr can generate the missing evidence ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)).

**Risks.** Social features are an RSD minefield (visible no-shows, being witnessed failing) — the *public failure* anti-pattern ([anti-patterns.md](anti-patterns.md), [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)). An AI "presence" variant is **speculative** — passive AI presence may carry none of the human-accountability mechanism, and companion drift is a documented harm vector ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)); if tested, it stays task-anchored, session-scoped, personality-light.

**Confidence: promising** — community-validated with an emerging survey base; mechanism (social presence, co-regulation) plausible; no controlled trials.

### 17. One-thing-now focus view

**Problem.** The information-density debate ("I need everything visible" vs. "dense UIs shut me down") is real on both sides; during execution, visible everything-else is a distraction amplifier ([ux-design-for-adhd](ux-design-for-adhd.md), [attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).

**Direction.** The working view shows exactly one task: its next action sentence, its time shape (direction 27), and a capture overlay hotkey. The full list is one deliberate tap away, never ambiently visible mid-session. Density elsewhere is user-controlled; progressive disclosure is backed by a visible "hidden, not lost" promise (direction 2).

**Constraints from research.**
- The most-loved pattern across ADHD-native tools (Llama Life, Marvin's Super Focus) ([app-landscape](app-landscape.md)).
- One job and one visually primary action per screen; salience is a rationed budget ([ux-design-for-adhd](ux-design-for-adhd.md)).
- Handle *internal* distraction too: the capture overlay (direction 1) and a brain-dump surface belong inside the focus view ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).

**Risks.** For users who orient by seeing everything, hiding the list can trigger out-of-sight anxiety — the density dial and the guaranteed-resurfacing promise are the mitigations, not a single house style ([ux-design-for-adhd](ux-design-for-adhd.md), [memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).

**Confidence: promising** — convergent lab mechanisms (choice overload, distraction amplification) plus strong market evidence; no direct trials of the view itself.

### 18. Flow-respecting timers with an interruption budget

**Problem.** Rigid Pomodoro yanks people out of flow — the community's top timer complaint — and countdown pressure can itself block initiation; meanwhile app-initiated interruptions re-bill the full restart cost ([evidence-based-strategies](../strategies/evidence-based-strategies.md), [time-perception](../foundations/time-perception.md), [attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).

**Direction.** Timers offer count-down *and* first-class count-up ("just start; I'll track it"); session ends ring softly with continue / wrap-up choices; overruns are logged as flow, never as overtime. During any session Klyr budgets itself to at most one system-initiated interruption (default zero) — everything else queues for session end. Breaks pull from the user's dopamine menu (direction 33).

**Constraints from research.**
- Never hard-stop a user in flow; flexible intervals and easy on-ramps are the ADHD adaptation that matters ([evidence-based-strategies](../strategies/evidence-based-strategies.md)).
- An unfinished session is never marked failed ([time-perception](../foundations/time-perception.md)).
- Interruption-by-Klyr is an explicit, budgeted event ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).

**Risks.** Timer mechanics drift toward manufactured urgency if defaults turn red and loud (*fake urgency* anti-pattern, [anti-patterns.md](anti-patterns.md)); pressure aesthetics stay opt-in (direction 34). Softness has a cost: with zero structure some users get nothing from sessions — offer firmer formats as equipment, not policy.

**Confidence: promising** — clinical consensus plus massive community endorsement; no RCTs of timer-based work in ADHD.

---

## Transition and finish

Transitions cost more than the switch itself: switch costs are elevated in ADHD, and unfinished tasks keep taxing the next one (attention residue). Endings deserve as much design as starts ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).

### 19. Ready-to-resume bookmarks

**Problem.** Every interruption or task switch re-pays the full initiation cost, and event boundaries flush working memory (the doorway effect) — threads die at the seams, not in the middle ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md), [memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).

**Direction.** Every task exit offers a one-field, ~30-second, skippable **ready-to-resume** prompt: *where I stopped / what's next / what I'm postponing.* On reopen, the resume note renders first — before the description, before subtasks — as a launch instruction ("you were mid-way through X; next step was Y"). A neutral one-tap switch-reason (stuck / bored / interrupted / changed mind) is optional and never surfaced as a failure count.

**Constraints from research.**
- The ready-to-resume plan is the best-evidenced mechanic in the attention doc (four studies: reduced attention residue, better subsequent performance) ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).
- Persist "where was I" state across every boundary; breadcrumbs externalize expensive reconstruction ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).
- Prompt must be skippable — a mandatory exit toll would tax the freedom to stop, which demand-sensitive users guard ([motivation-and-gamification](../strategies/motivation-and-gamification.md)).

**Risks.** If the prompt fires on every trivial app-switch it becomes friction and gets disabled; scope it to substantive sessions. Switch-reason data is behavioral exhaust — age it out by default ([privacy-and-data-ethics](privacy-and-data-ethics.md)).

**Confidence: evidence-backed** — direct experimental support for the mechanic, though not yet in ADHD samples.

### 20. Soft landings: transition ramps and hyperfocus check-outs

**Problem.** Hard-cut transitions are where ADHD pays double — and hyperfocus, a genuine strength, has real costs (timelessness, ignored body needs, difficulty stopping) that users want help *exiting*, not preventing ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md), [adhd-overview](../foundations/adhd-overview.md)).

**Direction.** Scheduled transitions get a configurable pre-alarm ramp (10/5/1 minutes) whose default message is a ramp, not a stop: "5 minutes left — good moment to note where you are" (feeding direction 19). For unplanned deep sessions, opt-in **check-outs**: a passive, non-modal time anchor ("you've been on this 2h 40m") plus optional body-needs nudges (water, food, movement), dismissible forever per session. Users author their own guardrails in calm moments; Klyr never decides the user has focused "too long."

**Constraints from research.**
- Inform rather than interrupt; default to passive and non-modal — guardrails that break a productive state destroy the main ADHD attentional strength ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).
- Exit control, not correction: "want a nudge in an hour?" never "you've been distracted for an hour" ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).
- Never promise to *induce* hyperfocus ([adhd-overview](../foundations/adhd-overview.md)).

**Risks.** Miscalibrated nudges either shatter flow (too firm) or get banner-blind (too soft) — per-user calibration is the feature, and habituation is the enemy ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)). Body-needs nudges edge toward parenting the user; keep them opt-in and literal ([populations-and-variation](../foundations/populations-and-variation.md)).

**Confidence: promising** — transition-warning practice and AHQ-measured costs are documented; the check-out UX is untested.

### 21. Finish states beyond done: started, partial, paused

**Problem.** Binary done/not-done converts 60% success into felt failure for all-or-nothing thinkers, and "unfinished" without a parked state keeps generating attention residue and shame ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md), [attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).

**Direction.** The task model gains first-class states: **started**, **chipped at** ("2 of 5"), **paused** (parked cleanly with a resume note, distinct from not-started and never rendered as overdue), and **done**. Partials display and count as progress in every recap; starts are celebrated as wins in their own right (initiation is the impaired step, so rewarding only completion re-punishes the deficit).

**Constraints from research.**
- Partial completion must be visible, celebrated, counted ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).
- A cleanly parked task stops costing attention; one that can only be "not done" keeps costing it ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).
- Track and acknowledge initiations, coordinating with restart design ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md), [habits-and-routines](../daily-life/habits-and-routines.md)).

**Risks.** Perfectionistic users may discount partials anyway — an open question in [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md); don't oversell partials as praise, present them as fact. State proliferation adds model complexity the UI must absorb, not export ([ux-design-for-adhd](ux-design-for-adhd.md)).

**Confidence: promising** — attention-residue evidence supports the paused state; the motivational effect of visible partials is untested.

---

## Review and recover

Every famous methodology dies at its maintenance ritual ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)). Klyr's stance: the system reviews itself, debt cannot structurally accumulate, and recovery is a designed flow rather than a user virtue.

### 22. Automated no-ceremony review

**Problem.** The weekly review is GTD's single point of failure for ADHD: boring, delayed-reward, EF-heavy — and when it lapses, the system fills with stale, accusing debris that triggers the collapse–shame–new-system cycle ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

**Direction.** Klyr performs the review continuously and invisibly: stale items sink and fade instead of glaring; one item at a time surfaces at natural moments as a single **keep / shrink / someday / let go** tap (direction 4's cadence). Days and weeks auto-close and open clean, generating a blameless recap — "what moved, what carried" — that leads with completions and partials and never tabulates what wasn't done. Carrying an item forward is a deliberate micro-act (one tap), and after repeated carries Klyr asks the intentionality question — "still worth your attention?" — with letting go equally honorable.

**Constraints from research.**
- An hour-long curation ritual as a prerequisite for system trust is a designed-in death ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).
- Show what was done; never tabulate what wasn't — no "you missed X this week" surface, ever ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).
- No execution scores, percentages, or grades on the recap ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md), [outcomes-and-measurement](outcomes-and-measurement.md)).

**Risks.** Fully frictionless carry-forward may decay into meaningless auto-rollover (the BuJo intentionality question — an explicit open question in [planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)). Auto-fading items too eagerly reads as the app losing things — pace against the trust ledger (direction 2).

**Confidence: promising** — the manual ritual's failure is thoroughly documented; the automated replacement is the design bet Klyr exists to test.

### 23. Overdue amnesty and the resurfacing engine

**Problem.** Overdue accumulation is the single clearest abandonment mechanic in task managers: red counts pile up until opening the app *is* the shame trigger, so users stop opening it ([app-landscape](app-landscape.md), [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)). Meanwhile "remember to check the app" is itself a prospective-memory task, so a passive list quietly fails its purpose ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).

**Direction.** Two coupled mechanics. **Amnesty:** tasks that age past their moment quietly de-emphasize and, past a threshold, move to a calm **parked** state — a 47-item overdue list is structurally impossible, and "overdue" is never a rendered state, only a data fact. User-initiated amnesty is a first-class ritual: "archive everything older than X; keep these 3," "forget this month, keep my projects." **Resurfacing:** a push-first engine brings parked and stale items back a few at a time, at receptive moments, with no-judgment framing ("Still matter? Shrink it? Let it go?"), changing form on each pass (different wording, channel, or a shrink offer) instead of repeating identically.

**Constraints from research.**
- Amnesty is a core mechanic, not a settings toggle ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)); user-controlled forgetting is not silent loss — deletion propagates honestly ([privacy-and-data-ethics](privacy-and-data-ethics.md)).
- Resurfacing is budgeted against habituation: identical repeated alerts train ignoring (clinical alert override rates run 49–96%); three consecutive ignores means change strategy, not volume ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).
- Age out behavioral exhaust (deferral logs, lapse ledgers) by default while keeping user content forever ([privacy-and-data-ethics](privacy-and-data-ethics.md)).

**Risks.** Amnesty that fires too fast feels like the app not taking the user seriously ("it deleted my task!"); too slow lets piles form — the threshold is per-user and untested ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md) open questions). Resurfacing everything eventually is the *notification carpet-bombing* anti-pattern ([anti-patterns.md](anti-patterns.md)); some parked items should be allowed to rest until asked for.

**Confidence: promising** — the abandonment mechanism is among the best-documented findings in the corpus; thresholds and cadence need real-user calibration.

### 24. Elastic recurring chores

**Problem.** Chores fail at the cycle level: laundry has no endpoint, and a system that accrues each missed cycle as debt shows "overdue ×14" on a task whose real-world remedy is *one* load of laundry — a shame counter, not information ([daily-life-impact](../daily-life/daily-life-impact.md)).

**Direction.** Recurring tasks are cycles, not clones: a missed cycle compresses into a single "next instance," always current, never late. Cadence stretches with reality ("every ~4 days, elastic") and, during declared low-capacity periods, recurring items **skip, not stack** ([when-to-back-off](when-to-back-off.md)). The chore's face shows "next: today" — never a deficit history.

**Constraints from research.**
- Never display accumulated misses on cyclic tasks; the return-to-a-wall-of-overdue moment drives permanent abandonment ([when-to-back-off](when-to-back-off.md), [app-landscape](app-landscape.md)).
- Distinguish task species: bills, refills, and appointments carry real deadlines and lead-time runway (direction 10); elastic physics applies to cycles, not to consequences ([daily-life-impact](../daily-life/daily-life-impact.md)).
- Frequency data can quietly power the estimate learner (direction 28) but never a consistency grade ([outcomes-and-measurement](outcomes-and-measurement.md)).

**Risks.** Over-elasticity can silently stretch "water the plants" until the plants die — genuinely consequence-bearing recurrences need a gentle floor the *user* sets. Hiding all history may frustrate users who want honest mirrors; keep history queryable, never pushed ([privacy-and-data-ethics](privacy-and-data-ethics.md) open questions).

**Confidence: promising** — the harm it removes is thoroughly documented; the elastic model mirrors real-world physics but has no trial evidence.

### 25. Dread receipts: feared-vs-actual on avoided tasks

**Problem.** Twenty-minute admin tasks get avoided for months, and users repeatedly discover the six-month dread task took 19 minutes — but nothing captures that lesson, so the next avoidance starts from scratch ([daily-life-impact](../daily-life/daily-life-impact.md)).

**Direction.** When a long-avoided task finally completes, Klyr can show a quiet, private receipt: "feared for 4 months · took 20 minutes." Over time, a personal pattern library ("phone calls: feared ~8×, actual ~15 min") surfaces *only* at the moment a similar task is being avoided — as ammunition against the Wall of Awful, phrased as data, never as "see, that wasn't so bad."

**Constraints from research.**
- Show feared-vs-actual history as calibration, never as a failure metric ([daily-life-impact](../daily-life/daily-life-impact.md), [time-perception](../foundations/time-perception.md)).
- Delivery must pass the shame test — the delay is never editorialized ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).

**Risks.** The valence is explicitly untested: "you feared this for 6 months" may build self-trust or may re-trigger shame about the delay ([daily-life-impact](../daily-life/daily-life-impact.md) open questions). Ship dark-launched (data collected, surface off) until tested; a wrong tone here is the *guilt copy* anti-pattern wearing a lab coat ([anti-patterns.md](anti-patterns.md)).

**Confidence: speculative** — coherent mechanism (fear-of-failure mediation, self-trust building), zero direct evidence, known valence risk.

---

## Return after absence

Every user will disappear; the boom-bust cycle guarantees it ([daily-life-impact](../daily-life/daily-life-impact.md)). The lifecycle's kill point is the return — *"miss one day, feel guilty, avoid it, never open it again"* ([app-landscape](app-landscape.md)) — which makes the comeback Klyr's single highest-leverage flow.

### 26. The restart ritual

**Problem.** Reopening an abandoned system means facing the debris: overdue walls, broken streaks, gap visualizations. Shame converts one missed day into a dead system, and almost no product designs for this step ([app-landscape](app-landscape.md), [habits-and-routines](../daily-life/habits-and-routines.md), [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).

**Direction.** After any absence, the first screen is a designed hero flow: a warm, brief welcome; an auto-tidied state (amnesty applied, recurrences compressed, plans re-flowed — directions 22–24 did the work silently); and **one small next action** to reenter with, plus the most recent resume bookmark if one exists. No gap arithmetic ("you were away 9 days" is banned), no recap of what was missed, no make-up work. Resumes are treated as wins: the return event itself gets the app's most sincere celebration, and **restart latency** — not streak length — is the metric the team optimizes ([outcomes-and-measurement](outcomes-and-measurement.md)).

**Constraints from research.**
- Design the comeback as a hero flow; the restart moment is where shame kills systems ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).
- Detect return-after-miss and make it the most rewarding, lowest-friction moment in the app, with a one-tap restart-day minimum version of routines ([habits-and-routines](../daily-life/habits-and-routines.md)).
- Neutral acknowledgment, no backlog wall, immediate small win ([when-to-back-off](when-to-back-off.md), [planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).
- During the absence itself: no guilt notifications, no "we miss you" engagement bait ([ux-design-for-adhd](ux-design-for-adhd.md)).

**Risks.** Over-celebrating a return can read as condescension from the tone-deaf end of the toxic-positivity spectrum ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)); calibrate against direction 38's tone dial. If auto-tidying was aggressive, the welcome must link the trust ledger ("here's what we tidied — undo anything") or the user may feel the app rewrote their life (direction 2).

**Confidence: promising** — the failure it repairs is the best-documented lifecycle fact in the market analysis; the flow itself is Klyr's core original bet, untested.

---

## Cross-cutting layer: Time

Never assume the user can feel duration, sequence a day, or notice a deadline approaching; the app holds time — visibly, ambiently, without punishment ([time-perception](../foundations/time-perception.md)).

### 27. Visual time and countdowns

**Problem.** Timing deficits in ADHD span all four lab paradigms (lifespan meta-analytic g ≈ 0.69), and time is often experienced as binary now/not-now — numerals alone demand the exact arithmetic the deficit sits in ([time-perception](../foundations/time-perception.md)).

**Direction.** Everywhere a duration matters, time renders as space: shrinking wedges/bars/arcs beside numerals for sessions, tasks, and time-until-next-commitment. A persistent, glanceable "time left in this block" lives on widgets and lock screen (direction 43). Countdown surfaces are calm by default — pressure styling is user-summoned equipment (direction 34).

**Constraints from research.**
- Reading time must be a perceptual judgment, not a subtraction ([time-perception](../foundations/time-perception.md)).
- Externalizing works: time-assistive devices RCT improved time-processing (d = 0.38) and parent-rated daily time management (d = 1.0) — while self-ratings didn't move, a warning against expecting felt relief ([time-perception](../foundations/time-perception.md)).
- Ambient beats interruptive: continuous display avoids the context-switch cost of check-ins ([time-perception](../foundations/time-perception.md), [attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).
- Market convergence: Time Timer's shrinking disc and Tiimo's visual timelines are the most consistently praised ADHD affordances ([app-landscape](app-landscape.md)).

**Risks.** A perpetually draining bar can become ambient anxiety for anxious users (*fake urgency* adjacency, [anti-patterns.md](anti-patterns.md)); depletion styling needs the calm default and a reduced-stimulation variant ([populations-and-variation](../foundations/populations-and-variation.md)).

**Confidence: evidence-backed** — measured timing deficits plus an RCT for externalization devices plus clinical consensus.

### 28. Learned personal time-estimate correction

**Problem.** The planning fallacy compounds with ADHD time blindness: estimates are systematically optimistic, honest optimism sets up visibly failed days, and clinicians already tell patients to measure instead of estimate ([time-perception](../foundations/time-perception.md), [planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

**Direction.** Klyr silently tracks estimate-vs-actual per user and per task category. After enough samples it pads plans automatically and, where useful, shows the calibration gently: "you usually say 30 min — these have taken you ~50. Plan for 50?" Day-plan fit checks (directions 6, 8) always use corrected durations. Framed as calibration, never as a failure metric; the correction factor belongs to the user and is inspectable.

**Constraints from research.**
- Learn from actuals and surface the plan-vs-hours collision *at plan time*, not after the day fails ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).
- Never present the gap as a deficiency readout; time-related failure must not generate shame copy ([time-perception](../foundations/time-perception.md), [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).
- Duration logs are behavioral exhaust — retention-limited by default ([privacy-and-data-ethics](privacy-and-data-ethics.md)).

**Risks.** Showing a user they're "always 1.7× off" can read as the app keeping receipts on their deficit — surface corrections as *offers*, keep the multiplier discoverable rather than ambient. Sparse or noisy actuals will miscalibrate; hold suggestions until confidence is real (a wrong correction spends trust, [ai-assistance-for-adhd](ai-assistance-for-adhd.md)).

**Confidence: promising** — clinician practice and mechanism are solid; software-learned correction for ADHD users is untested.

### 29. Salience where monitoring fails: J-curve deadlines and leaving-soon mode

**Problem.** ADHD clock-checking fails on *allocation*, not frequency — too few checks in the critical window — and steep discounting makes deadlines weightless for weeks, then overwhelming ([time-perception](../foundations/time-perception.md)). Departures fail at the last task before leaving ("one-more-thing-itis").

**Direction.** Reminder salience follows a J-curve: near-silent early, escalating sharply in the last 10–20% of a runway — uniform daily nags are the named anti-pattern. For long runways, Klyr proposes **intermediate commitments** (a soft self-deadline days early, spaced toward the goal) so urgency arrives early and cheap. Before any departure, **leaving-soon mode**: new work stops being offered, the departure checklist surfaces, and a shrinking countdown targets *stop-doing-things* time — which is earlier than leave time, itself earlier than the event.

**Constraints from research.**
- Timing of the prompt matters more than the number of prompts (strategic-monitoring mediation study) ([time-perception](../foundations/time-perception.md)).
- Self-imposed deadlines beat none but are set badly — the system should propose spacing (Ariely & Wertenbroch — a classic finding with mixed replication; see [evidence-based-strategies](../strategies/evidence-based-strategies.md)).
- Model commitments as stop → transition → prepare → travel → buffer, with auto-inserted, tunable buffers; never schedule back-to-back by default ([time-perception](../foundations/time-perception.md)).

**Risks.** Late-window escalation is deliberate urgency engineering — for anxious users it can tip into panic; escalation curves must be per-user tunable and capped (*fake urgency* anti-pattern boundary, [anti-patterns.md](anti-patterns.md), [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)). Intermediate deadlines the user starts ignoring train deadline-blindness — track and adapt rather than repeat.

**Confidence: promising** — grounded in a strong mediation finding and deadline research; the J-curve parameters are hypotheses.

---

## Cross-cutting layer: Motivation and reward

ADHD motivation is altered reward timing, not weak will: immediate, frequent, interesting consequences move behavior; distant importance mostly doesn't ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md), [motivation-and-gamification](../strategies/motivation-and-gamification.md)).

### 30. Instant, unconditional acknowledgment

**Problem.** Anticipatory reward signaling is blunted while response to delivered rewards is comparatively intact — plans don't pull, but ticking the box lands. A reward that arrives in a weekly summary is motivationally nonexistent ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)).

**Direction.** Every completion — including 2-minute versions, partials, and starts — gets acknowledged within the same interaction: fast, sincere, small. The *presence* of acknowledgment is guaranteed (never a gamble); its *expression* varies to fight habituation (direction 31). Prefer informational feedback ("that's 9 of the last 12 weeks the bills got paid") over transactional points; aim rewards at aversive tasks and keep hands off intrinsically loved ones.

**Constraints from research.**
- Immediate, frequent, consistent reinforcement is the ADHD-effective pattern; if choosing between a beautiful animation and a fast one, ship the fast one ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)).
- Never promise-and-miss: a predicted reward that fails to arrive is an active demotivator ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)).
- Vary delight, never *whether* work is acknowledged — variable-ratio on the core loop is the slot-machine red line ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md), [motivation-and-gamification](../strategies/motivation-and-gamification.md)).
- Overjustification caution: reward the boring, not the loved ([motivation-and-gamification](../strategies/motivation-and-gamification.md)).

**Risks.** Constant confetti is patronizing to some users and dysregulating for AuDHD users — intensity is a dial with calm defaults (direction 38; [populations-and-variation](../foundations/populations-and-variation.md)). Whether checkbox-level acknowledgment functions as reinforcement for ADHD adults at all is an open empirical question ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md) open questions).

**Confidence: evidence-backed** — reinforcement-timing evidence is strong; app-delivered form needs validation.

### 31. Novelty rotation mechanics

**Problem.** Novelty habituates: every productivity app works for two weeks, gamification impact dips around week four, and "I need a new system" is how users exit — the honeymoon is Klyr's single biggest product risk ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md), [motivation-and-gamification](../strategies/motivation-and-gamification.md)).

**Direction.** Novelty is a renewable, *offered* resource: rotating themes, celebration content, alternate day-view modes, and seasonal mechanics — proposed proactively when engagement dips ("brains get bored of tools; want to try Board view for a while?"), previewed before applying, reversible without data loss. The user restyles the surface; the substrate (their data, their structure) never has to be rebuilt to feel fresh.

**Constraints from research.**
- Vary the surface, never the substrate; requiring rebuild-to-refresh is the trap Klyr exists to escape ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)).
- Never make novelty ambient or sprung: monotropic users experience unannounced change as a cost — stability is the default, novelty is reached for ([populations-and-variation](../foundations/populations-and-variation.md)).
- Normalize rotation in copy so declining engagement routes to variety, not shame ([motivation-and-gamification](../strategies/motivation-and-gamification.md), [evidence-based-strategies](../strategies/evidence-based-strategies.md)).
- Keep customization shallow — complexity creep is its own abandonment trigger ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

**Risks.** Rotation can relocate the customization spiral (fiddling instead of doing) — detect setup-spirals and gently redirect ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md) open questions). Whether scheduled rotation genuinely resets the novelty clock is untested in all three docs that recommend it.

**Confidence: promising** — the decay it fights is well documented; rotation-as-cure is the plausible, unproven half.

### 32. Forgiving consistency metrics

**Problem.** Reset-to-zero streaks convert one miss into catastrophe — users abandon the whole practice, not the day — and real users quit Duolingo and Habitica specifically over lost streaks and punishment mechanics ([habits-and-routines](../daily-life/habits-and-routines.md)).

**Direction.** The default consistency surface is rolling and dense, not chained: "22 of the last 30 days," density heatmaps, cumulative "days showed up" totals that only ever grow. One miss is a visible small dip, never a cliff; a resume adds a celebrated mark (direction 26). If any streak-like element is ever tested, it is unbreakable by design: auto-applied repair, decay-not-reset, opt-in only.

**Constraints from research.**
- One miss barely dents automaticity — the metric should mirror the science ([habits-and-routines](../daily-life/habits-and-routines.md)).
- No zeroing, no fire-goes-out animation; a hard reset is an uninstall event ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md), [motivation-and-gamification](../strategies/motivation-and-gamification.md)).
- Consistency displays are for the user's information, never a grade; team-side metrics live elsewhere ([outcomes-and-measurement](outcomes-and-measurement.md)).

**Risks.** The named tension: enough forgiveness may dissolve the commitment device entirely — some users genuinely want stakes ([habits-and-routines](../daily-life/habits-and-routines.md), [motivation-and-gamification](../strategies/motivation-and-gamification.md) open questions). Resolution: forgiving-by-default, opt-in intensity, A/B validated on behavior — never a punishing default (*streak hostage-taking* anti-pattern, [anti-patterns.md](anti-patterns.md)).

**Confidence: promising** — the harm evidence is strong; whether forgiving metrics sustain behavior equally well is untested.

### 33. Temptation bundling and dopamine menus

**Problem.** Boring-but-important tasks lose the motivational math — distant abstract payoff against steep discounting — and at low-EF moments users can't even generate good break or reward options ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md), [evidence-based-strategies](../strategies/evidence-based-strategies.md)).

**Direction.** Two pre-computed pleasure mechanics. **Bundles:** attach a chosen pleasure (playlist, podcast, show) to a dreaded task — "laundry = the only time you get that podcast" — with one-tap start of both together. **Dopamine menu:** a user-built menu of stimulation options (appetizers: 5-minute resets; mains: real breaks; desserts: the doomscroll-adjacent ones, behind deliberate friction) that populates break screens and stuck moments so choosing a reward doesn't require executive function in the moment.

**Constraints from research.**
- Temptation bundling raised gym attendance 29–51% in the canonical study — general population, untested in ADHD; label honestly ([evidence-based-strategies](../strategies/evidence-based-strategies.md)).
- Bundling effects decay; treat bundles as refreshable ([evidence-based-strategies](../strategies/evidence-based-strategies.md)).
- Dopamine menus are community-grade strategy — copy must say "many people find," and must never use "dopamine hit"/"detox" framing ([evidence-based-strategies](../strategies/evidence-based-strategies.md), [dopamine-and-motivation](../foundations/dopamine-and-motivation.md)).

**Risks.** Bundling the *loved* activity to obligation can taint the love (overjustification adjacency, [motivation-and-gamification](../strategies/motivation-and-gamification.md)); the user picks the pleasure, Klyr never assigns one. Dessert-tier friction must not moralize ("are you sure?" guilt is *guilt copy*, [anti-patterns.md](anti-patterns.md)) — frame as the user's own pre-commitment.

**Confidence: promising** — RCT-grade for bundling in general populations; ADHD transfer and menu mechanics untested.

### 34. Urgency as opt-in equipment

**Problem.** Deadline pressure genuinely activates ADHD brains — it collapses delay to zero — but it only fires late, degrades quality, entrenches a stress-based work style, and for anxious or demand-sensitive users it backfires hard. This is the corpus's clearest design tension ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md), [adhd-overview](../foundations/adhd-overview.md), [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).

**Direction.** Urgency tools live in a visible equipment rack the user reaches for: beat-the-clock sprints, race-a-friend sessions, visible time-until-deadline, "before dinner" framings — each user-initiated, per-task, with intensity settings. The house default is calm: Klyr never manufactures deadline panic, never turns ambient surfaces red, never escalates styling on stalling tasks. Expect tolerance decay and rotate sprint formats (direction 31).

**Constraints from research.**
- Offer urgency; never impose it — red alarm states the user didn't ask for are simulated deadline stress ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)).
- Urgency about the task, never judgment about the person: "this closes at 5pm" yes; "you're running out of chances" never ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).
- Manufactured urgency decays with repetition; treat as a consumable, not a baseline ([motivation-and-gamification](../strategies/motivation-and-gamification.md)).
- Make pressure a reversible user setting; never A/B users into high-pressure UI without consent ([adhd-overview](../foundations/adhd-overview.md), [outcomes-and-measurement](outcomes-and-measurement.md)).

**Risks.** The *fake urgency* anti-pattern is this direction's shadow ([anti-patterns.md](anti-patterns.md)): the moment urgency becomes house policy or growth lever, Klyr becomes the stressor its users already drown in. Chronic self-administered urgency is still chronic stress — watch for users living in sprint mode and gently offer alternatives ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)).

**Confidence: promising** — the activation mechanism is real and well understood; the safe-dosing model is unvalidated.

### 35. A companion creature that never needs you

**Problem.** Sustained engagement needs warmth, and the market's standout punishment-free pattern is caring-for-a-creature (Finch): it externalizes self-care and adds relatedness without demands ([motivation-and-gamification](../strategies/motivation-and-gamification.md), [app-landscape](app-landscape.md)).

**Direction.** An optional companion whose wellbeing rides on the user's *presence*, never on performance: it celebrates what happened, naps when the user is away, and greets returns warmly. It never starves, decays, dies, or guilts. Fully opt-in at any time, fully retirable without data loss or farewell drama.

**Constraints from research.**
- The creature must never need the user on a schedule; stepping away is guilt-free by construction ([motivation-and-gamification](../strategies/motivation-and-gamification.md)).
- No punishment mechanics of any kind — Habitica's HP loss punishing busy productive weeks is the named counterexample ([motivation-and-gamification](../strategies/motivation-and-gamification.md), [app-landscape](app-landscape.md)).
- Sensory expression obeys the calm-defaults panel (direction 38; [populations-and-variation](../foundations/populations-and-variation.md)).

**Risks.** Even a no-consequence pet can generate abandonment guilt ("I left my bird") — an explicit open question in [motivation-and-gamification](../strategies/motivation-and-gamification.md); off-boarding must be emotionally clean. A companion is not a *companion chatbot*: no conversation loop, no parasocial deepening ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).

**Confidence: promising** — the strongest natural experiment in the market, no controlled evidence.

---

## Cross-cutting layer: Emotional safety

Tone is architecture, not polish: users arrive pre-shamed and criticism-sensitive, and the tool itself can become the shame trigger ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).

### 36. When to back off: Essentials mode

**Problem.** Capacity collapse is a scheduled event, not an edge case — comorbid anxiety/depression are the norm and boom-bust is the documented rhythm — and a tool that only models "on weeks" hurts people on off weeks ([when-to-back-off](when-to-back-off.md), [adhd-overview](../foundations/adhd-overview.md)).

**Direction.** A one-tap, no-explanation **Essentials mode**: the visible system shrinks to 1–3 user-chosen anchors, all deficit meters freeze, recurring tasks skip rather than stack, notifications drop to the anchors only — but the app never goes fully dark (tiny graded engagement tracks behavioral-activation evidence). Entry is user-declared or gently offered after soft signals ("want a lighter week?") — never imposed, never diagnosed. Exit is always manual, and re-entry to full mode uses the restart ritual (direction 26).

**Constraints from research.**
- The asymmetry principle: auto-de-escalate freely on weak signals; never escalate, label, or interpret without asking — false-positive math and surveillance costs forbid inference ([when-to-back-off](when-to-back-off.md)).
- No mental-health-state naming, no clinical screeners, no diagnostic thresholds — the FDA general-wellness line, nearly verbatim ([when-to-back-off](when-to-back-off.md)).
- Backing off means removing pressure and shrinking demands, not removing all structure ([when-to-back-off](when-to-back-off.md)).
- A "Get support" surface (verified, country-aware crisis resources) stays passively reachable at all times and never springs algorithmically ([when-to-back-off](when-to-back-off.md)).
- Mode state is sensitive-tier data ([privacy-and-data-ethics](privacy-and-data-ethics.md)).

**Risks.** Backing off too aggressively reads as the app giving up on the user; any check-in can read as surveillance — the resolution candidate (user-configured policies executed predictably) itself needs validation with real users in real troughs ([when-to-back-off](when-to-back-off.md)). Hard deadlines (rent, court dates, refills) must survive Essentials mode; "keep critical deadlines" requires user-designated criticality, decided in calm moments.

**Confidence: promising** — shipped precedents (Finch, Daylio, Bearable) plus behavioral-activation logic; the mode itself is untested.

### 37. Pressure-release valves: renegotiation and deferral-sensitive de-escalation

**Problem.** A task app is structurally a demand machine, and for demand-sensitive users the moment a want becomes an obligation it turns aversive; meanwhile a repeatedly deferred task usually signals a **Wall of Awful** (community model) — an emotional barrier that escalation only builds higher ([motivation-and-gamification](../strategies/motivation-and-gamification.md), [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).

**Direction.** Two valves, one principle: pressure always has a one-tap exit. **User-initiated:** any self-set commitment renegotiates in one tap — move it, shrink it, downgrade it to someday — with zero friction, zero penalty, zero record on the task's face. **System-initiated:** when a task hits N snoozes/skips, Klyr *lowers* the pressure — "this one keeps being hard to start — make it tiny? pair it with something good? let it go?" — instead of escalating. The reminder changes form (direction 23); urgency styling never intensifies on a stalling task; the deferral count is never displayed.

**Constraints from research.**
- Doors, not sirens: emotional-state change opens the Wall; escalation adds bricks ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).
- Invitations over commands; one-tap renegotiation with no penalty is the demand-defusing pattern ([motivation-and-gamification](../strategies/motivation-and-gamification.md)).
- Snooze-death breaker: after ~3 snoozes, convert the reminder into a triage choice with "let it go" shame-free ([ux-design-for-adhd](ux-design-for-adhd.md)); snooze itself re-anchors to a meaningful cue, never a bare +10 minutes ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).

**Risks.** "I noticed you keep skipping this" can read as caring or as being watched failing — wording and timing need testing with rejection-sensitive users ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md) open questions). Frictionless renegotiation may let genuinely important items slide indefinitely; the resurfacing engine (direction 23) is the honest backstop, not added friction.

**Confidence: promising** — grounded in documented demand-sensitivity and habituation dynamics; N, tone, and net behavioral effect untested.

### 38. Calm-by-default intensity presets

**Problem.** The same celebration that delights one user dysregulates an AuDHD user, humiliates a third, and overwhelms a fourth; every sensory and pressure choice Klyr hard-codes is a group it harms ([populations-and-variation](../foundations/populations-and-variation.md), [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).

**Direction.** A first-class intensity panel — motion, celebration sound, haptics, color saturation, copy warmth, pressure styling — each independently adjustable, all defaulting calm. Nameable presets ("more calm / less surprise," "bring the confetti," "recently diagnosed — go gentle") are discoverable without self-classification, because the defaults are already safe for the most sensitive group. `prefers-reduced-motion` is honored everywhere; nothing autoplays or loops.

**Constraints from research.**
- Resolve every population collision the same way: safe-default toggle, never house style ([populations-and-variation](../foundations/populations-and-variation.md)).
- Literal, plain copy is house style, not a toggle — no idioms or action-hiding cuteness on functional controls ([populations-and-variation](../foundations/populations-and-variation.md)).
- Motion rules and typography floors from the accessibility baseline apply regardless of preset ([ux-design-for-adhd](ux-design-for-adhd.md)).

**Risks.** Calm-by-default may under-stimulate ADHD-only users on first run and cost early engagement — an explicitly untested trade-off ([populations-and-variation](../foundations/populations-and-variation.md) open questions). A sprawling settings panel is its own cognitive load; presets must carry the weight, with granular controls behind them ([ux-design-for-adhd](ux-design-for-adhd.md)).

**Confidence: promising** — the population-collision evidence is solid; the right default intensity is an open empirical question.

---

## Cross-cutting layer: AI assistance

The placement rule: invisible AI beats conversational AI for defaults, because every conversation is itself an initiation task with a blank-canvas problem ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).

### 39. AI task breakdown with calibrated trust

**Problem.** Decomposition is precisely the executive step ADHD impairs — planning is broken (d = 1.60) while execution is comparatively intact — so "break it down yourself" outsources the hardest step to the person least equipped at that moment ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md), [task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)).

**Direction.** On any stuck or vague task, one tap yields a generated breakdown: first step ≤ ~2 minutes, concrete verb + single object per step, 3–7 steps visible with the rest chunked, zero prose. A **granularity dial** (Goblin Tools' "spiciness," the folk answer research hasn't caught up to) regenerates finer or coarser for free. Steps are editable in one tap; accepting inserts them under the task; nothing is written silently. Each suggestion carries one line of reasoning, and a user correction visibly teaches the system ("won't suggest that again").

**Constraints from research.**
- This is the flagship AI feature — strongest mechanism fit and strongest community evidence of the AI use cases ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).
- The trust ladder is architecture: Suggest (free) / Act (preview + undo only) / Data (no silent writes, ever) ([ai-assistance-for-adhd](ai-assistance-for-adhd.md), [ux-design-for-adhd](ux-design-for-adhd.md)).
- Facts are extract-or-ask, never invent — a hallucinated deadline in the user's external memory is the worst available AI failure ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).
- Output shape: short, scannable, no hedging, no lectures — verbose "neurotypical" responses are the top documented friction ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).

**Risks.** Reviewing machine steps can itself overwhelm; a bad first suggestion triggers algorithm aversion, so the first-error recovery UX decides the feature's survival ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)). Long-term dependency effects are unknown — the corpus's stance: AI does the sequencing, the user keeps the judgment; whether that boundary holds needs longitudinal watching ([ai-assistance-for-adhd](ai-assistance-for-adhd.md) open questions).

**Confidence: promising** — the highest-confidence AI use case in the corpus, but no study yet tests AI-generated step granularity for ADHD.

### 40. Invisible-first AI with visible provenance

**Problem.** The blank canvas and the prompt box are both initiation tasks; making chat the primary AI surface taxes the exact deficit. Meanwhile parsing, triage, scheduling, and resurfacing are high-frequency drudgery AI can absorb sub-second and sub-cent ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).

**Direction.** AI's default form is infrastructure the user never converses with: natural-language capture parsing ("dentist thurs 3" → scheduled item, shown for confirmation), stale-item triage suggestions, resurfacing-moment selection, day-plan reflow (direction 7). Everything AI touched is labeled with provenance and a one-line why; every action previews or undoes; every AI feature has its own off switch, honoring "do it with me, not for me."

**Constraints from research.**
- Suggest visibly, preview before acting, undo after — never silently rearrange the user's external memory ([ux-design-for-adhd](ux-design-for-adhd.md), [memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).
- Keep AI off the capture critical path: capture is sacred and sub-second ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).
- Small/on-device models for high-frequency invisible ops; sensitive fields stay out of training pipelines, stated explicitly ([ai-assistance-for-adhd](ai-assistance-for-adhd.md), [privacy-and-data-ethics](privacy-and-data-ethics.md)).
- Instrument the trust loop (suggestion acceptance over time, abandonment after errors), not chat engagement ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).

**Risks.** Parse errors on messy input (fragments, voice mumbles) below the reliability floor turn magic into mistrust — real-world accuracy rates are unknown ([ai-assistance-for-adhd](ai-assistance-for-adhd.md) open questions). Provenance chips everywhere can become clutter; the *silent data loss* anti-pattern (AP-21, [anti-patterns.md](anti-patterns.md)) — whose AI variant is exactly this silent rearranging — is avoided by legibility on demand, not labels on everything.

**Confidence: promising** — the placement logic is well reasoned from documented frictions; production reliability for this population is unmeasured.

### 41. Bounded unstick conversations

**Problem.** The one consistent, positive qualitative finding: LLM conversation helps ADHDers *start* — a judgment-free thinking space at stuck moments ("cognitive scaffolding for initiating tasks," 147-discussion Reddit analysis). The documented dangers are sycophancy, verbosity, and companion drift ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).

**Direction.** From any stuck task (or the overwhelm exit, direction 15), an optional short dialogue: task-anchored, a few turns, engineered to end in one accepted next action or a shrunk task — then it closes itself. It validates feelings but evaluates plans, and it can kindly disagree when a plan fights the user's own stated goals. No open-ended chat surface exists anywhere in Klyr; the assistant has no name, no persona depth, no memory of affection.

**Constraints from research.**
- Conversation earns its place only at stuck moments; it exits into action within a few turns ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).
- An anti-sycophancy behavior spec is written and tested against — preference-trained models systematically favor agreement, and RSD-prone users are the worst-case audience for flattery loops ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).
- Hard no-companion boundary: dose-dependent psychosocial harm and dependence are documented for companion-style use ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).
- Never therapy, never diagnosis; crisis handling per the passive-resource rules ([when-to-back-off](when-to-back-off.md)).

**Risks.** Disagreement lands hard on rejection-sensitive users — "kindly" is a testable spec, not an adjective ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)). Turn caps that feel like being hung up on could sour the rescue; the sweet spot between unstick and time-sink is an open question ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).

**Confidence: promising** — consistent qualitative evidence for the mechanism; the bounded format is Klyr's containment hypothesis, untested.

---

## Cross-cutting layer: Integrations and ubiquity

Help works at the **point of performance** — the place and time where the action must happen — which is usually not inside an open app ([executive-function](../foundations/executive-function.md)).

### 42. Glanceable counter-top surfaces

**Problem.** Out of sight is out of mind — cue-dependent memory means invisible tasks stop existing — but static always-on displays habituate into wallpaper ("in sight, but no insight") ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).

**Direction.** A small persistent surface — home-screen widget, lock screen, menu bar — showing 1–3 current items (next action phrasing, direction 3) plus ambient time-left-in-block (direction 27). The display deliberately rotates what it features to fight habituation, and it is glanceable without unlock-app-navigate: the point of performance is the hallway, not the app.

**Constraints from research.**
- Users need visual persistence (piles are rational external memory), and rotation fights both invisibility and habituation ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).
- Never lock core value behind widget/gesture discovery — older adults and low-fluency users must get the happy path without it ([populations-and-variation](../foundations/populations-and-variation.md)).
- Ambient time display beats interruptive reminders for continuous externalization ([time-perception](../foundations/time-perception.md)).

**Risks.** A widget that shows stale or wrong items actively damages trust in the whole external-memory contract — freshness is a hard requirement. The 1–3 item figure is a design hypothesis from attention principles, not a measured threshold ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md) open questions).

**Confidence: promising** — externalization evidence is strong and market convergence (Tiimo widgets, Time Timer) is real; rotation cadence is untested.

### 43. Calendar as the day's skeleton

**Problem.** Fixed commitments define the day's true shape — usable gaps, waiting windows, departure runways — but task lists and calendars usually live apart, forcing exactly the mental time-assembly ADHD impairs ([time-perception](../foundations/time-perception.md)).

**Direction.** Two-way calendar sync makes events the skeleton the day view hangs on: gaps render as usable time with fit-checked task offers (corrected durations, direction 28), pre-event windows trigger waiting-mode layout (direction 8) and leaving-soon mode (direction 29), and event ends become if-then anchors ("after standup → invoice"). External deadline ecosystems — school syllabi, term dates, recurring bill dates — import as first-class deadlines with long-runway decomposition offered (direction 39).

**Constraints from research.**
- Students and externally-deadlined users need ingestion plus accommodation encoding (e.g., "1.5× time") so the system does the pressure math ([populations-and-variation](../foundations/populations-and-variation.md)).
- Auto-inserted transition buffers around events by default ([time-perception](../foundations/time-perception.md)).
- Easy import from incumbent tools removes the cost of trying Klyr ([app-landscape](app-landscape.md)).

**Risks.** Two-way sync errors (duplicated or vanished events) strike at the never-lose-anything contract — sync state must be legible and conservative (direction 2). Rendering a dense calendar risks recreating the wall-of-commitments anxiety manual time blocking causes ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)); show today's shape, not the month's judgment.

**Confidence: promising** — the mechanisms it serves are evidence-backed; the integration form is standard engineering with known UX hazards.

### 44. Own the loop, not the data: portability

**Problem.** ADHD users are serial tool-switchers by design (novelty decay), and data lock-in converts natural churn into resentment; billing and export betrayal are top review complaints in this market ([app-landscape](app-landscape.md)).

**Direction.** One-tap full export in open formats, forever free; imports from Todoist, Notion, calendars, and plain text that land safely in the inbox for drip triage (direction 4). Cancellation as easy as signup (≤2 steps, in-app), loud trial-end warnings, no dynamic pricing. Klyr's bet is that being easy to leave is why people stay — and why they come back after trying the next shiny thing.

**Constraints from research.**
- Transparent, forgiving billing is itself a differentiator for people prone to forgotten subscriptions; trial-to-charge ambushes are named quit-drivers ([app-landscape](app-landscape.md)).
- Cancellation and consent revocation must cost no more steps than the grant (grant/revoke symmetry) ([ux-design-for-adhd](ux-design-for-adhd.md), [privacy-and-data-ethics](privacy-and-data-ethics.md)).
- Portability is a GDPR obligation anyway — build it as architecture, not a favor ([privacy-and-data-ethics](privacy-and-data-ethics.md)).

**Risks.** This direction measurably reduces short-term revenue retention; it is the price of the trust positioning, and the temptation to walk it back under growth pressure is the *billing ambush / lock-in* anti-pattern arriving in a suit ([anti-patterns.md](anti-patterns.md), [ux-design-for-adhd](ux-design-for-adhd.md)).

**Confidence: promising** — market-evidence-grounded trust play; its retention economics are a bet the corpus argues for but cannot prove.

### 45. Shared lists that absorb the nag

**Problem.** In households, the non-ADHD partner becomes the external executive function — planner, reminder, nag — and the relationship slides into a resented parent–child dynamic; reminder-delivery is a relationship-safety issue an app can absorb ([daily-life-impact](../daily-life/daily-life-impact.md)).

**Direction.** Shared lists where the *system* is the one who reminds: a partner can add or flag an item, but the nudge always arrives as a neutral Klyr reminder at a good moment (cue-anchored, direction 5), never as a partner-branded ping. Visibility is self-chosen and scoped — progress can be shared ("handled"), while deferral counts, misses, and completion stats are structurally unshareable. An optional occasional "maintenance load you actually carried" view supports fairness conversations without becoming a scoreboard.

**Constraints from research.**
- No partner-facing failure stats, no completion leaderboards — accountability features between partners are actively dangerous here ([daily-life-impact](../daily-life/daily-life-impact.md)).
- Visible-labor accounting is for self-compassion and negotiation, never scoring ([daily-life-impact](../daily-life/daily-life-impact.md)).
- Any teen/parent variant is consented, scoped, non-punitive, never default-on ([populations-and-variation](../foundations/populations-and-variation.md)).

**Risks.** Even neutral system reminders can be weaponized ("I put it in Klyr, did you not see it?") — the open question of whether labor visibility helps or hurts couples needs testing with real households ([daily-life-impact](../daily-life/daily-life-impact.md) open questions). Social surfaces multiply RSD exposure; every shared element defaults private (*public failure* anti-pattern, [anti-patterns.md](anti-patterns.md)).

**Confidence: promising** — the dynamic it defuses is well documented qualitatively; the defusing mechanism is untested.

---

## Open questions this doc hands to design and research

1. **The urgency line.** Nothing in the corpus locates how much time pressure activates versus panics a given ADHD+anxiety user; directions 29 and 34 need per-user calibration machinery and pre-registered shame guardrails before any experimentation ([outcomes-and-measurement](outcomes-and-measurement.md)).
2. **Amnesty and resurfacing thresholds.** Too fast breaks trust, too slow builds piles; the numbers in directions 22–23 are all placeholders for user testing ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).
3. **Does forgiveness sustain behavior?** Forgiving metrics and elastic recurrence are safer, but whether they preserve as much actual behavior change as stakes do is untested in ADHD populations ([habits-and-routines](../daily-life/habits-and-routines.md)).
4. **Configuration burden vs. personalization.** Directions 9, 38, and 34 all add dials; the corpus simultaneously demands zero-config first value. Presets, harvested configuration, and safe defaults carry the load, but the ceiling on total settings is unknown ([ux-design-for-adhd](ux-design-for-adhd.md), [dopamine-and-motivation](../foundations/dopamine-and-motivation.md)).
5. **AI dependency over months.** Whether scaffolded decomposition builds, preserves, or erodes users' own planning is the field's biggest open question; Klyr should instrument it rather than assume ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).
6. **Does any of this move real-world function?** No consumer task app has demonstrated ADHD functional-outcome improvement. The measurement plan — return-after-lapse as North Star, function scales in reserve, proxies as hypotheses — is how Klyr finds out honestly ([outcomes-and-measurement](outcomes-and-measurement.md)).
