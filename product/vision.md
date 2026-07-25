---
title: "Klyr Product Vision"
file: product/vision.md
status: living
updated: 2026-07-25
informed_by: research/INDEX.md
summary: >
  Klyr is the executive function an adult with ADHD wears on the outside: a push-first
  delivery layer that holds memory, time, and next actions and lands them at the point of
  performance. It is designed for the worst week and the comeback, judged by
  return-after-lapse, and bound by the corpus's design constitution.
tags: [vision, product]
---

# Klyr Product Vision

*This vision is grounded in the research corpus ([INDEX](../research/INDEX.md)); where this document and the corpus conflict, the corpus wins until the conflict is resolved deliberately.*

P-numbers reference [design-principles](../research/product/design-principles.md), AP-numbers reference [anti-patterns](../research/product/anti-patterns.md), D-numbers reference [feature-directions](../research/product/feature-directions.md) with their confidence grades.

## TL;DR

- Klyr is **the executive function you wear on the outside**: it holds your memory, your time, and your next move and delivers them where and when the action happens — permanently; a prosthesis, never a training program (P1, P2).
- ADHD is a performance disorder, not a knowledge disorder: planning is the broken step (d = 1.60), execution largely intact once a concrete, cue-bound plan exists ([memory-and-object-permanence](../research/foundations/memory-and-object-permanence.md)).
- Competitors build a **place** to visit and maintain; Klyr is a **delivery layer** that goes to you; the gate: *if you ever have to remember to check Klyr, Klyr has failed.*
- The category's median day-15 retention is ~3.9% (mental-health-adjacent apps), and the community post-mortem locates the death at the missed day; Klyr expects you to disappear and makes coming back painless — the comeback is the core loop, built like autosave (P6, [app-landscape](../research/product/app-landscape.md)).
- First territory: the life load — bills, refills, chores, the dreaded call — where the ADHD tax bleeds and no ADHD-native tool yet competes (an open bet); win Tuesday night before Monday morning ([daily-life-impact](../research/daily-life/daily-life-impact.md)).
- Six pillars: blind-trust capture, point-of-performance delivery, physical time, startable sentences, organization as Klyr's chore, warmth as precision.
- Three loops close without user memory. The daily loop is the comeback loop at small amplitude; a comeback is just the most expensive start.
- V1 is 15 items skewed to capture, delivery, and time; the market's warmth features (body doubling, companions, chat) are deferred behind a month-three decision gate.
- North Star: **return-after-lapse** — engagement may veto, never justify; shame and demand-pressure stops are pre-registered; we never A/B test shame (P19).
- Your memory and the basic executive loop are free forever; zero third-party trackers (P18, AP-24).

## 1. Why Klyr exists

An adult with ADHD almost always knows what to do. The gap between knowing and doing *is* the condition: ADHD is a performance disorder, not a knowledge disorder ([executive-function](../research/foundations/executive-function.md)). The three internal resources every productivity tool quietly assumes — self-directed speech, felt time, summoned motivation — are precisely the weak ones: covert information is "weak as a source of stimulus control"; time collapses into now and not-now ([time-perception](../research/foundations/time-perception.md)); delayed payoffs are steeply discounted (d = 0.43) — *plans don't pull; ticking the box does* ([dopamine-and-motivation](../research/foundations/dopamine-and-motivation.md)).

A to-do list documents intentions — a record of the problem, not a solution. Worse, the standard app is a *pull* system, and "remember to check the app" is itself a prospective-memory task, the exact function that fails ([memory-and-object-permanence](../research/foundations/memory-and-object-permanence.md)); help delivered at planning time mostly does not transfer — it must land at the point of performance. The cost concentrates in unpaid, boring, recurring life work: an ADHD tax of roughly £1,600/year in one UK survey, ~46% of prescriptions refilled on time in one records study ([daily-life-impact](../research/daily-life/daily-life-impact.md)).

