---
title: "Klyr Anti-Patterns: The Binding Never-Do-This Catalog"
area: product
file: research/product/anti-patterns.md
tags: [anti-patterns, synthesis, dark-patterns, shame, streaks, gamification, notifications, onboarding, pricing, data-ethics, maintenance-burden]
related:
  - research/product/design-principles.md
  - research/product/app-landscape.md
  - research/product/ux-design-for-adhd.md
  - research/strategies/motivation-and-gamification.md
  - research/strategies/planning-methodologies-and-adhd.md
  - research/daily-life/habits-and-routines.md
  - research/foundations/emotional-regulation-and-rsd.md
  - research/foundations/dopamine-and-motivation.md
  - research/product/privacy-and-data-ethics.md
  - research/product/when-to-back-off.md
  - research/product/outcomes-and-measurement.md
sources: 0
updated: 2026-07-25
summary: >
  The binding catalog of 24 anti-patterns for Klyr, each with real-market examples, the
  ADHD-specific harm mechanism, the specified alternative, and a severity ruling
  (BANNED / AVOID-BY-DEFAULT / HANDLE-WITH-CARE). Consult at every design, copy, pricing,
  and experiment review, alongside design-principles.md.
---

# Klyr Anti-Patterns: The Binding Never-Do-This Catalog

[design-principles](design-principles.md) says what Klyr is; this catalog says what must never appear in it. Every entry is a pattern that shipping products actually use — most of them successfully, on neurotypical users — that the corpus shows to be specifically harmful to people with ADHD. Evidence lives in the linked docs; this doc carries no sources of its own.

## TL;DR

- **24 anti-patterns, three severities, binding on product, copy, pricing, marketing, and experiments.** A mockup, notification, or A/B arm containing a BANNED pattern is a defect, not a debate — the same contract as the design constitution ([design-principles](design-principles.md)).
- **The unifying mechanism:** every entry monetizes or triggers a documented ADHD vulnerability — shame reactivity and rejection sensitivity ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)), loss aversion plus guaranteed lapses ([habits-and-routines](../daily-life/habits-and-routines.md)), impulsivity and steep delay discounting ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)), prospective-memory failure ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)), and the high cost of maintenance work ([executive-function](../foundations/executive-function.md)).
- **The market has already run the experiments.** Todoist's red overdue pile, Habitica's HP loss, Duolingo's streak economy, Notion's template graveyard, Opal's trial ambush, and Sunsama's daily ritual are each a documented abandonment engine in [app-landscape](app-landscape.md); this catalog names the pattern behind each body.
- **The largest cluster is shame surfaces** — overdue arithmetic, streak hostage-taking, punishment mechanics, guilt copy, all-or-nothing day verdicts. All BANNED: users arrive pre-shamed, and a tool that renders failure as numbers becomes the shame trigger itself ("you feel guilty every time you open it, so you stop opening it").
- **Mechanic and framing are judged separately.** Streaks, urgency, social presence, and customization are not intrinsically toxic; their loss-framed, imposed, public, or bottomless variants are. Where the distinction matters, the entry draws it explicitly (AP-2 vs. AP-3; AP-8 vs. AP-9).
- **The money red lines are also the differentiator:** trial ambushes, hard-to-cancel subscriptions, data hostage, and paid randomness monetize the ADHD tax — and billing betrayal is a top 1-star theme across the category, so the ethical stance is a commercial position, not just a moral one ([app-landscape](app-landscape.md), [ux-design-for-adhd](ux-design-for-adhd.md)).
- **Structural bans protect the system from needing discipline:** setup before value, blank-canvas first runs, weekly-review dependencies, and buried capture all make the product's correctness depend on the user's executive function — the exact resource Klyr exists to replace.
- **Data and truth bans are absolute:** silent data loss, uninvited mental-state inference, improvement promises, and third-party trackers each break a contract (external memory, dignity, calibrated claims, health-data handling) that cannot be un-broken.
- **Severity rounds up.** When a proposal sits between two levels, apply the stricter one; the corpus's standing bias is toward the calm, forgiving, autonomy-preserving option ([design-principles](design-principles.md)).

## How this catalog binds

| Severity | Meaning | How it can ship |
|---|---|---|
| **BANNED** | Never ship — in any surface, tier, experiment arm, or marketing asset. No A/B testing exceptions: experimenting with shame or pressure on this population is itself prohibited ([outcomes-and-measurement](outcomes-and-measurement.md)). | It can't. The only amendment path is changing what the corpus says. |
| **AVOID-BY-DEFAULT** | Legitimately valuable for a self-selected minority, harmful as a default. | Only behind explicit, informed, per-feature user opt-in — off by default, framed honestly, reversible in one tap with no data loss — plus a written justification citing the corpus at design review. |
| **HANDLE-WITH-CARE** | The feature family is core or unavoidable, but its documented failure modes eject ADHD users. | Ship it with the entry's guardrails implemented; review against them explicitly. |

Entries reference the design principles (P1–P20) in [design-principles](design-principles.md); where an anti-pattern sits on a genuine tension between corpus docs, the entry names the tension and the adopted resolution rather than pretending the question is closed.

## The catalog at a glance

