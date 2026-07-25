---
title: "Evidence-Based Strategies and Interventions for Adult ADHD"
area: strategies
file: research/strategies/evidence-based-strategies.md
tags: [interventions, evidence-grades, cbt, implementation-intentions, body-doubling, timers, accountability, environment-design]
related:
  - research/strategies/planning-methodologies-and-adhd.md
  - research/strategies/motivation-and-gamification.md
  - research/daily-life/task-initiation-and-paralysis.md
  - research/foundations/executive-function.md
  - research/daily-life/habits-and-routines.md
sources: 51
updated: 2026-07-25
summary: >
  The intervention evidence review: what actually helps adult ADHD (clinical and tactical layers),
  with an evidence grade for every technique and a ranked list of what Klyr should operationalize.
  Read before designing any feature that claims to "help" — this doc says which mechanisms are real.
---

# Evidence-Based Strategies and Interventions for Adult ADHD

## TL;DR

- **CBT for adult ADHD works**: SMD ≈ 0.76 vs. waitlist, ≈ 0.43 vs. active controls; its *ingredients* (chunking, graded tasks, external structure, if-then plans) are exactly what a task app can operationalize.
- **Implementation intentions (if-then planning)** are the best-evidenced portable technique in this doc: d = .65 across 94 tests in the general population, d ≈ .99 in clinical samples; ADHD-specific trials (children) show improved inhibition and delay of gratification. Klyr should natively convert vague intentions into cue-based plans.
- **Body doubling** is community-discovered and research-emerging: in the first academic survey (220 neurodivergent people), 85% said they were more likely to complete a task alongside someone. No RCTs yet; mechanisms are plausible (social presence, accountability, co-regulation).
- **Temptation bundling** (Milkman) raised gym attendance 29–51% by locking a pleasure to a should-task — a direct patch for ADHD's steep temporal discounting. Untested in ADHD specifically.
- **Deadlines and commitment devices help but misfire**: self-imposed deadlines beat none but are set badly (Ariely & Wertenbroch); high-stakes commitment contracts cause real losses for many users, and pressure backfires hard for demand-avoidant profiles. Stakes must be opt-in, low, and reversible.
- **Mindfulness, exercise, coaching, psychoeducation**: all beneficial as lifestyle/clinical adjuncts; effects vs. *active* controls are modest or unproven. Klyr can encourage, not deliver, most of these.
- **Timer-based work** (visual timers, ADHD-adapted Pomodoro) rests on clinical consensus + massive community endorsement, not RCTs. The adaptation that matters: flexible intervals, easy on-ramps, never yank a user out of flow.
- **"Eat the frog" is wrong for most ADHDers most of the time**: in an ADDitude survey (389 readers) only 7% do the hardest thing first; 68% say it depends on the day. Task ordering must be state-based, not doctrine.
- **Energy/spoons planning, dopamine menus, novelty rotation** are community-grade strategies with no trials but coherent mechanisms — legitimate design material if labeled honestly.
- **What fails**: working-memory training (Cogmed-style) does not transfer to symptoms or real life; rigid all-or-nothing planner regimes collapse; motivation exhortation ("just try harder") adds shame, not activation. Klyr must build none of these.

## How to read the evidence grades

| Grade | Meaning |
|---|---|
| **Strong** | Multiple RCTs or meta-analyses, including adult ADHD samples |
| **Moderate** | Meta-analytic or RCT support in general/clinical populations; ADHD-specific evidence limited or indirect |
| **Emerging** | Early studies, surveys, small trials; promising, unreplicated |
| **Community** | Widespread lived-experience endorsement + plausible mechanism; no controlled trials. Valid UX truth, unproven clinical claim |
| **Refuted** | Properly tested and failed, or contradicted by systematic evidence |

A "Community" grade is not a dismissal — several of Klyr's likely killer features live there — but Klyr's copy must never imply clinical proof where there is none.

## The clinical layer (brief)

Medication remains the single most effective symptom treatment for most adults and is out of an app's scope (see [adhd-overview](../foundations/adhd-overview.md)). The psychosocial layer below matters to Klyr for a different reason: its **active ingredients are behavioral techniques an app can embed**.

