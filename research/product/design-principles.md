---
title: "Klyr Design Principles"
area: product
file: research/product/design-principles.md
tags: [design-principles, synthesis, constitution, shame-free, externalization, capture, restart, low-maintenance, privacy]
related:
  - research/foundations/executive-function.md
  - research/foundations/emotional-regulation-and-rsd.md
  - research/foundations/memory-and-object-permanence.md
  - research/foundations/dopamine-and-motivation.md
  - research/foundations/time-perception.md
  - research/foundations/populations-and-variation.md
  - research/daily-life/habits-and-routines.md
  - research/strategies/planning-methodologies-and-adhd.md
  - research/product/app-landscape.md
  - research/product/ux-design-for-adhd.md
  - research/product/when-to-back-off.md
  - research/product/outcomes-and-measurement.md
  - research/product/privacy-and-data-ethics.md
sources: 0
updated: 2026-07-25
summary: >
  The binding design constitution for Klyr: twenty testable principles ordered by how early and
  how often they should decide a question, each grounded in the corpus, with named tensions and
  resolutions. Read before designing, building, measuring, or writing copy for any Klyr surface.
---

# Klyr Design Principles

## TL;DR

- This is the **design constitution**. Twenty principles, ordered by consult priority. Each has a testable statement; a mockup, feature, experiment, or sentence of copy that violates a statement is a defect, not a debate. Collisions between principles are resolved in the **Tensions** subsection of the higher-ranked one.
- Klyr's identity in one sentence: **a permanent external executive system that expects the user to disappear and makes coming back painless** ([app-landscape](app-landscape.md), [executive-function](../foundations/executive-function.md)).
- The load-bearing core (P1–P7): Klyr *is* the executive function, help lands at the point of performance, capture is sacred, nothing is silently lost, shame is designed out structurally, the comeback is the core loop, and two weeks of neglect must leave the system trustworthy.
- Doing and starting (P8–P13): everything decomposes to a startable step (Klyr does the decomposing), time is rendered as space and held by the app, motivation invites and never punishes, acknowledgment is instant and guaranteed, screens do one thing, and everything is designed for month three — when the novelty is gone.
- People and state (P14–P16): capacity is weather, not character — de-escalate automatically, escalate never; Klyr never becomes the distraction; and wherever populations conflict, ship a calm-default dial, never a house style.
- Data and truth (P17–P20): automation shows its work, everything stored is treated as health data, the product is judged by return-after-lapse and real-world function rather than engagement, and no claim ever outruns its evidence.
- This doc synthesizes; it does not originate. To amend a principle, first change what the corpus says (new evidence, new doc, corrected doc) — preference, taste, or growth pressure is not an amendment path.

## Principles at a glance

| # | Name | Statement in one line |
|---|---|---|
| P1 | The prosthesis principle | Klyr is the executive function — permanent scaffold, never a training program. |
| P2 | Point of performance | Help arrives where and when the action happens, never only at planning time. |
| P3 | Sacred capture | Capture takes under three seconds, zero decisions, from anywhere, before any account. |
| P4 | Nothing silently lost | Every automatic change leaves a visible, reversible trace; export is always one tap. |
| P5 | Shame-free by architecture | Failure is never rendered as arithmetic; aging items get amnesty by default. |
| P6 | Restart is the core loop | Every return — after an hour or a month — lands on a calm, current state with zero make-up work. |
| P7 | Survives neglect | Two weeks of total neglect must leave Klyr correct, calm, and trustworthy. |
| P8 | Startable steps | Everything decomposes to a concrete next action — and Klyr does the decomposing. |
| P9 | Time made physical | Duration renders as space, transitions are budgeted, and no default assumes the user feels time. |
| P10 | Motivation without coercion | Invite, reward, celebrate — never punish, pressure, or take hostages. |
| P11 | Instant, guaranteed acknowledgment | Completion is acknowledged the moment it happens, unconditionally, every time. |
| P12 | One thing now | Every screen has one job; density is the user's dial; a one-item mode is one tap away. |
| P13 | Built for month three | Novelty is a budgeted, opt-in, renewable resource; honeymoon data proves nothing. |
| P14 | Capacity is weather | De-escalate automatically and freely; escalate, interpret, or label never. |
| P15 | Never the distraction | Klyr never competes for the attention it exists to protect. |
| P16 | Dials, not house style | Where populations conflict, ship a user-owned dial with a calm default. |
| P17 | Legible automation | AI suggests freely, acts behind preview-and-undo, and never writes silently. |
| P18 | Health data by default | Everything stored is treated as health data; architecture enforces every promise. |
| P19 | Function over engagement | Judged by return-after-lapse and real-world function; engagement can veto, never justify. |
| P20 | Calibrated claims | Never claim more than the evidence carries; a tool, never a treatment. |

## How this document binds

Ordering reflects how early and how often a principle should decide a question, not how negotiable it is — none are negotiable. When two principles collide in a real decision, the **Tensions** subsection of the higher-ranked principle names the resolution; if it does not, resolve toward the lower-numbered principle and file the gap as a bug against this doc. The principles bind product, engineering, copy, marketing, pricing, metrics, and experiments equally. Evidence lives in the linked corpus docs; this doc carries no sources of its own.

## The principles

### P1: The prosthesis principle