| ID | Anti-pattern | Severity | The rule in one line |
|---|---|---|---|
| AP-1 | Overdue shame stacks and red badge walls | BANNED | No surface may render failure as arithmetic. |
| AP-2 | Streak hostage-taking | BANNED | A lapse never destroys accumulated progress or its evidence. |
| AP-3 | Streaks as the default motivator | AVOID-BY-DEFAULT | Continuity metrics are opt-in equipment, never the success frame. |
| AP-4 | Punishment mechanics | BANNED | Reward presence; never punish absence. |
| AP-5 | Guilt copywriting and confirmshaming | BANNED | No sentence ships that a good ADHD coach wouldn't say mid-shame-spiral. |
| AP-6 | Leaderboards and social comparison | AVOID-BY-DEFAULT | No comparison surface without opt-in; public failure never renders. |
| AP-7 | All-or-nothing day plans and execution grades | BANNED | Every plan has a valid partial state; minimum counts as success. |
| AP-8 | Fake urgency and manufactured scarcity | BANNED | Klyr never lies about time, scarcity, or stakes. |
| AP-9 | Urgency as house policy | AVOID-BY-DEFAULT | Urgency is user-initiated equipment, never ambient pressure. |
| AP-10 | Casino mechanics and gambled rewards | BANNED | No paid or scarcity-mediated randomness; acknowledgment is never a slot machine. |
| AP-11 | Notification carpet-bombing | BANNED | Notifications spend a trust budget; engagement pings are theft from it. |
| AP-12 | Trial ambushes and hard-to-cancel subscriptions | BANNED | Cancellation costs no more than signup; trials never convert silently. |
| AP-13 | Data hostage on lapsed subscription | BANNED | Payment state never gates access to the user's own data. |
| AP-14 | Setup before value | BANNED | First value precedes all configuration and any account. |
| AP-15 | The blank-canvas trap | BANNED | Klyr ships working defaults; users never build the system to get one. |
| AP-16 | Ritual dependency (the weekly-review trap) | BANNED | No feature's correctness depends on a recurring user ceremony. |
| AP-17 | Infinite customization rabbit holes | HANDLE-WITH-CARE | Customization stays shallow: presets over settings, surface over substrate. |
| AP-18 | Productivity-porn feature bloat | HANDLE-WITH-CARE | Every feature passes the worst-week and two-weeks-of-neglect gates. |
| AP-19 | Rigid schedules that shatter — or thrash | HANDLE-WITH-CARE | Plans self-heal legibly; wreckage is never displayed, replanning never silent. |
| AP-20 | Buried capture | BANNED | Capture is one step, zero decisions, under three seconds. |
| AP-21 | Silent data loss | BANNED | Nothing is silently lost, altered, or expired — ever. |
| AP-22 | Uninvited state inference and labeling | BANNED | Klyr never infers or names the user's mental state unasked. |
| AP-23 | Improvement promises and myth copy | BANNED | No claim outruns its evidence; no graduation mechanics. |
| AP-24 | Third-party trackers on health-adjacent data | BANNED | Zero ad/analytics SDKs; everything stored is health data. |

Count: 18 BANNED, 3 AVOID-BY-DEFAULT, 3 HANDLE-WITH-CARE.

## Shame, punishment, and judgment

### AP-1: Overdue shame stacks and red badge walls

**What it looks like.** Missed tasks turn red and compound into an "Overdue" pile that greets the user at open; the app icon wears a growing badge count; recurring chores display "overdue ×14." Todoist and TickTick are the canonical cases — review syntheses describe users who "learned to associate opening Todoist with the feeling of being behind," and the cycle in full: "Opening the app triggers the shame response, which makes starting any task harder, which creates more overdue items — the tool reinforces the cycle it was meant to break" ([app-landscape](app-landscape.md)).

**Why it harms ADHD users.** Users arrive criticism-sensitized and pre-shamed; counts read as verdicts, and the badge acts as a disappointed parent ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)). Intermittent execution is guaranteed by fluctuating executive output and boom-bust cycles ([daily-life-impact](../daily-life/daily-life-impact.md)), so the pile is not an edge case — it is the scheduled future of every account. A stream of negative signals attached to the app's own cues literally teaches the reward system to avoid the app ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)). Shame → avoidance → deletion is the single clearest abandonment mechanic in general task managers.

**What to do instead.** Make the count structurally impossible, not suppressed: overdue amnesty as a core mechanic (aging items de-emphasize, then park with a neutral "Still matter? Shrink it? Let it go?"), missed recurring chores compress into one next instance, recaps lead with what happened and render misses only as actionable choices, and the home surface shows "today's 3," never "you have 247" (P5; [daily-life-impact](../daily-life/daily-life-impact.md)). Named tension: amnesty that moves too fast reads as "the app deleted my task" — parking must leave a visible, reversible trace (P4), and the threshold needs user testing.

**Severity: BANNED.** If a 47-item overdue wall *can* render, it eventually will — for every user, on their worst week.

### AP-2: Streak hostage-taking

**What it looks like.** An unbroken-chain counter that resets to zero on one missed day, dressed in loss framing: fire-goes-out animations, "don't lose your 40-day streak" alarms, paid streak freezes and repairs. Duolingo is the cautionary case — loss-framed streaks with a paid-repair economy and documented user anxiety, controversial even internally ([ux-design-for-adhd](ux-design-for-adhd.md)); community testimony records people rage-quitting the app *and the practice* over a lost streak ([habits-and-routines](../daily-life/habits-and-routines.md)). Todoist's karma/streak layer adds the same second failure surface to a task list; in a 30-day self-test, 8 of 10 habit trackers "broke" the author the same way — a single missed day treated as failure ([app-landscape](app-landscape.md)).

**Why it harms ADHD users.** Losses weigh roughly twice gains, so the mechanic motivates precisely until the first miss — and for ADHD users the first miss is guaranteed, making a reset-to-zero streak a *scheduled shame event* ([ux-design-for-adhd](ux-design-for-adhd.md)). The abstinence violation effect then converts one slip into abandoning the entire practice ([habits-and-routines](../daily-life/habits-and-routines.md)). The reset is also scientifically dishonest: in the Lally data, one missed day barely dents habit automaticity — the zero on the screen reports a catastrophe that did not happen. Selling the repair monetizes loss aversion (see AP-10, AP-12).

**What to do instead.** Metrics that mirror the science: rolling windows ("22 of the last 30 days"), density heatmaps, cumulative totals ("142 days, total"), partial credit always visible, and the resume after a miss celebrated as the highest-value event in the app — "resumes are wins" ([habits-and-routines](../daily-life/habits-and-routines.md), P6).