| Intervention | Grade | Headline evidence | What Klyr takes from it |
|---|---|---|---|
| CBT for adult ADHD | **Strong** | SMD 0.76 vs. waitlist; 0.43 vs. active control [1]; benefits on symptoms, executive function, mood [2][3]; strongest functional gains at work [4] | Its skill modules are Klyr feature specs |
| Metacognitive/organizational-skills therapy | **Strong** (as CBT variant) | Solanto's 12-week group RCT (n=88) improved inattention vs. supportive therapy [5] | Time management, planning, task breakdown are teachable |
| ADHD coaching | **Emerging** | Pre-post gains, medium-large effects; almost no RCTs; self-selected samples [7][8][9] | Coach-like check-ins and forward scaffolding, minus outcome claims |
| Mindfulness-based programs | **Moderate w/ caveat** | SMD 0.32–0.56 on symptoms/function [11]; earlier metas larger [12]; ~no advantage over active controls, publication bias [13] | Optional practice content at most; not a pillar |
| Exercise | **Moderate** | Meta-analyses show improved inhibitory control in adults (8 RCTs, n=372) and broad EF benefits [14][15][16] | Movement is legitimate "productivity" — let users schedule it guilt-free |
| Psychoeducation | **Moderate (thin but foundational)** | Recommended as base of care; pilot RCTs improve quality of life and self-knowledge more reliably than symptom scores [17][18] | Klyr teaching users *why* a feature works is itself an intervention |

Three details worth keeping:

- **CBT's edge shrinks against active controls** (0.43) and doesn't always beat other structured treatments [1][4]. The honest reading: *structure, skills practice, and a supportive frame* carry much of the effect — good news for a product that can deliver structure daily at near-zero cost.
- **CBT packages for adult ADHD are mostly skills, not cognition-restructuring**: Safren's and Solanto's manuals train task breakdown, graded exposure to boring work, calendars/capture systems, and problem-solving [5][6]. An app that quietly walks users through the same moves at the **point of performance** (see [executive-function](../foundations/executive-function.md)) extends the clinic into daily life.
- **Coaching's evidence is honest-to-goodness "emerging"**: reviews of workplace support find coaching and psychoeducation rated most useful, while lamenting the paucity of controlled research [10]. Klyr may borrow coaching's *stance* (collaborative, non-judgmental, forward-looking) without claiming its outcomes.

## The tactical layer (Klyr's raw material)

### Implementation intentions (if-then planning) — Grade: Strong (general), Emerging (ADHD-specific)

An **implementation intention** is a pre-decided link between a cue and an action: "If it is 9:00 and I've opened my laptop, then I draft the invoice email." Gollwitzer & Sheeran's meta-analysis (94 tests, 8,461 participants) found d = .65 on goal attainment over and above having the goal [19]; effects on *getting started* (d = .61) and *shielding ongoing work from derailment* (d = .77) are precisely ADHD's two weak points. In clinical and analogue samples the pooled effect is larger still — d = .99 across 28 studies [20]. A 2024 mega-meta (642 tests) confirmed effects of .27–.66 and that the contingent **if-then format** outperforms vaguer plans [21].

**Mechanism**: the plan delegates initiation to the environment. Deliberation ("should I start now? what first?") happens once, in advance, when the user is calm — not at the moment of action, where ADHD's executive and motivational deficits live. Gollwitzer calls this *strategic automaticity* [22].

**ADHD-specific status**: trials by Gawrilow, Gollwitzer and colleagues in children with ADHD improved response inhibition, delay of gratification, and executive task performance [22]. No large adult-ADHD RCT surfaced in this pass — an honest gap — but the mechanism directly compensates the deficit, and the clinical-samples meta [20] is encouraging.

**Failure modes**: plans multiply until they're noise; cues that never occur; plans formed under pressure become demands (see backfire section). Keep one active if-then per goal, tied to a cue that reliably happens.

### Body doubling — Grade: Community → Emerging

**Body doubling** is working in the (physical or virtual) presence of another person who may be doing something entirely different. The term circulated in ADHD coaching since ~1996 (Linda Anderson) and exploded via social media [23]. The first peer-reviewed investigation (Eagle, Baltaxe-Admony & Ringland, ASSETS 2023) surveyed 220 people, 88% neurodivergent: **186 of 220 (85%) said they were more likely to complete a task when working alongside someone else**; 24% only learned the term during the survey ("I've always done this") [23][24].

Participants' own explanations cluster into: **accountability** (someone might notice me scrolling), **companionship** (hard tasks feel less bad), **visual reminder/anchor** (their working keeps me tethered to working), and **mirroring** [23]. Theory adds social facilitation and co-regulation; honest status: *mechanisms unconfirmed, no RCTs; a 2025 VR study (n=12) found faster task completion with both human and AI doubles* [25][26].