The tools sold as the fix become the injury. The community post-mortem is one sentence: *"find new system, get excited, customize obsessively, use it perfectly for 10 days, miss one day, feel guilty, avoid it, never open it again"* ([app-landscape](../research/product/app-landscape.md)). The missed day is scheduled — a feature of ADHD, not a user failure — but the abandonment is manufactured: one miss barely dents habit automaticity ([habits-and-routines](../research/daily-life/habits-and-routines.md)). What kills the practice is what the tool displays afterward, landing on someone pre-shamed and criticism-sensitive (emotional dysregulation in an estimated 34–70% of adults; [emotional-regulation-and-rsd](../research/foundations/emotional-regulation-and-rsd.md)). *"You feel guilty every time you open it. So you stop opening it."*

What makes this buildable: planning, not execution, is the broken step (d = 1.60) — hand someone a decided, cue-bound first step and they disproportionately finish (if-then plans d ≈ 0.65 in general populations; child-ADHD replications, adult trials pending; [evidence-based-strategies](../research/strategies/evidence-based-strategies.md)); externalizing time moved parent-rated daily time management by d = 1.0 (child-ADHD RCT, time training and devices combined). You cannot train the sense of time; you can hand someone a clock they can feel.

The missing product is not a better container for tasks. It is a **delivery system for executive control at the moment of action** — trusted blindly, maintained never.

## 2. Who Klyr is for

One primary user: an adult with ADHD — diagnosed or self-recognized; no diagnosis gate (P16) — carrying a full life-load: job, household, admin, people. Over half of diagnosed US adults were diagnosed *as* adults; many arrive with relief and grief at once, decades of "not trying hard enough," and the lesson every buried planner taught: organizing tools accuse ([adhd-overview](../research/foundations/adhd-overview.md), [emotional-regulation-and-rsd](../research/foundations/emotional-regulation-and-rsd.md)).

We design for **states of that one person, not personas** ([populations-and-variation](../research/foundations/populations-and-variation.md)): honeymooner in week one, steady in week three, ghost in week six, wary returner in week nine. A boom-week overcommitter, a trough-week avoider — capacity collapse is a scheduled event, not an edge case ([when-to-back-off](../research/product/when-to-back-off.md)). Seasonal selves too: newly diagnosed; luteal or perimenopausal weeks (user-declared, never inferred); AuDHD seasons where surprise is a threat and change must be announced; the month-three self, for whom nothing here is novel.

Two consequences are law: defaults are set for the most sensitive state — capacity is weather, not character (P14) — and everything contested ships as a dial with a calm default, never a house style (P16). A prosthesis that works only in your good state is not a prosthesis.

## 3. The bet

Klyr's position, straight from the corpus: **the tool that expects you to disappear and makes coming back painless** ([app-landscape](../research/product/app-landscape.md)). Every competitor builds a place the user goes to manage tasks — each solving one mechanism (hence 3–5-app stacks); day planners lack depth; power tools are shame machines; nobody owns the restart — and all assume the user will come and maintain it: exactly what ADHD makes expensive. We believe five things competitors do not:

1. **The app is not the product; the moments it lands correctly in your day are.** The best session is three seconds on a lock screen; time-in-app is a cost ([outcomes-and-measurement](../research/product/outcomes-and-measurement.md)). The binding gate: *if you ever have to remember to check Klyr, Klyr has failed* (P1, P2).
2. **The lapse cannot be prevented, only survived.** The industry tries to out-notify neurobiology, and the pings poison the return; we spend nothing preventing absence and everything on the reunion — the first *return*, not the first session, decides the relationship (P6).
3. **The serial tool-switcher is the market, not churn.** A ~3.9% day-15 baseline for mental-health-adjacent apps means the market continually re-enters play; being easy to leave — free export, cheap cancellation, respectful imports — is why people stay, and come back (D44 promising).
4. **The first territory is the life load, not the work calendar.** Impairment scales with how boring, recurring, multi-step, and audience-free a task is — the tax bleeds at rent, refills, laundry, the dreaded form ([daily-life-impact](../research/daily-life/daily-life-impact.md)). Win Tuesday night before Monday morning.
5. **Blind trust is the moat.** Capture that never loses a word, a reminder channel that never lies and never spams — features get copied; trust compounds. We bet that for this user, the winning interface is mostly *not being an interface*.