**Klyr does the holding, sequencing, timing, and prompting itself — permanently — and never expects the user's executive function to improve, train up, or take over.**

**Why.** ADHD is a performance disorder, not a knowledge disorder: users almost always know what to do and cannot execute it at the moment it matters ([executive-function](../foundations/executive-function.md), [adhd-overview](../foundations/adhd-overview.md)). Barkley's evidence-aligned strategy is externalization — covert, self-directed information is "weak as a source of stimulus control" — and gains persist only as long as the accommodations do. The clearest negative result in the intervention literature is that cognitive training does not transfer to symptoms or daily life ([evidence-based-strategies](../strategies/evidence-based-strategies.md)).

**In practice:**
- The next action is always visible in one sentence on the task surface — never two taps away.
- No feature may depend on the user remembering to open the app; Klyr pushes and resurfaces, because "check the system" is itself a prospective-memory task ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).
- No graduation mechanics: reminders are never faded as a reward for consistency, and no copy implies the user should eventually manage without scaffolds.
- Brain-training minigames and cognitive-improvement claims are banned outright.
- Copy frames externalization as the smart strategy, never a crutch; tips and psychoeducation are seasoning, never the intervention.
- Every design review asks the worst-week question: *what does this feature cost the user on their worst week?*

**Tensions.** Externalization raises the dependency worry ("is the app doing my thinking?"). The corpus resolution: offloading *mechanics* is prosthetic, not corrosive — Klyr does the sequencing, the user keeps the judgment ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)). Offered structure also becomes a felt demand for demand-sensitive users ([motivation-and-gamification](../strategies/motivation-and-gamification.md)); Klyr therefore *offers* scaffolding — one tap to accept — rather than imposing it (P10). Business tension: "you'll finally build the habit" is a seductive story; P20 forbids it.

### P2: Point of performance

**Help arrives where and when the action happens: every cue is actionable at the moment it fires, and no intervention depends on a planning session held at some other time.**

**Why.** The point of performance — "that place and time... where they are failing to use what they know" — is the single most actionable principle in the ADHD literature; help delivered elsewhere mostly does not transfer ([executive-function](../foundations/executive-function.md)). If-then implementation intentions, which pre-bind an action to a concrete cue, carry d = 0.65 across 94 general-population tests and d ≈ 0.99 in clinical samples ([evidence-based-strategies](../strategies/evidence-based-strategies.md)). Event-based prospective memory is relatively spared in ADHD while time-based is most impaired — cues beat clocks ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).

**In practice:**
- Every reminder carries its action in the notification body — the link, the phone number, the decided first step. A notification that just names a task ("Report") is a defect ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)).
- If-then plans ("when I sit down with coffee → open the invoice draft") are first-class, schedulable objects in the data model, prompted gently at planning time.
- When a user sets a clock reminder, Klyr offers to convert it to an event anchor ("5 pm — is that 'when you close your laptop'?").
- Glanceable surfaces (widget, lock screen) outrank in-app dashboards in roadmap priority.
- No feature's value may depend on a weekly review or Sunday planning ritual (see P7).

**Tensions.** The phone is simultaneously the best-positioned cue-delivery system and the biggest source of competing stimulation — a real, testable worry ([executive-function](../foundations/executive-function.md)). Point-of-performance interrupts also spend the interruption budget P15 protects; resolution: only user-designated critical items interrupt, everything else batches. "The right moment" must come from user-set anchors, never from inferred mental state (P14, P18).

### P3: Sacred capture

**Capturing a thought costs under three seconds, zero required decisions, and zero navigation away from what the user was doing — from anywhere, before any account exists.**

**Why.** Uncaptured thoughts evaporate in seconds, and an uncaptured idea behaves like an unfinished task, consuming attention until it is parked — the corpus calls this distraction-by-anticipation ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md), [attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)). Every required field is a drop point, and front-loaded filing decisions are exactly where PARA-style systems die ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)). Zero-friction capture is what earns ADHD love in the market (Goblin Tools, Due), while setup-before-value is a documented abandonment engine ([app-landscape](app-landscape.md)).

**In practice:**
- Global quick-add from every screen, including mid-focus-session, as an overlay that dismisses back to the exact prior state.
- No required fields at capture: no project, date, priority, or category — ever. Classification is deferred to Klyr (suggestion, search, auto-archive), not the user.
- Voice, widget, and share-sheet paths ship early; input is typo-tolerant.
- First capture happens within 60 seconds of first open, before any account wall ([ux-design-for-adhd](ux-design-for-adhd.md)).
- AI stays off the capture critical path: capture feedback is sub-second; parsing runs after ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).

**Tensions.** Zero-decision capture seems to fight P8 (everything startable); the resolution is sequencing — capture now, decompose later, at plan time or the moment of paralysis, never at entry. Voice and location capture create sensitive data; P18's tiers apply. Business tension: sign-up walls inflate "activation" dashboards; the wall loses.

### P4: Nothing silently lost

**Nothing the user puts into Klyr is ever silently lost, altered, or expired — every automatic change leaves a visible, reversible trace, and full export is always one tap away.**