**Severity: BANNED.** Loss framing on continuity converts a guaranteed ADHD lapse into a designed punishment; the mechanic-without-punishment variant is governed by AP-3.

### AP-3: Streaks as the default motivator (even forgiving ones)

**What it looks like.** The softened version of AP-2: streaks with auto-freezes and grace days, but still installed as the default success frame — the number on the home screen, the thing notifications defend. Duolingo's own silent freezes prove repair can be automated; Duolingo also caps them, because unlimited forgiveness dissolves the commitment device ([motivation-and-gamification](../strategies/motivation-and-gamification.md)).

**Why it harms ADHD users.** Even a forgiving streak keeps *continuity* as the definition of success for a population whose capacity is documented weather (P14) — the frame itself manufactures dread between checkmarks, and streak length is on the corpus's banned anti-metrics list because it structurally manufactures shame ([outcomes-and-measurement](outcomes-and-measurement.md)). The genuine tension, named in [habits-and-routines](../daily-life/habits-and-routines.md): some ADHD users truly want streak stakes and thrive on them; forgiveness-by-default can cost momentum for that subset.

**What to do instead.** The corpus resolution is *forgiving-by-default, opt-in intensity*: rolling metrics as the house default, with an explicitly opt-in streak mode for users who choose it — cumulative framing, automatic repair, decay-not-reset, never the primary metric, never on the app icon, clean off-ramp with no data loss ([habits-and-routines](../daily-life/habits-and-routines.md), [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md), P10).

**Severity: AVOID-BY-DEFAULT.** Legitimate for self-selected users who ask for stakes; harmful as a default frame for a population with guaranteed lapses.

### AP-4: Punishment mechanics

**What it looks like.** The app hurts something when the user doesn't perform: Habitica's avatar loses HP for missed dailies and can drag down the party in group quests; Forest kills the tree if focus breaks — "Forest killed my 40-day forest because I answered a phone call. I felt genuinely bad about a cartoon tree" ([app-landscape](app-landscape.md)). The family includes decaying pets, sickening companions, wilting plants, red "shame states," and any avatar that visibly suffers for the user's week.

**Why it harms ADHD users.** Punishment lands on dysregulated emotion and rejection sensitivity, and it punishes capacity variance as if it were character: Habitica's HP loss measurably penalized busy, productive weeks and drove system-gaming ([motivation-and-gamification](../strategies/motivation-and-gamification.md)). The market ran the natural experiment: Finch — whose bird never sickens or dies, and whose design promise is "there's NO guilt if you miss tasks" — earns unusually long ADHD engagement, while Habitica's punishment loop ejects the same users ([app-landscape](app-landscape.md)). Gentle gamification demonstrably retains; punitive gamification demonstrably ejects.

**What to do instead.** Finch-shaped care mechanics: reward presence, never punish absence; missed days are neutral and simply absent, not red; a companion creature naps when the user is away — it never starves, and stepping away is guilt-free ([motivation-and-gamification](../strategies/motivation-and-gamification.md), P10).

**Severity: BANNED.** Attaching pain to the app's own cues is operant training to avoid the app — the one lesson this user base has already over-learned.

### AP-5: Guilt copywriting and confirmshaming

**What it looks like.** "We missed you!" comeback messages; "You failed to complete 12 tasks this week"; disappointed-mascot personas; "Still there?" nudges; sleep-shaming; moralizing overdue labels; and confirmshame opt-outs like "No thanks, I like being disorganized" — a pattern family the FTC explicitly catalogs ([ux-design-for-adhd](ux-design-for-adhd.md)). The gap recap ("you were away 9 days") is the same pattern wearing concern.

**Why it harms ADHD users.** The average user arrives carrying decades of corrective messaging and, for roughly a quarter of adults with ADHD, high internalized stigma; guilt copy lands on rejection-sensitive wiring as pain, not information ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)). Mechanistically it backfires: procrastination is short-term mood repair, so copy that worsens mood makes the task *more* aversive and feeds the exact avoidance loop it scolds ([task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)). Guilt copy is a documented quit-driver, and for demand-sensitive users every command-flavored sentence converts a want into an aversive obligation ([motivation-and-gamification](../strategies/motivation-and-gamification.md)).

**What to do instead.** Binding copy rules with a single test: *would a good ADHD coach say this sentence to a client mid-shame-spiral?* Invitations over commands, error states that blame the system ("that didn't save — we've kept your text"), comebacks that open with what matters now rather than what was missed, self-compassion touches used sparingly and never as lecture ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md), P5, P6).

**Severity: BANNED.** Guilt is the abandonment engine of this category; no growth metric buys it back.

### AP-6: Leaderboards and social comparison

**What it looks like.** Ranked productivity leaderboards; public streak displays; Habitica-style group quests where one member's miss damages teammates; and — the domestic version — partner-facing completion stats or failure dashboards in shared/household features.

**Why it harms ADHD users.** Rejection sensitivity makes perceived judgment disproportionately painful (in one qualitative study ~77% of young adults with ADHD related to RSD descriptions), and low-rank embarrassment is documented even in neurotypical cohorts ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md), [motivation-and-gamification](../strategies/motivation-and-gamification.md)). Boom-bust capacity cycles turn every trough into visible rank loss. In couples, visible failure stats feed the parent-child dynamic the corpus flags as a relationship hazard — Klyr must become the nag so the partner doesn't have to ([daily-life-impact](../daily-life/daily-life-impact.md)). Gollwitzer's identity-goal work adds a subtler failure: announcing goals can substitute for doing them — share deeds, not dreams.

**What to do instead.** Social features built on presence and progress, not rank: body-doubling sessions, "start together" invites, progress-sharing among chosen peers, effort-framed and opt-in; self-referenced challenge ("beat your own Tuesday") instead of comparison; in shared households, neutral system reminders and self-chosen visibility, never partner-facing scoreboards ([motivation-and-gamification](../strategies/motivation-and-gamification.md), [daily-life-impact](../daily-life/daily-life-impact.md)).