## 4. Pillars

**1. Capture you trust blindly.** Under three seconds, zero decisions, from anywhere, before any account — then never silently lost, altered, or expired; searchable forever; exportable in one tap. The mind releases an open loop only when it trusts retrieval; one dropped item collapses the prosthesis ([memory-and-object-permanence](../research/foundations/memory-and-object-permanence.md); P3, P4). **Rules out:** required fields at capture, account walls, expiry, text-eating sync (AP-14, AP-20, AP-21).

**2. Deliver at the point of performance.** Push-first: cues arrive where and when the action happens, carrying the decided first move; event anchors beat clock times (if-then binding, d ≈ 0.65; [evidence-based-strategies](../research/strategies/evidence-based-strategies.md); reminder science: [memory-and-object-permanence](../research/foundations/memory-and-object-permanence.md)); glanceable surfaces outrank dashboards (P1, P2, P15). **Rules out:** features that depend on opening the app or holding a ritual (AP-16), engagement pings (AP-11); a notification without an action ("Report") is a defect.

**3. Time is a physical object Klyr holds.** Duration renders as space; reminder salience follows a J-curve into the real deadline window; departures get leaving-soon countdowns to *stop-doing-things* time; defaults respect delayed chronotypes ([time-perception](../research/foundations/time-perception.md); P9). Sharpest case: bills, refills, renewals, appointments get lead-time runways Klyr holds — framed as tax avoided ("renewal caught 5 days early"), never a tally of what forgetting cost ([daily-life-impact](../research/daily-life/daily-life-impact.md); D10 promising). **Rules out:** numerals-only deadlines, uniform nags, fake countdowns, ambient red urgency — urgency is user-summoned or it does not exist (AP-8, AP-9, AP-19).

**4. Everything leads with a startable sentence.** Every surface leads with a concrete next physical action, not a task noun, and Klyr does the decomposing ([task-initiation-and-paralysis](../research/daily-life/task-initiation-and-paralysis.md); P8). Any task is one tap from its 2-minute version; one-thing-now and "I'm stuck" are one tap away (P12). AI serves this invisibly — suggest, preview, undo; never a silent write, never a chat front door ([ai-assistance-for-adhd](../research/product/ai-assistance-for-adhd.md); P17). **Rules out:** unstartable noun lists, "just break it down" homework, blank canvases (AP-15), perfect-or-failed day grades (AP-7).

**5. Organization is Klyr's chore, not yours.** No weekly review, no filing, no grooming — ever. Klyr reviews continuously with single keep/shrink/let-go taps, ages items into amnesty, compresses missed cycles, reflows and auto-closes blamelessly, and stays correct after two weeks of silence — every move legible and reversible ([planning-methodologies-and-adhd](../research/strategies/planning-methodologies-and-adhd.md); P5, P6, P7, P17). This machinery is autosave: invisible until needed, never discussed on the daily surface — no "when you fall off" copy anywhere. **Rules out:** ritual dependency, maintenance debt, customization rabbit holes, feature bloat, rigid auto-schedules, overdue arithmetic — the 47-item red pile is structurally impossible, not suppressed (AP-1, AP-16, AP-17, AP-18, AP-19, AP-21).

**6. Warmth is precision, not personality.** Warmth lives in exactly three moments: instant, unconditional acknowledgment of every action — starts and partials included; delight may vary, arrival never does (P10, P11; [dopamine-and-motivation](../research/foundations/dopamine-and-motivation.md)); the comeback (P6); and copy that passes "would a good ADHD coach say this mid-shame-spiral?" (P5; [emotional-regulation-and-rsd](../research/foundations/emotional-regulation-and-rsd.md)). Motivation invites, never coerces: pressure is opt-in equipment and repeated deferrals *lower* it ([motivation-and-gamification](../research/strategies/motivation-and-gamification.md)); rewards aim only at aversive tasks, never loves; the one-tap low-day dial makes the user the sensor (P14). Everywhere else, calm utility *is* the warmth: to someone whose tools have been disappointed parents, reliability is what care feels like. A good prosthesis loves you by working. **Rules out:** punishment, streak hostage-taking, guilt copy, leaderboards, casino mechanics, state inference, mascots and chatty personas in v1 (AP-2–AP-6, AP-10, AP-22).

