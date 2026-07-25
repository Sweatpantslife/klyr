---
title: "Task Initiation, ADHD Paralysis, and Procrastination"
area: daily-life
file: research/daily-life/task-initiation-and-paralysis.md
tags: [task-initiation, task-paralysis, procrastination, activation, implementation-intentions, body-doubling, next-action, urgency]
related:
  - research/foundations/executive-function.md
  - research/foundations/emotional-regulation-and-rsd.md
  - research/foundations/time-perception.md
  - research/strategies/evidence-based-strategies.md
  - research/daily-life/habits-and-routines.md
sources: 26
updated: 2026-07-25
summary: >
  Why starting is mechanically the hardest moment for ADHD brains: the executive + emotional + reward
  forces that stack at the start line, the flavors of paralysis, the emotion-regulation model of
  procrastination, and the interventions with real evidence. Read before designing anything in Klyr
  that asks a user to begin, resume, or choose a task.
---

# Task Initiation, ADHD Paralysis, and Procrastination

## TL;DR

- Starting a task is the single point where three ADHD-relevant systems fail **simultaneously**: executive machinery (sequencing, self-activation), emotion regulation (avoiding the bad feeling the task triggers), and the reward gradient (all cost is now, all payoff is later). Once a task is underway, it supplies its own stimulation; initiation is the expensive step.
- **ADHD paralysis** (community term, clinically plausible) comes in flavors: task paralysis (can't begin), choice paralysis (can't pick), and overwhelm/mental freeze (can't think). In one small 2025 self-report study of 50 adults with ADHD, 82% reported frequent decision-making difficulty and 58% experienced decision paralysis at least weekly.
- Procrastination is best understood as **short-term mood repair**: we delay to escape the negative feelings a task raises, "giving in to feel good" now and billing the future self (Sirois & Pychyl). Lab mood inductions alone are enough to make people procrastinate.
- ADHD multiplies this: one analysis reported ~75% of adults with ADHD classified as chronic procrastinators vs. ~35% of controls, with inattention — not hyperactivity/impulsivity — the symptom cluster that predicts procrastination.
- **Task ambiguity is a silent blocker**: an item with no defined next physical action gets skipped every time the user scans their list. Crucially, breaking work down is itself an impaired executive function in ADHD — "just decompose it" outsources the hardest step to the person least equipped for it at that moment.
- Perfectionism delays starting via **fear of failure**, which research suggests largely or fully mediates the perfectionism → procrastination link. Lowering the stakes ("ugly first draft") attacks the actual mechanism.
- "Waiting to feel like it" is backwards: behavioral-activation research (meta-analytic SMD ≈ −0.74 vs. controls in depression) shows action precedes motivation, not the reverse.
- Every transition is a fresh initiation event — each interruption or resume re-pays the full start cost, which is why fragmented days are so lethal to ADHD productivity.
- The **last-minute panic engine** genuinely works (deadline proximity finally compresses the reward gradient) but at severe cost: chronic stress, unreliability, burnout — and research finds "I work best under pressure" is largely self-deception.
- The strongest verified starter tools: implementation intentions (meta-analytic d = 0.65; replicated in ADHD samples by Gawrilow and colleagues), shrinking the first step, body doubling (community-validated, mechanism plausible, no controlled trials yet), launch rituals/countdowns, and manufactured urgency in safe doses.

## What actually happens at the moment of starting

For a neurotypical brain, "start the report" is one mental event. For an ADHD brain it is a pileup of three separate failures at one instant — which is why initiation, not effort or ability, is where things break.

**1. The executive layer.** Initiating requires holding the goal in working memory, sequencing the first moves, suppressing whatever is currently more interesting, and self-activating without an external trigger. These are exactly the functions impaired in ADHD (see [Executive function](../foundations/executive-function.md) — Barkley's point that ADHD is a *performance* disorder, not a knowledge disorder, and Thomas Brown's "activation" cluster). The person knows what to do and often genuinely wants to do it; the machinery that converts intention into motion misfires. Clinicians describe **task initiation** as the transition between thinking about a task and engaging with it — and note that for ADHDers "the challenge is rarely in continuing; it is in starting" [19].

**2. The emotional layer.** Most delayed tasks are **aversive** — boring, frustrating, ambiguous, or tied to past failure. Contemplating them produces a real negative feeling, and the fastest way to end that feeling is to look away. This is the engine of procrastination (next section), and in ADHD it is amplified by stronger, faster emotional responses (see [Emotional regulation and RSD](../foundations/emotional-regulation-and-rsd.md)).

**3. The reward-gradient layer.** At the start line, all of the cost is immediate and all of the payoff is distal. ADHD brains discount delayed rewards more steeply than average (see [Dopamine and motivation](../foundations/dopamine-and-motivation.md) and [Time perception](../foundations/time-perception.md)), so a task whose reward arrives in two weeks exerts almost no pull *today*. Steel's meta-analysis of the procrastination literature (691 correlations) found the strongest predictors of delay were **task aversiveness, task delay, low self-efficacy, and impulsiveness** — a pattern he formalized as **temporal motivation theory** (TMT): motivation = (expectancy × value) ÷ (1 + impulsiveness × delay) [2]. Every term in that equation moves the wrong way for ADHD.

Once a task is actually underway, it supplies its own stimulation, feedback, and micro-rewards; continuing is far cheaper than starting. The community shorthand — tasks have high **activation energy** — is chemically apt: the barrier is at ignition, not during the burn.

## The flavors of ADHD paralysis

**ADHD paralysis** is not a diagnosis; it is a community-coined umbrella term (status: community term, clinically endorsed as a description) for the frozen state where a person cannot convert intention to action. Community and clinical sources consistently describe three flavors [15][16]:

| Flavor | What it looks like in real life |
|---|---|
| **Task paralysis** | Sitting on the couch for two hours "about to" start laundry; opening the document and staring; doomscrolling *while feeling* the task loom |
| **Choice paralysis** (decision paralysis) | Can't pick which of 14 to-dos to start, so starts none; 40 minutes choosing what to eat; abandons an app because setup asked too many questions |
| **Overwhelm / mental freeze** | Too many inputs at once → thinking itself jams; can't speak, plan, or move; often ends in shutdown or an escape activity |

Cleveland Clinic pediatric behavioral health specialist Michael Manos frames the mechanism as a mismatch between **directed (effortful) attention**, which is weak in ADHD, and **automatic attention**, which is strong: the freeze is a refusal (not willful — a system-level balk) to engage effortful attention, and when options or stimuli multiply, the brain defaults to freezing rather than choosing [15]. Community sources add a stress-response framing ("freeze" as in fight/flight/freeze); that framing is plausible but not established mechanism — treat it as a useful metaphor, not settled science.

Scale of the problem: a small 2025 self-report study (conference abstract, n = 50 adults with ADHD; grade as preliminary) found 82% reported frequent decision-making difficulties, 58% experienced decision paralysis at least weekly (35% daily), 68% said it significantly affected work performance, and 74% said indecision delayed major life choices; decision paralysis correlated strongly with executive-dysfunction scores [8]. Small and self-selected, but consistent with the massive volume of community testimony.

The paralysis flavors matter for product design because each needs a different exit: task paralysis needs a smaller first step; choice paralysis needs fewer options (ideally one); overwhelm freeze needs *less input*, not more features.

## Executive dysfunction vs. procrastination — and why the distinction matters

Researchers define **procrastination** as *voluntarily delaying an intended action despite expecting to be worse off for the delay* [2]. The modern consensus account, led by Fuschia Sirois and Timothy Pychyl, is that procrastination is **emotion regulation gone wrong — short-term mood repair at the future self's expense** [1]:

1. An aversive task triggers negative feelings (boredom, anxiety, self-doubt).
2. Avoiding the task removes the feeling *right now* — "we give in to feel good" (Tice & Bratslavsky's phrase).
3. Relief reinforces avoidance; the task is now also tagged with guilt and shame, making it *more* aversive next time.
4. The consequences transfer to a future self we treat almost like a stranger — "I'll feel more like it tomorrow."

The evidence base for this is solid: experimentally inducing a bad mood is by itself enough to increase procrastination on an upcoming task (Tice, Bratslavsky & Baumeister, 2001, reviewed in [1]); procrastination correlates with shame, guilt, anxiety about past delays, and low self-compassion (average r = −.31 across four studies) [1]. Step 3 is the shame flywheel Klyr must never feed — it is the same loop Brendan Mahan describes as the **Wall of Awful** (see [Emotional regulation and RSD](../foundations/emotional-regulation-and-rsd.md)). One caution: some of the surrounding self-control literature from that era leaned on ego depletion, a construct weakened by later replication failures; the core mood-repair findings rest on the mood-induction and correlational work, not on depletion theory.

**How ADHD interacts with this.** Procrastination and executive dysfunction are different things that co-occur and compound:

- **Prevalence**: in research discussed by Pychyl, roughly 75% of adults with ADHD were classified as chronic procrastinators versus about 35% of adults without ADHD [14].
- **Which symptoms drive it**: in a study of 54 students, only **inattention** symptoms predicted procrastination once hyperactivity/impulsivity was controlled for — not the reverse [6]. Executive self-management of time and self-motivation deficits were the EF components most associated with procrastination in ADHD samples [14]. Prospective memory failures (forgetting to act at the right moment) partially mediate the ADHD–procrastination link [7] — meaning some "procrastination" is actually *forgetting*, a different failure needing different tools (see [Memory and object permanence](../foundations/memory-and-object-permanence.md)).
- **The distinction that matters**: classic procrastination is a *choice* (misguided mood repair); executive non-initiation is a *capacity failure* (the ignition didn't fire even with full willingness). Clinically they blur — Cleveland Clinic distinguishes paralysis from procrastination by the felt sense that *no action is even possible* [15]. In practice, an ADHD user's stuck moment is usually a braid of both plus ambiguity and fatigue.

Why this matters: the two failure modes respond to different interventions, but both are worsened by shame and both are helped by shrinking the task, clarifying the next action, and adding external structure. A product does not need to diagnose which one is happening; it needs to offer exits that work for both and language that moralizes neither.

## Task ambiguity: the silent blocker

A large fraction of "can't start" is actually "can't see the first move." David Allen's GTD tradition made this concrete with the **next physical action**: the most immediate visible behavior that moves things forward. Productivity practitioners observe that when an item is ambiguous ("plan the party," "deal with insurance," "think about taxes"), the brain silently skips it on every list scan and it gets postponed indefinitely [24][25] — ambiguity reads as aversiveness (and Steel's meta-analysis confirms *lack of structure* is part of what makes tasks aversive [2]).

The ADHD-specific twist is brutal: **decomposing a project into steps is itself planning/sequencing — one of the impaired executive functions.** Standard advice ("just break it down!") therefore outsources the hardest cognitive step to the user at their weakest moment. This is the single most actionable insight in this doc: the *system* must do the breaking down, or make it nearly free. (See [Planning methodologies and ADHD](../strategies/planning-methodologies-and-adhd.md) for why GTD's clarify step is simultaneously the most ADHD-compatible idea and the most ADHD-hostile chore.)

Markers of a startable task: begins with a concrete physical verb ("email," "open," "put"), doable in one sitting, one context, no hidden prerequisite decisions. "Write report" fails all of these; "open report doc and write one bad paragraph" passes.

## The perfectionism–delay loop

Perfectionism delays starting through a specific mechanism: **fear of failure**. Recent work (Yosopov et al., 2024) finds fear of failure and overgeneralization of failure ("this failure proves what I am") mediate the perfectionism → procrastination relationship [10]; related chain-mediation studies of negative perfectionism point the same way [11]. Several studies suggest that when fear of failure is accounted for, the direct perfectionism–procrastination link mostly disappears — i.e., **it is not high standards that block starting; it is what a bad outcome would mean about the self**.

Daily-life shape: the email that took three weeks because it had to be worded perfectly; the hobby never begun because the first attempt would be clumsy; re-reading instead of writing. For ADHDers carrying years of criticism and a hair-trigger response to perceived failure (see RSD in [Emotional regulation and RSD](../foundations/emotional-regulation-and-rsd.md)), the anticipated cost of imperfect output is enormous — so the rational-feeling move is to not generate output at all.

The countermeasure with the best mechanistic fit is **stake-lowering**: explicitly reframing the first attempt as a draft that is *supposed* to be bad ("ugly first draft," "draft zero," "vomit draft"). This targets fear of failure directly by redefining success as *existence of output*, not quality.

## "Waiting to feel like it": mood-dependence and behavioral activation

The default folk model — *motivation arrives first, then action* — is empirically backwards, and ADHDers stuck in "waiting to feel like it" mode can wait forever, because the feeling is exactly what their reward system under-generates for distal, dull tasks. Sirois & Pychyl document the signature cognition: "I'll feel more like doing it tomorrow" — a forecast that reliably fails, because tomorrow's self inherits the same task plus extra guilt [1].

**Behavioral activation** (BA) — the depression treatment built on scheduling action *before* mood improves — is the strongest evidence that the causal arrow runs action → motivation. A meta-analysis of 26 RCTs (n = 1,524) found BA superior to control conditions (SMD −0.74) and even to medication in a small set of comparisons [12]; the mechanism is contact with reward: doing the thing produces the reinforcement that thinking about the thing cannot. (Study quality caveats noted by the authors; the direction of effect is robust.) BA is a depression literature, not an ADHD literature — the transfer is mechanistically plausible (both involve blunted anticipatory reward) but should be labeled an extrapolation.

Product translation: any feature that waits for the user to feel ready is designed backwards. The design goal is making the first 30 seconds of action so small that it can happen *without* motivation — after which motivation has a chance to show up.

## Transitions: every resume is a new start

Initiation cost is not paid once per task; it is paid at **every transition** — starting the day, returning from lunch, switching subtasks, recovering from a Slack ping. ADHDers show particular difficulty disengaging from a current activity and re-engaging the next one (a full "mental reset," not a small adjustment) [18], and community clinical sources describe losing momentum entirely after interruptions: the thread of the task drops out of working memory and the return trip requires re-paying the whole activation cost, now with added friction because the warm context is gone [19].

This is why a day of meetings with 40-minute gaps produces zero deep work ([waiting mode](../foundations/time-perception.md) compounds this — the pre-commitment dead zone before any appointment), and why "I was doing great until the phone rang" is a complete explanation, not an excuse. The best-attested lightweight mitigation is the **parking note / bookmark**: writing down the literal next step before stopping, so the future resume starts from a concrete instruction instead of a reconstruction [18][19]. See [Attention and hyperfocus](../foundations/attention-and-hyperfocus.md) for interruption-recovery mechanics.

## Body factors: the ignition runs on physiology

Initiation capacity is not constant across a day, and treating it as constant produces false "laziness" data:

- **Sleep debt** degrades attention and executive control in everyone and hits ADHD brains that were already borrowing against those systems; ADHD and sleep problems are heavily comorbid [26].
- **Medication windows**: stimulant coverage wearing off (late afternoon/evening for many) can produce rebound — worse-than-baseline focus and irritability — which is precisely when home-admin tasks are scheduled [26]. A task that is startable at 10 a.m. may be genuinely un-startable at 8 p.m.
- **Hunger, dehydration, under-stimulation**: community heuristic (HALT — hungry, angry, lonely, tired) rather than ADHD-specific research, but coaches report checking body state resolves a meaningful share of "mystery" paralysis. Status: community wisdom, low risk, worth supporting.

See [Daily-life impact](daily-life-impact.md) for sleep and [Time perception](../foundations/time-perception.md) for chronotype effects (ADHD skews toward delayed sleep phase, making mornings worse than schedules assume).

## The last-minute panic engine: it works, at a cost

The most common ADHD "system" is no system: wait until the deadline is close enough that panic ignites the engine. It genuinely works, and it is important to be honest about why: as delay shrinks toward zero, TMT's denominator collapses and motivation spikes [2]; deadline pressure delivers the arousal, stakes, and singular focus that the ADHD activation system needed all along. Community sources describe adrenaline acting as a stand-in for the missing dopamine drive — a mechanistic simplification (status: community explanation, plausible, not precisely established) but the phenomenology is universal: night-before hyperfocus that produces in 6 hours what 3 weeks could not [17][22].

The costs, though, are structural:

- **Stress physiology**: running every project on threat response; the crash after each sprint; accumulating toward burnout [22].
- **Unreliability**: panic only fires when the deadline is real, singular, and near. Multi-week projects, tasks with no deadline (exercise, taxes-adjacent admin, relationships), or two deadlines at once break the engine entirely.
- **Quality ceiling and error rate**: research on so-called **arousal procrastinators** finds that people who say they delay because they "work best under pressure" are, in the researchers' words, likely "fooling themselves" — providing a believable excuse rather than describing a real performance advantage [9][23]. The wins are memorable; the costs (errors, lost sleep, the times it didn't work) fade.
- **Shame interest**: every save-at-the-buzzer reinforces "I can only work this way," deepening identity-level hopelessness about starting early.

The design-relevant conclusion is *not* "eliminate urgency" — urgency is the one reliably working activator this population has. It is **synthesize urgency safely and early**: timers, races, milestones-as-mini-deadlines, visible countdowns, accountability dates — the manufactured-urgency toolkit ADHD clinicians and coaches already prescribe [17]. Klyr's tension to manage: harness the urgency lever without becoming a stress machine (see [Motivation and gamification](../strategies/motivation-and-gamification.md) for red lines).

## What verifiably helps at the start line

| Strategy | Core move | Mechanism | Evidence grade |
|---|---|---|---|
| **Implementation intentions** (if–then plans) | "When [cue], I will [action]" — e.g., "When I close my 3 p.m. call, I will open the report doc" | Delegates initiation to an environmental cue; action fires semi-automatically, bypassing in-the-moment deliberation | **Strong**: meta-analysis of 94 studies, d = 0.65 [3]; ADHD-specific replications in children — improved delay of gratification [4] and normalized Go/No-Go response inhibition, best when combined with medication [5]. Adult-ADHD trials still thin |
| **Shrink the first step** ("2-minute version," "just open the file") | Redefine the task as its smallest physical opener | Cuts activation energy below the ignition threshold; parallels BA's graded task assignment [12] | **Moderate**: universal clinical + community consensus [15][16]; direct ADHD trials lacking; mechanism well-grounded |
| **Body doubling / external witness** | Work alongside another person, physically or on video; focus rooms and apps | Plausible stack: social facilitation, gentle accountability, co-regulation, scheduled start time converts "sometime" into "now" | **Community-validated, research-pending**: no controlled trials as of this writing; anecdotal reports range from transformative to distracting [13][20]. Strong lived-experience endorsement |
| **Countdown / launch ritual** (5-4-3-2-1, "blast off") | Count down and move on "1"; fixed personal start ritual (same song, same drink, same desk) | Interrupts the deliberation loop before avoidance wins; ritualizes the cue → action link (an implementation intention in costume) | **Community**: popularized by Mel Robbins (who has ADHD); widely echoed by ADHD coaches [21]; no ADHD trials |
| **Momentum sequencing** (warm-up task first) | Start the day/session with one small, likable, guaranteed-win task, then roll into the hard one | Uses the fact that continuing is cheaper than starting; imports activation from an easy start | **Community/coaching**: consistent with BA scheduling logic; not independently trialed |
| **Lowering stakes** (ugly-first-draft mode) | Explicitly authorize a bad version | Disarms fear of failure, the active ingredient in perfectionist delay [10][11] | **Moderate-indirect**: mediation evidence for mechanism; the specific tactic untrialed |
| **Timers and races** ("how much can I do in 20 minutes?") | Sprint against a visible clock; Pomodoro-style bounded effort | Manufactured urgency: compresses the reward gradient on demand; bounded duration also lowers commitment fear ("only 20 minutes") | **Clinical/community**: standard ADHD-coaching prescription [17]; timer-based methods under-researched in ADHD specifically |
| **Parking notes / resume bookmarks** | On every stop, write the literal next step | Converts a resume (expensive re-initiation) into instruction-following | **Community/clinical** [18][19] |

Two notes on the strongest tool: implementation intentions work best when the cue is specific and external (time, place, preceding event), which is exactly the externalization principle from [Executive function](../foundations/executive-function.md); and the ADHD studies are child studies — effects in adults with ADHD are plausible but should be validated in-product. Full intervention-evidence detail lives in [Evidence-based strategies](../strategies/evidence-based-strategies.md).

What reliably does *not* help: exhortation ("just start!"), consequences-listing (adds threat, deepens freeze), motivational content consumed instead of acting, and any tool that demands setup decisions at the moment of paralysis — that is choice paralysis served as a cure.

## Design implications for Klyr

1. **Klyr must enforce startability, not just capture.** Every actionable item should carry (or be one tap from) a concrete next physical action with a physical verb. Rationale: ambiguous items get silently skipped on every scan [24][2]; a list of unstartable items is a shame display, not a tool.
2. **Klyr should do the decomposition, not ask the user to.** Offer automatic/AI-assisted task breakdown ("turn this into steps") because planning-sequencing is itself the impaired function; "break it down yourself" outsources the hardest EF step to the stuck user. Suggest, let the user edit — never require them to author structure from scratch.
3. **One-tap task shrinking.** Any task should collapse to a "2-minute version" ("open the doc," "put one dish away") on demand. Rationale: activation energy is the barrier; the smallest opener is the intervention with the broadest mechanism support [12][15].
4. **A panic-free single-task mode.** An "I'm stuck / overwhelmed" state that collapses the entire UI to exactly one small next action — no list, no counts, no badges. Rationale: choice paralysis and overwhelm freeze are input problems; the exit is fewer options, ideally one [8][15].
5. **Build implementation-intention scaffolding into scheduling.** When a user commits to a task, prompt for a cue ("after lunch," "when I get home") and phrase the plan as if–then; fire the reminder *at the cue*, worded as the pre-made decision. Rationale: d = 0.65 meta-analytic support [3] plus ADHD replications [4][5]; this is the cheapest high-evidence feature available.
6. **Ship launch rituals: countdowns, start sounds, "launch" affordances.** A 5-4-3-2-1 start button is nearly free to build and matches a community-beloved pattern [21]. Treat as delight + activation, not gimmick.
7. **Momentum-aware ordering.** When proposing a session or day plan, default to one small guaranteed-win first, then the priority task — and after any completion, immediately surface the next pre-chosen action while the engine is warm. Rationale: continuing is cheaper than starting; transitions are where momentum dies [18][19].
8. **Resume bookmarks everywhere.** Stopping work on a task should offer a one-line "next step when you return" capture, shown front-and-center at resume. Rationale: every resume re-pays initiation cost; a parking note converts re-initiation into instruction-following [19].
9. **Offer safe synthetic urgency — with a governor.** Timers, sprints, "race the clock," visible time-until-deadline, interim milestones [17]. But cap it: no artificial countdown-panic on everything, no red-alarm aesthetics by default. Rationale: urgency is the one reliable activator, and chronic urgency is the burnout engine [9][22]. This is a genuine design tension; resolve it with user-controlled intensity.
10. **Ugly-first-draft mode.** Let users (or Klyr) mark a task as draft-stakes: copy explicitly authorizes a bad version ("goal: a bad paragraph exists"). Rationale: fear of failure is the mediating mechanism of perfectionist delay [10][11].
11. **Count starts as wins.** Track and celebrate initiations (started at all, did 2 minutes), not only completions. Rationale: initiation is the impaired step; rewarding only completion re-punishes the exact deficit. (Coordinate with streak/restart design in [Habits and routines](habits-and-routines.md).)
12. **Body-doubling hooks.** Support co-working: shared focus sessions, "start together" invites, or integration-friendly session links. Label honestly as community-validated [13][20]; instrument it — Klyr can generate the missing evidence.
13. **Never moralize non-starting.** No overdue-shaming, no streak-guilt, no "you've postponed this 6 times" phrased as accusation. Rationale: procrastination runs on negative mood; shame makes tasks *more* aversive and directly fuels the avoidance loop [1]. If Klyr surfaces repeated postponement at all, it must be as diagnosis-plus-offer ("this one keeps sliding — want a smaller version or a different cue?").
14. **Respect physiology in scheduling.** Allow energy/medication-window tagging and time-of-day defaults ("hard starts before 3 p.m."), and treat evening as reduced-capacity by default rather than judging the user's 9 p.m. non-start [26].
15. **Reminders must carry an action, not just a name.** A notification saying "Report" re-triggers the freeze; "Open report doc — you decided: one bad paragraph" is a launch instruction. Rationale: reminders that point at ambiguity reproduce the original blocker [3][24].

## Open questions

- Implementation-intention evidence in ADHD is strongest in children; how large is the effect for adults with ADHD using app-delivered if–then prompts, and does it decay with repetition (novelty wear-off)?
- Can automated task decomposition actually relieve initiation, or does reviewing machine-generated steps create its own overwhelm/rejection friction? Needs testing with real ADHD users.
- Where is the burnout line for synthetic urgency — how much timer/race pressure helps before it tips into chronic stress or habituates into background noise?
- Does counting "starts" as first-class wins measurably reduce shame and abandonment, or do users discount them as participation trophies?
- Body doubling: which ingredient carries the effect (presence, schedule, accountability, co-regulation)? A product A/B could contribute real evidence here.
- How should a product distinguish, in the moment, between "forgot" (prospective memory), "can't start" (paralysis), and "avoiding" (mood repair) — and does the right exit actually differ enough to justify asking the user?
- Do resume bookmarks measurably shorten re-initiation time after interruptions in ADHD users?

## Sources

1. [Sirois, F. & Pychyl, T. (2013). Procrastination and the Priority of Short-Term Mood Regulation: Consequences for Future Self. Social and Personality Psychology Compass](https://eprints.whiterose.ac.uk/id/eprint/91793/1/Compass%20Paper%20revision%20FINAL.pdf) [research]
2. [Steel, P. (2007). The Nature of Procrastination: A Meta-Analytic and Theoretical Review of Quintessential Self-Regulatory Failure. Psychological Bulletin](https://www.researchgate.net/publication/6598646_The_Nature_of_Procrastination_A_Meta-Analytic_and_Theoretical_Review_of_Quintessential_Self-Regulatory_Failure) [research]
3. [Gollwitzer, P. & Sheeran, P. (2006). Implementation Intentions and Goal Achievement: A Meta-Analysis of Effects and Processes. Advances in Experimental Social Psychology](https://www.researchgate.net/publication/37367696_Implementation_Intentions_and_Goal_Achievement_A_Meta-Analysis_of_Effects_and_Processes) [research]
4. [Gawrilow, C., Gollwitzer, P. M., & Oettingen, G. (2011). If-Then Plans Benefit Delay of Gratification Performance in Children With and Without ADHD](https://bpb-us-e1.wpmucdn.com/wp.nyu.edu/dist/c/6235/files/2019/02/gawrilow-et-al-2011-if-then-plans-benefit-delay-of-gratification-performance-in-children-with-and-without-adhd.pdf) [research]
5. [Gawrilow, C. & Gollwitzer, P. M. Implementation Intentions Facilitate Response Inhibition in Children with ADHD](https://www.semanticscholar.org/paper/Implementation-Intentions-Facilitate-Response-in-Gawrilow-Gollwitzer/676726226cd8d35a7aaeae2fccc5bf64dfeaf292) [research]
6. [Niermann, H. C. M. & Scheres, A. (2014). The relation between procrastination and symptoms of ADHD in undergraduate students](https://pubmed.ncbi.nlm.nih.gov/24992694/) [research]
7. [Altgassen, M. et al. (2019). Prospective memory (partially) mediates the link between ADHD symptoms and procrastination](https://www.researchgate.net/publication/332265491_Prospective_memory_partially_mediates_the_link_between_ADHD_symptoms_and_procrastination) [research]
8. [Oroian, B. A., Nechita, P., & Szalontay, A. (2025). ADHD and Decision Paralysis: Overwhelm in a World of Choices. European Psychiatry (abstract)](https://pmc.ncbi.nlm.nih.gov/articles/PMC12438291/) [research]
9. [Simpson, W. K. & Pychyl, T. A. (2009). In search of the arousal procrastinator. Personality and Individual Differences](https://www.sciencedirect.com/science/article/abs/pii/S0191886909003213) [research]
10. [Yosopov, L., Saklofske, D. H., Smith, M. M., Flett, G. L., & Hewitt, P. L. (2024). Failure Sensitivity in Perfectionism and Procrastination: Fear of Failure and Overgeneralization of Failure as Mediators](https://journals.sagepub.com/doi/10.1177/07342829241249784) [research]
11. [The Chain Mediating Effect of Negative Perfectionism on Procrastination: An Ego Depletion Perspective (2022)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9368400/) [research]
12. [Ekers, D. et al. (2014). Behavioural Activation for Depression: An Update of Meta-Analysis of Effectiveness and Sub Group Analysis. PLOS ONE](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0100100) [research]
13. [You Are Not Alone: Designing Body Doubling for ADHD in Virtual Reality (2025). arXiv preprint](https://arxiv.org/pdf/2509.12153) [research]
14. [Pychyl, T. A. (2018). ADHD and Procrastination. Psychology Today "Don't Delay" blog](https://www.psychologytoday.com/us/blog/dont-delay/201809/adhd-and-procrastination) [clinical]
15. [Cleveland Clinic (Michael Manos, PhD). Feeling Stuck? Here's How To Overcome ADHD Paralysis](https://health.clevelandclinic.org/adhd-paralysis) [clinical]
16. [ADDA — Attention Deficit Disorder Association. ADHD Paralysis Is Real: Here Are 8 Ways to Overcome It](https://add.org/adhd-paralysis/) [community]
17. [Lasky, S. (ADDitude). Do You Shine Under Pressure? How to Manufacture a Sense of Urgency](https://www.additudemag.com/sense-of-urgency-productivity-hack-adhd/) [clinical]
18. [ADDitude. Why Task Switching is Difficult for ADHD Brains — and 7 Ways to Smooth Transitions](https://www.additudemag.com/task-switching-adhd-difficulty-transitions-teens/) [clinical]
19. [ADHD Philadelphia. Why Adults With ADHD Lose Momentum After Interruptions](https://www.adhdphiladelphia.com/blog/why-adults-with-adhd-lose-momentum-so-easily-after-interruptions) [community]
20. [Medical News Today. Body doubling for ADHD: Definition, how it works, and more](https://www.medicalnewstoday.com/articles/body-doubling-adhd) [clinical]
21. [Sinfield, J. (Untapped Brilliance). ADHD and The 5 Second Rule](https://untappedbrilliance.com/adhd-and-the-5-second-rule/) [community]
22. [Inflow. Overcoming a Lack of Urgency with an ADHD Brain](https://www.getinflow.io/post/no-sense-of-urgency) [community]
23. [Psychology Today. "But I Work Best Under Pressure" (2022)](https://www.psychologytoday.com/us/blog/still-procrastinating/202207/i-work-best-under-pressure) [clinical]
24. [Super Productivity. GTD Next Actions: The Art of Defining What's Actually Doable](https://super-productivity.com/blog/gtd-next-actions-guide/) [product]
25. [FacileThings. The Importance of Next Actions](https://facilethings.com/blog/en/the-importance-of-next-actions) [product]
26. [ADDitude. Sleep Deprivation and ADHD Adults: How to Rest Better](https://www.additudemag.com/sleep-deprivation-and-adhd/) [clinical]