The paper's key design gift is a **two-axis continuum**: space/time (live shared room ↔ pre-recorded "study with me" video) × mutuality (explicit mutual accountability ↔ ambient strangers in a café) [23]. Focusmate-style structured sessions (declare a goal → work in parallel on video → check out) occupy the high-mutuality corner [28]; a LoFi study stream is the low corner. Different users need different corners, sometimes on the same day.

**Backfire**: for socially anxious users or heavy maskers, being watched is a cost not a support [26][27]; forced cameras and chatty partners are the top community complaints. Presence must be adjustable down to "ambient."

### Time externalization and visual timers — Grade: Clinical consensus + Community

ADHD time is felt, not tracked — "now vs. not now" (see [time-perception](../foundations/time-perception.md)). Barkley's core prescription is to **externalize time**: make it a physical, visible thing at the point of performance rather than a mental representation (see [executive-function](../foundations/executive-function.md)). Analog-disk timers (Time Timer style), shrinking progress bars, and "time until next commitment" displays all implement this. Direct controlled-trial evidence for visual timers in adults is thin — this recommendation rests on clinical consensus and overwhelming community endorsement, not RCTs (not verified against a controlled trial in this pass). Given near-zero cost and mechanism fit, it is still among the safest bets in this doc.

### Pomodoro, ADHD-adapted — Grade: Community

Classic Pomodoro (25 min work / 5 min break) is loved and hated in the ADHD community for the same reason: rigidity. Community and clinician consensus on adaptations [29][30]:

- **Flexible intervals** (10–45 min): 25 can be too long to dare starting and too short once flowing. A "just 10 minutes" ramp is an initiation tool, not a lesser Pomodoro.
- **Never yank hyperfocus**: when the bell rings mid-flow, offer "keep going" with a soft wrap-up buffer and hydration/movement nudges, instead of a hard stop (see [attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)).
- **Protect the break**: unstructured breaks default to infinite scroll, and the session dies. Breaks need pre-chosen, bounded activities (see dopamine menus below).
- The timer is a **pacing guide, not a rule**; missed intervals are data, not failure.

No ADHD-specific RCTs of Pomodoro surfaced in this pass; the ingredients it bundles (time externalization, chunked effort, scheduled rest) each have better standing than the brand itself.

### Task chunking and graded task assignment — Grade: Moderate (as a validated CBT component)

Breaking work into small, concrete, next-physical-action steps is a core module of every evidence-based CBT/metacognitive package for adult ADHD [5][6], inheriting from **graded task assignment** in behavioral activation. Mechanism: each chunk lowers activation energy below the paralysis threshold, and completion frequency rises — more reward events per hour for a brain that under-responds to distant outcomes (see [dopamine-and-motivation](../foundations/dopamine-and-motivation.md), [task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)). The community-tested constraint: chunks must match *today's* capacity — a chunk list written by Monday-you can still paralyze Thursday-you. Auto-chunking (AI-suggested step breakdowns the user can accept/edit) is one of the highest-leverage things Klyr can build, because generating steps is itself the executive task users are stuck on.

### "Eat the frog" vs. "start with an appetizer" — Grade: Community (both camps), personalize

**Eat the frog** (do the hardest/most important task first) assumes willpower is freshest early and dread taxes the whole day. **Appetizer-first** argues ADHD runs on interest-generated momentum: start with something engaging, get the engine hot, then ride into the hard thing ("eat the ice cream first" — ADHD Jesse) [32]. ADDitude's reader survey (n=389): **7% frog-first, 25% easy-first, 68% "depends on the day"** [31].

| Signal today | Better opening move |
|---|---|
| Medication/energy peak, deadline salient, dread is poisoning everything | Frog (or 5-minute "poke the frog" contact) |
| Initiation is the problem; everything feels equally impossible | Appetizer: small, interesting, guaranteed win |
| Easy tasks are multiplying while the frog rots | Frog-adjacent chunk + bundling/body double |

The design conclusion isn't a winner — it's that **ordering doctrine fails; state-based ordering wins**. The known appetizer risk is productive procrastination (a day of appetizers, no entrée), so momentum starts need a planned hand-off to the real task [31][32].

### Energy-based and spoons-based planning — Grade: Community