## 5. The core loops

Three loops close without user memory and survive being skipped. They nest — **the daily loop is the comeback loop at small amplitude**, and **a comeback is just the most expensive start** — one engine for the lunch resume, the derailed Tuesday, the three-week silence (P6, P7).

**Capture loop (seconds → days).**
1. A stray thought is captured in under three seconds, from any surface.
2. A visible "got it" lands, and the mind lets go.
3. Later, at a natural moment, one skippable question: next step, a date, or leave it parked?
4. The item becomes a startable sentence bound to a cue.
5. It lands at its point of performance — the loop closes when the cue fires, never when the user remembers.
6. Parked items provably come back.

**Daily loop (one day).**
1. The day assembles itself: calendar skeleton, 1–3 protected items — Klyr proposes, the user confirms (P17's preview moment) — and the bench beneath.
2. Ordering is warm-up-first by declared state; in v1, "state" means the low-day dial plus time of day (richer inputs wait with D9). Hardest-first is doctrine for only 7% of surveyed ADHDers ([evidence-based-strategies](../research/strategies/evidence-based-strategies.md)).
3. Cues land where the user is, carrying the decided first move.
4. Acknowledgment is instant; starts and partials count.
5. Exits — leaving the one-thing-now view, or marking an item started or paused — offer a skippable resume note; the next action surfaces with no re-decision gap.
6. Stuck collapses to one small action.
7. Slips reflow with visible reasoning and undo; wreckage never renders.
8. The day auto-closes blamelessly. The minimum obligation is zero.

**Comeback loop (days → months).**
1. Silence. No guilt pings, ever.
2. Klyr quietly tidies: amnesty parks with traces, cycles compress, plans reflow.
3. The return lands calm and current: a neutral hello; "here's what we tidied — undo anything"; one small next action plus the last resume note.
4. The restart is celebrated as a win.
5. Full state, zero make-up work, no gap arithmetic.
6. Another silence arrives eventually — expected, unfeared.

## 6. What Klyr is not

- **Not a medical device or treatment.** No diagnosing, screening, or treating; no copy implying it (P20; [when-to-back-off](../research/product/when-to-back-off.md)).
- **Not a training program.** No graduation mechanics or fading reminders — gains persist only as long as the scaffold does (P1; AP-23).
- **Not an AI companion.** Task-anchored assistance only — the corpus's hard no-companion line ([ai-assistance-for-adhd](../research/product/ai-assistance-for-adhd.md)).
- **Not a Notion-style canvas.** Klyr ships working defaults; users never build the system to get one (AP-15).
- **Not a social network.** No feeds, leaderboards, or public failure; future presence features are chosen-peer and opt-in (AP-6).
- **Not a surveillance wellness app.** No mental-state inference, no mood mining, no third-party trackers (P18; AP-22, AP-24).
- **Not a gamified casino.** No paid or scarcity-mediated randomness (AP-10).
- **Not an engagement business.** A shorter, better-placed session beats a longer one (P19).

## 7. V1 scope

The smallest Klyr that embodies all six pillars — skewed toward capture, delivery, and time: the prosthesis's spine.

**The spine** — what the product cannot exist without: capture (1), next-action extraction (2), cue binding (3), the reminder engine (6), amnesty and elastic recurrence (11), the restart ritual (13), and instant acknowledgment (14). **Launch platform: one mobile OS first** — widget, lock screen, and share sheet *are* the product; desktop follows. If v1 must shrink further, cut in this order: item 15's presets, item 9's state-based ordering, item 8's life-deadline runways, item 7's leaving-soon mode — never the spine. **Fast-follows, deliberately outside the fifteen:** voice capture, the desktop overlay, Todoist/Notion/plain-text importers with drip triage (D44 promising), and the breakdown granularity dial.

1. **Instant capture + nothing-lost trust surface** (D1 evidence-backed; D2 promising): sub-3-second zero-field capture from widget, lock screen, and share sheet; one search over everything ever captured; export free forever. First run *is* capture: something captured within 60 seconds, before any account exists, zero configuration, value before signup (P3; AP-14) — arrival and restart share the same calm-landing machinery.
2. **Next-action extraction + task shrinking** (D3, D12 evidence-backed; D39, D40 promising): every item one tap from a startable sentence and a 2-minute version; suggest → preview → undo only — invisible-first AI with visible provenance (D40).
3. **If-then cue binding** (D5 evidence-backed): event anchors as the first-class reminder type; clock times are offered conversion.
4. **Drip-fed clarification** (D4 promising): one skippable question at natural moments; no inbox-zero surface exists anywhere.
5. **Glanceable ambient surface** (D42 promising; D27 evidence-backed): 1–3 rotating next actions plus time-left-in-block on widget and lock screen — the primary product surface.
6. **Reminder engine with a trust budget + low-day dial** (D37, D36-lite promising): interrupts and batched digests only, action in the body, quiet hours default-on; snooze-death becomes triage at ~3; three ignores change strategy, never volume; one-tap renegotiation; a no-explanation low-day dial quiets all but the user's designated critical anchors (Klyr may suggest rent/refill candidates; the user confirms them); recurring items skip, not stack.
7. **Visual time: J-curve salience + leaving-soon mode** (D27 evidence-backed; D29 promising): shapes beside numerals; salience concentrated in the final window; stop-doing-things countdowns before departures; before an appointment, a guaranteed interrupt — "I'll tell you at 2:35" — so the wait doesn't have to consume the afternoon (D8's load-bearing piece).
8. **Life deadlines with runway** (D10 promising, deadline species only): bills, refills, renewals, appointments as first-class objects with lead-time defaults and concretized first steps — no budgeting module, no health suite.
9. **Tiny day plan on the calendar skeleton** (D6, D43, D13 promising): 1–3 protected items plus bench; warm-up-first state-based ordering; *read-only* calendar sync in v1.
10. **Self-healing reflow, legible** (D7 promising): automatic replan with one-line reasoning and undo; no rescheduled-count ever shown.
11. **Amnesty, resurfacing, elastic recurrence** (D23, D24 promising): aging items park with visible traces — overdue cannot render; missed cycles compress to one next instance; parked items resurface a few at a time: "Still matter? Shrink it? Let it go?"
12. **Automated review + blameless auto-close** (D22 promising): days close themselves; recaps read "what moved, what carried," never "what you missed."
13. **The restart ritual** (D26 promising): the hero flow — neutral welcome, tidied state with an undoable trace, one small re-entry action; restart latency instrumented from day one.
14. **Instant acknowledgment + resume bookmarks + finish states beyond done** (D30, D19 evidence-backed; D21 promising): sub-400 ms, unconditional; every exit offers a skippable breadcrumb, rendered first on reopen; started / partial / paused are celebrated states.
15. **One-thing-now, I'm-stuck collapse, calm intensity presets** (D15, D17, D38 promising): the whole UI collapses to one small action on demand; motion, sound, and celebration dials default calm; literal copy as house style; celebration content itself rotates on a small cycle — a zero-setup novelty valve (P13; D31-lite) so acknowledgment never goes stale.