**Severity: AVOID-BY-DEFAULT.** Chosen-peer, effort-framed comparison serves a real accountability appetite — but only ever opt-in, and the sub-pattern of *publicly rendered failure* stays flatly banned (P10 red line).

### AP-7: All-or-nothing day plans and execution grades

**What it looks like.** Day structures whose only states are perfect or failed: strict-order MIT/Ivy Lee lists where item 3 is unreachable because item 1 stalled; 12 Week Year-style weekly execution scores that grade the user; days that "fail" at midnight; planners where an untouched plan renders as an empty, silently reproachful timeline ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md), [app-landscape](app-landscape.md)). The habit-tracker version — binary done/failed days — is what "broke" 8 of 10 apps' testers the same way.

**Why it harms ADHD users.** Perfectionistic all-or-nothing thinking is the single most commonly cited routine-collapse cause, and a plan with no valid partial state converts a 60%-done day into a felt zero ([habits-and-routines](../daily-life/habits-and-routines.md), [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)). Energy variance breaks strict ordering ("eat the frog" fits only 7% of surveyed ADHDers as doctrine), execution scoring converts fluctuation into a falling-behind spiral, and delayed chronotypes make midnight a hostile grader — the corpus is blunt: rigid all-or-nothing planner regimes collapse, "Klyr must build none of these" ([evidence-based-strategies](../strategies/evidence-based-strategies.md), [time-perception](../foundations/time-perception.md)).

**What to do instead.** Tiered days — full / minimum / missed — with *minimum scored as success*; every routine built as a menu with a minimum-viable floor, never a script; partial completion ("started," "2 of 5") as a first-class celebrated state; small capped plans (1–3 protected items) with state-based, not doctrinal, ordering; no execution scores, percentages, or grades anywhere ([habits-and-routines](../daily-life/habits-and-routines.md), [planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md), P5, P9).

**Severity: BANNED.** A plan that can only be perfect or failed is a shame machine with a calendar attached.

## Exploiting the ADHD nervous system (engagement and monetization)

### AP-8: Fake urgency and manufactured scarcity

**What it looks like.** Fake countdown timers, "only 2 left," expiring-tonight discounts, artificial deadline pressure on upgrade screens, false alarms about mechanics ("your progress is about to disappear!"). The FTC's dark-patterns report names fake countdowns in its first family of misleading design, and enforcement is active ([ux-design-for-adhd](ux-design-for-adhd.md)).

**Why it harms ADHD users.** It weaponizes the two impairments this product exists to shelter: impulsivity converts urgency cues into purchases, and time blindness — the now/not-now binary — makes whatever screams *now* the only visible thing ([time-perception](../foundations/time-perception.md), [dopamine-and-motivation](../foundations/dopamine-and-motivation.md)). Worse, it is self-destroying: Klyr's core function is rendering time honestly, and every fake alarm trains users to distrust the app's *real* deadline signals ([ux-design-for-adhd](ux-design-for-adhd.md)).

**What to do instead.** Honest time, made vivid: J-curve reminder salience that concentrates in a real deadline's final window, curve-shaped urgency indicators, system-suggested intermediate commitments so urgency arrives early and cheap, and user-initiated sprints for manufactured-but-consensual pressure ([time-perception](../foundations/time-perception.md), AP-9).

**Severity: BANNED.** A time prosthesis that lies about time has forfeited its reason to exist.

### AP-9: Urgency as house policy

**What it looks like.** Real deadlines delivered as ambient panic: red-alarm resting aesthetics, countdown pressure attached to everything, a default day view that is a wall of ticking bombs, and person-framed pressure ("you're running out of chances"). Distinct from AP-8: nothing here is fake — the delivery is the harm.

**Why it harms ADHD users.** Urgency is the corpus's sharpest tension: it is the single most reliable activation lever (deadline proximity collapses the delay term) *and* the mechanism that entrenches a stress-based work style, degrades quality, and burns out — while anxiety is already comorbid at ~5× odds ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md), [task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md), [adhd-overview](../foundations/adhd-overview.md)). Countdown pressure can itself block initiation, and imposed urgency tolerance decays with repetition ([time-perception](../foundations/time-perception.md), [motivation-and-gamification](../strategies/motivation-and-gamification.md)). Red alarm states the user did not ask for are simulated deadline stress — the thing they are already drowning in.

**What to do instead.** The three-doc convergent resolution, adopted by P9: urgency is *user-initiated equipment* — beat-the-clock sprints, countdowns, "before dinner" framings, offered on demand with a governor — defaulted low, always about the task ("this closes at 5 pm"), never about the person; count-up timers first-class; formats rotated as tolerance decays.

**Severity: AVOID-BY-DEFAULT.** The lever genuinely works and some users reach for it; only imposition, ambience, and person-framing are the harm.

### AP-10: Casino mechanics and gambled rewards

**What it looks like.** Loot boxes, gacha pulls, paid or currency-gated chance, limited-time odds boosts, prize wheels on the upgrade path — and the subtler version: making *whether the user's work gets acknowledged* itself variable, so completion sometimes lands to silence and sometimes to fanfare.

**Why it harms ADHD users.** Variable-ratio reward is the slot-machine mechanism, and this population is the wrong audience to aim it at: ADHD symptoms are associated with gaming disorder, loot-box engagement correlates with problem gambling and impulsivity, and steep delay discounting makes "maybe now" pulls disproportionately strong ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md), [motivation-and-gamification](../strategies/motivation-and-gamification.md)). An expected reward that fails to arrive is not neutral — it produces a negative prediction error, an active demotivator attached to Klyr's own cues.

**What to do instead.** The corpus red line: **vary delight, never whether the user's work is acknowledged** (P11). Acknowledgment is instant, unconditional, guaranteed; occasional *surprise* celebration on top is legitimate and habituation-resistant; nothing random is ever purchasable, scarce, or attached to odds ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md), [motivation-and-gamification](../strategies/motivation-and-gamification.md)).

