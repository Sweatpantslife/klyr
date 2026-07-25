---
title: "Executive Summary: The Klyr Research Corpus in Ten Minutes"
area: root
file: research/00-executive-summary.md
tags: [executive-summary, synthesis, navigation, product-strategy]
related:
  - research/INDEX.md
  - research/GLOSSARY.md
  - research/product/design-principles.md
  - research/product/feature-directions.md
  - research/product/anti-patterns.md
  - research/product/app-landscape.md
sources: 0
updated: 2026-07-25
summary: >
  The whole corpus in under 2,000 words: what ADHD actually is, the seven mechanisms
  that break ordinary productivity tools, the levers with real evidence behind them,
  why the market keeps losing ADHD users, and the ten principles that bind Klyr.
---

# Executive Summary: The Corpus in Ten Minutes

## TL;DR

- ADHD is a **performance disorder, not a knowledge disorder**. Users already know what to do; the gap between knowing and doing *is* the condition. No app closes that gap with better advice — only with better architecture.
- Seven mechanisms break ordinary productivity tools for ADHD: the intention gap, reward-timing asymmetry, time blindness, leaky working and prospective memory, accumulated shame, initiation paralysis, and novelty decay.
- The levers with real evidence: externalize everything at the point of performance, make consequences immediate, shrink the start into an if-then plan, add human presence, build forgiveness into the structure, and reduce pressure automatically when capacity drops.
- The market's defining fact is abandonment — median 15-day retention for mental-health-adjacent apps is roughly 3.9% — and the death spot is always the same: miss a day, feel accused, never open the app again.
- Klyr's position: **the tool that expects you to disappear and makes coming back painless.** Its north star is return-after-lapse, not engagement.
- Twenty principles bind the product ([design-principles](product/design-principles.md)); the ten most load-bearing are below. A design that violates one is a defect, not a debate.

## 1. What Klyr is

Klyr is a life organizer — tasks, projects, routines, the whole load — built from the ground up for people with ADHD. "ADHD-first" is not a friendly color palette bolted onto a normal task manager; it inverts the basic contract of productivity software. Every mainstream tool assumes the user will maintain the system, and this corpus shows, mechanism by mechanism, that maintenance is exactly what ADHD makes expensive — so Klyr maintains the system, and the user gets their life back. It is designed for the user's worst week, because that is the week that decides whether the tool survives.

## 2. What ADHD actually is

ADHD is a neurodevelopmental condition of **self-regulation**, not a shortage of attention, effort, or character. Attention gets allocated — often intensely — just not reliably to what the person intended; dopamine signaling is dysregulated, not absent; emotions arrive at full strength while the executive brake that moderates them runs weak. The most useful framing for builders is Russell Barkley's: ADHD is a disorder **of performance, not knowledge** — a gap between what someone knows to do and what they can execute at the moment it matters ([adhd-overview](foundations/adhd-overview.md)).

The scale and texture matter: about 3.1% of adults worldwide, 6% of US adults reporting a current diagnosis — over half of them diagnosed as adults — heritability around 74%, and comorbidity (anxiety, depression, sleep disorders) as the default rather than the exception. Capability fluctuates hour to hour and week to week. So the user is not someone who needs more information, more discipline, or a fresh start. They need the right cue, at the right moment, from a system that does not judge them between cues.

## 3. The mechanisms that break ordinary productivity tools

1. **The intention gap.** Executive functions are the self-directed actions people use to steer themselves toward goals; in Barkley's formulation, EF *is* self-regulation, and he informally calls ADHD "intention deficit disorder." A to-do list documents intentions — which makes it a record of the problem, not a solution to it. Deep dive: [executive-function](foundations/executive-function.md).

2. **Reward timing asymmetry.** ADHD brains under-respond while *anticipating* rewards and discount delayed payoffs steeply (meta-analytic d = 0.43), so distant importance is a weak force while immediacy, interest, and novelty are strong ones. Plans don't pull; ticking the box does. Tools that bet on "this matters, so you'll do it" lose that bet daily. Deep dive: [dopamine-and-motivation](foundations/dopamine-and-motivation.md).