D28 (learned duration correction, promising) runs dark: actuals collected, nothing surfaced until confidence is real.

**Deliberately not in v1:**

- **The warmth cluster** — body doubling (D16), companion (D35), unstick chat (D41), all promising: the market's most-loved, highest-willingness-to-pay features, deferred so the calm substrate proves itself solo and social RSD surfaces stay at zero; the riskiest cut, gated at month three (section 12).
- **Pressure and reward layering** — urgency rack (D34), temptation bundling/dopamine menus (D33), promising: the house stays calm until these are genuinely opt-in with tripwires.
- **Novelty rotation (D31, promising):** the surface/substrate split is architectural from day one, and v1 ships only the D31-lite celebration rotation (item 15); the full wardrobe arrives when month-three data says boredom drives churn.
- **Energy windows and cycle-aware options (D9, promising):** sensitive-tier consent architecture first (P18). **Full Essentials mode (D36, promising):** the low-day dial plus skip-not-stack plus amnesty carries troughs; the mode that quiets everything but user-designated anchors follows.
- **Waiting-mode day layout (D8, remainder), routine menus (D11), soft landings (D20)**, all promising — item 7 carries D8's load-bearing guaranteed interrupt; the gap-sized task offers wait. **Launch rituals (D14), flow-respecting timers (D18), forgiving consistency metrics (D32)**, all promising: D18 is first in line beside the warmth gate (timers pair naturally with body doubling), and D32 is the sanctioned future consistency lane, distinct from the banned streak package (AP-3). **Dread receipts (D25, speculative):** dark-launch data only.
- **Deep project hierarchies, two-way calendar sync (D43), shared household lists (D45), opt-in streak mode** (AP-3 package — possibly never). A v1 "project" is a parked bundle with a next action; long-horizon depth is the year-two move into the market's third gap ([app-landscape](../research/product/app-landscape.md)).