**Why.** The mind releases an open loop only when it trusts the external system to bring it back; a single dropped item can collapse that trust, and with it the entire prosthesis ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)). Data lock-in and silent loss convert churn into resentment in a market of serial tool-switchers ([app-landscape](app-landscape.md)). For AI, a hallucinated fact written silently into a task is the single worst available failure ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).

**In practice:**
- Undo instead of confirmation dialogs; archive instead of delete; autosave everything; no data-losing timeouts ([ux-design-for-adhd](ux-design-for-adhd.md)).
- "Show me everything I ever captured" always works, in one place, searchable.
- Auto-tidying (P6, P7) demotes and parks; it never deletes, and it always leaves a trace the user can find and reverse.
- AI never modifies stored content without preview and undo; facts are extract-or-ask, never invented (P17).
- One-tap full export in open formats, free forever; account recovery is designed for people who lose passwords ([privacy-and-data-ethics](privacy-and-data-ethics.md)).

**Tensions.** Never-lose collides with P5 — history can be a shame object — resolved as *keep everything, push nothing*: the archive is queryable, never an ambush ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)). It collides with privacy retention limits — resolved by the content/exhaust split: user content is kept forever, behavioral exhaust ages out, and user-invoked amnesty is honest deletion, not silent loss ([privacy-and-data-ethics](privacy-and-data-ethics.md)). Full end-to-end encryption collides with recoverability; P18's tiering resolves it.

### P5: Shame-free by architecture

**Klyr never renders failure as arithmetic — no overdue counts, no red badges, no broken streaks, no missed-item recaps — and items that age past their moment receive amnesty by default.**

**Why.** Users arrive pre-shamed: emotional dysregulation affects an estimated 34–70% of adults with ADHD, criticism sensitivity is among the most consistent findings in lived-experience research, and every abandoned planner has already taught them that organizing tools accuse ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)). Overdue-pile guilt is the single clearest abandonment mechanic in general task managers — "you feel guilty every time you open it, so you stop opening it" ([app-landscape](app-landscape.md)). Shame is not a tone problem to polish; it is an architecture problem: if a 47-item overdue list *can* render, it eventually will.

**In practice:**
- The home screen, app icon, and tab never show a count of overdue items — the count is structurally impossible, not suppressed.
- Overdue amnesty is a core mechanic: aging items quietly de-emphasize, then park with a neutral resurface prompt ("Still matter? Shrink it? Let it go?").
- Missed recurring chores compress into one next instance; "overdue ×14" cannot render ([daily-life-impact](../daily-life/daily-life-impact.md)).
- Recaps lead with what happened, including partials; missed items appear only as actionable choices, never statistics. No "you missed X this week" surface exists.
- Partial completion ("started," "2 of 5") is a first-class, celebrated state.
- Error states blame the system, never the user; all copy passes the test *"would a good ADHD coach say this sentence to a client mid-shame-spiral?"*

**Tensions.** Forgiveness vs. momentum: total amnesty can dissolve productive stakes, and some users genuinely want hard accountability ([habits-and-routines](../daily-life/habits-and-routines.md)); resolution is forgiving-by-default with opt-in, reversible intensity — never punishment imposed as house policy (P10). Amnesty that moves too fast reads as "the app deleted my task" — a P4 violation in the user's eyes — so parking is visible, reversible, and threshold-tested. Business tension: guilt notifications re-engage in the short term; they are banned, and P19 refuses the metric that would justify them.

### P6: Restart is the core loop

**Reopening Klyr after an absence — an hour, a week, a month — always lands on a calm, current, immediately usable state with zero make-up work; the comeback is the most-designed moment in the product.**

**Why.** Every user will disappear: boom-bust cycles are the documented rhythm of ADHD life, and the community lifecycle — "use it perfectly for 10 days, miss one day, feel guilty, never open it again" — names the kill point almost no product designs for ([daily-life-impact](../daily-life/daily-life-impact.md), [app-landscape](app-landscape.md)). The load-bearing skill in habit research is resuming after a miss, not maintaining a perfect run; one miss barely dents automaticity, but the shame spiral after it ends the whole practice ([habits-and-routines](../daily-life/habits-and-routines.md)). Klyr's market positioning is exactly this: the tool that expects you to disappear and makes coming back painless.

**In practice:**
- The welcome-back flow is a hero flow: neutral greeting, auto-tidied today (amnesty applied, trace kept), one small next action — never "you were away 9 days," never a recap of the gap ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).
- Resumes are wins: returning after a miss is detected and celebrated as the most rewarding, lowest-friction moment in the app.
- Every task exit offers a skippable one-line "ready-to-resume" note; on reopen, the breadcrumb shows before the description ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).
- Every recurring structure — habits, routines, chores — has a zero-make-up-work re-entry with a one-tap minimum version.
- Restart latency (time from return to first meaningful action) is instrumented as a headline product metric (P19).

**Tensions.** A designed comeback must not become a designed guilt trip: no "we missed you" copy, no streak-repair upsells. Tidying on return must respect P4 — demoted, not deleted, with a visible trace. Restart-first also loses to DAU on any engagement dashboard; P19 makes that trade explicit and final.

### P7: Survives neglect

**Klyr stays correct, calm, and useful after two weeks of total neglect; any feature that needs a recurring user ritual to stay trustworthy is rejected at design review.**