**Severity: BANNED.** Monetized randomness converts a clinical impulsivity profile into revenue; Klyr must be safe to use compulsively, which means never built to be used compulsively.

### AP-11: Notification carpet-bombing

**What it looks like.** Engagement pings dressed as help: identical daily nags, streak-defense alarms, "you have 14 tasks" pushes, marketing mixed into the functional channel, aggressive rating prompts (a named Tiimo complaint), and reminders that repeat verbatim until dismissed forever ([app-landscape](app-landscape.md)).

**Why it harms ADHD users.** Klyr's prosthetic-memory function *runs on* notification trust, and habituation is how that trust dies: identical repeated alerts get overridden at 49–96% rates in clinical alerting, and alert fatigue — not raw count — is what predicts harm ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md), [ux-design-for-adhd](ux-design-for-adhd.md)). Every ignored notification trains ignoring; a burned channel means the one reminder that truly matters (the bill, the refill, the flight) arrives pre-muted. An ADHD tool that adds interruptions is net-negative regardless of content ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md), P15).

**What to do instead.** Treat notification trust as a budgeted currency: two classes only — point-of-performance interrupts and batched digests — every one actionable from the shade, quiet hours on by default, "why this fired" visible; a snooze-death breaker that converts ~3 snoozes into a triage choice (reschedule / shrink / let it go, shame-free); three ignored resurfacings trigger a strategy change, never a volume increase. Named tension: Due-style relentless re-nagging is genuinely loved — as *user-configured persistence for a tiny set of self-designated critical items*, which is consent, not carpet-bombing ([app-landscape](app-landscape.md), [ux-design-for-adhd](ux-design-for-adhd.md)).

**Severity: BANNED.** Spending the alert-trust budget on engagement metrics defunds the app's actual job.

### AP-12: Trial ambushes and hard-to-cancel subscriptions

**What it looks like.** Free trials that convert silently ("Opal charged me $99.99 the day my trial ended"), unexpected charges and repeated price hikes (Motion), opaque dynamic pricing that "undermines the product's warm philosophy" (Finch's $9.99–$129.99 annual spread), cancellation mazes (Cerebral's, named in an FTC order; Amazon's internally named "Iliad Flow" — four pages, six clicks, fifteen options — ended in a reported $2.5B settlement) ([app-landscape](app-landscape.md), [ux-design-for-adhd](ux-design-for-adhd.md), [privacy-and-data-ethics](privacy-and-data-ethics.md)).

**Why it harms ADHD users.** This is the ADHD tax with a billing system: prospective-memory failure converts free trials into months of unwanted charges, and impulsive signup plus forgetting *is* the revenue model being exploited ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md), [daily-life-impact](../daily-life/daily-life-impact.md) — the tax runs ~£1,600/year in one survey). Billing betrayal is a top 1-star theme across the entire category, and in a population burned serially by productivity tools, it is unrecoverable trust damage — plus live FTC Section 5 exposure.

**What to do instead.** Loud, advance trial-end warnings; cancellation in-app in ≤2 steps, no harder than signup (grant/revoke symmetry as a release-blocking rule); transparent, stable pricing; a genuinely useful free tier; export always available. Named tension, priced in deliberately: this measurably reduces short-term revenue retention — it is the cost of the trust positioning, and Forest's $3.99 goodwill shows the upside ([ux-design-for-adhd](ux-design-for-adhd.md), [app-landscape](app-landscape.md)).

**Severity: BANNED.** Monetizing the customer's diagnosis is both the ethical floor and, per the market's loudest reviews, commercial self-harm.

### AP-13: Data hostage on lapsed subscription

**What it looks like.** Lapsed payment locks the user out of their own tasks; export sits behind the paywall; "pay to recover your progress/data"; downgrade flows that render years of captured life read-only-if-you-resubscribe or gone.

**Why it harms ADHD users.** Klyr's entire premise is being the user's external memory ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)); ransoming that memory is ransoming the prosthesis. ADHD users lapse payments by forgetfulness, not decision — the same population that refills only ~46% of prescriptions on time — so the hostage scenario is guaranteed, recurring, and lands mid-trough ([daily-life-impact](../daily-life/daily-life-impact.md)). The market is serial tool-switchers: lock-in does not retain them, it converts churn into resentment ([app-landscape](app-landscape.md)); the ux ban list is unambiguous — pay-to-recover data "converts executive-function failures into revenue; unacceptable."

**What to do instead.** Payment state gates premium *features*, never data: read access and one-tap full export in open formats remain free forever, the free tier keeps existing data usable, and easy import respects where users came from (P4, [privacy-and-data-ethics](privacy-and-data-ethics.md), [app-landscape](app-landscape.md)).

**Severity: BANNED.** Holding someone's externalized mind for ransom is the single fastest way to prove every fear this user base has about tools.

## Maintenance burden and structural traps

### AP-14: Setup before value

**What it looks like.** Onboarding questionnaires, account walls, permission marches, and configuration wizards standing between the user and their first captured task. Motion's "difficult onboarding" and Tiimo's "setup investment before the magic shows" are named review complaints; the counterexample that earned the category's most love is Goblin Tools — value in under 30 seconds, no account, zero setup ([app-landscape](app-landscape.md)).

**Why it harms ADHD users.** Abandonment concentrates in the first sessions, and for ADHD users the novelty window *is* the adoption window — honeymoon dopamine spent on configuration is spent, not banked ([ux-design-for-adhd](ux-design-for-adhd.md), [dopamine-and-motivation](../foundations/dopamine-and-motivation.md)). Choice overload bites hardest under uncertain preferences, which is the definition of a first run; and delay before anything happens is affectively costly, not merely inconvenient. Setup is also where the customization spiral begins (AP-17).

**What to do instead.** First capture within 60 seconds of first open, before any account wall; a usable capture-and-today experience with zero configuration; configuration harvested from use, never asked up front; defaults already safe for the most sensitive populations so skipping settings never harms (P3, P16, [ux-design-for-adhd](ux-design-for-adhd.md)).