## 8. How it should feel

Like a good prosthesis: you notice that it works, not that it is there.

- **Instant.** Feedback under ~400 ms; cold starts and sync spinners are motivational taxes ([ux-design-for-adhd](../research/product/ux-design-for-adhd.md); P11).
- **Calm.** One primary action per screen; salience is rationed; red is never the resting color of anything (P12, P14). Density and celebration are dials defaulting low — stimulation-seekers turn it up; nobody has to turn it down (P16).
- **Literal.** Buttons say what they do; no idioms, sarcasm, or action-hiding cuteness; dyslexia-safe typography as the floor ([populations-and-variation](../research/foundations/populations-and-variation.md)).
- **Legible.** Every automatic move shows one line of reasoning and offers undo; "hidden, not lost" is stated in the UI (P17, P4).
- **Quietly kind.** Every sentence passes the coach-mid-shame-spiral test; error states blame the system; self-compassion used sparingly, never as lecture ([emotional-regulation-and-rsd](../research/foundations/emotional-regulation-and-rsd.md); AP-5). The voice is a competent, unbothered assistant who has seen your mess and is not worried.

The feeling that matters most is the reopen after absence: not dread — relief. If a surface reads as a disappointed parent, it does not ship.

## 9. Success

**North Star: return-after-lapse** ([outcomes-and-measurement](../research/product/outcomes-and-measurement.md); P19). Of users who go quiet after regular use, the share who return and act in their first session back — complete, shrink, or consciously release an item, mirroring amnesty's choices — with no guilt prompt having fired. Definitions, since Klyr's success mode is not opening the app: *activity* is any meaningful action on any surface — a notification action, a widget interaction, a capture, an in-app act; a *lapse* is the absence of all of these for N days (N is a calibration question), and comeback tidying keys off the same definition. Thresholds are calibration questions; verdicts read at month three+, never on honeymoon data (P13). Proxies (hypothesis-grade): **restart latency**, **resurfaced-item action rate**, **capture-to-next-action**. Functional tier: opt-in validated instruments, quarterly, aggregate, never gates.

**Guardrails — watched, never optimized; stop conditions pre-registered:**
1. **Shame risk:** overdue-anxiety growth, churn attributable to specific surfaces, negative check-in sentiment; we never A/B test shame or pressure — there is no equipoise.
2. **Amnesty-undo rate:** reversals mean the machine ate things users still wanted — "the app deleted my task" is a P4 violation in the user's eyes.
3. **Notification trust:** action and ignore/override trends — habituation is channel death, and the channel is the product.
4. **Demand pressure:** deferral rates rising after prompts auto-de-escalate the feature — the demand-sensitivity tripwire.
5. **Real-world safety:** user-designated critical anchors (rent, refills, and the like) must not be missed more during low-capacity weeks than baseline — forgiveness that costs the rent is a failed design.
6. **Time-in-app, watched as a cost:** for an overwhelm-reducing tool, more is often worse.

**Anti-metrics — banned as success measures:** DAU, streak length, task throughput, time-in-app, overdue counts, honeymoon NPS (P19). Standing Goodhart clause: any activation count is a diagnostic, never a target — the moment we maximize it, we have built the nag.