**Why.** Every major productivity methodology dies at the same spot: the recurring maintenance ritual — weekly review, migration, filing, board grooming — which is boring, delayed-reward, and executive-function-heavy, exactly the task profile ADHD handles worst ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)). Maintenance debt is why Notion produces a "template graveyard" and daily-planning ceremonies become second jobs ([app-landscape](app-landscape.md)). A system that requires executive function to maintain fails hardest during the weeks it is needed most ([adhd-overview](../foundations/adhd-overview.md)).

**In practice:**
- There is no weekly review. Klyr performs review work continuously — one stale item at a time, as a single keep/kill/someday tap at natural moments.
- Plans self-heal when a day slips: automatic reflow with visible reasoning and undo; the wreckage of the old plan is never displayed.
- Days and weeks auto-close and open clean, with a blameless auto-generated recap ("what moved, what carried") replacing self-run retros.
- Stale items sink and fade automatically (visible trace per P4); the backlog exists but never squats in the daily view.
- Configuration is harvested from use, never demanded up front; feature gate at review: *what does this look like after it is ignored for two weeks?* If the answer is clutter or accusation, it does not ship.

**Tensions.** Maintenance-free pulls against power-user configurability — every option is future maintenance debt and complexity creep is itself an abandonment trigger; resolution: opinionated defaults, shallow customization, presets over settings (P16). Automated tidying pulls against legibility; automation must show its work (P17). Bullet-journal evidence suggests some friction carries intentionality — resolution: one-tap carry-forward plus an "is this still worth your attention?" question after repeated carries, never silent rollover ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

### P8: Startable steps

**Every actionable item carries — or is one tap from — a concrete next physical action, and Klyr generates it, because decomposition is the impaired step, not the user's homework.**

**Why.** An item with no defined next physical action gets silently skipped on every scan; a list of unstartable items is a shame display, not a tool ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)). Crucially, planning is the broken component (d = 1.60 in the best adult study) while plan retention and execution are largely intact — people with ADHD execute well once a concrete plan exists, so "just break it down yourself" outsources the hardest step to the person least equipped for it in that moment ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)). Task breakdown is also the highest-confidence AI use case in the corpus ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).

**In practice:**
- Every stored task carries a next physical action with a physical verb; Klyr proposes one when the capture is vague.
- AI breakdown is available at the point of paralysis: first step ≤ ~2 minutes, concrete verb + single object, 3–7 steps visible, a granularity dial, free regeneration.
- Any task collapses to a two-minute version on one tap ("open the doc," "put one dish away").
- Reminders phrase the pre-made decision: "Open report doc — you decided: one bad paragraph."
- Decomposition is never demanded at capture (P3) and never auto-committed without review (P17).

**Tensions.** Decomposition inflates lists and can itself become an avoidance ritual — how much is right is an open question ([executive-function](../foundations/executive-function.md)); resolution: steps stay chunked behind the current one (P12), and over-listing is absorbed gracefully, never displayed as failure. Machine-generated steps can misread the task; they are editable suggestions, not writes (P17).

### P9: Time made physical

**Klyr holds time for the user: durations render as space, transitions are budgeted, reminder salience concentrates where it changes behavior, and no default assumes the user feels time passing.**

**Why.** Timing deficits in ADHD are robust across all four lab paradigms (lifespan meta-analytic g = 0.688), delay discounting is steeper (d = 0.43), and time is often experienced as a binary of now and not-now — so deadlines are weightless for weeks, then overwhelming in the last hours ([time-perception](../foundations/time-perception.md)). Monitoring fails on *allocation*, not frequency: the evidence supports concentrating salience in the final window, not spreading nags evenly. Externalizing time works better than trying harder to feel it (time-assistive RCT: parent-rated daily time management d = 1.0).

**In practice:**
- Remaining time renders as a shrinking wedge, bar, or arc alongside numerals, everywhere durations matter.
- Reminder salience follows a J-curve: near-silent early, escalating sharply in the last 10–20% of the runway.
- Transitions are budgeted: default buffers between commitments, no back-to-back scheduling by default, and a "leaving soon" mode that stops offering new work and counts down to *stop-doing-things* time.
- Waiting mode is designed for: state the usable gap in plain words, offer only gap-sized tasks, and guarantee the interrupt ("I'll tell you at 2:35 — stop watching the clock").
- Klyr learns per-user duration correction factors from actuals and presents them as calibration, never as a failure metric.
- Timers are optional, resumable, and non-punitive: count-up is first-class, sessions extend without ending, and unfinished sessions are never marked failed; a timer never hard-stops flow ([evidence-based-strategies](../strategies/evidence-based-strategies.md)).
- Defaults respect delayed chronotypes: no morning-anchored plans, no early-bird moralizing, no plan failed because it slipped past midnight ([adhd-overview](../foundations/adhd-overview.md)).

**Tensions.** Urgency is the sharpest tension in the corpus: it is the most reliable activation lever and the most likely to produce anxiety, avoidance, and abandonment ([time-perception](../foundations/time-perception.md), [dopamine-and-motivation](../foundations/dopamine-and-motivation.md), [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)). All three docs converge on one resolution, adopted here: urgency is user-initiated equipment, defaulted low, always about the task ("this closes at 5 pm"), never about the person ("you're running out of chances"). Ambient countdowns can themselves trigger clock anxiety; visibility is a dial (P16).