**Severity: BANNED.** Every screen before first value is a bet that a novelty-driven attention system will wait; the retention data says it won't.

### AP-15: The blank-canvas trap

**What it looks like.** Infinite flexibility as the product: Notion's empty workspace that must be architected before it manages anything — so seductive and so abandoned that the community named the result (the **template graveyard**) and built a paid economy of ADHD templates to fix previously abandoned setups; Obsidian inherits the same trap with better data ethics ([app-landscape](app-landscape.md)). Note the distinction: bullet journaling's blank *page* forgives — it absorbs absence without judgment inside a defined method; the blank *canvas* demands the user invent the method itself ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

**Why it harms ADHD users.** It converts users into unpaid system administrators, and administration is precisely the executive work ADHD makes expensive ([executive-function](../foundations/executive-function.md)). Documented failure mechanisms: novelty burnout, complexity creep, perfectionism paralysis ("avoid the system entirely rather than face imperfection"), and working-memory-taxing dashboards ([app-landscape](app-landscape.md)). Choice overload is maximal when options are infinite and preferences uncertain ([ux-design-for-adhd](ux-design-for-adhd.md)). The blunt community verdict: "your brain isn't the problem — your system is."

**What to do instead.** Opinionated defaults that work on contact; Klyr absorbs complexity (Tesler's law) instead of exporting it; structure arrives as swappable presets and modes, never as an empty page plus a manual; the new-system itch is served by surface-level novelty rotation, not structural rebuilding (P13, [app-landscape](app-landscape.md), [ux-design-for-adhd](ux-design-for-adhd.md)).

**Severity: BANNED.** Shipping a kit instead of a tool outsources the product's hardest job to the person least resourced to do it; deep custom views may exist only behind working defaults (see AP-17).

### AP-16: Ritual dependency (the weekly-review trap)

**What it looks like.** A system whose correctness depends on a recurring user ceremony: GTD's weekly review, Sunsama's daily planning ritual (praised as calm, lived as a chore), PARA's per-capture filing and progressive summarization, 12 Week Year's self-run ceremonies, Trello/Asana board grooming. Skip the ritual and the system silently rots into stale, accusing debris ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md), [app-landscape](app-landscape.md)).

**Why it harms ADHD users.** The maintenance ritual is boring, delayed-reward, and executive-function-heavy — the exact task profile ADHD handles worst — which is why every famous methodology dies at the same spot ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)). The collapse arc is predictable: ritual lapses → system fills with stale debris → shame → avoidance → a new system for the fresh-start dopamine. A single point of failure that fails during bad weeks means the system fails exactly when it is needed most.

**What to do instead.** Automate the review; never schedule one. Klyr performs review work continuously — one stale item at a time as a single keep/kill/someday tap at natural moments; days and weeks auto-close and open clean with a blameless auto-recap ("what moved, what carried"); plans self-heal; the design-review gate is explicit: *what does this feature look like after two weeks of total neglect?* If the answer is clutter or accusation, it does not ship (P7). Optional, assisted reflection may exist — as long as skipping it costs nothing and breaks nothing.

**Severity: BANNED.** A ritual dependency is a scheduled abandonment with extra steps.

### AP-17: Infinite customization rabbit holes

**What it looks like.** Amazing Marvin's 300+ settings and toggleable strategy library — genuinely brilliant, and buried under a learning curve steep enough that MetaFilter threads exist solely to ask how to set it up; Notion re-architecture weekends; theme-and-layout fiddling that feels like productivity. The community lifecycle names the step: "you keep adding features until your simple system becomes an overwhelming monster you dread opening" ([app-landscape](app-landscape.md)).

**Why it harms ADHD users.** Configuration is displacement activity with a dopamine payout — setup *is* rewarding, novelty-wise, which makes it productive procrastination ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md), [app-landscape](app-landscape.md)). Every option is future maintenance debt and choice-overload surface; complexity creep is itself a documented abandonment trigger; and perfectionist tuning postpones actual doing ([ux-design-for-adhd](ux-design-for-adhd.md), [planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

**What to do instead.** Customization exists — P16 *requires* dials, because populations conflict — but shallow: few visible dials, presets over settings, human-named bundles ("more calm / less surprise"), configuration harvested from use, and novelty that changes the surface but never the substrate (restyle without rebuild, migration, or data loss). Marvin's real lesson, minus Marvin's overwhelm: give the switch-itch an in-app destination with opinionated defaults and progressive disclosure ([app-landscape](app-landscape.md), P13, P16). Consider detecting a setup-spiral and gently redirecting — an open question worth testing ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

**Severity: HANDLE-WITH-CARE.** Dials are mandatory for this population; depth is the trap.

### AP-18: Productivity-porn feature bloat

**What it looks like.** Shipping what demos well to productivity enthusiasts: stat dashboards, elaborate matrix views, analytics for everything, one more panel per release. The market's shape shows where this ends: power tools with project depth are "shame machines without ADHD affordances," and users already run overwhelming 3–5-app stacks ([app-landscape](app-landscape.md)). Klyr is *specifically* exposed because its ambition — owning the whole capture→restart loop — is a standing invitation to bloat; [app-landscape](app-landscape.md) names the tension outright: integrated scope fights simplicity.

**Why it harms ADHD users.** ADHD taxes extraneous cognitive load at a premium — every decorative element and unnecessary decision competes with the user's task; choice overload bites hardest under decision difficulty ([ux-design-for-adhd](ux-design-for-adhd.md)). Features that flatter week-one enthusiasm become month-three clutter ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)), and even honest analytics can become a self-judgment surface (Eisenhower-style self-classification asks for exactly the discrimination ADHD impairs — [planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

**What to do instead.** Resolve scope through progressive disclosure, not feature deletion — depth exists, but never squats on the surface (P12's salience budget: one primary action per screen). Every proposal passes three gates before shipping: the worst-week question (P1), the two-weeks-of-neglect question (P7), and the month-three question (P13). When a feature and a calm surface conflict, the surface wins.

**Severity: HANDLE-WITH-CARE.** Depth is Klyr's market gap; undisciplined depth is how it becomes the next shame machine.

### AP-19: Rigid schedules that shatter — or thrash

**What it looks like.** Two failure modes of the same feature. *Shatter:* manual time-blocked days that "collapse by 10 am Monday," leaving visible wreckage and calendar anxiety ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)). *Thrash:* auto-schedulers that endlessly, silently rearrange — Motion's own ADHD reviews report "the constant re-prioritization can actually be distracting — the app keeps changing your plan," and that auto-schedulers optimize calendar Tetris while ignoring how you feel ([app-landscape](app-landscape.md)). Add the quiet third: morning-anchored defaults and back-to-back blocks that pre-fail a population with delayed sleep phase in 73–78% ([time-perception](../foundations/time-perception.md)).

**Why it harms ADHD users.** Slips are guaranteed (executive-function variability, boom-bust weeks, planning fallacy on top of time blindness), so a rigid plan is a scheduled failure display — and displayed wreckage triggers the abstinence-violation spiral ([habits-and-routines](../daily-life/habits-and-routines.md)). But opaque flexibility fails too: a plan that changes every time you look at it can't be trusted as external memory, and ADHD users demonstrably resent black-box scheduling ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

**What to do instead.** Self-healing with legibility: when a day slips, the plan reflows automatically *with visible reasoning and undo*, and the old plan's wreckage is never displayed — the auto-schedulers' genuinely loved feature is guilt-free *re*-scheduling ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md), P7, P17). Default buffers between commitments; duration estimates corrected from actuals and presented as calibration, never failure; chronotype-respecting defaults; no plan marked failed because it slipped past midnight (P9).