## 10. Trust economics

One transparent, stable subscription inside the documented $30–100/year ADHD-native norm ([app-landscape](../research/product/app-landscape.md)). The split protects the thesis: **your memory and the basic executive loop are free forever.** Capture, search, archive, export, the tiny day plan, basic point-of-performance reminders, the widget, amnesty, and the restart never cost money and never lapse — and the loop stays startable and wreckage-free for everyone: baseline next-action extraction, the 2-minute shrink, single-day blameless reflow, and auto-close are inside the free executive loop (P7, P8; AP-19). A free user gets a push-first prosthesis, not a documented-intentions app. Payment buys depth and scale — deeper and higher-volume AI breakdowns, multi-day and multi-project schedule optimization, deeper life lanes — never relief from manufactured pain, never the difference between helped and accused.

The rails: payment never touches data — read and export stay free (AP-13); trials warn loudly, never convert silently; cancellation in-app in ≤2 steps (AP-12); no dynamic pricing, no paid randomness (AP-10); long-inactive subscribers are offered a pause, not a silent renewal — we will not earn a dollar from prospective-memory failure; resubscribing lands on the restart ritual, not a guilt screen.

Privacy is architecture, not copy (P18; [privacy-and-data-ethics](../research/product/privacy-and-data-ethics.md)): zero third-party ad or analytics SDKs (AP-24); two-tier storage — recoverable encryption for the task graph, local-first optionally-E2E sensitive fields; behavioral exhaust ages out; "forget this period" is honest, propagating deletion; consent just-in-time, per-category, default-off. Claims stay inside the evidence — a tool, never a treatment; "many people find…" vs. "research shows…" used honestly (P20; AP-23). In this market, billing and privacy honesty is not overhead — it is the positioning.

## 11. Platform posture

Klyr lives where the moments are, not where the dashboard is: lock screen, notification shade, and widgets first; share sheet and voice; a two-keystroke desktop overlay; only then the app — glanceable surfaces outrank in-app screens (P2). Capture works offline and never waits on a network: feedback is local and sub-second; AI parsing runs after, off the critical path (P3; [ai-assistance-for-adhd](../research/product/ai-assistance-for-adhd.md)).

The calendar is read as the day's skeleton in v1 and written to not at all; two-way sync arrives only when it cannot betray the trust contract (D43; P4). Redundancy hedges the OS-owned channel: if notifications are throttled, the widget still shows the next action; if both fail, the app opens on a calm, current today. No stack choices here — though any stack that cannot deliver sub-second capture and fresh ambient surfaces is disqualified.

## 12. Risks and open questions

