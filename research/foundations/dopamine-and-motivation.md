---
title: "Dopamine, Reward, and Motivation in ADHD"
area: foundations
file: research/foundations/dopamine-and-motivation.md
tags: [dopamine, reward, motivation, delay-discounting, novelty, interest-based-nervous-system, incentive-salience, reinforcement]
related:
  - research/foundations/adhd-overview.md
  - research/foundations/executive-function.md
  - research/foundations/time-perception.md
  - research/strategies/motivation-and-gamification.md
  - research/daily-life/task-initiation-and-paralysis.md
sources: 26
updated: 2026-07-25
summary: >
  What dopamine actually does (wanting vs. liking, reward prediction error, tonic vs.
  phasic), what the ADHD reward evidence does and does not support, why boring tasks
  are neurologically expensive while deadlines work, and which motivational levers are
  safe to build on. Read this before designing any reward, streak, nudge, or
  gamification feature — it is the doc that keeps Klyr off pop-dopamine myths.
---

# Dopamine, Reward, and Motivation in ADHD

## TL;DR

- **Dopamine is not a pleasure chemical.** Berridge's work separates **"wanting"** (incentive salience — the pull toward a cue, dopamine-dependent) from **"liking"** (hedonic pleasure, mediated by small opioid/endocannabinoid systems and *not* dopamine-dependent) [[1]](#sources). You cannot make an ADHD user *want* a task by making it pleasant.
- Dopamine neurons signal **reward prediction error (RPE)** — the gap between expected and actual outcome. As learning proceeds the response shifts from the reward to the **earliest reliable cue that predicts it**; a predicted reward that fails to arrive produces a *dip* [[2]](#sources)[[3]](#sources).
- The most replicated ADHD reward finding is **ventral-striatal hyporesponsiveness during reward *anticipation***: Plichta & Scheres' meta-analysis of 8 fMRI studies (~340 participants) found Cohen's *d* = 0.48 (0.58 for monetary-incentive-delay tasks), with **no significant group difference at reward feedback** [[4]](#sources).
- One small study (n = 14 ADHD / 15 controls) found the mirror image at delivery — greater striatal response to the reward itself — and interpreted it as **impaired transfer of dopamine firing from reward to reward-predicting cues** [[5]](#sources). Plausible, underpowered, but it matches lived experience: *plans don't pull; ticking the box does.*
- **Delay discounting is steeper in ADHD** and this is robust: Jackson & MacKillop's meta-analysis (25 case-control comparisons, N = 3,913) found *d* = 0.43, unmoderated by age or comorbidity [[6]](#sources). Marx et al. (37 comparisons, N = 3,763) found real rewards nearly doubled the odds ratio versus hypothetical ones [[7]](#sources).
- **"ADHD brains have no dopamine" is false.** A 2024 review of 40+ years of human and animal evidence found *limited support for a hypo-dopaminergic state per se* as a core component of ADHD; the honest framing is **dysregulated signaling, heterogeneous across people** [[8]](#sources)[[9]](#sources).
- **"Dopamine detox" is pseudoscience.** You cannot fast from an endogenous neuromodulator; neuroscientists interviewed on the trend call phrases like "lowering dopamine" *essentially meaningless* [[3]](#sources). Klyr must never use this framing, even casually.
- Boring-but-important tasks are expensive because the motivational math collapses: distant, abstract payoffs interact with steep discounting. Wagner et al.'s scoping review (only 12 studies) found ADHD participants reported **more affective distress — especially frustration — during effort**, but *no* consistent evidence they discount effort more when rewards are on offer [[10]](#sources). The barrier looks more like felt aversiveness than cold cost accounting.
- **Deadline pressure works because it collapses delay to zero**, not because ADHDers "work well under pressure." It is a real lever with a real bill: it only fires at the last moment, degrades quality, and reinforces itself.
- **Dodson's "interest-based nervous system"** (interest, novelty, challenge/competition, urgency, + passion) is an **influential clinical heuristic, not a validated construct** — no peer-reviewed operationalization exists. It is directionally consistent with the reward and arousal literature and it is how users describe themselves, so Klyr should speak this language while not building falsifiable claims on it [[11]](#sources)[[12]](#sources).
- **The novelty honeymoon is Klyr's single biggest product risk.** Dopamine responses to novel stimuli habituate as stimuli become familiar [[13]](#sources); Dodson notes plainly that "novelty is short-lived" [[11]](#sources). Every productivity app works for two weeks. Klyr must be designed to survive month three, when it is no longer new.
- **Variable rewards outperform fixed ones — and are the slot-machine mechanism.** Given the association between ADHD symptoms and gaming disorder [[14]](#sources), Klyr's red line is: vary *delight*, never vary *whether the user's work is acknowledged*.

---

## 1. What dopamine actually does

Almost every popular claim about dopamine and ADHD is a compression of four findings, each of which loses something important when compressed.

### 1.1 "Wanting" is not "liking"

Kent Berridge and Terry Robinson's incentive-salience work is the most product-relevant neuroscience in this doc. They showed that the brain circuitry generating **"wanting"** — the motivational pull toward a reward cue — is dissociable from the circuitry generating **"liking"** — the actual pleasure of consuming it. Mesolimbic dopamine drives wanting; liking is produced by much smaller, more fragile opioid and endocannabinoid "hedonic hotspots" and does **not** depend on dopamine [[1]](#sources).

Two consequences for Klyr:

1. **Making a task nicer does not make it more startable.** Prettier UI, warmer copy, and pleasant animations move *liking*. They do not, by themselves, move *wanting*. Wanting is generated by **cues** that have acquired predictive value.
2. **Wanting is cue-triggered and can outrun liking.** This is why someone can compulsively reopen a phone app they no longer enjoy. It is also why a well-designed cue can pull someone into a task they still expect to dislike.

### 1.2 Reward prediction error

Wolfram Schultz's dopamine neuron recordings established that midbrain dopamine cells encode **reward prediction error**: they burst when an outcome is better than predicted, stay flat when it matches prediction, and dip below baseline when a predicted reward fails to appear [[2]](#sources)[[3]](#sources). Crucially, with learning the burst **migrates backward in time** from the reward to the earliest reliable cue predicting it.

The design translation is direct and under-appreciated:

- A reliable cue that predicts something good **becomes** the motivating stimulus. This is what a well-built app can manufacture.
- A **predicted reward that does not arrive produces a negative signal**, not a neutral one. An app that promises acknowledgment and then buries it, or celebrates inconsistently, is not merely failing to help — it is actively teaching the user's reward system to disengage from the cue.

Newer work suggests dopamine may signal predictions more generally, not exclusively reward-related ones [[3]](#sources); the RPE framework is powerful but not the whole story.

### 1.3 Tonic vs. phasic — and why the models disagree

Anthony Grace's distinction separates **tonic** dopamine (slow, background, sets the gain on the system) from **phasic** dopamine (fast, sub-second bursts evoked by stimuli, cleared by reuptake). Tonic levels down-modulate phasic responses through presynaptic autoreceptors.

Sagvolden and colleagues' **dynamic developmental theory** proposes that ADHD involves *blunted phasic bursts alongside low tonic levels*, producing a steepened **delay-of-reinforcement gradient** — reinforcement only "sticks" to behavior that immediately precedes it [[15]](#sources). A 2022 computational model formalizes ADHD as a phasic/tonic imbalance during reinforcement learning [[16]](#sources).

**Be honest that this is contested.** Other work argues for *attenuated tonic and enhanced phasic* release in ADHD — the opposite phasic direction [[17]](#sources). The shared, defensible claim is narrower: **the timing relationship between reinforcement and behavior is altered in ADHD**, which is why reinforcement delay matters far more than reinforcement size.

### 1.4 Novelty gets its own signal

Dopamine neurons respond to **novel stimuli** and those responses **habituate as the stimulus becomes familiar**, in parallel with the fading of orienting responses. Bromberg-Martin, Matsumoto and Hikosaka describe this as a **novelty bonus** that promotes exploration, and note that dopamine's roles extend beyond reward to alerting and information-seeking [[13]](#sources).

This is the mechanism behind every abandoned productivity app. Hold onto it for §5.

---

## 2. The ADHD evidence: dysregulated, not depleted

### 2.1 The anticipation deficit

The most replicated finding is that people with ADHD show **reduced ventral-striatal activation while anticipating a reward**, not while receiving one. Plichta & Scheres pooled 8 fMRI studies (~340 participants) and found a medium effect for ventral-striatal hyporesponsiveness during anticipation, *d* = 0.48 (*p* < 0.001), rising to 0.58 in monetary-incentive-delay tasks — with **no significant group difference during feedback** [[4]](#sources). The authors explicitly caution that the study count is too small for a final answer.

Furukawa et al. (n = 14 ADHD adults, 15 controls) found controls activated ventral and dorsal striatum during anticipation while the ADHD group did not — and the ADHD group showed *greater* striatal response at reward **delivery**. Their interpretation: **impaired transfer of dopamine cell firing from reward to reward-predicting cues** [[5]](#sources). The sample is small and this needs replication, but the mechanism it proposes is exactly the RPE-migration failure predicted by §1.2, and it explains an everyday pattern: *the plan for Saturday generates nothing; ticking the box generates something.*

### 2.2 Steeper delay discounting

**Delay discounting** is how sharply a reward's subjective value drops as it moves into the future. Two independent meta-analyses agree it is steeper in ADHD:

| Meta-analysis | Scope | Effect | Notable moderator |
|---|---|---|---|
| Jackson & MacKillop 2016 [[6]](#sources) | 25 case-control comparisons, N = 3,913 | *d* = 0.43 (*p* < 10⁻¹⁵), low heterogeneity | None significant — not age, not real-vs-hypothetical rewards, not comorbidity |
| Marx et al. 2021 [[7]](#sources) | 37 comparisons, N = 3,763 (53% ADHD) | Small-to-medium across both simple-choice and discounting paradigms | **Real rewards nearly doubled the odds ratio** in the simple-choice paradigm |

The moderator disagreement matters. Jackson & MacKillop found real vs. hypothetical rewards made no difference; Marx et al. found real rewards made ADHD-related impulsive choice much more visible, and argued the pattern reflects **delay aversion** (an affective push to escape waiting) interacting with the demotivating effect of hypothetical rewards. Sonuga-Barke's **dual pathway model** formalizes delay aversion as a motivational route to ADHD that is neurobiologically distinct from the executive-dysfunction route [[18]](#sources) — meaning some users' difficulty is genuinely motivational rather than a working-memory problem. See [time-perception.md](time-perception.md) for the temporal side and [executive-function.md](executive-function.md) for the executive side.

**Product translation of "delay aversion":** waiting is not neutral for many ADHDers; it is actively unpleasant. A spinner, a sync delay, or a three-step flow before anything happens is not a minor UX cost — it is a motivational tax on the exact population you are serving.

### 2.3 Volkow's motivation correlation

Volkow and colleagues used PET in 45 adults with ADHD and 41 controls, measuring dopamine D2/D3 receptor and transporter availability in the midbrain and nucleus accumbens. ADHD participants scored lower on a trait-motivation (Achievement) scale (11±5 vs. 14±3), and those scores **correlated with D2/D3 receptor and transporter availability in ADHD participants but not in controls** [[19]](#sources).

Read this carefully. It is a correlation between receptor *availability* and a *trait questionnaire* — not a measurement of "dopamine levels," and not a demonstration that low dopamine causes low motivation. It supports the modest claim that motivational difficulty in ADHD is neurobiologically grounded rather than a character failing. That claim alone is worth a great deal of Klyr's copy tone.

### 2.4 What the evidence does *not* support

| Claim you will hear | Status |
|---|---|
| "ADHD brains have no / not enough dopamine" | **False as stated.** MacDonald et al.'s 2024 review of human studies and animal models found *limited support for a hypo-dopaminergic state per se* as a key component of ADHD [[8]](#sources). A 2025 editorial concurs that *what* the dysregulation is remains uncertain [[9]](#sources). |
| "Dopamine detox resets your reward system" | **Pseudoscience.** You cannot abstain from an endogenous neuromodulator; dopamine never acts in isolation; "lowering dopamine" is described by researchers as essentially meaningless [[3]](#sources). The *underlying* concern — overstimulating environments crowding out low-stimulation goals — is real; the mechanism story is not. |
| "Reward Deficiency Syndrome explains ADHD" | **Contested umbrella construct**, cited in some clinical writing [[20]](#sources) but not a DSM-5-TR diagnosis and not consensus. Do not build on it. |
| "ADHD = uniformly blunted reward response" | **Oversimplified.** Findings are heterogeneous; anticipation and delivery dissociate; reward *type* (social vs. monetary) matters; some subgroups look reward-hypersensitive. Heterogeneity is the finding [[8]](#sources)[[9]](#sources). |
| "Stimulants work by adding the missing dopamine" | **Too simple.** Methylphenidate is a catecholamine reuptake inhibitor affecting dopamine *and* norepinephrine; fMRI work shows it increases the ventral-striatal *differentiation* between reward and non-reward cues — i.e. it sharpens cue signaling rather than topping up a tank [[21]](#sources). |

**Klyr's house framing: dopamine signaling in ADHD is dysregulated and heterogeneous, not depleted.** This is both more accurate and more useful — a dysregulated signal can be worked *with* by shaping cues and timing; a depleted tank implies nothing an app can do.

---

## 3. Why boring-but-important tasks are so expensive

### 3.1 The motivation math

Steel and König's **temporal motivation theory** compresses expectancy, value, delay, and impulsiveness into one relation: motivation rises with expectancy and value, and falls with delay — scaled by the person's sensitivity to delay. Researchers have applied it directly to the ADHD–procrastination link [[22]](#sources).

Run a typical Klyr task through it. *Renew car insurance.* Expectancy: uncertain (you're not sure what the steps are). Value: negative-ish (you avoid a penalty; nothing good happens). Delay: three weeks. Impulsiveness/delay-sensitivity: elevated. The product of those terms is near zero — for anyone. For an ADHDer with a steeper discount curve, it is *closer* to zero, for longer, and then spikes when the deadline collapses the delay term. This is arithmetic, not weakness.

Every term in that expression is a design surface:

- **Expectancy** rises when the next physical action is named and visibly small.
- **Value** rises when the task is linked to something the user actually cares about, or when a real proximate reward is attached.
- **Delay** falls when the app manufactures a nearer horizon than the real deadline.

### 3.2 Effort feels different, even when it isn't valued differently

The intuitive story is that ADHDers avoid effort because they weigh it as more costly. **The evidence does not cleanly support that.** Wagner, Mason and Eastwood's scoping review found only 12 studies on the subjective experience of effort in ADHD — remarkable given that effort avoidance appears in the diagnostic criteria. Mental-effort preference tasks found *no* group differences; physical-effort tasks likewise. What did emerge: ADHD participants reported **more affective distress, particularly frustration**, during effortful tasks [[10]](#sources). The authors note every paradigm included rewards, confounding effort with reward processing.

This reframes the problem usefully. If ADHDers are *willing* to work for reward but find the process more aversive, then the intervention target is **the felt experience of the middle of a task**, not the price tag on the front. Reducing frustration — clear next steps, no dead ends, no re-orienting cost after an interruption — may matter more than reducing effort.

Sergeant's **cognitive-energetic / state regulation** account fits here: individuals with ADHD may be insufficiently activated by ordinary task demands and must volitionally supply effort to compensate; manipulations that raise arousal — faster event rates, performance incentives — improve performance by lowering the effort required [[10]](#sources).

### 3.3 Why deadline pressure works suspiciously well

Nothing mystical is happening. A deadline collapses the *delay* term to near zero, and it raises arousal into a range where engagement becomes possible. Both mechanisms are already in the literature above.

The catch is that this lever has three costs, and every ADHD adult has paid them: it **only fires at the last possible moment**, so it cannot be scheduled; it **degrades output quality** relative to the person's actual capability; and it is **self-reinforcing** — it worked, so it gets used again, with the stress and shame accumulating underneath. Community and clinical writing converge on this pattern, though rigorous longitudinal evidence on the cost side is thin.

Klyr's job is to give users **urgency they choose** (a started timer, a session with an end, a "just this one thing before dinner") so they are not dependent on **urgency that happens to them** (a crisis at 11pm). See [task-initiation-and-paralysis.md](../daily-life/task-initiation-and-paralysis.md).

---

## 4. The interest-based nervous system

**Status: influential clinical heuristic. Not a validated scientific construct.**

Psychiatrist William Dodson proposes that neurotypical motivation runs on importance, secondary importance (other people's priorities), and rewards/consequences — while an ADHD nervous system is activated instead by **interest, challenge/competition, novelty, and urgency**. His formulation: for ADHDers, "the things that motivate the rest of the world are merely nags" [[11]](#sources). The acronym is variously rendered **ICNU** (Dodson's original) or the more viral **PINCH** (Passion, Interest, Novelty, Challenge, Hurry).

**What it gets right.** It correctly separates *knowing something matters* from *being able to start it* — the same knowledge/performance gap Barkley identifies (see [executive-function.md](executive-function.md)). Its four activators map loosely onto real findings: interest onto value in the motivation equation, novelty onto dopamine novelty responses [[13]](#sources), urgency onto delay collapse [[6]](#sources)[[22]](#sources), challenge onto arousal/state regulation [[10]](#sources).

**What to be careful about.** No peer-reviewed study operationalizes or tests "interest-based nervous system" as a construct; sympathetic explainers present it as an explanatory observation without citing validating research [[12]](#sources). Its binary framing (ADHD brains *cannot* use importance) is stronger than the evidence — ADHDers demonstrably respond to reward, sometimes more than controls, and the deficit is better characterized as anticipatory and delay-sensitive than as a categorical inability. Treating it as literal biology would license bad design, e.g. gating all functionality behind manufactured competition.

**Klyr's position:** adopt the vocabulary, because it is genuinely how users describe their own experience and it lowers shame; do not treat it as a mechanism, and never make a falsifiable product claim that rests on it. Flag it in the [GLOSSARY](../GLOSSARY.md) as a clinical heuristic.

---

## 5. The novelty honeymoon — Klyr's biggest product risk

Here is the failure mode, stated plainly:

> A new system arrives. It is novel, so it generates a genuine dopaminergic response [[13]](#sources). The user spends three enthusiastic days configuring it. The configuration itself feels productive. Then habituation does exactly what habituation does — the novelty response fades — and the app becomes one more object that produces guilt on sight.

This is not folklore. Dopamine responses to novel stimuli habituate as stimuli become familiar [[13]](#sources). Dodson states it from the clinic: "Novelty is short-lived, though, and everything gets old after a while" [[11]](#sources). And the community documents the outcome in detail: apps "downloaded with real hope and abandoned within two weeks," home screens described as **productivity-app graveyards**, and the specific trap of spending setup time *instead of* doing the work [[23]](#sources). Jessica McCabe (How to ADHD) describes the same thing from the inside — strategies that work fine, which her brain stops using because it got bored [[24]](#sources).

The design conclusion is uncomfortable and important: **any engagement Klyr earns in weeks 1–2 tells you nothing.** Novelty is a confound in your own metrics. The honest measurement is month-three behavior among users who have stopped finding the app interesting.

Two distinctions make this tractable:

| Kind of novelty | Decays? | Safe to build on? |
|---|---|---|
| Novelty of **the tool** (new app, new setup, new system) | Yes, fast | No — and chasing it means constant re-onboarding cost |
| Novelty **within the task** (fresh framing, different order, varied surfacing, a new way in) | Renewable | Yes — it can be regenerated indefinitely without the user rebuilding anything |
| Novelty of **the user's data model** (new structure, new fields, migration) | n/a | **Never** — this is the maintenance burden Klyr exists to avoid |

The generalizable rule: **vary the surface, never the substrate.** Klyr may present the same commitments in genuinely different ways over time. It must never require the user to rebuild their setup to feel fresh again.

---

## 6. Stimulation-seeking is a regulation attempt, not a vice

Phone scrolling, snacking, doomscrolling, picking a fight, leaving everything to the last minute, taking a risk that makes no sense — clinical writing frames these as attempts to reach a workable arousal state. Ellen Littman, writing for ADDitude, is explicit that "the struggle for self-regulation is neurological, and has nothing to do with character deficiencies," and lists the usual repertoire: screens, risk, substances, food, and manufactured conflict or chaos [[20]](#sources). (Note: that piece leans on "reduced dopamine in the synapses" and Reward Deficiency Syndrome — both stronger than §2.4 supports. The *reframe* is sound; the *mechanism story* is loose.)

Klyr should take three things from this:

1. **Never moralize about competing stimulation.** "You spent 40 minutes on your phone" is a shaming metric that also happens to be measuring a coping attempt. See [emotional-regulation-and-rsd.md](emotional-regulation-and-rsd.md).
2. **Compete honestly for the same job.** If the phone is winning, it is because it offers immediate, salient, low-effort engagement. Klyr's counter is to be *fast and immediately responsive*, not to be *disciplinarian*.
3. **Take the ethical constraint seriously.** ADHD symptoms are associated with gaming disorder and problematic internet use in systematic review [[14]](#sources). This population is not the right one to test compulsion mechanics on.

---

## 7. Levers that actually move motivation

| Lever | Mechanism | Evidence | Notes for Klyr |
|---|---|---|---|
| **Reward immediacy** | Steep discounting + altered delay-of-reinforcement gradient | Strong: two meta-analyses on discounting [[6]](#sources)[[7]](#sources); behavioral guidance emphasizes immediate, frequent, consistent reinforcement for ADHD [[25]](#sources) | Acknowledgment must be instant. A sub-second response to "done" is a motivational feature, not polish. |
| **Reinforcement density** | Children with ADHD are less responsive to inconsistent, delayed, weak reinforcement [[25]](#sources) | Moderate (mostly child samples; adult generalization assumed, not proven) | Many small completions beat one big one. Favor decomposition. |
| **Real over hypothetical** | Hypothetical rewards demotivate; real rewards nearly doubled the observed effect in one meta-analysis [[7]](#sources) | Moderate, with disagreement [[6]](#sources) | "You'll feel better later" is a hypothetical reward. Prefer concrete, present ones. |
| **Cue salience** | RPE migrates to reliable predictive cues [[2]](#sources); ADHD shows blunted anticipatory response and possibly impaired cue transfer [[4]](#sources)[[5]](#sources) | Moderate–strong | The cue must be *external and present* (see [executive-function.md](executive-function.md) on externalization), and must reliably predict a real payoff. |
| **Interest linking** | Value term in the motivation equation; consistent with Dodson's clinical account [[11]](#sources)[[22]](#sources) | Weak-to-moderate (mechanistically plausible, not directly tested in this form) | Let users attach a *why* to a task in their own words — and show it at the moment of doing, not at planning time. |
| **Chosen urgency** | Collapses the delay term; raises arousal [[10]](#sources)[[22]](#sources) | Moderate | Timers, sessions, "before X" framings. Offered, never imposed. |
| **Variable rewards** | Unpredictable reinforcement produces stronger engagement than fixed [[26]](#sources) | Strong — and that is the problem | See red line below. |

### The red line on variable rewards

Variable-ratio reinforcement is the most powerful schedule in behavioral psychology, and it is the mechanism of slot machines, loot boxes, and infinite feeds [[26]](#sources). Klyr's users are a population with elevated association to gaming disorder and problematic internet use [[14]](#sources), and Klyr's stated purpose is to *reduce* pressure. Those facts foreclose the obvious move.

**The line: Klyr may vary the *expression* of acknowledgment. It must never vary *whether* work is acknowledged, and must never make acknowledgment contingent on a random draw.** A different animation or phrase each time is variety. A chance of getting nothing is a slot machine. Detailed element-by-element treatment belongs in [motivation-and-gamification.md](../strategies/motivation-and-gamification.md).

---

## Design implications for Klyr

1. **Acknowledge completion instantly and unconditionally.** Steep discounting and impaired anticipatory signaling mean the reward has to land at the moment of action, not in a weekly summary [[4]](#sources)[[6]](#sources)[[25]](#sources). If Klyr ever has to choose between a beautiful animation and a fast one, ship the fast one.
2. **Never promise a reward Klyr does not deliver.** A predicted reward that fails to arrive produces a negative prediction error — an active demotivator, not a neutral event [[2]](#sources). Inconsistent celebration is worse than no celebration.
3. **Treat overdue counters and broken-streak displays as prohibited by default.** They deliver a stream of negative signals attached to Klyr's own cues, which is precisely how you teach a reward system to avoid an app. If a streak-like mechanic ships, it must be forgiving by construction (see [habits-and-routines.md](../daily-life/habits-and-routines.md)).
4. **Design for month three, not week one.** Novelty responses habituate [[13]](#sources) and every competitor has already won weeks 1–2 [[23]](#sources). Klyr's core retention metric must be behavior among users past the novelty window; early engagement is a confound, not a signal.
5. **Vary the surface, never the substrate.** Renewable in-task novelty (fresh framing, varied order, new entry points) is legitimate. Requiring users to rebuild their setup to feel fresh is the trap Klyr exists to escape.
6. **Minimize the delay between opening Klyr and something happening.** Delay aversion means waiting is affectively costly, not merely inconvenient [[7]](#sources)[[18]](#sources). Cold-start time, sync spinners, and multi-step entry flows are motivational taxes.
7. **Optimize the middle of a task, not just its start.** ADHD participants reported elevated frustration during effort without consistently discounting effort more [[10]](#sources). Invest in no-dead-ends, resumable state, and cheap re-orientation after interruption (see [attention-and-hyperfocus.md](attention-and-hyperfocus.md)).
8. **Offer urgency; never impose it.** User-initiated timers, sessions, and "before dinner" framings collapse the delay term without manufacturing crisis [[22]](#sources). Red alarm states that the user did not ask for are simulated deadline stress — the thing they are already drowning in.
9. **Attach a user-authored "why" to hard tasks and surface it at execution time, not planning time.** Klyr can raise the value term, but only where the anticipatory signal is weakest — the point of performance, not the point of planning [[5]](#sources).
10. **Prefer many small acknowledged completions to one large one.** Reinforcement in ADHD is more effective when immediate, frequent, and consistent [[25]](#sources); decomposition is therefore a motivational feature, not merely an organizational one.
11. **Ban variable-ratio mechanics on the core loop.** Vary the expression of acknowledgment freely; never gamble whether it appears [[14]](#sources)[[26]](#sources). Klyr must be safe to use compulsively, which means it must not be built to be used compulsively.
12. **Purge pop-dopamine language from all copy.** No "dopamine hit," no "dopamine detox," no "your brain doesn't make enough dopamine" [[3]](#sources)[[8]](#sources). Approved framing: *dopamine signaling in ADHD is dysregulated, not depleted — which is why timing and cues matter more than willpower.*
13. **Frame competing stimulation without judgment.** Phone use, snacking, and chaos-seeking are regulation attempts [[20]](#sources). Klyr must never report on them moralistically; if it references them at all, it does so as information the user asked for.
14. **Assume capability varies with medication state and time of day.** Stimulants sharpen ventral-striatal cue differentiation [[21]](#sources), so the same user has meaningfully different anticipatory pull at 9am and 7pm. Klyr must work in the low-signal state — meaning it should never depend on the user having felt motivated when they set something up.
15. **Name the tension honestly in design reviews.** The levers that work fastest (urgency, variability, loss framing) are the ones that cause harm at scale in this population. When a growth metric and this doc conflict, this doc is the tiebreaker.

---

## Open questions

- **Does the anticipatory-signal deficit replicate in adults at scale?** The core meta-analysis rests on 8 studies (~340 participants) and the anticipation/delivery dissociation on a 29-person study [[4]](#sources)[[5]](#sources). Both authors flag the sample problem. Treat the mechanism as promising, not settled.
- **Does app-delivered acknowledgment function as reinforcement at all?** Nearly all ADHD reinforcement evidence uses monetary or social rewards delivered by a person or a lab, largely in children [[25]](#sources). Whether a checkbox animation is a reinforcer for an ADHD adult is an empirical question Klyr should test, not assume.
- **How much in-task novelty is enough, and where does it become disorienting?** The habituation mechanism is established [[13]](#sources); the dose-response curve for a productivity interface is not. Needs A/B testing on month-3 retention with real ADHD users.
- **Is manufactured urgency net-helpful or net-harmful over months?** Short-term efficacy is plausible; the long-run stress and shame cost is documented mainly in clinical and community writing, not in longitudinal trials.
- **Do reward-sensitivity subgroups predict who a feature helps?** Pilot work suggests individual reward sensitivity may predict behavioral-intervention response in children. If that generalizes, Klyr's motivational features may need to be user-configurable rather than universal — but adding configuration burden contradicts the low-maintenance goal. Real tension; needs testing.
- **Does the effort finding hold without rewards in play?** Every effort paradigm reviewed included rewards, confounding effort cost with reward processing [[10]](#sources). Whether ADHDers find effort *itself* more aversive is genuinely unresolved.

---

## Sources

1. [Neuroscience of Liking and Wanting — Berridge Lab, University of Michigan](https://sites.lsa.umich.edu/berridge-lab/research-overview/neuroscience-of-linking-and-wanting/) — [research]
2. [Glimcher, P.W. (2011). Understanding dopamine and reinforcement learning: The dopamine reward prediction error hypothesis. *PNAS* 108(Suppl 3):15647–15654](https://pmc.ncbi.nlm.nih.gov/articles/PMC3176615/) — [research]
3. [Debunking the Dopamine Detox Trend — The Scientist (interviews with Talia Lerner, Stephanie Borgland, Nandakumar Narayanan; Schultz's RPE work)](https://www.the-scientist.com/debunking-the-dopamine-detox-trend-72036) — [research]
4. [Plichta, M.M. & Scheres, A. (2014). Ventral–striatal responsiveness during reward anticipation in ADHD and its relation to trait impulsivity in the healthy population: A meta-analytic review of the fMRI literature. *Neuroscience & Biobehavioral Reviews* 38:125–134](https://pmc.ncbi.nlm.nih.gov/articles/PMC3989497/) — [research]
5. [Furukawa, E. et al. (2014). Abnormal Striatal BOLD Responses to Reward Anticipation and Reward Delivery in ADHD. *PLOS ONE*](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0089129) — [research]
6. [Jackson, J.N.S. & MacKillop, J. (2016). Attention-Deficit/Hyperactivity Disorder and Monetary Delay Discounting: A Meta-Analysis of Case-Control Studies. *Biological Psychiatry: CNNI* 1(4)](https://pubmed.ncbi.nlm.nih.gov/27722208/) — [research]
7. [Marx, I., Hacker, T., Yu, X., Cortese, S. & Sonuga-Barke, E. (2021). ADHD and the Choice of Small Immediate Over Larger Delayed Rewards: A Comparative Meta-Analysis. *Journal of Attention Disorders*](https://journals.sagepub.com/doi/10.1177/1087054718772138) — [research]
8. [MacDonald, H.J., Kleppe, R., Szigetvari, P.D. & Haavik, J. (2024). The dopamine hypothesis for ADHD: An evaluation of evidence accumulated from human studies and animal models. *Frontiers in Psychiatry*](https://pubmed.ncbi.nlm.nih.gov/39619336/) — [research]
9. [Editorial: Deciphering dopamine dysregulation in adult ADHD (PMC)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12206545/) — [research]
10. [Wagner, Mason & Eastwood (2024). The experience of effort in ADHD: a scoping review. *Frontiers in Psychology*](https://pmc.ncbi.nlm.nih.gov/articles/PMC11184226/) — [research]
11. [Dodson, W. — Secrets of the ADHD Brain. *ADDitude*](https://www.additudemag.com/secrets-of-the-adhd-brain/) — [clinical]
12. [Interest-Based Nervous System and ADHD Motivation — Neurodivergent Insights](https://neurodivergentinsights.com/interest-based-nervous-system/) — [community]
13. [Bromberg-Martin, E.S., Matsumoto, M. & Hikosaka, O. (2010). Dopamine in Motivational Control: Rewarding, Aversive, and Alerting. *Neuron*](https://www.cell.com/neuron/fulltext/S0896-6273(10)00938-4) — [research]
14. [The emerging evidence on the association between symptoms of ADHD and gaming disorder: A systematic review and meta-analysis (2023)](https://pubmed.ncbi.nlm.nih.gov/37883910/) — [research]
15. [Sagvolden, T., Johansen, E.B., Aase, H. & Russell, V.A. (2005). A dynamic developmental theory of ADHD. *Behavioral and Brain Sciences*](https://static.cambridge.org/content/id/urn:cambridge.org:id:article:S0140525X05310077/resource/name/S0140525X05000075a.pdf) — [research]
16. [A mechanistic model of ADHD as resulting from dopamine phasic/tonic imbalance during reinforcement learning (2022). *Frontiers in Computational Neuroscience*](https://www.frontiersin.org/journals/computational-neuroscience/articles/10.3389/fncom.2022.849323/full) — [research]
17. [Attenuated Tonic and Enhanced Phasic Release of Dopamine in Attention Deficit Hyperactivity Disorder (PMC)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4589406/) — [research]
18. [Sonuga-Barke, E.J.S. (2002). Psychological heterogeneity in AD/HD — a dual pathway model of behaviour and cognition. *Behavioural Brain Research*](https://pubmed.ncbi.nlm.nih.gov/11864715/) — [research]
19. [Volkow, N.D. et al. (2011). Motivation deficit in ADHD is associated with dysfunction of the dopamine reward pathway. *Molecular Psychiatry*](https://pubmed.ncbi.nlm.nih.gov/20856250/) — [research]
20. [Littman, E. — Brain Stimulation and ADHD: Cravings, Dependency and Regulation. *ADDitude*](https://www.additudemag.com/brain-stimulation-and-adhd-cravings-dependency-and-regulation/) — [clinical]
21. [Methylphenidate modifies reward cue responses in adults with ADHD: An fMRI study. *Neuropharmacology*](https://www.sciencedirect.com/science/article/pii/S0028390819303995) — [research]
22. [Using the temporal motivation theory to explain the relation between ADHD and procrastination (2023). *Australian Psychologist*](https://www.tandfonline.com/doi/full/10.1080/00050067.2023.2218540) — [research]
23. [I Have ADHD and I Tried 12 Productivity Apps. Only 3 Actually Helped. — Medium (lived experience; "app graveyard" pattern)](https://medium.com/@theo-james/i-have-adhd-and-i-tried-12-productivity-apps-only-3-actually-helped-b2d01d39e8fb) — [community]
24. [McCabe, J. — *How to ADHD: An Insider's Guide to Working with Your Brain (Not Against It)*](https://howtoadhdbook.com/) — [community]
25. [Behavior Management for School Aged Children with ADHD (PMC) — immediacy, frequency and consistency of reinforcement](https://pmc.ncbi.nlm.nih.gov/articles/PMC4167345/) — [clinical]
26. [The Psychology of Hot Streak Game Design — UX Magazine (variable reinforcement schedules in product design and their ethics)](https://uxmag.medium.com/the-psychology-of-hot-streak-game-design-how-to-keep-players-coming-back-every-day-without-shame-3dde153f239c) — [product]