3. **Time blindness.** Time collapses into **now** and **not-now**: a deadline is nearly weightless for weeks, then detonates in the final hours — panic is a late-arriving motivational signal, not a personality flaw. Timing deficits show up across every lab paradigm, so a tool that prints a date and assumes the user will feel it approaching is writing fiction. Deep dive: [time-perception](foundations/time-perception.md).

4. **A leaky scratchpad and a silent alarm.** Working memory drops the thread mid-task, and prospective memory — remembering to remember — fails worst for "at 5 pm" style intentions. Uncaptured thoughts evaporate in seconds, and "remember to check the app" is itself a prospective-memory task, which is why any tool that waits to be pulled has already failed. Deep dive: [memory-and-object-permanence](foundations/memory-and-object-permanence.md).

5. **Emotional load and shame.** Emotional dysregulation affects an estimated 34–70% of adults with ADHD, criticism sensitivity is among the most consistent findings in lived-experience research, and users arrive carrying decades of "you're not trying hard enough" (one back-of-envelope estimate: ~20,000 corrective messages by age 10). A red badge lands on all of that history at once: "You feel guilty every time you open it. So you stop opening it." Deep dive: [emotional-regulation-and-rsd](foundations/emotional-regulation-and-rsd.md).

6. **Initiation and paralysis.** Starting is the single point where executive, emotional, and reward systems fail *simultaneously* — once a task is underway it supplies its own stimulation, but the start is the expensive step, and one small analysis reported by Pychyl classified roughly 75% of adults with ADHD as chronic procrastinators versus ~35% of controls (unpublished student data — directional, not a validated prevalence estimate). Vague tasks are silent blockers, yet decomposition is itself an impaired executive function — "just break it down" outsources the hardest step to the person least equipped for it in that moment. Deep dive: [task-initiation-and-paralysis](daily-life/task-initiation-and-paralysis.md).

7. **Consistency, novelty decay, and the honeymoon cliff.** Novelty genuinely activates ADHD motivation — and reliably fades; habits automatize slowly for everyone (median ~66 days, not the mythical 21) and plausibly slower and less durably with ADHD. So every system works for two weeks, until one missed day meets all-or-nothing thinking and the *whole practice* dies: the system-collapse → shame → new-system cycle that fills the productivity graveyard. Deep dives: [habits-and-routines](daily-life/habits-and-routines.md), [planning-methodologies-and-adhd](strategies/planning-methodologies-and-adhd.md).

## 4. What demonstrably helps

- **Externalization at the point of performance.** Internal speech, felt time, and summoned motivation are weak sources of control in ADHD, so make them physical — visible sentences, visible time, visible state — delivered where and when the action happens, because help given at a Sunday planning session mostly does not transfer. In one RCT, externalizing time onto devices moved parent-rated daily time management by d = 1.0: you cannot train the sense of time, but you can hand someone a clock they can feel. See [executive-function](foundations/executive-function.md), [memory-and-object-permanence](foundations/memory-and-object-permanence.md), [time-perception](foundations/time-perception.md).
- **Immediacy.** Temporal Motivation Theory compresses the design space: Motivation = (Expectancy × Value) / (1 + Impulsiveness × Delay) — and the workable lever is the denominator. Acknowledge completion instantly and unconditionally, bundle a "should" with a "want" (temptation bundling raised gym attendance 29–51%), and shorten horizons instead of preaching importance. See [dopamine-and-motivation](foundations/dopamine-and-motivation.md), [motivation-and-gamification](strategies/motivation-and-gamification.md).
- **Shrinking the start into an if-then plan.** Implementation intentions ("when X happens, I do Y") carry meta-analytic d = 0.65 and replicate in ADHD samples; in the best adult study, *planning* was the broken step (d = 1.60) while execution was largely intact. Hand the user a tiny, concrete, already-decided first step and ADHD brains finish disproportionately well. See [evidence-based-strategies](strategies/evidence-based-strategies.md), [task-initiation-and-paralysis](daily-life/task-initiation-and-paralysis.md).
- **Body doubling.** Working alongside another person — silent, virtual, even ambient — is the community's most-loved starter: 85% of 220 neurodivergent adults surveyed said presence makes completion likelier. No controlled trials yet; the mechanism (social presence, co-regulation) is plausible, and saying exactly that is part of Klyr's voice. See [evidence-based-strategies](strategies/evidence-based-strategies.md).
- **Forgiving systems.** The load-bearing skill is *resuming*, not maintaining: auto-schedulers' most-loved feature is guilt-free rescheduling, and the bullet journal's quiet genius is a blank page that absorbs absence without judgment. Forgiveness is not softness — it is the difference between a lapse and an ending. See [habits-and-routines](daily-life/habits-and-routines.md), [planning-methodologies-and-adhd](strategies/planning-methodologies-and-adhd.md).
- **Knowing when to back off.** Comorbid anxiety and depression are the norm and boom-bust cycles are the documented rhythm of ADHD life, so capacity collapse is a scheduled event, not an edge case. Software cannot reliably tell a depressive shutdown from a busy week — so the rule is asymmetric: reduce pressure automatically and freely; never label, diagnose, or escalate uninvited. See [when-to-back-off](product/when-to-back-off.md).