1. **The warmth bet may be wrong.** The category's biggest documented spend targets the starting problem (coaching at $99–345/month is priced accountability for getting started); body doubling is the community's most-loved starter (85% of 220 surveyed; no trials) — and v1 ships neither presence nor companionship, betting that task-anchored starters (shrinking, cue binding, the stuck collapse) carry that weight. Mitigation: the month-three gate, pre-registered like the guardrails — if return-after-lapse misses its calibration target, or churn interviews cite isolation or missing accountability above a pre-set rate, the warmth cluster moves up, body doubling (D16) first; cohorts who requested it are the comparison group that isolates the effect.
2. **Channel and cue fragility.** The thesis rides on OS-throttled notifications and widgets, where habituation is documented (alerts overridden at 49–96% in clinical settings); event anchors misfire in chaotic lives; amnesty is a knife-edge between relief and "the app deleted my task." Every mitigation — J-curve, form-shifting resurfacing, the trust budget, surface redundancy — rests on parameters the corpus flags as untested ([anti-patterns](../research/product/anti-patterns.md)).
3. **Objective benefit without felt benefit.** In the time-externalization RCT (children; time training and devices combined), observer-rated function moved (d = 1.0) while self-ratings did not. A prosthesis can work without feeling like it works; retention and word of mouth run on feelings, and P20 forbids closing that gap with claims.
4. **Ordinary bugs are trust breaches.** Fifteen ambient, OS-integrated systems mean a stale widget or one eaten capture is not a defect ticket but a P4 breach of the only contract that matters. Engineering quality is product strategy.
5. **The frame underweights emotional paralysis.** Procrastination is mood repair ([task-initiation-and-paralysis](../research/daily-life/task-initiation-and-paralysis.md)), and the right sentence at the right moment can still lose to the Wall of Awful ([emotional-regulation-and-rsd](../research/foundations/emotional-regulation-and-rsd.md)). V1's answers — shrinking, the stuck collapse, amnesty, valves — are structural, not emotional; some users will need mood-side equipment sooner, and the month-three gate exists for them too.
6. **Forgiveness may dissolve stakes, and the life wedge may be refused.** Whether forgiving metrics sustain behavior as well as stakes is untested ([habits-and-routines](../research/daily-life/habits-and-routines.md)); over-elastic recurrence can stretch consequences until plants die. And users may not want bills and refills inside a task app ([daily-life-impact](../research/daily-life/daily-life-impact.md) flags it open); if the life wedge is rejected, a simpler day planner beats us on calm.
7. **Klyr's own honeymoon.** The novelty honeymoon is named in the corpus as Klyr's single biggest product risk ([dopamine-and-motivation](../research/foundations/dopamine-and-motivation.md)) — and it applies to Klyr. Excitement fades on schedule; v1 bets quiet correctness survives boredom better than fresh paint; if month-three data disagrees, rotation moves up (P13). Also: quiet utility demos badly; the free layer may suppress conversion; the North Star spends money dashboards bank. The vision only works if the company holds P19 under growth pressure — a governance risk; naming it is the first control.

**Open questions:** amnesty pacing; urgency dosage and decay; default density and celebration intensity; restart-ritual tone; whether return-after-lapse predicts LTV; rotation cadence; measuring felt benefit without manufacturing self-judgment. Until answered, the calm, forgiving, autonomy-preserving option is the default ([design-principles](../research/product/design-principles.md)).

## Appendix: traceability

| Pillar | Design principles | Key evidence docs | Guards against |
|---|---|---|---|
| 1. Capture you trust blindly | P3, P4 | [memory-and-object-permanence](../research/foundations/memory-and-object-permanence.md), [ux-design-for-adhd](../research/product/ux-design-for-adhd.md) | AP-14, AP-20, AP-21 |
| 2. Deliver at the point of performance | P1, P2, P15 | [executive-function](../research/foundations/executive-function.md), [evidence-based-strategies](../research/strategies/evidence-based-strategies.md) | AP-11, AP-16 |
| 3. Time is a physical object Klyr holds | P9 | [time-perception](../research/foundations/time-perception.md), [daily-life-impact](../research/daily-life/daily-life-impact.md) | AP-8, AP-9, AP-19 |
| 4. Everything leads with a startable sentence | P8, P12, P17 | [task-initiation-and-paralysis](../research/daily-life/task-initiation-and-paralysis.md), [ai-assistance-for-adhd](../research/product/ai-assistance-for-adhd.md) | AP-7, AP-15 |
| 5. Organization is Klyr's chore | P5, P6, P7, P17 | [planning-methodologies-and-adhd](../research/strategies/planning-methodologies-and-adhd.md), [habits-and-routines](../research/daily-life/habits-and-routines.md) | AP-1, AP-16, AP-17, AP-18, AP-19, AP-21 |
| 6. Warmth is precision, not personality | P5, P10, P11, P14, P16 | [emotional-regulation-and-rsd](../research/foundations/emotional-regulation-and-rsd.md), [motivation-and-gamification](../research/strategies/motivation-and-gamification.md), [when-to-back-off](../research/product/when-to-back-off.md) | AP-2, AP-3, AP-4, AP-5, AP-6, AP-10, AP-22 |
| Cross-cutting: money, data, claims | P18, P19, P20 | [privacy-and-data-ethics](../research/product/privacy-and-data-ethics.md), [outcomes-and-measurement](../research/product/outcomes-and-measurement.md) | AP-12, AP-13, AP-23, AP-24 |
