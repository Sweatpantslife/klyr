---
title: "Working Memory, Prospective Memory, and Out of Sight, Out of Mind"
area: foundations
file: research/foundations/memory-and-object-permanence.md
tags: [working-memory, prospective-memory, object-permanence, capture, reminders, cue-dependence, doorway-effect, external-memory]
related:
  - research/foundations/executive-function.md
  - research/foundations/time-perception.md
  - research/daily-life/task-initiation-and-paralysis.md
  - research/strategies/evidence-based-strategies.md
  - research/product/ux-design-for-adhd.md
sources: 39
updated: 2026-07-25
summary: >
  How ADHD affects working memory (holding a thought) and prospective memory (remembering to
  act later), why memory is cue-dependent, what the community means by "object permanence,"
  and what reminder science says about timing, context, and snoozing. Read this before
  designing capture, reminders, resurfacing, or anything that assumes the user will remember.
---

# Working Memory, Prospective Memory, and Out of Sight, Out of Mind

## TL;DR

- **Working memory** — the mental scratchpad that holds and manipulates information over seconds — is one of the most consistently impaired functions in ADHD: moderate group deficits in adults (d ≈ 0.5), larger central-executive and visuospatial deficits in children (d up to ~1.06). Not universal: an estimated 62–85% of children with ADHD show measurable WM deficits.
- Daily consequences: losing the thread mid-task, forgetting multi-step instructions by step two, being unable to juggle a plan mentally. It is a failure of **performance in the moment**, not of knowledge or ability.
- **Prospective memory** ("remembering to remember") splits into event-based, time-based, and activity-based intentions. Time-based ("at 5pm") is the most reliably impaired in ADHD; event-based ("when I see the mailbox") is relatively spared — but fails when the cue is non-salient or working memory is loaded.
- In the best adult component study, **planning** was the broken step (d = 1.60), while plan retention and execution were largely intact — people with ADHD execute well once a concrete plan exists.
- Memory is **cue-dependent**: intentions fire when the retrieval context matches encoding. Walking through a doorway (an "event boundary") measurably purges working memory — the doorway effect.
- The community term **"object permanence issues"** is not literal Piagetian object permanence; the real mechanism is cue-dependent attention and memory. It still encodes real UX truth: piles are rational external memory, putting things away feels like deleting them, and produce dies in the crisper drawer.
- Uncaptured thoughts evaporate in seconds. Capture must be near-instant, from anywhere, with zero required decisions.
- The GTD insight: the mind releases an open loop only when it **trusts** the external system to bring it back. One dropped item can collapse that trust. And for ADHDers, "remember to check the app" is itself a prospective-memory task — so the system must push, not wait to be pulled.
- Reminder science: prompts work at the **point of performance** (right time, right place, actionable now), tied to context/location cues, phrased as specific next actions. Snoozed usually means lost; identical repeated alerts habituate fast (clinicians override 49–96% of clinical alerts).
- Klyr's job in one sentence: be an external working memory and prospective-memory prosthesis — sub-3-second capture, aggressive but forgiving resurfacing, visual persistence of what matters, context-attached reminders, and a guarantee that nothing is ever silently lost.

## Working memory: the leaky scratchpad

**Working memory (WM)** is the limited-capacity system that temporarily holds and *manipulates* information to guide behavior over seconds — in Baddeley's standard model, a domain-general **central executive** plus two storage subsystems, the **phonological loop** (verbal) and **visuospatial sketchpad**. It is what lets you keep a phone number in mind while finding a pen, hold the reason you walked into the kitchen, or track where you are in a five-step recipe. In both Barkley's and Brown's models it is a core executive function (see [executive-function.md](executive-function.md)).

### What the evidence actually shows

WM impairment in ADHD is among the best-replicated cognitive findings, but the sizes matter for design:

| Measure | Children/adolescents (Martinussen et al. 2005 meta-analysis) | Adults (Alderson et al. 2013 meta-analysis, 38 studies) |
|---|---|---|
| Verbal WM | storage d ≈ 0.47; central executive d ≈ 0.43 | d ≈ 0.55 |
| Visuospatial WM | storage d ≈ 0.85; central executive d ≈ 1.06 | d ≈ 0.49 |