## 5. Why existing apps fail ADHD users

The community has already written the post-mortem, and it is always the same one: *"find new system, get excited, customize obsessively, use it perfectly for 10 days, miss one day, feel guilty, avoid it, never open it again."* Almost nothing on the market designs for the "miss one day" step — the single highest-leverage moment in the entire lifecycle. The rest of the market's failures are that sentence wearing different interfaces: Todoist's red overdue pile makes opening the app the shame trigger; Notion's infinite flexibility becomes a template graveyard of maintenance debt; Habitica and Forest punish; Sunsama's daily ritual becomes one more chore; trials convert silently and cancellation hides. Median 15-day retention for mental-health-adjacent apps is ~3.9%, with more than 80% of users gone within ten days — and ADHD users churn *additionally by design*, because novelty decay is a feature of ADHD motivation, not a bug in the user. Each tool solves one mechanism, so users run stacks of three to five apps; ADHD-native apps are mostly day planners without project depth, while the power tools are shame machines without ADHD affordances. The middle — a full life organizer that survives neglect — is open, and it is Klyr's lane: optimize for returns after lapse, never for streaks or DAU. Deep dives: [app-landscape](product/app-landscape.md), [anti-patterns](product/anti-patterns.md).

## 6. The ten commandments for Klyr

Distilled from the twenty-principle design constitution ([design-principles](product/design-principles.md)), in its own priority order. A mockup, feature, experiment, or sentence of copy that violates one is a defect, not a debate.

1. **Be the prosthesis.** Klyr *is* the executive function — a permanent scaffold, never a training program the user graduates from.
2. **Land at the point of performance.** Help arrives where and when the action happens, never only at planning time.
3. **Capture is sacred.** Under three seconds, zero required decisions, from anywhere — before any account wall.
4. **Nothing is silently lost.** Every automatic change leaves a visible, reversible trace; full export is always one tap away.
5. **Shame-free by architecture.** Failure is never rendered as arithmetic — no overdue counts, no red badges — and aging items get amnesty by default.
6. **The comeback is the core loop.** Every return, after an hour or a month, lands on a calm, current state with zero make-up work.
7. **Survive neglect.** Two weeks of silence must leave Klyr correct, calm, and trustworthy.
8. **Everything decomposes to a startable step.** And Klyr does the decomposing, not the user.
9. **Time is made physical.** Duration renders as space, the app holds the schedule, and no default assumes the user can feel time.
10. **Motivation invites; it never coerces.** Reward, celebrate, vary the delight — never punish, pressure, or take hostages.

The second ten bind just as hard: build for month three when the novelty is gone, treat capacity as weather rather than character, treat everything stored as health data, judge the product by real-world function rather than engagement, and never claim more than the evidence carries — a tool, never a treatment. The [anti-patterns](product/anti-patterns.md) catalog turns these principles into 24 specific bans with severity rulings, and [feature-directions](product/feature-directions.md) turns them into 45 evidence-graded, buildable directions.

## 7. Where to go deeper

Start at [INDEX](INDEX.md), which routes any question or task to the right deep-dive docs, and keep the [GLOSSARY](GLOSSARY.md) beside you — every term above is defined there with an honest tag for how solid its science is.