**Spoon theory** (Christine Miserandino, early 2000s) models capacity as a small, variable daily budget of "spoons"; **energy accounting** (Maja Toudal / Tony Attwood) frames activities as withdrawals and deposits [33][34]. ADHD capacity genuinely swings day to day (sleep, meds, interest, cycle), so time-based plans that assume constant throughput systematically overcommit. Community pacing guidance includes planning to ~two-thirds of estimated capacity to avoid boom-bust cycles [34]. No controlled trials; as a *planning UI paradigm* (tag tasks by cost, match the day's plan to the day's budget) it is a differentiator no mainstream task manager offers.

### Dopamine menus — Grade: Community

A **dopamine menu** (popularized by Jessica McCabe / How to ADHD) is a pre-built personal menu of rewarding activities organized like courses: *appetizers* (2-minute boosts), *entrées* (sustaining activities), *sides* (stackable stimulation — music, fidgets, body doubling), *desserts* (high-capture activities to portion deliberately), *specials* (planned treats) [35]. Mechanism (plausible, untested): when stimulation-hunger hits, choosing is itself an executive task; a pre-computed menu redirects the seeking toward chosen options instead of the phone's defaults. The "dopamine" framing is metaphor, not measured neurochemistry — science journalism rates the tool plausible but untested as an intervention [36]. Klyr fit: break menus, reward pickers, and the ADDitude build steps (streamline; reduce friction to good options, add friction to desserts) [35].

### Temptation bundling — Grade: Moderate (general population; untested in ADHD)

Katy Milkman's **temptation bundling**: restrict a craved indulgence to co-occur with an avoided should-task. In the flagship RCT (n=226), gym-only access to page-turner audiobooks raised gym visits **51%** (full restriction) and **29%** (self-imposed restriction) vs. control; effects decayed over weeks, yet 61% of participants offered the option afterward chose to *pay* for gym-locked audiobooks [37]. A later field experiment showed teaching the technique produces modest but real gains [38]. Mechanism: it welds an immediate reward onto a delayed-reward behavior — a direct countermeasure to ADHD's steep temporal discounting ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)). The decay finding matters: bundles are consumables that need refreshing, which dovetails with novelty rotation below.

### Accountability structures and commitment devices — Grade: Moderate, with documented backfire

Evidence runs along a hardness spectrum:

- **Deadlines**: people willingly self-impose costly deadlines and they help — but people set them suboptimally; evenly spaced, externally anchored deadlines performed best (Ariely & Wertenbroch) [39]. Translation: Klyr suggesting interim deadlines beats asking users to invent them.
- **Appointments beat penalties**: in a health field experiment, appointment-style commitments roughly doubled follow-through while most users of financial commitment devices lost their stakes [41]. A scheduled *social* slot (a body-doubling session, a check-in) is a gentler, more effective device than money-burning.
- **High stakes hurt real people**: in field data, a large share of commitment-contract takers fail and pay — commitment can select the wrong people into the wrong contracts [40].
- **Demand-avoidant backfire**: for users with a **PDA profile** (pathological demand avoidance / "persistent drive for autonomy" — a contested, non-DSM construct overlapping autism/ADHD), external pressure converts even *self-chosen* goals into threats, triggering avoidance or shutdown; reward-and-consequence systems read as manipulation [42][43]. Many ADHDers without full PDA report a milder version: yesterday's own to-do list already feels like someone else's orders. Add the shame/RSD channel — a failed pledge is an RSD grenade ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)) — and the design rule writes itself: **accountability in Klyr must be opt-in, low-stakes, reversible, and socially warm rather than punitive.**

### Environment design and friction manipulation — Grade: Moderate–Strong (general behavior science)

Wendy Wood's habit research shows behavior tracks environmental cues and friction more than intentions: reduce friction and sharpen cues for desired actions, add friction and hide cues for undesired ones [44]. Duckworth & Milkman's review ranks such **situation modification** above in-the-moment willpower — "play offense, not defense" [45]. Even small added effort (extra taps, delays, distance) measurably suppresses a behavior [44][45]. For ADHD this compounds: out of sight is out of mind ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)), and supports work only at the **point of performance**. Klyr's version: one-tap capture (lowest possible friction at the moment a thought exists), surfacing today's few tasks where the user already looks (widget, lock screen, watch), and optional friction-adders (focus-mode links, dessert delays) rather than moralizing about distraction.

### Planned novelty rotation — Grade: Community