(Cohen's d anchors: 0.2 small, 0.5 medium, 0.8 large.) Three nuances:

1. **In children, visuospatial and central-executive demands hurt most**; verbal deficits are smaller. In adults the two domains converge to moderate. Russell Barkley has similarly suggested (in ADDitude) that nonverbal/visual working memory is the relatively weaker channel in ADHD — directionally consistent with the child data, though the adult meta-analysis found roughly equal moderate deficits.
2. **Deficits are common, not universal.** Kofler and colleagues' heterogeneity work estimates 62–85% of children with ADHD have measurable WM deficits (versus 21–46% for inhibitory control). A meaningful minority of users will have decent WM — design for the failure mode without assuming it in everyone.
3. **The "working" part breaks more than the "memory" part.** Kofler, Rapport and colleagues argue central-executive deficits (updating, dual-processing, reordering) are functionally linked to observed inattentive behavior itself — attention drifts *when the scratchpad overflows* — and WM deficits predict real-world organizational-skills problems. Their latent-variable work puts numbers on this asymmetry: **very large central-executive impairments (d ≈ 1.6–2.0), present in roughly 75–81% of children with ADHD, while phonological short-term *storage* is often intact** (Kofler et al. 2020, bifactor modeling) — juggling fails before holding does.

### How it shows up in daily life

- **Losing the thread mid-task**: start the laundry, notice a cup, carry it to the kitchen, see the dishwasher, start unloading — the laundry is gone from awareness (not chosen against; *gone*).
- **Forgetting instructions**: a three-part verbal request ("grab the folder, sign page 2, scan it to Ana") loses parts two and three by the time part one starts.
- **Failing to mentally juggle a plan**: reordering the day in your head when a meeting moves ("so if gym moves to 6, then dinner…") exceeds the scratchpad; the whole plan collapses into "I'll figure it out later."
- **Mid-sentence evaporation**: knowing the point you were making and losing it mid-sentence — the classic "wait, what was I saying?"
- Clinicians emphasize this is **performance, not ability**: the knowledge exists and resurfaces minutes later; it was simply not accessible at the moment of need (Focused Mind ADHD Counseling; Barkley's broader "point of performance" framing).

### Remediation fails; compensation works

WM "brain training" (e.g., Cogmed) shows near-transfer to trained tasks but **no convincing far transfer** to symptoms, academics, or daily function — in an RCT with 67 children with ADHD there were no symptom changes at home or school, and the Melby-Lervåg/Redick/Hulme meta-analytic review found no reliable far-transfer improvements. The evidence-backed alternative is **externalization**: put the information in the world, at the place and time it is needed (Barkley's *point of performance* — sticky notes, signs, timers, lists in the problem setting). Klyr's entire premise sits on this finding: don't train the scratchpad, *be* the scratchpad. (Full intervention grading lives in [../strategies/evidence-based-strategies.md](../strategies/evidence-based-strategies.md).)

## Prospective memory: remembering to remember

**Prospective memory (PM)** is memory for delayed intentions — not "what was the thing?" (retrospective) but "do the thing later, unprompted." Everyday life is saturated with it: take meds, reply after the meeting, move the laundry, pay rent. Clinician Petra Hoggarth's summary is apt: PM failure is neurological, "not about caring or intelligence" — which matters because PM failures are exactly the ones that read socially as not caring (forgotten birthdays, unanswered texts; see [emotional-regulation-and-rsd.md](emotional-regulation-and-rsd.md)).

Two distinctions sharpen the picture. Every PM act has a **prospective component** (noticing *that* something is due — the flag popping up) and a **retrospective component** (recalling *what* it was). ADHD failures are overwhelmingly prospective: the moment passes flagless, and the content surfaces hours late, fully intact ("I *knew* I had to send it — I just didn't think of it *then*"). PM also fails in reverse via **output-monitoring** lapses — not remembering whether you already did the thing — which drive double-taken meds, re-sent emails, and anxious re-checking ("did I actually lock the door?"): the action ran on autopilot and left no retrievable trace (examples per Talkiatry's psychiatrist-authored overview).

### Three kinds of intention, three failure profiles

| Intention type | Trigger | Everyday example | Status in ADHD |
|---|---|---|---|
| **Event-based** | An external cue appears | "When I see Sam, return his charger" | Relatively strongest. Findings historically inconsistent (Talbot & Kerns review); deficits emerge when the cue is peripheral/non-salient or WM load is high |
| **Time-based** | A clock time or elapsed interval | "Meds at 8:00"; "check the oven in 20 min" | Most reliably impaired; requires self-initiated time monitoring, which ADHD undermines (see [time-perception.md](time-perception.md)) |
| **Activity-based** | Finishing/starting another activity | "After breakfast, pack the gym bag" | Little direct ADHD research; task transitions are known vulnerable moments, so treat as fragile |

The cleanest adult demonstration: Altgassen, Kretschmer & Kliegel (2014) had 25 adults with ADHD and 25 controls do the Dresden Breakfast Task (prepare a virtual breakfast under rules and time constraints). Groups did **not differ on event-based PM**, but the ADHD group showed a **large impairment in time-based PM** — the tasks with no external cue, where you must self-generate clock checks. In children, time-based PM difficulty correlates with poorer time perception and less efficient clock-checking strategies — a 2025 naturalistic virtual-reality study found the failure is not checking the clock *less* but checking it **less strategically** (failing to ramp up checks as the deadline nears), with strategic time-monitoring explaining ~22% of time-based PM variance. A 2021 study also produced *event-based* deficits by raising the load — four target cues instead of one, or cues in peripheral locations — and, strikingly, **reward eliminated the group difference** (motivation interacts with memory; see [dopamine-and-motivation.md](dopamine-and-motivation.md) and note for the gamification doc).

### Planning, not retention, is the broken step

Fuermaier et al. (2013, PLOS ONE) decomposed complex PM in 45 unmedicated adults with ADHD vs 45 controls: **task planning was severely impaired (d = 1.60)** — plans were less elaborate — while **plan retention after 40 minutes (~87% in both groups), self-initiation, and execution fidelity were largely intact**. Their clinical recommendation: invest effort in elaborate, careful planning of delayed intentions; once the plan is concrete, people with ADHD carry it out reliably. For a task app this is close to a product spec: the highest-leverage moment is *when the intention enters the system* — turn "dentist" into "call Dr. Reyes at lunch tomorrow, number attached" and downstream execution takes care of itself far more often.

### PM failures cascade into procrastination

Altgassen, Scheres & Edel (2019) found adults with ADHD recalled and executed fewer of their own real-life intentions, and everyday PM performance **partially mediated the link between ADHD symptoms and procrastination**. Some of what looks like avoidance is simply intentions never resurfacing at an actionable moment (the rest of the initiation story lives in [../daily-life/task-initiation-and-paralysis.md](../daily-life/task-initiation-and-paralysis.md)).

## Cue dependence: memory fires where it was loaded

### Context-dependent recall

Memory retrieval is **cue-dependent**: what comes back to mind depends on the match between current context and encoding context. The classic Godden & Baddeley (1975) diver study — word lists learned underwater recalled best underwater, land-learned best on land — generalizes: Smith & Vela's (2001) meta-analysis found environmental context effects are reliable though modest, stronger for free recall than recognition, and weaker when other salient cues dominate or people mentally reinstate the original context. Kvavilashvili & Fisher's naturalistic work adds that real-world intentions mostly resurface via **incidental cues and spontaneous retrievals** — and the more often an intention spontaneously resurfaces, the likelier it gets done.

The ADHD-relevant consequence: **an intention formed in one context tends not to fire in another.** "I'll email the plumber" formed in bed at midnight is nowhere present at 10am at a work desk. Neurotypical brains partially bridge such gaps with self-directed rehearsal; weak WM plus distractibility make the bridge unreliable in ADHD. Intentions need to be *deliberately bound* to cues that will actually occur.

### The doorway effect

Radvansky and colleagues' **location updating effect**: walking through a doorway — even in virtual environments, even *imagined* — measurably worsens memory for what you were just carrying/thinking, relative to walking the same distance within a room. The **Event Horizon Model** explanation: a doorway is an **event boundary**; the brain closes one event model and opens another, flushing now-"irrelevant" working-memory contents (Pettijohn & Radvansky 2016). Honest caveats: the effect is small in absolute terms, and at least one multimodal investigation ("Doorways do not always cause forgetting," 2021) found it is not unconditional — it appears most reliably when memory is already under load. No study in this pass directly measured doorway effects in ADHD; the community's version ("the doorframe erased my thought") is extrapolation — but a plausible one, since ADHD means a smaller, faster-clearing scratchpad that is more often at load.

Design translation: **transitions are where things die** — room changes, app switches, tab switches, interruptions. Anything Klyr can do to persist state across boundaries ("you were doing X") replaces what the brain flushes.

### Implementation intentions: engineering the cue

**Implementation intentions** — pre-deciding "if [specific situation], then I will [specific action]" — are among the best-evidenced cognitive strategies in psychology: d = 0.65 for goal attainment across 94 studies (Gollwitzer & Sheeran 2006), with meta-analytic support specifically for improving prospective memory (Chen et al. 2015), including under high attentional demands, and everyday-life smartphone studies showing if-then plans speed responses to real-world PM targets (Zuber et al.). The active ingredient is **cue specificity**: naming the exact situational trigger makes the cue itself grab attention and fire the action semi-automatically, offloading the need for deliberate monitoring. This is the scientific backbone for context-attached reminders: "when I get home, put meds by the kettle" beats "remember meds" by a wide margin. (Effectiveness in ADHD populations specifically is less studied — evidence: promising, not yet definitive; see the strategies doc.)

## "Object permanence": out of sight, out of mind

### What the community term really means

The ADHD community widely says "I have no object permanence": unseen things stop existing. **Status: community metaphor, not clinical fact.** Literal **object permanence** is Piaget's infant milestone — knowing hidden objects still exist — developed in the first year of life (classic accounts: ~8–9 months) and fully intact in people with ADHD. What is actually happening, per Inflow, Simply Psychology, and others: ADHDers *know* the item/person/task exists; they just **fail to maintain an active representation of it in awareness without a cue** — cue-dependent attention plus weak working memory. One psychiatrist's refinement (John Kruse, via Inflow): sometimes it's "**in sight, but no insight**" — the item is visible but has habituated into the background. Klyr copy should never claim ADHDers "lack object permanence" (it is infantilizing and wrong) but must absolutely design for the phenomenon the term names — the doc uses the term because users search for it and self-describe with it.

### How it plays out

- **Produce dies in the crisper drawer.** The opaque drawer is where vegetables go to be forgotten; therapist KC Davis notes "that type of forgetfulness — issues with working memory and the need to be visually cued — can be common among neurodivergent folks," and recommends storing produce at eye level and demoting condiments to drawers.
- **Meds inside cabinets don't get taken; bills filed away don't get paid; a text opened and mentally answered is never actually answered.** The item's disappearance from view *is* its disappearance from the task queue.
- **Relationships**: friends not seen stop being thought of — not less loved, just uncued (common r/ADHD theme; belongs mostly in [../daily-life/daily-life-impact.md](../daily-life/daily-life-impact.md)).

### Piles as external memory — and the fear of putting things away

**Doom piles** (community term for accumulations of miscellaneous stuff too daunting to sort) are best understood as a *rational compensation strategy*: the pile on the counter is a physical to-do list. Putting things away "properly" feels dangerous because **filing is functionally deleting** — if it's in a drawer, it's gone. Community and clinical sources (Life Skills Advocate, Psychology Today's "Mythbusting ADHD") converge on the same loop: visible = remembered, so everything stays visible, until *everything* is visible and competes for attention, at which point habituation sets in and the pile becomes invisible anyway — plus a source of shame. Recommended physical-world mitigations preserve visibility while reducing chaos: clear bins, open shelving, one designated visible surface for active items.

This is the single most important tension for Klyr to hold: **users need visual persistence AND visual persistence decays.** A digital system can do what a countertop cannot — keep everything, but *rotate what is currently visible*.

## Idea volatility and the capture problem

Thoughts in ADHD evaporate on a timescale of seconds — an idea in the shower, a "must reply to that" while driving, a brilliant fix mid-meeting. The mechanism is ordinary WM decay plus interference, amplified: smaller effective capacity, faster displacement by the next stimulus, and event boundaries (that doorway) flushing the buffer. Community guidance is unanimous and blunt: **capture immediately or lose it** — notepads in every room, voice memos, "write it down before you take a single step" (Focused Mind; ADDitude's externalization advice; ubiquitous r/ADHD folklore).

Every step between thought and stored capture is a drop point: unlock phone → find app → open it → choose a list → type a title → pick a project → save is six opportunities for the thought to vanish or a distraction to hijack. This is why the assignment's **sub-3-second capture** target is not a nicety but the difference between a captured and an uncaptured thought.

### The trusted system — and how trust collapses

David Allen's GTD (see [../strategies/planning-methodologies-and-adhd.md](../strategies/planning-methodologies-and-adhd.md)) is built on one psychological claim: the mind keeps rehearsing **open loops** (uncaptured commitments — the Zeigarnik effect, the classic 1927 observation that interrupted tasks stay mentally active) until they are captured in a system the mind **trusts** to resurface them at the right time. Masicampo & Baumeister's "Consider it done!" studies (2011) sharpened the mechanism: unfulfilled goals intrude on unrelated thinking until a *specific plan* exists — then the intrusions stop, even though the task is still undone. Capture-plus-plan buys quiet. (Caveat: the original Zeigarnik memory advantage replicates inconsistently in modern work; treat it as a directional insight about intrusive open loops, not a precise law. ADHD-specific caveat, from community observation and the PM evidence above: ADHD open loops don't nag reliably at *actionable* moments — they surface at 2am or not at all — so the untrusted-system tax is paid mostly in diffuse anxiety rather than timely recall.) Trust is the load-bearing word: *write items into a notebook you never reopen and the brain learns this quickly and resumes nagging* — or worse, stops nagging and the item is simply lost.

For ADHD users the trust bar is higher and the failure mode sharper, because **checking the system is itself a prospective-memory task**. The canonical ADHD app-death spiral: install app → capture diligently → forget the app exists (out of sight, out of mind applies to apps too) → discover three weeks later a graveyard of stale items → feel shame → abandon. After the first consequential dropped item ("the app had it and I still missed it"), the brain quietly reclassifies the system as untrustworthy and reverts to anxiety, rehearsal, and piles. Therefore: a trustworthy system for ADHD cannot be a passive repository that waits to be pulled — **it must push**, and its pushes must reliably arrive.

## Reminder science: timing, context, specificity — and the snooze trap

**Point of performance.** Barkley's principle: assistance works when placed *where and when the behavior must occur*, not upstream of it. A reminder is a prompt, not a memory-transfer: "dentist at 3" delivered at 11am is an instruction to *remember for four more hours* — i.e., a new prospective-memory task assigned to the exact system that is impaired. Reminders should fire when the action is possible *now*, or they should create a visible persistent trace rather than a transient ping.

**Context and location triggers.** Because retrieval is cue-driven, reminders bound to real contexts outperform bare times: the Place-Its study (UbiComp 2005) found location-triggered phone reminders useful precisely because *people already use location as a memory cue*; smartphone-based PM aids improve prospective-memory performance in cognitively impaired populations. "When you get home," "when you leave the office," "when this meeting ends," "next time you open the banking app" are the digital equivalents of implementation-intention cues.

**Specificity.** A reminder that names the concrete next action ("call Dr. Reyes — number attached — say you need a cleaning") outperforms a label ("dentist!") because it removes the WM work of reconstructing what the reminder even meant — a reconstruction that frequently fails ("what did I mean by 'Tuesday thing'?").

**Snoozed usually means lost.** Status: product/community wisdom, strongly convergent with habituation research. Mechanisms: (1) a snooze re-fires at an arbitrary time no more actionable than the first; (2) each identical re-alert is a training trial in ignoring it — in clinical systems, 49–96% of interruptive alerts are overridden and 55% of physicians admit dismissing alerts without reading (alert fatigue); the same **notification habituation/banner blindness** dynamics are documented in consumer UX (LogRocket); (3) a swiped-away notification leaves no persistent trace — one swipe from oblivion (TidBITS's case for persistent alarms). Effective patterns from reminder-product practice: persistence until acknowledged for the few things that truly matter, escalation/form-change instead of identical repetition, and multi-channel delivery — always balanced against the fatigue those same mechanisms cause when overused (notification ethics belong to [../product/ux-design-for-adhd.md](../product/ux-design-for-adhd.md)).

## Design implications for Klyr

1. **Klyr must offer sub-3-second, zero-decision capture from anywhere** — lock screen, widget, share sheet, voice — with no required fields (no project, no date, no category at capture time). Rationale: ideas evaporate in seconds; every additional tap or decision is a drop point (idea volatility; WM decay).
2. **Klyr must never silently lose anything.** No auto-archive without a visible trace, no expiring items, no captures that vanish into unsearchable states; "show me everything I ever captured" must always work. Rationale: system trust collapses after the first dropped item, and trust is what lets the user's mind release open loops (GTD; Zeigarnik framing).
3. **Klyr should be push-first: an aggressive resurfacing engine, not a passive list.** Assume the user will *not* remember to open the app — checking the system is itself a prospective-memory task. Stale items should be proactively resurfaced ("still want this?") rather than left to rot into a shame graveyard.
4. **Klyr should attach reminders to contexts, not just clocks**: locations ("when I get home"), transitions ("after this calendar event ends"), other tasks ("after standup"), app/device events. Rationale: event-based PM is relatively spared in ADHD while time-based is most impaired (Altgassen 2014); implementation-intention cue-binding carries d ≈ 0.65 evidence.
5. **When a user sets a time-based reminder, Klyr should offer to convert it into an event/context anchor** ("5pm — is that 'when you close your laptop'?"). Rationale: same evidence as #4; translate the weakest PM channel into the strongest one.
6. **Reminders must fire at the point of performance and be actionable at receipt** — including the phone number to call, the link to open, the exact next physical action. A reminder that arrives hours early or requires reconstruction ("what did I mean?") delegates remembering back to the impaired system (Barkley; specificity evidence).
7. **Klyr should rebuild snooze as "re-anchor": snoozing must attach the item to a new meaningful cue** (a context, an event, a chosen moment), never a bare +10 minutes default; repeatedly deferred items should change form (different wording, channel, or a "want to shrink this task?" offer) instead of repeating identically. Rationale: identical re-alerts habituate (49–96% override rates in clinical alerting); snoozed-means-lost.
8. **Klyr should provide a small, persistent visual surface — a rotating "counter top" of 1–3 current items** (widget/today view), deliberately cycling what it shows. Rationale: users need visual persistence (piles as external memory) but static displays habituate ("in sight, but no insight"); rotation fights both.
9. **Klyr should support digital "doom pile" semantics: a guilt-free holding pen that is visible, browsable, and periodically resurfaced** — explicitly not an "inbox zero" debt. Rationale: piles are rational external memory; the failure is invisibility and shame, not the pile itself.
10. **At capture-to-plan time, Klyr should do the planning WITH the user**: prompt for when/where/first-step, prefill defaults, attach the cue — because planning is the impaired component (d = 1.60) while retention and execution are comparatively intact (Fuermaier 2013). One elaboration question at the right moment is worth ten reminders later.
11. **Klyr should persist "where was I" state across every boundary**: one-tap park-and-resume on task switch, automatic breadcrumbs ("you were mid-way through X, next step was Y") on return. Rationale: event boundaries flush working memory (doorway effect); interruptions and app-switches are where threads die (see [attention-and-hyperfocus.md](attention-and-hyperfocus.md)).
12. **Klyr must keep any single screen's WM demand near zero**: never require remembering information from a previous screen, always show the task's context inline, confirm captures visibly. Rationale: moderate-to-large WM deficits, central-executive overload expressed as inattention (Kofler); details in the UX doc.
13. **Klyr must not ship WM "brain training" or imply memory can be fixed by exercises.** Evidence shows no far transfer to symptoms or daily function. Klyr is a prosthesis, not a gym — and copy should frame externalization as the smart strategy, not a crutch (non-pathologizing framing; performance-not-ability).
14. **Tension to manage: resurfacing aggressiveness vs. habituation and shame.** Every ignored notification trains ignoring; every "you still haven't…" risks shame (see [emotional-regulation-and-rsd.md](emotional-regulation-and-rsd.md)). Klyr should budget notifications ruthlessly (few, high-value, forgiving in tone), vary their form, and treat a user ignoring three consecutive resurfacings as signal to change strategy, not volume.
15. **Klyr should exploit motivation as a memory amplifier, carefully**: reward eliminated the event-based PM gap in children with ADHD in lab conditions — making resurfaced items feel rewarding to act on (novelty, quick wins) is mechanistically justified, but red lines live in [../strategies/motivation-and-gamification.md](../strategies/motivation-and-gamification.md).

## Open questions

- **Resurfacing cadence**: how often can Klyr resurface a stale item before habituation or annoyance? No direct research found; needs A/B testing with real ADHD users (measure: action rate per resurfacing, mute/uninstall rates).
- **Doorway/event-boundary effects in ADHD specifically**: plausible amplification, no direct studies found in this pass. Low design risk (persisting state helps everyone), but worth watching the literature.
- **Activity-based intentions in ADHD** ("after X, do Y") are nearly unstudied; Klyr's task-chaining features will effectively be original research — instrument them.
- **Trust repair**: after Klyr inevitably fails a user once (missed notification, OS-killed alarm), what rebuilds trust — transparency ("here's what happened"), redundancy, apology UX? Untested.
- **How many persistent visual items before blindness?** The 1–3 figure in implication #8 is a design hypothesis from attention/habituation principles, not a measured threshold.
- **Location-based triggers in practice**: geofencing is battery-hungry, imprecise, and privacy-sensitive; do ADHD users accept and keep them enabled? Place-Its is 2005-era; modern validation needed.
- **Individual calibration**: given 62–85% (not 100%) prevalence of WM deficits, should Klyr detect (via behavior, not tests) how much memory scaffolding each user needs and titrate?

## Sources

1. [Martinussen et al. (2005), A Meta-Analysis of Working Memory Impairments in Children With ADHD, JAACAP](https://www.jaacap.org/article/S0890-8567(09)61489-1/abstract) [research]
2. [Alderson, Kasper, Hudec & Patros (2013), ADHD and working memory in adults: a meta-analytic review, Neuropsychology 27(3)](https://pubmed.ncbi.nlm.nih.gov/23688211/) [research]
3. [Kofler et al. (2019), Executive Functioning Heterogeneity in Pediatric ADHD, J Abnorm Child Psychol](https://link.springer.com/article/10.1007/s10802-018-0438-2) [research]
4. [Working memory and inhibitory control deficits in children with ADHD (2024), Frontiers in Psychiatry](https://www.frontiersin.org/journals/psychiatry/articles/10.3389/fpsyt.2024.1277583/full) [research]
5. [Kofler et al. (2010), ADHD and Working Memory: The Impact of Central Executive Deficits… on Observed Inattentive Behavior, J Abnorm Child Psychol](https://pubmed.ncbi.nlm.nih.gov/19787447/) [research]
6. [Kofler et al. (2018), Working memory and organizational skills problems in ADHD, JCPP](https://acamh.onlinelibrary.wiley.com/doi/abs/10.1111/jcpp.12773) [research]
7. [Altgassen, Kretschmer & Kliegel (2014), Task Dissociation in Prospective Memory Performance in Individuals With ADHD, Journal of Attention Disorders](https://journals.sagepub.com/doi/10.1177/1087054712445484) [research]
8. [Fuermaier et al. (2013), Complex Prospective Memory in Adults with ADHD, PLOS ONE](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0058338) [research]
9. [Altgassen, Scheres & Edel (2019), Prospective memory (partially) mediates the link between ADHD symptoms and procrastination, ADHD Atten Def Hyp Disord 11:59–71](https://pubmed.ncbi.nlm.nih.gov/30927231/) [research]
10. [Event-Based Prospective Memory Deficit in Children with ADHD: Underlying Cognitive Factors and Association with Symptoms (2021), Int J Environ Res Public Health](https://pmc.ncbi.nlm.nih.gov/articles/PMC8199111/) [research]
11. [Pettijohn & Radvansky (2016), Walking through doorways causes forgetting: event structure, QJEP](https://memorylab.nd.edu/assets/259392/pettijohn_radvansky_2016_quarterly_journal_of_experimental_psychology_.pdf) [research]
12. [Doorways do not always cause forgetting: a multimodal investigation (2021)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7938580/) [research]
13. [Smith & Vela (2001), Environmental context-dependent memory: A review and meta-analysis, Psychonomic Bulletin & Review](https://link.springer.com/article/10.3758/BF03196157) [research]
14. [The Godden and Baddeley (1975) experiment on context-dependent memory: a replication (2021)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8568063/) [research]
15. [Chen et al. (2015), The effect of implementation intention on prospective memory: a systematic and meta-analytic review, Psychiatry Research](https://www.sciencedirect.com/science/article/abs/pii/S0165178115000360) [research]
16. [Gollwitzer & Sheeran (2006), Implementation Intentions and Goal Achievement: A Meta-Analysis of Effects and Processes](https://www.researchgate.net/publication/37367696_Implementation_Intentions_and_Goal_Achievement_A_Meta-Analysis_of_Effects_and_Processes) [research]
17. [Implementation intentions facilitate prospective memory under high attention demands, Memory & Cognition 36:716](https://link.springer.com/article/10.3758/MC.36.4.716) [research]
18. [Melby-Lervåg, Redick & Hulme (2016), Working Memory Training Does Not Improve Performance on Measures of "Far Transfer", Perspectives on Psychological Science](https://journals.sagepub.com/doi/10.1177/1745691616635612) [research]
19. [Few Effects of Far Transfer of Working Memory Training in ADHD: A Randomized Controlled Trial (2013)](https://pmc.ncbi.nlm.nih.gov/articles/PMC3790857/) [research]
20. [Kvavilashvili & Fisher, discussed in Prospective Memory in Everyday Tasks (chapter)](https://www.researchgate.net/publication/273596781_Prospective_Memory_in_Everyday_Tasks) [research]
21. [Sohn et al. (2005), Place-Its: A Study of Location-Based Reminders on Mobile Phones, UbiComp](https://cseweb.ucsd.edu/~wgg/Abstracts/tsohn-placeits-ubicomp05-final.pdf) [research]
22. [Physicians' Perspectives on Prescription Alerts: A Journey Towards Reducing Fatigue (2025)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12307096/) [research]
23. [Barkley, The Important Role of Executive Functioning and Self-Regulation in ADHD (fact sheet)](https://www.russellbarkley.org/factsheets/ADHD_EF_and_SR.pdf) [clinical]
24. [ADDitude, Improving Your Working Memory: Executive Function and ADHD](https://www.additudemag.com/working-memory-powers-executive-function/) [clinical]
25. [Petra Hoggarth, Prospective Memory and ADHD: When "I'll Remember to Do That" Goes Wrong](https://www.petrahoggarth.co.nz/post/prospective-memory-and-adhd-when-i-ll-remember-to-do-that-goes-wrong) [clinical]
26. [Focused Mind ADHD Counseling, If I Don't Write It Down, It Won't Happen: Working Memory Problems in ADHD](https://focusedmindadhdcounseling.com/if-i-dont-write-it-down-it-wont-happen-working-memory-problems-in-adhd-explained/) [clinical]
27. [Psychology Today (Mythbusting ADHD), Is Your ADHD Making You a Doom Piler? (2023)](https://www.psychologytoday.com/us/blog/mythbusting-adhd/202306/is-your-adhd-making-you-a-doom-piler) [clinical]
28. [Inflow, Object permanence is NOT a symptom of ADHD](https://www.getinflow.io/post/object-permanence-constancy-adhd-symptom) [community]
29. [Simply Psychology, Object Permanence & ADHD: "Out of Sight, Out of Mind"](https://www.simplypsychology.org/object-permanence-and-adhd.html) [community]
30. [Vanderhacks (KC Davis), Don't store produce in your produce (drawer)](https://vanderhacks.substack.com/p/dont-store-produce-in-your-produce) [community]
31. [Life Skills Advocate, How To Clear DOOM Piles Without Losing Your Mind](https://lifeskillsadvocate.com/blog/doom-piles/) [community]
32. [Super Productivity, The Open Loop Problem: Why Your Brain Needs a GTD Inbox](https://super-productivity.com/blog/gtd-inbox-capture-system/) [product]
33. [TidBITS, A Call to Alarms: Why We Need Persistent Calendar and Reminder Notifications (2023)](https://tidbits.com/2023/05/11/a-call-to-alarms-why-we-need-persistent-calendar-and-reminder-notifications/) [product]
34. [LogRocket, Why users ignore notifications (and how to fix it)](https://blog.logrocket.com/ux-design/notification-blindness-ux-strategies/) [product]
35. [Kofler et al. (2020), Working memory and short-term memory deficits in ADHD: A bifactor modeling approach, Neuropsychology](https://psycnet.apa.org/record/2020-32863-001) [research]
36. [A naturalistic virtual reality task reveals difficulties in time-based prospective memory and strategic time-monitoring in children with ADHD (2025), Scientific Reports](https://www.nature.com/articles/s41598-025-08944-w) [research]
37. [Implementation intentions speed up young adults' responses to prospective memory targets in everyday life (Zuber et al.), PMC](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8765629/) [research]
38. [Talkiatry, Object Permanence & ADHD: A Psychiatrist Explains](https://www.talkiatry.com/blog/object-permanence-adhd) [clinical]
39. [Super Productivity, The Zeigarnik Effect: Definition, Examples & Research (summarizes Zeigarnik 1927; Masicampo & Baumeister 2011, "Consider it done!"; Syrek et al. 2017)](https://super-productivity.com/blog/zeigarnik-effect-productivity/) [product]