### P10: Motivation without coercion

**Klyr invites, rewards, and celebrates; it never punishes, pressures, moralizes, or takes hostages — every motivational mechanic is opt-in, reversible, and safe to walk away from.**

**Why.** ADHDers grow up under unusually heavy external control, and reward-only designs trap users in controlled motivation that collapses when the rewards stop; Self-Determination Theory — autonomy, competence, relatedness — is the safest foundation ([motivation-and-gamification](../strategies/motivation-and-gamification.md)). Punishment mechanics are the market's clearest natural experiment: Habitica's HP loss punishes busy weeks and drives abandonment, while Finch's punishment-free care model earns durable love ([app-landscape](app-landscape.md)). Streak resets convert one miss into quitting the entire practice ([habits-and-routines](../daily-life/habits-and-routines.md)), and a task app is structurally a demand machine for a demand-sensitive population.

**In practice:**
- Hard red lines: no health/pet-harm/decay mechanics, no reset-to-zero streaks, no public failure or default leaderboards, no paid or scarcity-mediated randomness, no guilt copy — anywhere, ever.
- Every gamification layer (pet, XP, sounds, confetti) is individually toggleable with clean off-ramps and no data loss.
- Rewards aim at aversive tasks (laundry, forms); Klyr never attaches rewards to activities the user already loves (overjustification risk).
- Feedback is informational before transactional: visible progress and competence evidence ("9 of the last 12 weeks") over points.
- Language is invitational; any self-set commitment renegotiates in one tap with zero penalty; "overdue" never moralizes.
- If streak-like mechanics ship at all: cumulative framings, automatic repair, decay-not-reset, opt-in only.

**Tensions.** Forgiveness vs. commitment power: enough forgiveness can dissolve a commitment device entirely (Duolingo caps its freezes for exactly this reason); Klyr accepts weaker commitment devices as the price of survivable ones and offers opt-in stakes — low, reversible, appointment-shaped rather than financial ([evidence-based-strategies](../strategies/evidence-based-strategies.md)). Variable rewards outperform fixed ones and are the slot-machine mechanism; the red line is vary *delight*, never *whether* the user's work is acknowledged (P11).

### P11: Instant, guaranteed acknowledgment

**Acknowledgment is instant, unconditional, and guaranteed: the moment of action is rewarded at the moment it happens, and Klyr never promises a reward it might not deliver.**

**Why.** The most replicated ADHD reward finding is blunted anticipatory signaling (d = 0.48) with intact response at delivery — *plans don't pull; ticking the box does* — and steep discounting means value decays fast with delay ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)). A predicted reward that fails to arrive produces a negative prediction error: an active demotivator, not a neutral event. Reinforcement works in ADHD when it is immediate, frequent, and consistent; a weekly summary is none of those.

**In practice:**
- Completion, starts, and partials are acknowledged the instant they happen; if a beautiful animation and a fast one conflict, ship the fast one.
- Acknowledgment never gambles: expression may vary (P13), arrival may not.
- Interaction feedback lands under ~400 ms; cold starts, sync spinners, and multi-step entry flows are treated as motivational taxes, not polish issues ([ux-design-for-adhd](ux-design-for-adhd.md)).
- Many small acknowledged completions beat one large one — decomposition (P8) is a motivational feature, not just an organizational one.
- Starts count as wins and are tracked as such; rewarding only completion re-punishes the impaired step ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)).

**Tensions.** Instant acknowledgment vs. calm (P15): acknowledgment happens in-surface at the moment of action, never as a push notification. Celebration intensity is population-sensitive — confetti delights some users and patronizes others ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)); intensity is a dial with a modest default (P16).

### P12: One thing now

**Every screen has one job and one primary action; density is a user-owned dial; and a one-item mode for overwhelmed moments is never more than one tap away.**

**Why.** ADHD taxes extraneous cognitive load at a premium, and choice overload bites hardest under decision difficulty and uncertain preferences — precisely the ADHD profile ([ux-design-for-adhd](ux-design-for-adhd.md)). Choice paralysis and overwhelm freeze are input problems whose exit is fewer options, ideally one ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)). One-task-at-a-time views are among the most-loved patterns in the ADHD app market (Llama Life, Amazing Marvin's Super Focus) ([app-landscape](app-landscape.md)).

**In practice:**
- One visually primary action per screen; salience (color, motion, highlight) is a rationed budget of roughly one spend per screen.
- A one-thing-now focus mode shows exactly one task; the list is one tap away but never ambiently visible during a session ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).
- An "I'm stuck" state collapses the entire UI to one small next action — no lists, no counts, no badges.
- Progressive disclosure is backed by guaranteed resurfacing, and the promise is stated in the UI: *hidden, not lost* (P4).
- The persistent ambient surface (widget/today) shows 1–3 rotating items, never the whole system ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)).

**Tensions.** This principle sits on the corpus's loudest user-side contradiction: "if it leaves the screen it stops existing" vs. "dense screens shut me down" ([ux-design-for-adhd](ux-design-for-adhd.md) reconciles the community conflict). The resolution is architectural, not a compromise: minimal defaults, a density dial (P16), and a resurfacing engine trustworthy enough that hiding something does not mean losing it — if resurfacing ever fails, users will rationally re-hoard everything onto the screen.