The community pattern is near-universal: a new system delivers a glorious two weeks, then novelty decays and the system is abandoned — followed by shame, followed by a new system ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md), [habits-and-routines](../daily-life/habits-and-routines.md)). Coaches and ADHD productivity writers now prescribe **rotation on purpose**: keep a small set of interchangeable formats/views and switch *within* the system when boredom hits; use undated, restart-friendly formats so any random Tuesday is a valid fresh start; treat switching as maintenance, not failure [46][47]. No trials exist; as retention design it converts Klyr's biggest threat (abandonment) into a supported gesture — users should be able to "get a new app" without leaving the app.

## What does not hold up

- **Working-memory training (Cogmed and kin) — Refuted for real-world transfer.** Training improves the trained tasks and near-transfer WM measures, but meta-analyses find no convincing far transfer to attention, academics, or daily function [48], RCTs in ADHD find few far-transfer effects [49], metas restricted to blinded/objective outcomes find little to nothing [50], and even Cogmed-focused meta-analysis concedes gains don't generalize [51]. Klyr must not ship "brain-training" games or imply that in-app exercises treat ADHD.
- **Rigid planner regimes — no direct trials, convergent negative signal.** Full-stack systems (complete GTD, elaborate bullet journals, wall-to-wall time blocking) demand daily executive upkeep — exactly the scarce resource — and community data shows they collapse, then punish the user with a visible record of failure. Detailed autopsy in [planning-methodologies-and-adhd](./planning-methodologies-and-adhd.md).
- **Motivation exhortation — wrong model of the disorder.** ADHD is a performance problem (doing what you know at the right time and place), not a knowledge or willpower problem — Barkley's point-of-performance principle ([executive-function](../foundations/executive-function.md)). Pep talks, "no excuses" streaks, and guilt-copy add shame without adding activation, and shame is itself demotivating fuel ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)). Any Klyr copy containing "just" + verb is a bug.

## Design implications for Klyr

**The ranked build list** — techniques Klyr should natively support, ordered by (evidence strength × mechanism fit × operationalizability):

| Rank | Technique | Mechanism exploited | Grade |
|---|---|---|---|
| 1 | If-then planning built into tasks (cue + first action) | Delegates initiation to environmental cues; strategic automaticity | Strong |
| 2 | Auto-chunking into next physical actions | Lowers activation energy; raises reward frequency | Moderate (CBT-validated) |
| 3 | Time externalization: visual timers, "time until next," shrinking bars | Makes time perceivable; compensates time blindness | Clinical consensus |
| 4 | Body-doubling layer (live sessions ↔ ambient presence) | Social presence, accountability, co-regulation | Community→Emerging |
| 5 | Temptation bundling (pair dreaded task with chosen pleasure) | Immediate reward welded to delayed-reward behavior | Moderate |
| 6 | Friction tooling: one-tap capture, point-of-performance surfacing | Situation modification beats willpower | Moderate–Strong |
| 7 | Flexible focus sprints (adapted Pomodoro, flow-respecting) | Chunked effort + externalized pacing | Community |
| 8 | Energy/spoons-based day planning | Matches plan to variable capacity; prevents overcommit | Community |
| 9 | Dopamine menu for breaks and rewards | Pre-computed stimulation choices at low-EF moments | Community |
| 10 | State-based task ordering (frog vs. appetizer prompt) | Interest/energy-driven sequencing | Community (survey-backed heterogeneity) |
| 11 | Soft accountability: check-ins, shared goals, appointments | Social commitment without punitive stakes | Moderate |
| 12 | Sanctioned novelty rotation (themes, views, modes) | Novelty-seeking channeled inside the product | Community |

Numbered implications:

1. **Klyr should make "when/where will this happen?" a first-class task property**, gently prompting an if-then cue at capture or planning time. Rationale: d = .65–.99 evidence for implementation intentions, strongest exactly on initiation and derailment [19][20].
2. **Klyr should offer AI-assisted chunking that outputs concrete next physical actions**, editable in one tap. Generating steps is the stuck point; chunking is a validated CBT ingredient [5][6].
3. **Klyr should render time visually everywhere durations matter** — analog-style depletion, countdown to next commitment — not as numerals alone. Externalization is the consensus compensation for time blindness.
4. **Klyr should ship a body-doubling presence layer with an intensity dial**: silent ambient co-working ↔ goal-declared sessions with check-ins. 85% of surveyed neurodivergent users report it helps; the continuum model says one intensity won't fit all [23].
5. **Klyr should support attaching a "bundle" (playlist, podcast, show) to dreaded tasks** and treat bundles as refreshable, since bundling effects decay [37][38].
6. **Klyr's timers must never hard-stop a user in flow**: ring softly, offer continue/wrap-up, and log overruns as flow, not overtime. Interrupting hyperfocus is the community's top timer complaint [29][30].
7. **Klyr should ask (or infer) a lightweight daily state — energy/meds/mood — and reorder suggestions accordingly**, offering a frog-poke on strong days and appetizers on frozen days. 68% of users say ordering "depends on the day"; doctrine loses to state [31].
8. **All accountability features must be opt-in, low-stakes, reversible, and framed as invitations** ("want a check-in Thursday?"), never penalties by default. Appointments outperform financial stakes; high stakes cause losses; demand-avoidant users treat pressure as threat [39][40][41][42].
9. **Klyr should propose interim deadlines spaced toward the goal** instead of relying on user-invented ones, which Ariely & Wertenbroch show are set suboptimally [39].
10. **Klyr should include a personal dopamine-menu builder and use it to populate break screens**, with deliberate friction before "desserts." Mechanism-plausible, community-loved; must be labeled as a community strategy, not neuroscience [35][36].
11. **Klyr should build novelty INTO the product**: rotating themes/layouts/modes offered proactively when engagement dips, so "I need a new system" resolves inside Klyr. Converts the abandonment cycle into retention [46][47].
12. **Klyr must never ship brain-training minigames or claim cognitive-improvement outcomes.** WM training's far-transfer record is the clearest negative result in the ADHD intervention literature [48][49][50][51].
13. **Klyr's copy must be exhortation-free**: no "just," no "no excuses," no discipline moralizing; explain mechanisms instead (psychoeducation improves self-knowledge and QoL [17]). Tone spec belongs with [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md).
14. **Tension to manage**: structure helps (CBT effects) yet imposed structure becomes a demand (PDA backfire). Klyr should default to *offered* structure — suggestions the user accepts with one tap — preserving autonomy while still doing the executive lifting [1][42][43].
15. **Klyr should label evidence honestly in-product** (e.g., a small "why this works" note citing grade). Users burned by miracle apps trust calibrated claims; overclaiming is both an ethical and a churn risk.

## Open questions

- No adult-ADHD RCTs yet for implementation intentions, body doubling, temptation bundling, energy-based planning, or dopamine menus — Klyr's telemetry could produce the first large-scale observational evidence; what would ethical, privacy-respecting measurement look like?
- Where is each user's line between "helpful scaffold" and "felt demand"? Can Klyr detect demand-avoidant reactance early (e.g., snoozing spikes after reminders) and auto-soften?
- Optimal if-then dosage: how many active plans before interference erodes the effect? Research hints "few," but the number is untested.
- Does virtual/ambient body doubling retain efficacy long-term, or does it decay like temptation bundles? Does AI presence work as well as human (one n=12 study says maybe [25])?
- Can energy forecasting (from history, sleep, cycle data) beat self-report for spoons-based planning, without becoming surveillance-feeling?
- Frog vs. appetizer: is there a measurable interaction with medication timing that Klyr could learn per user?
- Novelty rotation cadence: proactive rotation offers vs. on-demand — which sustains engagement without feeling gimmicky?

## Sources