**Severity: HANDLE-WITH-CARE.** Holding the user's day is core Klyr value; rigidity, visible wreckage, and silent thrash are the three documented ways it turns hostile.

### AP-20: Buried capture

**What it looks like.** More than one step between a thought and its safe storage: required fields at entry (project, date, priority, category), filing decisions at capture time (PARA's per-capture taxonomy), capture behind navigation or an account wall, slow-loading entry screens. Notion's capture is rated "slow" for exactly this reason; the most-loved ADHD tools (Goblin Tools, Due, Todoist's NL entry) are all capture-fast ([app-landscape](app-landscape.md), [planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md)).

**Why it harms ADHD users.** Uncaptured thoughts evaporate in seconds under working-memory volatility — every additional tap or decision is a drop point ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)). Until parked, the thought behaves as **distraction-by-anticipation**: an intrusive idea that must be acted on *now* because the alternative is losing it — so slow capture doesn't just lose ideas, it hijacks the current task ([attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md)). Capture is also the trust loop that lets the mind release open loops at all; a leaky inbox breaks the whole prosthesis contract.

**What to do instead.** Sacred capture (P3): global quick-add from every screen in under three seconds, zero required decisions, voice/widget/share-sheet paths, typo-tolerant input, classification deferred to Klyr (suggestion, search, auto-archive — organize-never beats organize-at-entry), sub-400 ms feedback, first capture before any account exists.

**Severity: BANNED.** Every field between impulse and storage is a dropped thought, and dropped thoughts are the one failure an external memory cannot survive.

## Data, dignity, and truth

### AP-21: Silent data loss

**What it looks like.** Captures that vanish into unsearchable states; auto-archive or expiry without a trace; sync conflicts and timeouts that eat text; destructive confirmations that punish a mis-tap; and the AI variant — an assistant that silently rewrites, merges, "cleans up," or hallucinates a detail into stored tasks ([ai-assistance-for-adhd](ai-assistance-for-adhd.md) calls a hallucinated fact written silently into a task the single worst available failure).

**Why it harms ADHD users.** The mind releases an open loop only when it trusts the external system to bring it back; one dropped item can collapse that trust — and with it the entire product premise ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)). For a user who cannot re-derive what was lost (that's why it was captured), silent alteration of external memory is functionally gaslighting (P17's framing). Data lock-in and loss convert churn into resentment in a switcher market ([app-landscape](app-landscape.md)).

**What to do instead.** The P4 package: undo instead of confirmation dialogs, archive instead of delete, autosave everything, no data-losing timeouts; every automatic change leaves a visible, reversible trace; "show me everything I ever captured" always works; AI changes carry provenance labels and act only behind preview-and-undo; one-tap full export, free forever. Named distinction: user-invoked amnesty ("forget this month") is honest, consented deletion — the opposite of silent loss, and a feature Klyr should ship ([privacy-and-data-ethics](privacy-and-data-ethics.md)).

**Severity: BANNED.** Trust in the external memory is binary; it does not survive the first betrayal.

### AP-22: Uninvited state inference and labeling

**What it looks like.** "You seem depressed lately"; auto-detected "burnout mode"; clinical screeners (PHQ-9-style) inside a task app; crisis interstitials sprung by keyword scans; menstrual-cycle phases inferred from behavior; "insights" that diagnose the user's slump back at them.

**Why it harms ADHD users.** Software cannot reliably distinguish a depressive shutdown from a busy week — passive-sensing studies are small, short, and rarely externally validated, and the base-rate math is brutal (one analysis: ~99.4% specificity needed before false positives stop dominating) — so wrong guesses are the normal case, and each one costs trust twice: it feels like surveillance *and* it pathologizes an ordinary week ([when-to-back-off](when-to-back-off.md)). Inferred states are legally radioactive as well: Washington's MHMD covers inferences from non-health data, and the FDA wellness safe harbor evaporates at diagnostic language ([privacy-and-data-ethics](privacy-and-data-ethics.md), [when-to-back-off](when-to-back-off.md)). Cycle inference is explicitly forbidden by the corpus: never auto-infer, never require logging ([populations-and-variation](../foundations/populations-and-variation.md)).