### P13: Built for month three

**Klyr is designed for the user who is bored of it: novelty is a budgeted, opt-in, renewable resource inside the product, and nothing is judged to work on honeymoon data.**

**Why.** Novelty responses habituate — every productivity app works for two weeks, and the novelty honeymoon is named in the corpus as Klyr's single biggest product risk ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)). Gamification studies show a reliable engagement dip around week four; median 15-day retention for mental-health-adjacent apps is ~3.9% ([motivation-and-gamification](../strategies/motivation-and-gamification.md), [app-landscape](app-landscape.md)). The community cycle — new system, fresh dopamine, collapse, shame, newer system — is the abandonment engine Klyr must route inward: the "I need a new system" itch must be scratchable inside Klyr.

**In practice:**
- Sanctioned novelty ships as a feature: rotating themes, celebration content, and swappable strategy modes, offered proactively when engagement dips.
- Novelty changes the surface, never the substrate: restyling never requires rebuild, migration, or data loss ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).
- Copy normalizes tool boredom without shame: "brains get bored of tools — try a different mode."
- Retention, benefit, and feature verdicts are read at month 3+; week-2 numbers are treated as a false-positive machine ([outcomes-and-measurement](outcomes-and-measurement.md)).
- Every new mechanic ships with a decay expectation and a rotation plan, not an assumption of permanence.

**Tensions.** Novelty rotation collides with the AuDHD need for sameness — for monotropic users, unannounced change is a cost, not a delight ([populations-and-variation](../foundations/populations-and-variation.md)); resolution: stability is the default, novelty is announced, previewed, and opt-in (P16). Novelty also flirts with maintenance debt (P7): if trying a new mode ever requires setup work, the feature has failed. Business tension: honeymoon metrics flatter every launch; P19 forbids shipping verdicts on them.

### P14: Capacity is weather

**Klyr treats capacity as weather, not character: it reduces pressure automatically and freely, and it never escalates, interprets, diagnoses, or labels the user's state without being asked.**

**Why.** Comorbidity is the default (odds ratios vs. non-ADHD populations: ~5.0 anxiety, ~4.5 depression), EF output fluctuates hour to hour, and boom-bust cycles guarantee that every user-year contains a trough — capacity collapse is a scheduled event, not an edge case ([adhd-overview](../foundations/adhd-overview.md), [when-to-back-off](when-to-back-off.md)). Software cannot reliably distinguish a depressive shutdown from a busy week, and false positives cost trust twice: surveillance plus pathologizing. Hence the asymmetry principle: wrongly quieting notifications costs almost nothing; wrongly implying "you seem depressed" costs the relationship.

**In practice:**
- Defaults are safe for a user with anxiety and depression: no punitive overdue states, no loss framing, red is never the resting color of an unfinished list.
- A one-tap, no-explanation capacity control (low-day toggle / energy dial) makes the user the sensor; plans reorder to match declared state ([evidence-based-strategies](../strategies/evidence-based-strategies.md)).
- Essentials mode shrinks the visible system to 1–3 user-chosen anchors and freezes all meters — reduced, never fully dark (behavioral-activation logic).
- Recurring tasks skip, not stack, during troughs; re-entry follows P6.
- Klyr never infers or names mental-health states from usage, ships no clinical screeners, scans no content for crisis keywords; verified crisis resources stay passively reachable at all times, never algorithmically sprung ([when-to-back-off](when-to-back-off.md)).

**Tensions.** Backing off too hard reads as the app giving up ("even my app thinks I can't do anything"), while any check-in can read as surveillance; the resolution is user-configured policies executed predictably, with consent-first, dismissible check-ins ([when-to-back-off](when-to-back-off.md)). Essentials mode vs. hard-consequence deadlines (rent, refills): the user chooses which anchors survive the freeze — Klyr never unilaterally decides which obligations matter. The regulatory line is absolute: wellness framing only, no detection or diagnostic claims (P20).

### P15: Never the distraction

**Klyr never competes for the attention it exists to protect: interruptions are budgeted, notifications are few and actionable, and engagement-maximizing mechanics are banned outright.**

**Why.** Notifications die by habituation — relevance and timing, not count, determine harm, and identical repeated alerts get overridden at rates of 49–96% in clinical alerting ([ux-design-for-adhd](ux-design-for-adhd.md), [memory-and-object-permanence](../foundations/memory-and-object-permanence.md)). Interruption cost is paid in stress and unfinished threads, and the documented pathways into compulsive feed use — boredom and emotion regulation — are exactly the states a task app finds its users in ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)). An ADHD tool that adds interruptions is net-negative regardless of content quality.

**In practice:**
- A focus session generates at most one system-initiated interruption unless the user configured more; everything else queues.
- Two notification classes only: point-of-performance interrupts (P2) and batched digests — every one actionable from the shade, quiet hours on by default, "why this fired" visible.
- Snooze-death breaker: after ~3 snoozes, the reminder converts into a triage choice — reschedule / shrink / let it go — with "let it go" shame-free.
- Three ignored resurfacings of an item signal a strategy change (shrink it, re-anchor it, offer release), never a volume increase.
- Banned outright: infinite scroll, variable-ratio notification rewards, engagement-bait pings, autoplaying or looping motion. Klyr must be safe to use compulsively, which means never built to be used compulsively ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)).