1. [Young, Moghaddam & Tickle — The Efficacy of CBT for Adults With ADHD: Systematic Review and Meta-Analysis of RCTs (J Atten Disord)](https://pubmed.ncbi.nlm.nih.gov/27554190/) [research]
2. [A meta-analysis of the intervention effect of cognitive behavioral therapy on adult ADHD (J Affective Disorders, 2025)](https://www.sciencedirect.com/science/article/abs/pii/S0165032725025492) [research]
3. [Cognitive-behavioral treatments for adults with ADHD: Systematic review with meta-analysis (2025)](https://www.researchgate.net/publication/391572567_Cognitive-behavioral_treatments_for_adults_with_ADHD_Systematic_review_with_meta-analysis) [research]
4. [ADHD Evidence Project — Meta-analysis: CBT for Adult ADHD (López-Pinar et al., functioning outcomes)](https://www.adhdevidence.org/blog/meta-analysis-cognitive-behavioral-therapy-for-adult-adhd) [clinical]
5. [Solanto et al. — Efficacy of Meta-Cognitive Therapy for Adult ADHD (Am J Psychiatry RCT)](https://psychiatryonline.org/doi/10.1176/appi.ajp.2009.09081123) [research]
6. [Knouse & Safren — Current Status of Cognitive Behavioral Therapy for Adult ADHD](https://pmc.ncbi.nlm.nih.gov/articles/PMC2909688/) [research]
7. [Kubik — Efficacy of ADHD coaching for adults with ADHD (J Atten Disord)](https://pubmed.ncbi.nlm.nih.gov/19276311/) [research]
8. [Ahmann, Saviet & Otto — Coaching for Adults With ADHD: A Prospective Study (2026)](https://journals.sagepub.com/doi/abs/10.1177/15598276261432960) [research]
9. [CHADD — Evidence-Based Coaching for Adult ADHD](https://chadd.org/adhd-news/adhd-news-adults/attention-monthly-evidence-based-coaching-for-adult-adhd/) [clinical]
10. [A systematic review of interventions to support adults with ADHD at work (Frontiers in Psychology, 2022)](https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2022.893469/full) [research]
11. [Mindfulness-based interventions for adults with ADHD: systematic review and meta-analysis (Medicine, 2025)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12440486/) [research]
12. [A Meta-analysis of Mindfulness-Based Interventions in Adults with ADHD: ADHD Symptoms, Depression, and Executive Functioning (Mindfulness, 2020)](https://link.springer.com/article/10.1007/s12671-020-01458-8) [research]
13. [ADHD Evidence Project — MBIs reduce ADHD symptoms in adults, but no better than active controls](https://www.adhdevidence.org/blog/meta-analysis-finds-mindfulness-based-interventions-reduce-adhd-symptoms-in-adults-but-no-better-than-active-psychological-controls) [clinical]
14. [The impact of physical activity on inhibitory control of adult ADHD: systematic review and meta-analysis (J Glob Health, 2025)](https://jogh.org/2025/jogh-15-04025) [research]
15. [Effects of Physical Activity, Exercise and Sport on Executive Function in Adults with ADHD: Systematic Review (2025)](https://www.mdpi.com/2673-5318/6/4/120) [research]
16. [ADHD Evidence Project — Seven New Meta-analyses Suggest Wide Range of Benefits from Exercise](https://www.adhdevidence.org/blog/seven-new-meta-analyses-suggest-wide-range-of-benefits-from-exercise-for-persons-with-adhd) [clinical]
17. [Effects of a psychoeducational group intervention for adults diagnosed with ADHD: pilot RCT (BMC Psychiatry, 2025)](https://link.springer.com/article/10.1186/s12888-025-07452-5) [research]
18. [PEGASUS: CBT-based psychoeducational groups for adults with ADHD and significant others — feasibility trial](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4340972/) [research]
19. [Gollwitzer & Sheeran — Implementation Intentions and Goal Achievement: Meta-Analysis of Effects and Processes (2006)](https://scispace.com/papers/implementation-intentions-and-goal-achievement-a-meta-4awoi9wm93) [research]
20. [Toli, Webb & Hardy — Implementation intentions in people with mental health problems: meta-analysis (Br J Clin Psychol, 2016)](https://pubmed.ncbi.nlm.nih.gov/25965276/) [research]
21. [The When and How of Planning: Meta-Analysis of Implementation Intentions in 642 Tests (2024)](https://www.researchgate.net/publication/378870694_The_When_and_How_of_Planning_Meta-Analysis_of_the_Scope_and_Components_of_Implementation_Intentions_in_642_Tests) [research]
22. [Gollwitzer — Implementation Intentions (overview incl. Gawrilow ADHD studies; NCI constructs paper)](https://cancercontrol.cancer.gov/sites/default/files/2020-06/goal_intent_attain.pdf) [research]
23. [Eagle, Baltaxe-Admony & Ringland — Proposing Body Doubling as a Continuum of Space/Time and Mutuality (ASSETS '23)](https://dl.acm.org/doi/10.1145/3597638.3614486) [research]
24. [Eagle et al. — "It Was Something I Naturally Found Worked": An Investigation of Body Doubling with Neurodivergent Participants (ACM TACCESS, 2024)](https://dl.acm.org/doi/full/10.1145/3689648) [research]
25. [You Are Not Alone: Designing Body Doubling for ADHD in Virtual Reality (2025)](https://arxiv.org/pdf/2509.12153) [research]
26. [Medical News Today — Body doubling for ADHD: definition and how it works](https://www.medicalnewstoday.com/articles/body-doubling-adhd) [clinical]
27. [ADDA — The ADHD Body Double: A Unique Tool for Getting Things Done](https://add.org/the-body-double/) [community]
28. [10000Hours — ADHD Body Doubling (Focusmate session structure description)](https://blog.make10000hours.com/post/adhd-body-doubling) [product]
29. [AuDHD Psychiatry — The Pomodoro Technique for ADHD: Does It Really Work?](https://www.audhdpsychiatry.co.uk/insights/does-pomodoro-really-work-for-adhd/) [clinical]
30. [Life Skills Advocate — Managing Distractions With The Pomodoro Technique For ADHD](https://lifeskillsadvocate.com/blog/pomodoro-technique-for-adhd/) [community]
31. [ADDitude — Eat the Frog: Advice for Completing Tasks, Overcoming ADHD Fatigue (reader survey, n=389)](https://www.additudemag.com/eat-the-frog-completing-tasks-adhd/) [community]
32. [ADHD Jesse — Don't Eat the Frog First](https://adhdjesse.com/posts/dont-eat-the-frog-first) [community]
33. [ADDA — ADHD and Spoon Theory: How to Understand and Manage Daily Energy](https://add.org/spoon-theory/) [community]
34. [Neurodivergent Insights — Intro to Pacing Systems (energy accounting, two-thirds principle)](https://neurodivergentinsights.com/intro-to-pacing-systems/) [clinical]
35. [ADDitude — Your ADHD Dopamenu: Build a Dopamine Menu in 5 Steps (after How to ADHD)](https://www.additudemag.com/dopamenu-dopamine-menu-adhd-brain/) [community]
36. [The Conversation — Dopamine menus: the science behind the trend](https://theconversation.com/dopamine-menus-the-science-behind-the-trend-and-how-it-might-help-people-with-adhd-218970) [clinical]
37. [Milkman, Minson & Volpp — Holding the Hunger Games Hostage at the Gym: An Evaluation of Temptation Bundling (Management Science, 2014)](https://pubsonline.informs.org/doi/10.1287/mnsc.2013.1784) [research]
38. [Kirgios et al. — Teaching temptation bundling to boost exercise: A field experiment (OBHDP, 2020)](https://www.sciencedirect.com/science/article/pii/S074959782030385X) [research]
39. [Ariely & Wertenbroch — Procrastination, Deadlines, and Performance: Self-Control by Precommitment (Psychological Science, 2002)](https://web.mit.edu/ariely/www/MIT/Papers/deadlines.pdf) [research]
40. [John — When Commitment Fails: Evidence from a Field Experiment](https://economics.yale.edu/sites/default/files/john_when_commitment_fails_march2018.pdf) [research]
41. [Appointments: A More Effective Commitment Device for Health Behaviors (field experiment)](https://arxiv.org/pdf/2110.06876) [research]
42. [Life Skills Advocate — Clear Answers About Pathological Demand Avoidance In Adults](https://lifeskillsadvocate.com/blog/pathological-demand-avoidance-in-adults-guide/) [community]
43. [Science Works Health — Demand Avoidance in ADHD: Overwhelm vs. Defiance](https://www.scienceworkshealth.com/post/demand-avoidance-in-adhd-overwhelm-vs-defiance-and-what-therapy-does-differently) [clinical]
44. [Wood — Habits, Goals, and Effective Behavior Change (Current Directions in Psychological Science, 2024)](https://journals.sagepub.com/doi/abs/10.1177/09637214241246480) [research]
45. [Duckworth & Milkman — Changing Behavior for Good (situational strategies review)](https://static1.squarespace.com/static/5353b838e4b0e68461b517cf/t/5b450d3188251bb11141a54b/1531252017224/20180112_JACR_Duckworth_Milkman_submit.pdf) [research]
46. [Life Skills Advocate — 7 ADHD Planners That Actually Work (and How To Stick With One)](https://lifeskillsadvocate.com/blog/adhd-planner/) [community]
47. [Saner.ai — How to Manage Tasks with ADHD: Systems, Strategies and Tools](https://blog.saner.ai/manage-tasks-with-adhd/) [product]
48. [Melby-Lervåg, Redick & Hulme — Working Memory Training Does Not Improve Performance on Measures of Far Transfer (Perspect Psychol Sci, 2016)](https://journals.sagepub.com/doi/10.1177/1745691616635612) [research]
49. [Chacko et al. — Few Effects of Far Transfer of Working Memory Training in ADHD: A Randomized Controlled Trial](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3790857/) [research]
50. [Computerized cognitive training in ADHD: meta-analysis of RCTs with blinded and objective outcomes](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10208955/) [research]
51. [Efficacy of Cogmed working memory training in school-age children: a meta-analysis](https://pubmed.ncbi.nlm.nih.gov/34085876/) [research]
