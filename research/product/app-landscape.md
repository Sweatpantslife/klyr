---
title: "The ADHD App Landscape: What Exists, What Users Praise, Why They Abandon It"
area: product
file: research/product/app-landscape.md
tags: [app-landscape, competitive-analysis, abandonment, pricing, gamification, task-managers, adhd-apps, market-gaps]
related:
  - research/product/ux-design-for-adhd.md
  - research/strategies/motivation-and-gamification.md
  - research/daily-life/habits-and-routines.md
  - research/strategies/planning-methodologies-and-adhd.md
  - research/foundations/dopamine-and-motivation.md
sources: 53
updated: 2026-07-25
summary: >
  Competitive survey of the tools ADHDers actually use — ADHD-native planners, general task managers,
  body doubling, coaching, gamified habit apps, blockers, and physical tools — with review-derived
  praise and abandonment themes, a feature/pricing comparison table, market gaps, and positioning
  opportunities for Klyr. Read before any feature, pricing, or positioning decision.
---

# The ADHD App Landscape: What Exists, What Users Praise, Why They Abandon It

## TL;DR

- The ADHD productivity market is crowded but fragmented: nearly every tool solves **one mechanism** (visual time, task breakdown, routine execution, accountability, nagging) — so users run stacks of 3–5 apps and subscriptions, and no product owns the full capture→start→finish→restart loop.
- **Abandonment is the market's defining fact, not an edge case.** Mental-health-adjacent apps show median 15-day retention around 3.9% (vs. ~6.3% for general health apps), with >80% of users gone within 10 days [1]. ADHD users additionally churn by design: novelty decay is a feature of ADHD motivation (see [dopamine-and-motivation](../foundations/dopamine-and-motivation.md)).
- The community-documented lifecycle: *"find new system, get excited, customize obsessively, use it perfectly for 10 days, miss one day, feel guilty, avoid it, never open it again"* [6]. Almost no product designs for the "miss one day" step — the single highest-leverage moment.
- General task managers (Todoist, TickTick) fail ADHDers through **guilt accumulation**: overdue tasks pile up in red until opening the app *is* the shame trigger. Notion fails through **maintenance debt**: the "template graveyard" is so common it supports a cottage industry of paid ADHD templates [7].
- What earns genuine ADHD love, per review themes: zero-friction capture (Goblin Tools, Due), one-task-at-a-time views (Llama Life, Amazing Marvin), visible time (Tiimo, Time Timer), punishment-free gamification (Finch), warm human presence (Focusmate, Dubbii), and toggleable novelty (Amazing Marvin's strategy modules).
- What kills tools, per review themes: setup burden before first value, daily rituals that become chores (Sunsama), punitive mechanics (Habitica HP loss, Forest's dead trees), notification habituation, trial-to-charge pricing ambushes (Opal, Motion), opaque/dynamic pricing (Finch), and data lock-in.
- ADHD-native apps are mostly **day-planners without project depth**; power tools with project depth are mostly **shame machines without ADHD affordances**. The middle — a low-maintenance life organizer that survives neglect — is open.
- Klyr's clearest positioning: **the tool that expects you to disappear and makes coming back painless.** Optimize for "returns after lapse," not streaks or DAU.
- Pricing norms: ADHD-native apps cluster at $30–$100/year subscriptions; coaching runs $99–$345/month; one-time pricing (Forest $3.99) earns durable goodwill. Transparent, forgiving billing is itself a differentiator in this market.

## Method and bias warning

This survey draws on product sites, app-store review themes, Reddit/community writing surfaced through them, longitudinal self-tests, and comparison articles. One structural caveat: **most "best ADHD apps" content is written by competitors** (Lifestack, Habi, Saner.ai, Rivva, Blok, Unstar, Inflow, Squad, Shimmer, and Focus Bear all publish comparison blogs that rank themselves or adjacent tools). These pieces still contain real review synthesis and are cited below as `[product]` sources, but every ranking claim should be read as marketing-adjacent. Pricing was recorded as reported in 2025–2026 sources and **must be re-verified before Klyr ships any comparison**; several apps (Motion, Finch) change prices frequently. Direct first-party Reddit quotes were not independently collected in this pass; community sentiment is cited via secondary syntheses and labeled accordingly.

## The abandonment lifecycle

Baseline retention for this category is brutal: a peer-reviewed analysis of objective usage data (Baumel et al., 2019) puts median 15-day retention for mental health apps at **3.9%** (general health apps: 6.29%), with over 80% of users abandoning between days 1–10 [1]. A cross-sectional mHealth survey found the main abandonment drivers are loss of interest, usability problems, hidden costs, data concerns — and, notably, *deliberately experimenting with many apps to find the right one* [2]. Regular use of self-monitoring features strongly predicts who stays [3].

For ADHD users specifically, community writing converges on a predictable arc [5][6][7]:

1. **Honeymoon.** A new system triggers interest and novelty — the exact conditions the ADHD motivation system responds to. Setup itself is rewarding (and can become productive procrastination).
2. **Customization spiral.** *"You keep adding features until your simple system becomes an overwhelming monster you dread opening"* [7]. Complexity creep converts the tool from support into a second job.
3. **The first miss.** A day gets skipped. Streaks break; overdue counts appear. In behavior-science terms this is the **abstinence violation effect** (Marlatt & Gordon): when a system treats one slip as failure, the slip triggers full abandonment [8] — see [habits-and-routines](../daily-life/habits-and-routines.md).
4. **Shame avoidance.** The app now displays evidence of failure. Opening it hurts, so it isn't opened. One competitor teardown of Todoist describes users who "learned to associate opening Todoist with the feeling of being behind" [34].
5. **Quiet death, then a new honeymoon** — usually in a different app, because almost no product offers a graceful in-app restart.

An aggregated screen-time-app review analysis found the same pattern even in blockers: a "novelty cliff" theme in ~10% of critical reviews — *"Every focus app works for me for exactly one week… great for a week, invisible by week three"* [45]. The lifecycle, not any single feature, is the thing Klyr must design against.

## The landscape, cluster by cluster

### 1. ADHD-native visual day planners and routine apps — Tiimo, Structured, Routinery, Brili

**Core mechanic:** externalize the day as a visual, icon-coded timeline (Tiimo, Structured) or walk the user step-by-step through a routine with per-step countdowns (Routinery, Brili). This is externalization of time perception — see [time-perception](../foundations/time-perception.md).

**Praise themes:** Tiimo — Apple's reported iPhone App of the Year 2025 [16][17] — is called "the gold standard for visual time perception" for ADHD and autistic users [16]; users praise seeing time as color and shape, widgets, and gentle non-alarm transitions [17][18]. Brili is praised for making time blindness manageable by "breaking [routines] down into timed, manageable steps" [25]. Structured is liked for showing routines inside the whole day's context at low cost (free tier; ~$20/yr premium) [24].

**Abandonment themes:** Tiimo reviews cite timer bugs, limited customization, aggressive rating prompts, "setup investment before the magic shows," and — critically — "day-planning only, no project or task-manager depth" [17]. Routinery's structural limit is captured by a competitor's line that is nonetheless accurate: *"Routinery starts at step one — it doesn't get you out of bed"* [24] — routine executors assume initiation has already happened (see [task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)). Daily replanning is itself maintenance: an unplanned day is an empty, silently reproachful timeline.

**Pricing:** Tiimo ≈ $54/yr (or ~$12/mo monthly) [17]; Structured freemium; Routinery/Brili freemium subscriptions [24][25].

### 2. ADHD-native task and focus tools — Llama Life, Goblin Tools, Amazing Marvin, Lunatask, Numo

**Llama Life** (founder has ADHD) shows one task at a time with a countdown against your own estimate — "active countdown pressure" vs. Tiimo's "passive visual timeline" [16]. An AuDHD reviewer: *"the cute llama mascot is so adorable that… 'I don't want to let the llama down… I'll stick it out'"* — affection-based, not guilt-based, pull [14]. Subscription with 7-day trial [15].

**Goblin Tools** is the category's friction floor: free on the web, no account, AI-powered Magic ToDo breaks "clean the kitchen" into startable subtasks, with a **"spiciness" slider** controlling breakdown granularity by how hard the task feels [19][20]. Built by Bram De Buyser for neurodivergent users; went viral via TikTok/Reddit [20]. Reviewers position it as a *companion*, not a system — "the fastest way to turn 'clean the kitchen' into 12 startable subtasks," but with no persistence layer worth living in [16][21]. Its lesson for Klyr: the most-loved ADHD tool of recent years has **zero setup, zero maintenance, zero guilt** — and (web version) zero price.

**Amazing Marvin** deserves special study. It is a modular toolkit: a library of toggleable **"strategies"** (Eisenhower matrix, Pomodoro, time blocking, GTD-style workflows, Super Focus single-task mode, a randomizing "Task Jar," a step-by-step "Procrastination Wizard") layered over 300+ settings, marketed as "Built for ADHD minds": *"Most task managers assume you'll just… do the things. Marvin actually helps you start, focus, and follow through"* [9]. The strategic insight: **Marvin turns system-switching — the ADHD churn behavior — into an in-app action.** When novelty fades, you toggle a new strategy instead of migrating apps. Users celebrate the customization and the reward marshmallows [10][11][12]; the recurring criticism is a steep learning curve and configuration overwhelm — MetaFilter threads exist solely to ask how to set it up [11]. Priced ~$12/mo or $96/yr [10].

**Lunatask** is a privacy-focused (end-to-end encrypted) ADHD-marketed task manager + habit/mood tracker that deliberately replaces deadlines with priorities and start dates because "deadlines create stress" [22]. **Numo** gamifies an ADHD planner with quests and "Karma" points [23]. Both are niche but signal demand for ADHD-specific philosophies (no-deadline scheduling; playful reward).

### 3. Body doubling and accountability — Focusmate, Dubbii, and kin

**Core mechanic:** another human's (real or recorded) presence makes starting and continuing possible — **body doubling** (community term; mechanism plausible but under-researched; a 2025 VR design paper notes validation research is still thin) [26][28]. See [evidence-based-strategies](../strategies/evidence-based-strategies.md).

**Focusmate** pairs strangers for silent 25/50/75-minute video sessions. Praise: "the accountability, the structure, and the subtle social support… made showing up and staying engaged feel easier" [27]; CHADD-adjacent writing endorses body doubling as a practical strategy [26]. Free tier (3 sessions/week), paid ~$8/mo [24]. Friction: scheduling a session is itself a commitment device — good when it works, a guilt source when you no-show.

**Dubbii** (from the ADHD Love creators Rich & Rox) offers follow-along body-doubling *videos* for chores, with a deliberately low-demand tone; ~100k downloads, 4.67 rating reported, ≈$4.99/mo or $29.99/yr [29][30]. Its insight: presence can be *asynchronous and pre-recorded* and still activate people.

The proliferation of body-doubling roundups by other ADHD companies (Shimmer, BrightMind, Squad) shows this cluster is now table stakes in the ADHD ecosystem conversation [31].

### 4. CBT content and human coaching — Inflow, Shimmer

**Inflow** packages CBT-based psychoeducation modules, exercises, and optional coaching. Reported pricing spans ~$22.49/mo (app only, ~$95.99/yr) to ~$47.99/mo with coaching (annual figures reported between $199.99 and $575.88 across reviews — pricing has clearly shifted; verify) [37][38]. A peer-reviewed usability/feasibility study exists [4]; controlled efficacy data was still pending in reviews consulted. The sharpest review criticism: if you already know your ADHD, *"the $47.99/month buys knowledge you may already have"* [37] — content apps hit a course-completion wall, after which paying feels pointless.

**Shimmer** sells human ADHD coaching through an app: reported ~$99/mo (15-min weekly), ~$230/mo (30-min weekly), up to ~$345/mo [39][40]. Reviews are strongly positive on coach quality; the barrier is purely price [39]. Relevance to Klyr: hundreds of dollars a month is what the "human who keeps me on track" job is worth to those who can pay — an AI or community feature that captures even part of that job has real willingness-to-pay behind it.

### 5. General-purpose task managers ADHDers adopt — Todoist, TickTick, Things

These are where most ADHDers start, because they're famous and cross-platform. **Praise:** fast natural-language capture (Todoist), and TickTick's bundled Pomodoro timer + Eisenhower matrix + calendar — Zapier's neurodivergent reviewer names TickTick "best for focus" (free; premium $35.99/yr) [13].

**Abandonment mechanic — guilt accumulation.** Both apps assume consistent execution; ADHD makes execution intermittent. Missed tasks turn red, roll into "Overdue," and compound: *"Opening the app triggers the shame response, which makes starting any task harder, which creates more overdue items — the tool reinforces the cycle it was meant to break"* [34] (competitor-authored, but it precisely matches the community lifecycle in §The abandonment lifecycle). Todoist's karma/streak features add a second failure surface. **Things 3** is praised in productivity communities for calm design and one-time pricing, but it is Apple-only and still date-driven (light claim; not verified against sources in this pass).

### 6. System builders — Notion, Obsidian, and the template graveyard

Notion's infinite flexibility makes it the most seductive and most abandoned ADHD tool. The pattern is so established that it has a name in community writing — the **template graveyard** — and an economy: marketplaces sell dozens of paid "ADHD Notion templates," many marketed explicitly as fixes for previously abandoned Notion setups [7][35]. Failure mechanisms documented in ADHD-oriented analyses: novelty burnout, complexity creep, perfectionism paralysis ("avoid the system entirely rather than face imperfection"), and working-memory-taxing dashboards [7]. The blunt community framing: "Your brain isn't the problem — your system is" [7]. Obsidian inherits the same system-builder trap with better data ethics (local plain-text files, no lock-in) — a portability bar Klyr should meet (light claim; community consensus, not verified in this pass).

**The meta-lesson:** ADHDers don't fail at these tools for lack of features — the tools convert users into unpaid system administrators, and administration is precisely the executive-function work ADHD makes expensive (see [executive-function](../foundations/executive-function.md)).

### 7. Calendar-centric daily planners and auto-schedulers — Sunsama, Motion, Reclaim, Akiflow, Trello/Asana

**Sunsama** ($16–20/mo) sells a calm **daily planning ritual**: pull tasks from other tools, estimate times, timebox the day, then a shutdown routine [13][41]. Praise: the guided ritual and anti-overwork ethos; it "integrates existing tools instead of demanding migration" [5]. Risk: the ritual *is* a daily habit — exactly the kind ADHDers struggle to sustain — and Zapier flags that its time-estimate dependence "struggles for those with time blindness" [13].

**Motion** ($19–49/mo reported across 2024–2026 — pricing has changed repeatedly [42][43][44]) auto-schedules tasks into the calendar with AI. Praise: it removes the planning decision entirely. Abandonment themes: "difficult onboarding, cluttered UI, weak mobile app… pricing that has increased more than once," unexpected trial charges [42][43][44], and an ADHD-specific failure: *"the constant re-prioritization can actually be distracting — the app keeps changing your plan"* [36]. Auto-schedulers also "ignore how you feel" — they optimize calendar Tetris, not energy state [33]. **Reclaim** shares the mechanic and the criticism [33]. **Akiflow** consolidates inboxes with keyboard-driven triage and morning/evening "rituals" [32][33][41] — power-user oriented, subscription-priced. Team tools (Trello, Asana) get adopted for personal use and abandoned the same way as Todoist: boards go stale, and staleness is visible shame (community pattern; not separately sourced in this pass).

### 8. Gamified habit and self-care — Finch vs. Habitica (a natural experiment in reward design)

**Finch** (free core; premium ~$10/mo, with dynamically-priced annual offers reported $9.99–$129.99/yr [8][13]) has users care for a pet bird by doing tiny self-care tasks. The design is explicitly punishment-free: *"There's NO guilt if you miss tasks"* — the bird never sickens or dies, and missed days are simply absent, not red [46][47]. ADHD users report unusually long engagement [13][46]. Its main criticism is not the mechanic but the **opaque dynamic pricing**, which "undermines the product's warm philosophy" [8].

**Habitica** (free core, optional subscription) turns tasks into an RPG where missed dailies cost the avatar HP and can hurt your party in group quests. For some ADHDers the RPG frame works; review themes and habit-tracker teardowns document the failure mode: "The HP-loss mechanic turns missed habits into anxiety triggers, especially once you're invested in a party" [48], a textbook abstinence-violation design [8].

A 30-day, 10-app habit-tracker self-test found 8 of 10 apps "broke" the author the same way — streak resets treating one missed day as failure — and concluded *"compliance is not what separates people who build habits from people who don't"* [8]. The two humane exceptions used an intentional-skip state and a moving-average "habit strength" score instead of binary streaks [8]. Full analysis belongs to [motivation-and-gamification](../strategies/motivation-and-gamification.md) and [habits-and-routines](../daily-life/habits-and-routines.md); the market fact for Klyr is that **gentle gamification demonstrably retains ADHD users and punitive gamification demonstrably ejects them.**

### 9. Blockers and nag apps — Forest, Freedom, Opal, one sec; Due

Aggregated review analysis of blockers [45]: **Forest** ($3.99 one-time) is loved for its grow-a-tree mechanic and its non-subscription price, but its 1-star reviews concentrate on "guilt backfire" — *"Forest killed my 40-day forest because I answered a phone call. I felt genuinely bad about a cartoon tree"* — and trivial bypass. **Freedom** ($39.99/yr) wins on cross-device blocking; **Opal** ($99.99/yr) on analytics — with the top complaint category across all of them being subscription shock (*"Opal charged me $99.99 the day my trial ended"*) [45]. **one sec** ($19.99/yr) inserts a breathing pause before opening apps; users habituate: "After a week I tap through without thinking" [45]. The analysis's closing line is a design axiom for Klyr: *"no app can want to be off your phone more than your phone wants you on it"* [45]. Blocking treats the symptom (access) not the mechanism (impulse + boredom); see [attention-and-hyperfocus](../foundations/attention-and-hyperfocus.md).

**Due** (paid, Apple-only) is the opposite philosophy: it *adds* notifications. Its auto-snooze re-nags every 1–60 minutes until you act, indefinitely if configured [49][50]. ADHD reviewers, including an ADHD coach, call it uniquely effective precisely because a dismissed notification isn't a lost task: "Due keeps reminding you until you mark the task complete… frictionless" [49][50]. Lesson: **persistence beats loudness** for critical reminders — but it only scales to a handful of truly critical items before nag habituation sets in (see [memory-and-object-permanence](../foundations/memory-and-object-permanence.md) and [ux-design-for-adhd](ux-design-for-adhd.md)).

### 10. Physical tools — Time Timer, paper planners, wall calendars

The **Time Timer** (~one-time hardware purchase) shows remaining time as a shrinking red disc: continuous, ambient, silent, glanceable — no mental arithmetic, no notification to dismiss [51][52]. It remains a clinician-recommended standard because it externalizes time *passively*. Paper planners and family wall calendars persist for the same reasons: always visible (no app to remember to open — out of sight is out of mind), tactile, zero notifications, zero subscription. Their failure modes: no reminders, no capture-anywhere, must be carried/maintained, and a skipped week of empty pages is its own guilt artifact (community consensus; see [memory-and-object-permanence](../foundations/memory-and-object-permanence.md)). Klyr should treat "as glanceable as a wall calendar, as persistent as a Time Timer" as a UX bar for widgets/ambient surfaces.

## Comparison table

Author's synthesis of the sources above. **Capture** = speed from thought to recorded task; **Maint.** = ongoing upkeep the tool demands to stay useful; **Shame risk** = likelihood that normal ADHD usage (lapses, overdue, partial completion) produces guilt-inducing UI states. Prices as reported 2025–2026 — re-verify before use.

| Tool | Core mechanic | Capture | Maint. | Shame risk | Gamification | Time support | AI | Price (reported) |
|---|---|---|---|---|---|---|---|---|
| Tiimo | Visual icon timeline for the day | Med | Med (plan daily) | Low | None | Visual timeline, widgets | Some (planning aids) | ~$54/yr [17] |
| Structured | Timeline day planner | Med | Med | Low–Med | None | Timeline | Premium tier | Free + ~$20/yr [24] |
| Routinery / Brili | Guided routine sequencer, step timers | n/a | Med (build routines) | Low–Med | Light (Brili rewards) | Per-step countdowns | None | Freemium subs [24][25] |
| Llama Life | One task at a time + countdown | Fast | Low | Low | Gentle (llama) | Countdown vs. estimate | Light | Sub, 7-day trial [15] |
| Goblin Tools | AI task breakdown ("spiciness") | Fast | None | None | None | Time estimator | Core | Free web; cheap apps [19][20] |
| Amazing Marvin | Toggleable strategy modules | Fast | Med–High (self-config) | Low (hideable debt) | Optional rewards | Timers, blocking, estimates | Light | $12/mo, $96/yr [10] |
| Lunatask | Encrypted tasks + habits + mood; no hard deadlines | Fast | Low–Med | Low | Light | Pomodoro | None | Freemium [22] |
| Numo | Gamified ADHD planner (quests, Karma) | Med | Low–Med | Low–Med | Core | Basic | None | Sub [23] |
| Focusmate | Live video co-working | n/a | Low | Low–Med (no-shows) | None | Fixed sessions | None | Free 3/wk; ~$8/mo [24] |
| Dubbii | Follow-along body-double videos | n/a | None | Low (low-demand ethos) | None | Task-length videos | None | ~$5/mo, $30/yr [30] |
| Inflow | CBT modules + coaching | n/a | Med (course progress) | Low–Med | Light | None | Some | ~$22–48/mo [37][38] |
| Shimmer | Human ADHD coaching | n/a | Low | Low | None | None | Human | $99–345/mo [39][40] |
| Todoist | General to-do, NL capture | Fast | Med | **High** (red overdue pile) | Karma (light) | Reminders only | Assist features | Freemium [34] |
| TickTick | To-do + calendar + Pomodoro | Fast | Med | **High** (overdue) | Light | Pomodoro, calendar | Light | Free; $35.99/yr [13] |
| Notion | Infinitely flexible workspace | Slow | **Very high** | Med (dead dashboards) | None | None native | Add-on sub | Freemium [7] |
| Sunsama | Daily planning ritual + timeboxing | Med | High (daily ceremony) | Low (gentle rollover) | None | Estimates, timeboxing | Light | $16–20/mo [13] |
| Motion / Reclaim | AI auto-scheduling calendar | Med | Med | Med (perpetual replan) | None | Auto-scheduled blocks | Core | ~$19–49/mo [42][43] |
| Finch | Self-care pet, reward-only | Fast (micro-tasks) | Low | **Very low** (pet never punished) | Core, gentle | None | None | Free; ~$10/mo; dynamic annual [8][13] |
| Habitica | RPG with HP loss for misses | Med | Med | **High** (punitive) | Core, punitive | None | None | Free + optional sub [48] |
| Forest | Grow tree while focused | n/a | None | Med (dead trees) | Core, loss-framed | Session timer | None | $3.99 once [45] |
| Freedom / Opal / one sec | App & site blocking / friction | n/a | Low | Low | None | Session blocks | None | $20–100/yr [45] |
| Due | Auto-snooze nagging reminders | Fast | Low | Low–Med (nag fatigue) | None | Escalating re-alerts | None | Paid app, Apple-only [49][50] |
| Time Timer | Physical shrinking red disc | n/a | None | None | None | Ambient analog time | None | One-time hardware [51][52] |

## Market gaps and positioning opportunities for Klyr

1. **Nobody owns the restart.** Every product implicitly assumes continuous use; lapses produce either visible debt (Todoist, Habitica, empty Notion dashboards) or silence. A product whose core loop includes *disappearing and returning* — with a warm, zero-debt re-entry — has no direct competitor. This is the largest gap and the one the retention data says matters most [1][2][6].
2. **The stack is the competitor.** ADHDers assemble Goblin (breakdown) + Tiimo/Structured (day) + Focusmate/Dubbii (starting) + Due (critical nags) + Finch (self-care) — 3–5 subscriptions and constant context-switching. An integrated capture→break-down→see-time→start→restart loop at one fair price directly attacks stack fatigue and the [ADHD tax](../daily-life/daily-life-impact.md) of forgotten subscriptions.
3. **Life-organizer depth without shame mechanics.** ADHD-native tools are day-planners "without project or task-manager depth" [17]; deep tools (Todoist, Notion, Asana) are shame machines under intermittent use. A tool holding long-horizon projects *and* honoring ADHD usage patterns is unclaimed territory.
4. **In-app novelty as a retention strategy.** Amazing Marvin proved switchable strategy modules keep novelty-seekers in-house [9][10], but buried the idea under a 300-setting learning curve. Klyr can ship the same insight with opinionated defaults and progressive disclosure: novelty *rotation*, not configuration overload.
5. **Trustworthy pricing as a feature.** The loudest 1-star themes in this market are billing betrayals: trial-to-charge ambushes (Opal, Motion) and dynamic pricing (Finch) [8][42][45]. Forest's $3.99 goodwill shows the counterfactual. Transparent billing, real free tier, easy cancel/export = differentiation, not just ethics (see [ux-design-for-adhd](ux-design-for-adhd.md) dark-patterns list).
6. **First-session value.** Goblin Tools became beloved by delivering value in <30 seconds with no account [19][20]. Klyr's onboarding competitor is not Tiimo's onboarding; it is Goblin's absence of one.
7. **The starting problem is monetized only by humans.** People pay $99–345/mo for coaching and $8/mo for strangers on video because *starting* is the bottleneck [24][39]. Any Klyr feature that reliably helps users start (breakdown at point of paralysis, body-double modes, warm nudges) taps the highest willingness-to-pay in the category.

## Design for the tool-switcher

The synthesis insight of this entire landscape: **the median ADHD user is a serial tool-switcher, and this is rational behavior, not user failure.** Novelty decay is intrinsic to ADHD motivation ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)); the mHealth literature even lists app-experimentation as a first-class abandonment driver [2]; community voices explicitly advise planning for rotation — when novelty fades, switching is fine, and "stepping away from something gives it the opportunity to feel new again" [53]. Products that fight the switcher (lock-in, sunk-cost streaks, punitive mechanics) get abandoned *harder*. Design consequences:

- **Assume episodic engagement.** Klyr should be built like a good friend, not a needy pet: fully useful on day 1, silently fine during week 5's absence, delightful on return in week 8.
- **Make state survive neglect.** Old tasks auto-fade/archive instead of rotting red; plans decay gracefully; nothing accumulates as visible debt.
- **Put novelty inside.** Rotating modes/themes/strategies give the switch-itch a destination inside Klyr (Marvin's lesson, simplified).
- **Free the data.** Painless export and import; import from Todoist/Notion/etc. respects where users came from and removes the "starting over" cost of committing to Klyr. Lock-in doesn't retain switchers — it just adds resentment to the churn.
- **Measure the right thing.** North-star metrics should include *return-after-lapse rate* and *time-to-first-completed-task*, never streak length or daily-open guilt levers.

## Design implications for Klyr

1. **Klyr must make re-entry after a lapse a designed, first-class flow** — e.g., "Welcome back — here's what still matters; everything else has been tidied away," with zero red debt. Rationale: the miss→shame→avoidance step is the documented kill-point of the lifecycle [6][7][34].
2. **Klyr must never display accumulating overdue counts, red badges of debt, or broken-streak states by default.** Overdue-pile shame is the single clearest abandonment mechanic in general task managers [8][34][45].
3. **Klyr should deliver value in the first session, before any setup** — capture something, break it down, start it, within ~60 seconds, no account wall for first value. Goblin Tools proves zero-friction is what earns ADHD love [19][20]; Notion proves setup-first kills [7].
4. **Klyr should keep total maintenance near zero and never require a ritual to stay functional.** Daily-planning ceremonies (Sunsama) and self-administered systems (Notion, Marvin's config) become second jobs; the system must remain useful when unmaintained [5][7][13].
5. **Klyr should make time visible ambiently** — Tiimo-style timelines, Time Timer-style shrinking-disc timers, widgets/glanceable surfaces — because passive externalized time is the most consistently praised ADHD affordance across digital and physical tools [16][17][51][52].
6. **Klyr should offer a one-thing-at-a-time focus mode** (current task + countdown, everything else hidden), the most-loved pattern in Llama Life and Marvin's Super Focus [9][14][16].
7. **Klyr should build AI task breakdown at the point of paralysis, with a granularity control** (Goblin's "spiciness"), invoked from any stuck task — the proven activation aid [19][20]; see [task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md).
8. **If Klyr gamifies, it must be Finch-shaped, never Habitica-shaped: reward presence, never punish absence.** No HP loss, no streak death, no dying trees; missed days are neutral. The Finch/Habitica contrast is the market's clearest natural experiment [8][45][46][48]; red lines detailed in [motivation-and-gamification](../strategies/motivation-and-gamification.md).
9. **Klyr should support persistent, escalating reminders for a tiny set of user-designated critical items (Due pattern) while keeping default notification volume low** — persistence beats loudness, but nag habituation is real [45][49][50]; budget notification trust like a currency ([ux-design-for-adhd](ux-design-for-adhd.md)).
10. **Klyr should ship swappable "modes"/strategies for planned novelty rotation, with opinionated defaults and progressive disclosure** — Marvin's retention insight without Marvin's 300-setting overwhelm [9][10][11].
11. **Klyr should integrate a starting-support surface** — body-double sessions (live, recorded, or AI-companion), warm start prompts — because starting is the bottleneck users already pay humans to solve [24][26][29][39].
12. **Klyr must use transparent, forgiving pricing: clear trial-end warnings, no dynamic pricing, easy cancellation, and a genuinely useful free tier.** Billing betrayal is a top-3 review complaint across this market and is disproportionately painful to people prone to forgotten subscriptions [8][42][45].
13. **Klyr must make data portable (easy import from Todoist/Notion/calendars, easy full export).** Tool-switchers are the market; lock-in converts churn into resentment, and import removes the cost of trying Klyr [2][7].
14. **Klyr should not position itself as "another planner" but own the full loop — capture → break down → see time → start → finish → lapse → restart.** Tension to manage: integrated scope fights implication 4's simplicity; resolve via progressive disclosure, not feature deletion.
15. **Klyr's success metrics must be lapse-tolerant** (return-after-absence, tasks *started*, first-session completion) — optimizing DAU/streaks would push the product back toward the guilt mechanics that kill its competitors [1][6][8].

## Open questions

- What do first-party app-store review corpora (not competitor syntheses) show at scale for Tiimo, Finch, and Todoist? A direct review-mining pass would firm up the themes cited here.
- What fraction of ADHD users actually run multi-app stacks, and what's the realistic consolidated price point? (No solid survey found in this pass — worth original user research.)
- Does in-app novelty rotation (Marvin-style) measurably extend retention for ADHD users, or does it just relocate the customization spiral? Needs A/B testing.
- Can an AI "body double" or warm-presence mode reproduce any of the human-presence starting effect? Evidence for even the human version is thin [28]; test with real users.
- Where is the line between Due-style helpful persistence and nag habituation for ADHD users specifically? Needs longitudinal testing of notification trust.
- How large is the paying market? Consumer willingness-to-pay signals are scattered (from $3.99 one-time to $345/mo coaching); no reliable ADHD-app market sizing was verified in this pass.
- Lapse-tolerant metrics conflict with investor-standard engagement metrics; what retention story does Klyr tell instead, and does return-after-lapse actually predict LTV?

## Sources

1. [research] [Baumel A, Muench F, Edan S, Kane JM (2019). Objective User Engagement With Mental Health Apps: Systematic Search and Panel-Based Usage Analysis. J Med Internet Res 21(9):e14567](https://www.jmir.org/2019/9/e14567/) — primary source for the 15-day retention figures; surfaced via [Scott Wallace's summary (Medium/Advances in AI for Mental Health)](https://medium.com/ai-in-mental-health/why-digital-mental-health-cant-keep-its-users-082051de6711)
2. [research] [User Engagement and Abandonment of mHealth: A Cross-Sectional Survey (PMC)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8872344/)
3. [research] [Effect of self-monitoring on long-term patient engagement with mobile health applications (PMC)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6062090/)
4. [research] [Usability and feasibility of a cognitive-behavioral mobile app for ADHD in adults (PLOS Digital Health)](https://journals.plos.org/digitalhealth/article?id=10.1371/journal.pdig.0000083)
5. [community] [Differentiation in personal productivity apps: tools for ADHD (Iterative Improvements, Substack)](https://iterativeimprovements.substack.com/p/differentiation-in-personal-productivity)
6. [community] [ADHD developer: I built the productivity system I wish existed (DEV Community)](https://dev.to/chudi_nnorukam_fb02ee5cb0/adhd-developer-i-built-the-productivity-system-i-wish-existed-4l20)
7. [product] [Notion Templates For ADHD: Why Your Brain Keeps Abandoning Systems (AFFiNE)](https://affine.pro/blog/notion-templates-for-adhd)
8. [community] [I Tested 10 Habit Trackers in 30 Days. 8 Broke Me the Same Way. (Tyler Ward, Medium)](https://medium.com/@wardtylerd/i-tested-10-habit-trackers-in-30-days-8-broke-me-the-same-way-9803ea20b228)
9. [product] [Amazing Marvin — The Customizable Task Manager for ADHD (official site)](https://amazingmarvin.com/)
10. [product] [Amazing Marvin Reviews (Product Hunt)](https://www.producthunt.com/products/amazing-marvin/reviews)
11. [community] [Making Amazing Marvin amazing — ADHD/executive functioning (Ask MetaFilter)](https://ask.metafilter.com/351417/Making-Amazing-Marvin-amazing)
12. [product] [Amazing Marvin — Apps for ADHD directory](https://appsforadhd.com/app/amazing-marvin)
13. [product] [5 to-do list apps that actually work with ADHD (Zapier, neurodivergent author)](https://zapier.com/blog/adhd-to-do-list/)
14. [community] [Review of Llama Life by an AuDHDer (Focus Bear blog)](https://www.focusbear.io/blog-post/review-of-llama-life-by-an-audhder)
15. [product] [ADHD Organizer: Llama Life (Google Play listing)](https://play.google.com/store/apps/details?id=com.llamaapp&hl=en_US)
16. [product] [6 Best Tiimo Alternatives for ADHD (Lifestack — competitor-authored)](https://lifestack.ai/blog/tiimo-alternative)
17. [product] [Tiimo Review 2026: Visual Planning for ADHD Brains (Selfpause)](https://www.selfpause.com/resources/tiimo)
18. [product] [Tiimo — Visual Planner for Every Neurotype (official site)](https://www.tiimoapp.com/)
19. [product] [About — Goblin Tools (official)](https://goblin.tools/About)
20. [product] [GoblinTools Reviews & Information (Gold Penguin)](https://goldpenguin.org/tools/goblintools/)
21. [product] [AI for ADHD: Best AI Tools and Assistants (Marblism)](https://www.marblism.com/blog/best-ai-tools-for-adhd)
22. [product] [Best ADHD Planner and Productivity App (Lunatask official ADHD page)](https://lunatask.app/adhd)
23. [product] [Numo: ADHD Planner for Adults (Google Play listing)](https://play.google.com/store/apps/details/Numo_ADHD_App_for_Adults?id=io.mindist.well&hl=en_AU)
24. [product] [6 Best Alternatives to Routinery for ADHD (Inflow — competitor-authored)](https://www.getinflow.io/post/best-alternatives-routinery-adhd)
25. [product] [Brili Routine Apps For Adults & Families with ADHD (official site)](https://brili.com/)
26. [clinical] [Could a Body Double Help You Increase Your Productivity? (CHADD Substack)](https://chaddhelp4adhd.substack.com/p/could-a-body-double-help-you-increase-5fd)
27. [community] [My Experience with Body Doubling on Focusmate (Abby Volk)](https://www.abbyvolk.com/post/my-experience-with-body-doubling-on-focusmate-a-digital-platform-for-folks-with-adhd)
28. [research] [You Are Not Alone: Designing Body Doubling for ADHD in Virtual Reality (arXiv, 2025)](https://arxiv.org/html/2509.12153v1)
29. [product] [Dubbii Body Doubling app review & alternative (Squad — competitor-authored)](https://www.joinsquad.co/compare/body-doubling-app-dubbii)
30. [product] [dubbii: the body doubling app (AppBrain listing)](https://www.appbrain.com/app/dubbii-the-body-doubling-app/com.gravitywell.adhdlove)
31. [product] [7 Best Body Doubling Apps for ADHD (Shimmer blog — competitor-authored)](https://www.shimmer.care/blog/best-body-doubling-apps)
32. [product] [Motion vs Sunsama: Which Tool Is Better? (Akiflow blog — competitor-authored)](https://akiflow.com/blog/motion-vs-sunsama)
33. [product] [Akiflow Alternatives: 6 Better Options (Efficient App)](https://efficient.app/alternatives/akiflow)
34. [product] [Todoist Pricing for ADHD: Free, Pro, and the Hidden Cost (Mutra — competitor-authored)](https://mutra.app/compare/pricing/todoist/)
35. [product] [ADHD Notion template listing (example of the paid-template economy, Gumroad)](https://notionforadhd.gumroad.com/l/ADHDdashboardessentials)
36. [product] [Motion vs Sunsama vs Akiflow: Which Task Planner is Best? (Rivva — competitor-authored)](https://blog.rivva.app/p/motion-vs-sunsama-vs-akiflow)
37. [product] [Inflow ADHD App Review (Choosing Therapy)](https://www.choosingtherapy.com/inflow-adhd-app-review/)
38. [product] [Inflow Review For ADHD App (FOCO)](https://www.tryfoco.com/inflow-review/)
39. [product] [Shimmer Care Review: Our Experience With ADHD Coaching (Zenmaster Wellness)](https://www.zenmasterwellness.com/shimmer-review/)
40. [product] [Premium ADHD Coaching, Without the Premium Cost (Shimmer pricing page)](https://www.shimmer.care/cost)
41. [product] [7 Best Akiflow Alternatives for Daily Planning (Lifestack — competitor-authored)](https://lifestack.ai/blog/akiflow-alternative)
42. [product] [Honest Motion Reviews: Features, Pricing, Pros, Cons (Saner.AI — competitor-authored)](https://www.saner.ai/blogs/motion-reviews)
43. [product] [Motion Pricing 2026: Pro $19, Business $29 (Alfred — competitor-authored)](https://get-alfred.ai/blog/motion-pricing)
44. [product] [Motion App Review 2026: Pros, Cons, Pricing & Verdict (Efficient App)](https://efficient.app/apps/motion)
45. [product] [Opal, Forest, Freedom, one sec, Jomo: 5 Screen Time Apps Ranked — aggregated review analysis (Unstar — competitor-authored)](https://unstar.app/blog/opal-forest-freedom-one-sec-jomo-screen-time-apps-ranked-2026)
46. [community] [Finch: ND-friendly self-care app (AuDHD Flourishing)](https://www.audhdflourishing.com/post/finch-adhd-self-care-app)
47. [community] [Managing Self-Care through the Finch App (University of Tennessee CEHHS)](https://cehhs.utk.edu/ero/managing-self-care-through-the-finch-app/)
48. [product] [5 Best Habitica Alternatives — includes long-term-user review themes (Habi — competitor-authored)](https://habi.app/insights/habitica-alternatives/)
49. [product] [ADHD Reminder Apps: We tested 20 Apps (Saner.ai blog — competitor-authored)](https://blog.saner.ai/best-adhd-reminder-apps/)
50. [community] [Due App (Reset ADHD — ADHD coach resource hub)](https://www.resetadhd.com/adhd-resource-hub/due-app)
51. [product] [Best ADHD timer (apps and physical) (Saner.ai blog — competitor-authored)](https://blog.saner.ai/best-adhd-timer/)
52. [community] [The Power Of Visual Timers: A Game-Changer (Life Skills Advocate)](https://lifeskillsadvocate.com/blog/the-power-of-visual-timers/)
53. [community] [How to ADHD reader notes on planning for novelty rotation (Goodreads notes on Jessica McCabe's How to ADHD)](https://www.goodreads.com/notes/125112558-how-to-adhd/70258846-kaja-trees/fc02d9d5-26c7-4312-9def-7a77a6710cc0)