**Tensions.** P1 demands aggressive resurfacing; P15 demands quiet. The resolution is the notification budget: few, high-value, batched, forgiving in tone — persistence is reserved for a tiny set of user-designated critical items (the Due pattern, [app-landscape](app-landscape.md)). Business tension: notifications are the industry's cheapest retention lever; Klyr's retention story must run through P6 instead.

### P16: Dials, not house style

**Where one user's delight is another's harm, Klyr ships a user-owned dial with the calm setting as the default — never a single house style.**

**Why.** At least five large sub-populations flip specific defaults in opposite directions, and the sharpest contradiction is AuDHD (roughly 38–40% of autistic people also have ADHD): the novelty, surprise, and sensory intensity that serve ADHD motivation are exactly what can dysregulate the autistic side ([populations-and-variation](../foundations/populations-and-variation.md)). Presentations shift over time, capability varies within one person, and the corpus's one near-universal is that forgiveness, low shame, and near-zero-cost capture serve every group — the deltas are sensory intensity, novelty, time pressure, and disclosure.

**In practice:**
- A first-class sensory panel: independent controls for motion, sound, haptics, and color saturation — defaulting low; `prefers-reduced-motion` honored everywhere.
- Change is announced, never sprung: layout changes preview before applying; "surprise me" is strictly opt-in.
- Literal, plain copy is house style: buttons say what they do; no idioms, sarcasm, or action-hiding cuteness on functional controls.
- Presets are nameable in human terms ("more calm / less surprise," "recently diagnosed," "lighter some weeks") — but defaults are already safe for the most sensitive group, so a user who never opens settings is never harmed.
- No diagnosis gate and no forced self-classification: "if this sounds like your brain," never "confirm your diagnosis" ([adhd-overview](../foundations/adhd-overview.md)).

**Tensions.** Every dial is itself choice-overload and maintenance surface (P7, [ux-design-for-adhd](ux-design-for-adhd.md)); the resolution is calm opinionated defaults, few visible dials, presets over settings, and configuration harvested from use. Calm-first may cost first-session wow for stimulation-seeking users — an accepted, monitored trade ([populations-and-variation](../foundations/populations-and-variation.md) leaves it open; P19 watches it at month three, not week one).

### P17: Legible automation

**Automation and AI may suggest freely, may act only behind preview and undo, and may never touch stored user data silently — and every automatic move shows its reasoning.**

**Why.** Failure economics are asymmetric: suggestions are cheap to be wrong about, but automation below ~0.70 reliability is worse than none, people abandon algorithms faster than humans after one visible error, and reliance grows exactly when load is high — where ADHD users live ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)). Klyr is the user's external memory (P1, P4); a system that silently rearranges someone's memory is indistinguishable from gaslighting, and ADHD users demonstrably resent black-box scheduling ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

**In practice:**
- The three-tier error budget is architecture, not policy: Suggest (free), Act (preview + undo only), Data (no silent writes, ever).
- Generated content is extract-or-ask: AI never invents facts, dates, or commitments into stored items.
- Every suggestion carries one line of reasoning; everything AI changed is labeled with provenance.
- After a user-flagged error, Klyr visibly adapts ("won't suggest that again") and correction is one tap.
- Invisible assists (parsing, triage, resurfacing, scheduling) are the default AI surface; chat is a bounded unstick tool that exits into action within a few turns — never an open-ended companion, never sycophantic ([ai-assistance-for-adhd](ai-assistance-for-adhd.md)).

**Tensions.** Preview-and-undo friction taxes the same executive budget Klyr exists to spare — users may just disable review ([ux-design-for-adhd](ux-design-for-adhd.md) flags this open); resolution: friction proportional to blast radius, one-tap acceptance, and automation scope that expands only with earned trust. The anti-sycophancy requirement can conflict with P5's warmth: the spec is *validate feelings, evaluate plans* — kind is not the same as agreeable.

### P18: Health data by default

**Klyr treats everything it stores as health data: no third-party ad or analytics code anywhere, sensitive fields tiered and opt-in, deletion honest, and no promise in copy that the architecture does not enforce.**

**Why.** Regulators already treat Klyr's data class as health data — GDPR Article 9 case law reaches even pharmacy orders, and Washington's MHMD covers mental-health information and *inferences from non-health data*; an account in an ADHD-branded app is itself sensitive ([privacy-and-data-ethics](privacy-and-data-ethics.md)). Every FTC health-app enforcement action (GoodRx, BetterHelp, Premom, Cerebral, Flo) began with ordinary ad/analytics SDKs plus a broken privacy sentence. Users carry real disclosure risk — workplace stigma, controlled-substance entanglement — and privacy failure is unrecoverable in a way engagement failure is not.

**In practice:**
- Zero third-party advertising or analytics SDKs/pixels in app or web funnel; first-party, minimal, privacy-reviewed telemetry only.
- Two-tier architecture from day one: recoverable encrypted cloud for the task graph; local-first, optionally E2E for sensitive fields (mood, cycle, energy windows).
- Consent is just-in-time, per-category, default-off, one-tap revocable; onboarding collects nothing sensitive; core task management never gates on sensitive data.
- Behavioral exhaust (deferral logs, lapse history) ages out by default; "forget this period" ships as a first-class amnesty flow with honest, propagating deletion.
- Cycle-aware and energy-window features are user-declared, opt-in, local-first, purged on disable — never inferred from behavior, never required ([populations-and-variation](../foundations/populations-and-variation.md)).
- State inferences compute on-device where feasible and are never persisted as a server-side mental-state profile.