**What to do instead.** The asymmetry principle (P14): de-escalate automatically and freely (quieter notifications, lighter defaults) without ever labeling why; make the user the sensor — a one-tap, no-explanation capacity dial has 100% precision and doubles as consent; check-ins opt-in, configured in calm moments, dismissible without consequence; crisis resources verified each release and passively reachable, never algorithmically sprung ([when-to-back-off](when-to-back-off.md)).

**Severity: BANNED.** Wrongly quieting notifications costs nothing; wrongly saying "you seem depressed" costs the relationship — and possibly the regulatory safe harbor.

### AP-23: Improvement promises and myth copy

**What it looks like.** "Build the habit in 21 days," brain-training minigames, "boost your dopamine," "detox your dopamine," "fix your focus," before/after testimonial marketing — and the mechanical version, graduation mechanics: fading reminders as a "reward" for consistency, implying the user should eventually manage without the scaffold.

**Why it harms ADHD users.** The claims are false on the corpus's own evidence: habits take a median ~59–66 days with a range of 4–335 (the 21-day rule is folklore — [habits-and-routines](../daily-life/habits-and-routines.md)); computerized cognitive training shows no blinded-rater transfer to symptoms or daily life ([executive-function](../foundations/executive-function.md)); "dopamine detox" is pseudoscience Klyr must never echo ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)). Barkley's evidence cuts the other way: gains persist only as long as accommodations do — so graduation mechanics dismantle the intervention (P1). This user base has been burned by miracle systems; overclaiming is simultaneously a churn engine, an FTC substantiation exposure, and a betrayal of the shame-free contract ([outcomes-and-measurement](outcomes-and-measurement.md), [evidence-based-strategies](../strategies/evidence-based-strategies.md)).

**What to do instead.** Calibrated claims (P20): a tool, never a treatment; "many people find…" for community strategies and "research shows…" only where it does; externalization framed as the smart permanent strategy, never a crutch to outgrow; reminders never fade as a reward; marketing audited per release against the wellness safe harbor.

**Severity: BANNED.** A promise the mechanism can't keep is a scheduled disappointment sold to people who track disappointments in their self-image.

### AP-24: Third-party trackers on health-adjacent data

**What it looks like.** Ordinary ad and analytics SDKs and pixels in the app or web funnel — the default startup stack. That default is the entire FTC health-app enforcement record: GoodRx ($1.5M, medication lists to Facebook), BetterHelp ($7.8M, intake answers to ad platforms), Premom, Flo, and Cerebral ($7M; ~3.2M mental-health/ADHD patients' data to LinkedIn/Snapchat/TikTok via pixels) all began with routine marketing tools plus a privacy sentence the product didn't keep ([privacy-and-data-ethics](privacy-and-data-ethics.md)).

**Why it harms ADHD users.** Everything Klyr stores is health data before Klyr thinks of itself as a health app — an account in an ADHD-branded product is itself a sensitive disclosure, and regulators reach inferences, not just fields ([privacy-and-data-ethics](privacy-and-data-ethics.md)). Users carry real disclosure risk (workplace stigma, controlled-substance entanglement), and the category baseline is rotten enough that users assume betrayal: 92% of top mental-health apps transmitted data to third parties while only ~59% disclosed it; Mozilla warning-labeled 28 of 32. Privacy failure, unlike engagement failure, is unrecoverable.

**What to do instead.** Zero third-party ad/analytics code anywhere — first-party, minimal, privacy-reviewed telemetry only; the two-tier architecture (recoverable encryption for the task graph, local-first/E2E-optional for sensitive fields); consent just-in-time, per-category, default-off; behavioral exhaust ages out by default; copy claims only what the architecture enforces (P18, [privacy-and-data-ethics](privacy-and-data-ethics.md)).

**Severity: BANNED.** Every enforcement action in this category started with exactly this pattern, and Klyr's data class is sensitive on arrival.

## Using this catalog

- **In design review:** walk the table; any BANNED match blocks, any AVOID-BY-DEFAULT match demands the opt-in package and written justification, any HANDLE-WITH-CARE match demands the entry's guardrails. When severity is ambiguous, round up.
- **In experiments:** the bans apply to every arm. No test ships a pattern you would not ship to someone on their worst day ([outcomes-and-measurement](outcomes-and-measurement.md)).
- **In copy and marketing:** AP-5, AP-8, AP-12, AP-23, and AP-24 bind store listings, emails, and screenshots exactly as they bind the product.
- **To amend:** like [design-principles](design-principles.md), this doc synthesizes and does not originate. An entry changes only when the underlying corpus changes; growth pressure, taste, and "just this once" are not amendment paths.

## Open questions

Inherited from the underlying docs, concentrated where this catalog's lines will be tested in practice:

- **Amnesty pacing (AP-1):** where is the de-emphasize→park threshold that reads as relief rather than "the app deleted my task"? ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md))
- **Forgiving metrics vs. momentum (AP-2/AP-3):** do rolling windows sustain actual behavior as well as streaks for the users who'd choose streaks? Does enough forgiveness dissolve the commitment device? ([habits-and-routines](../daily-life/habits-and-routines.md), [motivation-and-gamification](../strategies/motivation-and-gamification.md))
- **Urgency dosage (AP-9):** where does energizing challenge end and anxiety begin for rejection-sensitive users, and how fast does opt-in urgency tolerance decay? ([motivation-and-gamification](../strategies/motivation-and-gamification.md))
- **Snooze-death and resurfacing tone (AP-11):** at what count, and with what wording, does triage feel supportive rather than surveilled? ([ux-design-for-adhd](ux-design-for-adhd.md), [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md))
- **Auto-healing trust boundary (AP-19, AP-21):** do users experience automatic reflow and stale-item fading as relief or as loss? Where is the consent line? ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md))
- **Customization depth (AP-17):** how much restyling extends retention before it becomes displacement activity, and can a setup-spiral be detected and gently redirected? ([planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md))