**Tensions.** The corpus's sharpest architecture collision: full E2E privacy vs. P4's never-lose contract — ADHDers lose keys, and unrecoverable data is its own betrayal. Both docs resolve it the same way, adopted here: tiered sensitivity with recoverable encryption for the task graph and opt-in E2E for the health-adjacent layer, behind an honest tradeoff screen ([privacy-and-data-ethics](privacy-and-data-ethics.md), [memory-and-object-permanence](../foundations/memory-and-object-permanence.md)). Measurement (P19) needs data; default to aggregate, on-device, opt-in. Privacy is sold as discoverable character, never as a fear pitch.

### P19: Function over engagement

**Klyr is judged by whether people come back after disappearing and function better in real life — engagement numbers may veto a change, but they can never justify one.**

**Why.** Engagement and outcome are decoupled in this category: every app "works" for two weeks, median 15-day retention is ~3.9%, and for an overwhelm-reducing tool more time in app is often worse ([outcomes-and-measurement](outcomes-and-measurement.md), [app-landscape](app-landscape.md)). Global self-ratings are contaminated by positive illusory bias; everyday-function measures beat both lab tests and vibes ([executive-function](../foundations/executive-function.md)). The North Star is return-after-lapse: of users who go quiet, how many come back and do something meaningful without being guilt-tripped into it.

**In practice:**
- The written metric hierarchy is enforced: North Star (return-after-lapse) → functional outcomes (opt-in validated scales, quarterly at most, never gates) → behavioral proxies (hypothesis-grade until validated) → guardrails (engagement and shame-risk, watched not optimized). Decisions are made at the highest trustworthy tier; lower tiers may veto, never justify.
- Anti-metrics are banned as success measures: DAU, streak length, task throughput, time-in-app, overdue counts, honeymoon NPS.
- Shame-risk guardrails (overdue-anxiety growth, break-churn, negative check-in sentiment) are pre-registered stop conditions.
- No experiment arm ships that you would not ship to someone on their worst day; Klyr never A/B tests shame or pressure variants — there is no equipoise.
- Success numbers are team telemetry, never surfaced to the user as a grade (P5).

**Tensions.** Return-after-lapse conflicts with investor-standard growth stories ([app-landscape](app-landscape.md) leaves the LTV question open); this principle spends real money and is priced in deliberately — the alternative metrics push the product back toward the guilt mechanics that kill its competitors. Measuring function at all requires instruments and data; P14 and P18 bound how: tiny, optional, non-punitive, aggregate.

### P20: Calibrated claims

**Klyr never states a claim — in product copy, marketing, mechanics, or store listings — more confidently than the evidence behind it, and it is a tool, never a treatment.**

**Why.** The user base has been burned by miracle systems; calibrated claims are both an ethical floor and a churn defense ([evidence-based-strategies](../strategies/evidence-based-strategies.md)). The legal walls are explicit: FTC substantiation standards require competent and reliable scientific evidence for benefit claims, and the FDA general-wellness safe harbor evaporates the moment UI or copy references a disease, uses diagnostic thresholds, or prompts clinical action ([outcomes-and-measurement](outcomes-and-measurement.md), [when-to-back-off](when-to-back-off.md)). The corpus's myth screen is binding for a reason: pop-neuroscience framing would embarrass Klyr in front of the clinicians its users trust ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)).

**In practice:**
- The myth screen applies to every sentence Klyr ships: no "dopamine detox/deficit" framing, no 21-day habit rule, no "23 minutes to refocus," no brain-training promises, no "ADHD superpower" romanticism ([adhd-overview](../foundations/adhd-overview.md)).
- In-product "why this works" notes label evidence honestly: "many people find…" for community strategies (dopamine menus, body doubling), "research shows…" only where it does.
- Klyr does not diagnose, detect, screen, or treat; it never tracks medication as compliance; marketing, screenshots, and store copy stay inside wellness-safe-harbor language and are audited per release.
- Community-grade strategies are legitimate to ship — labeled as community wisdom and instrumented, so Klyr can help generate the evidence that does not yet exist.
- Any future benefit claim runs the honest-claims checklist first; testimonials never substitute for evidence.

**Tensions.** Calibrated claims sell worse than miracle claims — "may help you feel less behind" loses a headline contest to "fixes your focus." The corpus's answer: in a market defined by broken promises, honesty is a differentiator, and overclaiming is simultaneously a churn engine, an FTC exposure, and a betrayal of P5's contract with a shame-sensitized user. When marketing punch and calibration conflict, calibration wins.

## Where the unresolved questions live

This constitution states resolutions, not certainties. The open empirical questions behind each principle — amnesty thresholds, urgency dosage, novelty cadence, density defaults, E2E appetite, restart-nudge tone — live in the **Open questions** sections of the linked corpus docs and must be tested with real ADHD users, not settled by preference. Until a question is answered, the calm, forgiving, autonomy-preserving option is the default; that bias is itself a principle of this document.
