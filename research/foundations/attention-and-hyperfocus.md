---
title: "Attention Regulation, Hyperfocus, and Task Switching"
area: foundations
file: research/foundations/attention-and-hyperfocus.md
tags: [attention, hyperfocus, distraction, mind-wandering, task-switching, interruption-recovery, body-doubling]
related:
  - research/foundations/executive-function.md
  - research/foundations/memory-and-object-permanence.md
  - research/foundations/time-perception.md
  - research/foundations/dopamine-and-motivation.md
  - research/product/ux-design-for-adhd.md
sources: 32
updated: 2026-07-25
summary: >
  How ADHD attention is allocated rather than absent: external vs internal distraction, hyperfocus
  (definition, evidence status, costs), transition and switch costs, interruption recovery, and
  environmental modulation. Read before designing focus views, notifications, timers, capture inboxes,
  or anything that asks a user to stop one thing and start another.
---

# Attention Regulation, Hyperfocus, and Task Switching

## TL;DR

- ADHD is better described as **attention dysregulation** than attention deficit: attention gets allocated, often intensely, just not reliably to whatever the person intended. Any design that assumes "can't focus" will build the wrong product.
- **Internal distraction usually outweighs external distraction.** A latent-variable study (N=1,220) found external distraction, intrusive thoughts, and mind-wandering load onto one general distractibility factor ("d") that explains ~80% of their variance and relates to ADHD symptoms at β=.74–.78 ([source 5](#sources)).
- **Excessive spontaneous mind-wandering** — unintentional, unbidden thought drift tied to default mode network (DMN) regulation failure — correlates with inattention at r=.77 and with functional impairment at r=.81, in some analyses predicting impairment better than the DSM symptom items themselves ([source 2](#sources)).
- **Distraction-by-anticipation** (working term for this corpus): the intrusive idea that must be acted on *now* because the alternative is losing it. This is a memory-driven distraction, not an impulse-control failure, and it is the single strongest argument for a two-keystroke capture inbox.
- **Hyperfocus is real to users, thin in the literature.** It is not in the DSM-5. A 2019 review found only one empirical study measuring it in ADHD; a 2025 integrative review found 10 studies total and called the knowledge base "quite limited" ([sources 1, 15](#sources)).
- Validated measurement now exists: the **Adult Hyperfocus Questionnaire** defines hyperfocus by six qualities (timelessness, failure to attend to the world, ignoring personal needs, difficulty stopping/switching, total engrossment, feeling stuck on small details) and correlates r=.53 with ADHD traits ([sources 3, 4](#sources)).
- **Hyperfocus and distractibility go together, not against each other** (β≈.36) — the same weak attentional control produces both. Whether hyperfocus is simply flow by another name is genuinely contested.
- **Transitions cost more than the switch itself.** Children with ADHD show substantially larger task-switch costs, normalized by medication ([source 6](#sources)); on top of that sits Sophie Leroy's **attention residue**, where an *unfinished* prior task keeps consuming capacity in the next one ([source 8](#sources)).
- **The famous "23 minutes 15 seconds to recover from an interruption" is a meme, not a finding.** It comes from interviews with Gloria Mark, not from the cited paper — which actually found interrupted work was completed *faster*, but with more stress, frustration, and effort ([sources 17, 25](#sources)).
- **The fix that does have evidence is a ~1-minute "ready-to-resume" note** before you switch away: where you stopped, what's left, what to postpone. It measurably reduced attention residue across four studies ([source 9](#sources)).
- **Environment modulates attention measurably.** White/pink noise improved task performance in ADHD groups (g≈0.25) while *hurting* controls (g≈−0.21) in a 13-study meta-analysis ([source 10](#sources)); fidgeting appears compensatory, not merely disruptive ([sources 21, 22](#sources)); body doubling is widely used and essentially unstudied.

---

## 1. Reframe: allocation, not absence

The clinical label is misleading in a way that matters for product design. People with ADHD are not short of attention — they have unreliable *control over where it goes*. Attention gets pulled by salience (novelty, interest, threat, immediacy) rather than pushed by intention. See [executive-function.md](./executive-function.md) for the underlying control architecture and [dopamine-and-motivation.md](./dopamine-and-motivation.md) for why salience wins.

The best single piece of evidence for "dysregulation, not deficit" is a two-sample study (N=651 and N=569) testing whether distractibility is one thing or several. It found three correlated factors — **external distraction** (environmental stimuli), **unwanted intrusive thoughts**, and **mind-wandering** — of which roughly 80% of the variance loaded onto a single higher-order general distractibility factor, *d*. That factor related to ADHD symptoms and functional impairment at β=.74–.78. Crucially, it also related *positively* to hyperfocus (β=.36–.37) ([source 5](#sources)). The people who report being most distractible are the same people who report getting most stuck in a task. One control system, two failure modes.

## 2. Two kinds of distraction

### 2.1 External distraction

Environmental pulls — a notification, a passing person, an open tab — are the folk model of ADHD distraction and are real, but their effect is task-dependent: salient irrelevant stimuli disrupt ADHD adults more when the primary task leaves top-down control under-recruited.

There is a striking real-world quantification in a responsibility case-control study of 777 adult drivers involved in crashes. ADHD alone carried an adjusted odds ratio of 2.18 for being responsible for the crash. ADHD *combined with* external distraction jumped to aOR = 5.79 — far above what the two risks would predict additively ([source 13](#sources)). Distractors are not additive for ADHDers; they are multiplicative with the underlying condition.

### 2.2 Internal distraction: mind-wandering and DMN intrusion

The same study found that internal distraction (mind-wandering) carried a *higher* odds ratio than external distraction: aOR 2.38 (95% CI 1.50–3.77) versus 1.47 (95% CI 1.06–2.05) ([source 13](#sources)). Quiet rooms do not solve ADHD.

The mechanism proposed in the **mind-wandering account of ADHD** is failure to regulate the **default mode network** — the network active during self-referential, undirected thought — against the executive control network. Three regulatory processes are described as deficient: **context regulation** (neurotypical adults suppress mind-wandering as cognitive load rises; ADHD adults do this less), **sensory decoupling** (perceptual processing drops during mind-wandering), and **salience/reward sensitivity** (task rewards normalize DMN deactivation in ADHD in a way comparable to stimulant medication) ([source 2](#sources)).

The empirical anchor is the Mind Excessively Wandering Scale (MEWS), which discriminates ADHD from controls with sensitivity/specificity around 0.90 and correlates with inattention (r=.77), hyperactivity/impulsivity (r=.69), and impairment (r=.81). Over six months, change in mind-wandering tracked change in impairment (r=.62). The review also reports a single study in which 81% of the variance in task-unrelated thought frequency was explained by task-induced DMN deactivation — a remarkable figure, but one study, so treat it as suggestive rather than settled ([source 2](#sources)).

**Evidence grade: strong for the correlation, moderate for the causal model.** Not every finding lines up — at least one adolescent study linked DMN connectivity to delay aversion and temporal discounting but *not* to mind-wandering.

Design consequence: the two distraction types need different countermeasures. External distraction is fought with environment (blocking, single-task views, reduced surface area). Internal distraction cannot be blocked — it can only be *caught*.

### 2.3 Distraction-by-anticipation

**Working term for this corpus; community-described, mechanistically plausible, not a formal construct.** The pattern: mid-task, an unrelated but real thought arrives — "the passport expires in March," "I never replied to Dana." The ADHDer does not act on it because they are impulsive. They act on it because they have learned, correctly, that an unrecorded intention is a lost intention. See [memory-and-object-permanence.md](./memory-and-object-permanence.md) for the prospective-memory evidence behind that fear.

Two literatures converge here. First, intrusive thoughts are a first-class distraction factor in the *d*-factor model, not a footnote ([source 5](#sources)). Second, Leroy's work shows **incompleteness** is the strongest driver of attention residue ([source 8](#sources)) — and an uncaptured intention is, cognitively, an unfinished task. It keeps drawing resources until it is either done or safely stored. And research on **intention offloading** shows the escape actually works: people reliably store delayed intentions in external cues, doing so improves later follow-through, and whether they offload at all is governed by their *metacognitive confidence* in the store — so the tactic only defuses the "act now" urge if the user genuinely trusts the store will hand the item back at the right moment ([source 31](#sources)).

This makes capture a *focus* feature, not an inbox feature. If parking a thought is slower or less trustworthy than acting on it, the user will act on it, and the current task dies.

## 3. Hyperfocus

### 3.1 Working definition and evidence status

**Hyperfocus** is the state of near-total absorption in a task, with diminished perception of everything else. It is one of the most commonly reported adult ADHD experiences and **appears nowhere in DSM-5 criteria**.

Ashinoff & Abu-Akel's 2019 review in *Psychological Research* proposed four testable features: it is (1) induced by task engagement — fun, interesting, or important; (2) an intense state of sustained or selective attention; (3) accompanied by diminished perception of non-task-relevant stimuli; and (4) associated with *improved* task performance. They then reported the uncomfortable part: at the time, they could identify only **one** empirical study measuring cognitive or neural hyperfocus in ADHD (Sklar, 2013, an EEG study during video-game play, which lacked behavioral performance metrics) ([source 1](#sources)).

A 2025 integrative review of "deep concentration" in ADHD found 10 empirical studies (8 quantitative, 2 qualitative), reported high prevalence in adults with ADHD relative to those without, and concluded that "scientific knowledge on the topic is still quite limited" ([source 15](#sources)).

Measurement has improved. The **Adult Hyperfocus Questionnaire (AHQ)** defines hyperfocus as "a state of heightened, intense focus of any duration" that may include six qualities: *timelessness, failure to attend to the world, ignoring personal needs, difficulty stopping and switching tasks, feelings of total engrossment,* and *feeling 'stuck' on small details*. The 12-item dispositional subscale (AHQ-D, validated in 347 US adults) shows factor loadings 0.57–0.81 on a single factor, Cronbach's α = 0.93, and correlates r = .53 with ADHD traits on the CAARS ([source 3](#sources)). The original AHQ measured hyperfocus separately across school, hobby, and screen-time settings, with higher-ADHD respondents reporting more of it in each ([source 4](#sources)).

**Evidence grade: the experience is well-attested and now measurable; the cognitive and neural mechanism is largely unstudied.** Do not let Klyr's copy imply otherwise.

### 3.2 Triggers

Reported triggers cluster tightly: **interest**, **immediate feedback**, **appropriate challenge**, and **immediacy/urgency**. ADDitude's clinician-reviewed overview describes ADHD brains as drawn to "activities that give instant feedback," with Barkley noting difficulty shifting attention away from rewarding activity ([source 20](#sources)). Games, code, creative work, research rabbit holes, and infinite feeds dominate the anecdotal list — the last of which is the problem: the same trigger profile that produces a great work session produces four hours of scrolling. See [dopamine-and-motivation.md](./dopamine-and-motivation.md).

### 3.3 Gifts and costs

The gift is real: uninterrupted deep work, high output, subjective pleasure. Many ADHDers structure careers around it. Klyr must never treat hyperfocus as a symptom to be suppressed.

The costs are equally real and specific:

| Cost | How it shows up |
|---|---|
| Time loss | Hours vanish; "timelessness" is a core AHQ dimension. See [time-perception.md](./time-perception.md). |
| Body neglect | Meals, water, bathroom, sleep skipped — "ignoring personal needs" is an AHQ dimension, not a metaphor. |
| Missed obligations | Meetings, pickups, appointments blown through. ADDitude documents cases up to and including failing to notice a house fire ([source 20](#sources)). |
| Misallocation | The absorption lands on the wrong thing — the interesting sub-task, the reformatting, the feed. |
| Difficulty disengaging | "Difficulty stopping and switching tasks" is measured directly by the AHQ. |
| The crash | Widely reported exhaustion, fog, and low mood afterwards. **Community-reported; not established in peer-reviewed literature.** ([source 26](#sources)) |

**Myth screen:** the popular explanation that the crash is "the dopamine surge draining out" is pop-neuroscience with no supporting evidence. Klyr's copy must describe the crash phenomenologically ("after a long deep session, many people feel wiped out") and never state a neurochemical cause.

The 2025 integrative review also notes associations between hyperfocus and perseveration, internet addiction, and emotional dysregulation ([source 15](#sources)) — correlational, but a caution against romanticizing the state.

### 3.4 Hyperfocus vs flow

Contested, and the disagreement is substantive.

- **Ashinoff & Abu-Akel argue they are the same phenomenon** named differently by psychiatry and positive psychology — both involve intrinsic reward, intense concentration, and temporal distortion ([source 1](#sources)).
- **Most clinical and lived-experience writing argues they differ on volition and exit**: flow is entered somewhat deliberately and can be left; hyperfocus is described as attention capture you cannot easily escape, where bottom-up salience overrides executive control.
- Empirically, a study of college students found those with clinically significant ADHD symptoms reported *higher* hyperfocus and *lower* levels of most flow dimensions than peers ([source 16](#sources)) — consistent with the two being distinguishable, though self-report of an internal state is a soft measure.

For Klyr, the practical distinction is exit control, not ontology: **a state you can leave is a resource; a state you cannot leave needs a guardrail.**

## 4. Transitions and switch costs

### 4.1 The laboratory finding

Cepeda, Cepeda & Kramer (2000) ran a task-switching paradigm with children with and without ADHD. Children with ADHD showed **substantially larger switch costs**; when medicated, their switch performance was equivalent to controls ([source 6](#sources)). A study of adults found a *selective* impairment: when the attentional set was kept constant, ADHD participants were neither significantly slower nor showed higher switch costs — the deficit appeared specifically in flexibly reconfiguring which stimulus dimension to attend to ([source 7](#sources)).

That nuance matters. The expensive operation is not "doing a different thing" — it is **rebuilding the mental set**: reloading what this task is, where I was, what counts as done. Which is exactly what an app can externalize.

### 4.2 Attention residue

Sophie Leroy's 2009 paper in *Organizational Behavior and Human Decision Processes* established **attention residue**: after switching, part of attention stays on the previous task, reducing resources for the new one. The key finding is that **incompleteness drives residue** — participants who switched away from an unfinished task performed worse than those who finished it or reached a clear stopping point ([source 8](#sources)).

### 4.3 Why ADHD transitions are disproportionately expensive

The costs stack, and only the first is what people mean by "task switching":

1. **Set-reconfiguration cost** — larger in ADHD ([sources 6, 7](#sources)).
2. **Attention residue** — worse because ADHDers leave more tasks unfinished, by definition of the condition ([source 8](#sources)).
3. **Reconstruction load** — resuming requires rebuilding state in working memory, which is a documented ADHD weak point (see [memory-and-object-permanence.md](./memory-and-object-permanence.md)).
4. **Re-initiation cost** — the new task must be *started*, and starting is separately hard (see [task-initiation-and-paralysis.md](../daily-life/task-initiation-and-paralysis.md)).
5. **Affective cost** — leaving a stimulating state for an unstimulating one is aversive, sometimes acutely (see [emotional-regulation-and-rsd.md](./emotional-regulation-and-rsd.md)).

A neurotypical user pays cost 1. An ADHD user often pays all five. This is why "just switch tasks" advice fails, and why the transition — not the task — is frequently where the day breaks.

## 5. Interruption recovery: what the 23-minute figure actually says

The most-cited number in productivity software marketing is "it takes 23 minutes and 15 seconds to recover from an interruption," attributed to Gloria Mark. What Mark's work actually shows is more interesting and less convenient:

- The figure appears in **interviews with Mark, not in the peer-reviewed papers** normally cited alongside it. A detailed source trace could not locate it in the primary literature ([source 25](#sources)).
- What was measured for comparison was **the time until interrupted work was resumed on the same day** — during which workers typically completed about two intervening tasks. That is "when did they come back," not "how long until they were back at full capacity."
- Mark's CHI 2008 paper *The Cost of Interrupted Work: More Speed and Stress* found interrupted conditions were completed in about 20.3–20.6 minutes versus 22.8 minutes uninterrupted — interrupted work was **faster**, but at the price of significantly higher stress, frustration, time pressure, and effort ([sources 17, 25](#sources)).
- **Resumption lag** — the time to actually re-engage — was collected but not reported as a headline number.

What Mark's field observations *did* establish is how fragmented knowledge work already is. In her CHI 2005 study *No Task Left Behind?*, researchers shadowed 24 information workers to the second and found people spent on average only about **11 minutes** in a "working sphere" before switching or being interrupted; **57%** of work episodes were interrupted; and interruptions split almost evenly between **external (48%)** and **self-generated/internal (52%)** sources — self-interruption is roughly half the problem. Of interrupted work, **77%** was resumed the same day, but with more than two other tasks intervening first ([source 30](#sources)). So "recovery" is never one clean gap; it is a detour through several other tasks, each leaving its own residue. And the ambient baseline has only worsened: Mark's later observational work found average attention on a screen fell from about **2.5 minutes in 2004 to roughly 47 seconds** in recent years ([source 32](#sources)) — the environment every user works in is now natively hyper-fragmented.

Honest version for Klyr's internal use: *interruptions are costly, but the cost is largely paid in stress, error, and unfinished threads rather than in a fixed recovery clock, and the popular 23-minute figure should not appear in Klyr's copy.*

### 5.1 What does work: the ready-to-resume plan

Leroy & Glomb (2018, *Organization Science*) tested a one-minute intervention across four studies (a 202-professional field study plus lab studies of 66 and 44 participants): before switching away, briefly note **where to resume, what challenges remain, and what actions must be postponed**. Participants who made a ready-to-resume plan showed reduced attention residue, better performance on the interrupting task, better recall, and better decision quality ([sources 9, 18](#sources)). Note the honest limitation the authors flag: they did *not* test whether the plan improved performance on the originally interrupted task.

Separately, EEG work on task resumption suggests more available time before resuming — and flexibility about *when* to resume — supports cleaner disengagement and refocusing ([source 19](#sources)).

For a population with weak working memory and expensive set-reconfiguration, a ready-to-resume note is the single highest-leverage evidence-backed mechanic in this entire document.

## 6. Environmental modulation

### 6.1 Noise and music

A 2024 meta-analysis (Nigg and colleagues, *JAACAP*) of 13 randomized studies with 335 participants found white/pink noise produced a small but significant improvement in task performance in youth with ADHD or elevated attention problems (**g ≈ 0.249**), while producing a small *negative* effect in non-ADHD controls (**g ≈ −0.212**) ([sources 10, 23](#sources)). A genuinely differential effect — rare and useful. The authors caution: small samples, brief exposures, weak control conditions, no masking, no brown-noise data, and effects smaller than medication.

The theoretical explanation usually offered is the **Moderate Brain Arousal model** (noise raises suboptimal internal neural noise via stochastic resonance). That model is now **contested** — 2024 work found both random and non-random signals *reduced* neural noise in people with elevated ADHD traits, contradicting the proposed mechanism ([source 11](#sources)). The effect looks real; the story about why is unsettled.

For ambient human noise specifically: Mehta, Zhu & Cheema (2012, *Journal of Consumer Research*) found moderate ambient noise (~70 dB) improved creative task performance relative to low (50 dB), while high noise (85 dB) hurt it ([source 12](#sources)) — an inverted U. This was a general-population consumer study, not an ADHD study; do not present it as ADHD evidence. It does help explain why cafés work for some people.

### 6.2 Ambient presence and body doubling

**Body doubling** — working alongside another person, physically or virtually, without collaborating — is one of the most widely adopted ADHD strategies in the community. ADDA describes it as a core tool ([source 24](#sources)). Health media reviewing the literature are blunt: **no formal research has established how or whether it works; the evidence is anecdotal** ([source 28](#sources)). Plausible mechanisms are well-established phenomena stacked together: social facilitation, implicit accountability, co-regulation, and externalized activation. HCI researchers have begun designing and studying it directly, including in VR, focusing on ambient presence calibrated to be present-but-not-interactive ([source 14](#sources)).

**Status: high community confidence, low research confidence.** Ship it; do not claim it is evidence-based.

### 6.3 Fidgeting as regulation

Fidgeting in ADHD looks increasingly like compensation rather than noise. Laboratory work summarized by CHADD found children with ADHD moved substantially more (reported as up to ~25% more) when working-memory demands were unpredictable, suggesting movement is recruited *by* cognitive load rather than being random overflow ([source 21](#sources)). Adult work reported by UC Davis Health found intrinsic fidgeting associated with better cognitive-task performance, with the effect growing as time on task increased — i.e., as attention waned ([source 22](#sources)). Practical read: an ADHDer pacing during a planning session is regulating, not avoiding.

### 6.4 Screens as engineered attention traps

Infinite feeds hit every hyperfocus trigger — novelty, immediate feedback, zero initiation cost — with none of the payoff. A structural-equation study of 563 adults (Xu et al., 2025) found two distinct routes from ADHD symptoms to problematic short-video use: **inattention → boredom proneness → compulsive scrolling**, and **hyperactivity/impulsivity → poorer emotion regulation → distress → scrolling as escape** ([source 29](#sources)).

Two design consequences. First, the competitor for a Klyr user's attention is not another task app; it is a feed optimized by a much larger engineering team. Second, **Klyr must not adopt the feed's mechanics** — infinite scroll, variable-reward notification, streak anxiety — because those mechanics work by exploiting precisely the vulnerability Klyr's users came to manage. See [ux-design-for-adhd.md](../product/ux-design-for-adhd.md) and [motivation-and-gamification.md](../strategies/motivation-and-gamification.md).

## Design implications for Klyr

1. **Ship a two-keystroke capture inbox reachable from every screen, including mid-focus-session.** Distraction-by-anticipation means an uncaptured thought behaves like an unfinished task and keeps consuming attention ([sources 5, 8](#sources)). Target: thought → parked in under 3 seconds with zero categorization required. Any required field (project, due date, priority) at capture time defeats the purpose.

2. **Never make the user leave their current task to capture a thought.** If capture navigates away from the focus view, Klyr has itself become the interruption. Capture must be an overlay that dismisses back to exactly the prior state.

3. **Implement a "ready-to-resume" prompt on every task exit — one field, ~30 seconds, skippable.** Prompt: *where I stopped / what's next / what I'm postponing.* This is the best-evidenced mechanic in this doc (four studies, reduced attention residue, better subsequent performance) ([source 9](#sources)) and directly addresses ADHD set-reconfiguration cost ([source 7](#sources)).

4. **Show the resume note first when a task is reopened — before the description, before subtasks.** "Where was I" breadcrumbs externalize the working-memory reconstruction that ADHD makes expensive ([source 6](#sources), [memory-and-object-permanence.md](./memory-and-object-permanence.md)). Testable: time-to-first-action on a resumed task, with and without the breadcrumb.

5. **Default the focus view to exactly one task with everything else out of sight.** ADHD amplifies external distraction multiplicatively rather than additively ([source 13](#sources)). The list should be reachable in one tap but never ambiently visible during a session.

6. **Warn before transitions; never hard-cut them.** Offer a configurable pre-alarm (e.g., 10 / 5 / 1 minute) whose default message is a ramp, not a stop: "5 minutes left — good moment to note where you are." This pairs the transition warning practice used with ADHD children ([source 27](#sources)) with the ready-to-resume evidence ([source 9](#sources)).

7. **Build hyperfocus guardrails that inform rather than interrupt, and make the user the author of them.** A gentle time anchor ("you've been on this 2h 40m") plus optional body-needs nudges (water, food, movement, bathroom) addresses "timelessness" and "ignoring personal needs," both measured AHQ dimensions ([source 3](#sources)). **Tension to test:** guardrails that break a productive state destroy the main ADHD attentional strength. Default to passive, non-modal, dismissible-forever-per-session; let users opt into firmer ones.

8. **Klyr must never frame hyperfocus as a defect, and must never claim to "fix" it.** The evidence base is thin ([sources 1, 15](#sources)) and the state is a genuine strength. Copy should offer *exit control*, not correction: "want a nudge in an hour?" not "you've been distracted for an hour."

9. **Klyr must never cite the "23 minutes to refocus" statistic in product copy, marketing, or in-app education.** It is not supported by the underlying papers ([sources 17, 25](#sources)). The corpus commits to not shipping numbers we cannot source; this is the most tempting one to break that on.

10. **Treat unfinished-ness as a first-class state with an explicit "paused" affordance, distinct from "not started" and "overdue."** Incompleteness is the strongest driver of attention residue ([source 8](#sources)) and, in ADHD, the most common state. A task that can be *parked cleanly* stops costing attention; a task that can only be "not done" keeps costing it — and keeps generating shame.

11. **Offer environment presets inside the focus view — noise/soundscape, timer, and optional body-double session — as one-tap starts.** Noise has real, ADHD-specific (if small) evidence ([source 10](#sources)); fidget-friendly and movement-tolerant sessions are supported by compensation findings ([sources 21, 22](#sources)); body doubling is community-validated but research-thin ([source 28](#sources)). Label confidence honestly in any explanatory copy: "many people find…" not "research shows…"

12. **Klyr must never use infinite scroll, variable-ratio reward notifications, or loss-framed streaks.** The two documented pathways into compulsive feed use run through boredom and emotion regulation — the exact states a task app finds its users in ([source 29](#sources)). Building the feed's mechanics into Klyr would weaponize the product against its own audience.

13. **Make interruption *by Klyr* an explicit, budgeted event.** A focus session should generate at most one system-initiated interruption unless the user configured more; everything else queues. Rationale: interruption cost in the real data is paid in stress and unfinished threads ([source 17](#sources)), and an ADHD-facing tool that adds interruptions is net-negative regardless of how good its content is.

14. **Support "switch reason" capture on abandonment without judgment.** When a user leaves a task without finishing, offer the resume note and a neutral one-tap reason (stuck / bored / interrupted / changed mind). This produces the user's own attention data — valuable for later review — while explicitly refusing to moralize about it. Never surface these as a "failure" count.

15. **Assume both distraction types and design for both.** Blockers and single-task views handle external distraction; capture, resume notes, and brain-dump surfaces handle internal distraction — which the driving data suggests is the larger risk ([source 13](#sources)). A focus mode that only silences the phone solves half the problem.

## Open questions

- **Do hyperfocus guardrails help or harm net?** Nobody has tested whether time-anchor nudges during hyperfocus improve day-level outcomes or just destroy the best working hour. This needs an in-product A/B with real ADHD users, measured on both output and self-reported day satisfaction.
- **What is the right default nudge threshold?** 60 minutes? 90? Time-since-last-break? Time-past-a-calendar-boundary? Unknown. Likely highly individual and worth learning per user.
- **Does a ready-to-resume note transfer from knowledge work to household and admin tasks?** Leroy & Glomb studied professional/lab tasks. Whether a resume note helps someone return to a half-cleaned kitchen is untested.
- **Does capture actually reduce the intrusive-thought load, or just move it?** Plausible from residue theory, but no ADHD-specific study confirms that writing a thought down reduces its return rate.
- **Is hyperfocus a distinct construct from flow, or the same state under weaker exit control?** Genuinely unsettled ([sources 1, 16](#sources)); the answer would change whether Klyr should try to *induce* it.
- **Does the noise benefit (g≈0.25, in youth) hold for adults, and for browsing-adjacent tasks like planning rather than sustained-attention lab tasks?** The meta-analysis population was children and young adults.
- **Which body-doubling format works for whom?** Live video, ambient audio, asynchronous "someone else is also working now" presence, and AI-simulated presence are very different products with essentially no comparative evidence.

## Sources

1. [Ashinoff & Abu-Akel (2019), *Hyperfocus: the forgotten frontier of attention*, Psychological Research](https://pmc.ncbi.nlm.nih.gov/articles/PMC7851038/) — [research]
2. [Bozhilova et al., *Mind wandering perspective on attention-deficit/hyperactivity disorder*](https://pmc.ncbi.nlm.nih.gov/articles/PMC6525148/) — [research]
3. [Hupfeld et al. (2024), *Validation of the dispositional adult hyperfocus questionnaire (AHQ-D)*, Scientific Reports](https://pmc.ncbi.nlm.nih.gov/articles/PMC11339405/) — [research]
4. [Hupfeld, Abagis & Shah (2019), *Living "in the zone": hyperfocus in adult ADHD*, ADHD Attention Deficit and Hyperactivity Disorders](https://link.springer.com/article/10.1007/s12402-018-0272-y) — [research]
5. [*A d factor? Understanding trait distractibility and its relationships with ADHD symptomatology and hyperfocus*, PLOS ONE](https://pmc.ncbi.nlm.nih.gov/articles/PMC10599552/) — [research]
6. [Cepeda, Cepeda & Kramer (2000), *Task switching and attention deficit hyperactivity disorder*](https://pubmed.ncbi.nlm.nih.gov/10885680/) — [research]
7. [*Selective impairment of attentional set shifting in adults with ADHD*, Behavioral and Brain Functions (2018)](https://link.springer.com/article/10.1186/s12993-018-0150-y) — [research]
8. [Leroy (2009), *Why is it so hard to do my work? The challenge of attention residue when switching between work tasks*, Organizational Behavior and Human Decision Processes](https://ideas.repec.org/a/eee/jobhdp/v109y2009i2p168-181.html) — [research]
9. [Leroy & Glomb (2018), *Tasks Interrupted… and how a "ready-to-resume" plan mitigates the effects*, Organization Science](https://experts.umn.edu/en/publications/tasks-interrupted-how-anticipating-time-pressure-on-resumption-of/) — [research]
10. [Nigg et al. (2024), *Systematic Review and Meta-Analysis: Do White Noise or Pink Noise Help With Task Performance in Youth With ADHD…*, JAACAP](https://www.jaacap.org/article/S0890-8567(24)00074-1/abstract) — [research]
11. [*Stochastic resonance is not required for pink noise to have beneficial effects on ADHD-related performance? The moderate brain arousal model challenged*, Neuropsychologia (2024)](https://www.sciencedirect.com/science/article/abs/pii/S0028393224001763) — [research]
12. [Mehta, Zhu & Cheema (2012), *Is Noise Always Bad? Exploring the Effects of Ambient Noise on Creative Cognition*, Journal of Consumer Research](https://academic.oup.com/jcr/article-abstract/39/4/784/1798283) — [research]
13. [*The Increased Risk of Road Crashes in ADHD Adult Drivers: Driven by Distraction?*, PLOS ONE](https://pmc.ncbi.nlm.nih.gov/articles/PMC4275204/) — [research]
14. [*You Are Not Alone: Designing Body Doubling for ADHD in Virtual Reality* (arXiv, 2025)](https://arxiv.org/pdf/2509.12153) — [research]
15. [*Experiences of deep concentration in individuals with ADHD: an integrative review* (2025)](https://pmc.ncbi.nlm.nih.gov/articles/PMC12438511/) — [research]
16. [*Experiences of hyperfocus and flow in college students with and without ADHD*, Current Psychology](https://link.springer.com/article/10.1007/s12144-021-02539-0) — [research]
17. [Mark, Gudith & Klocke (2008), *The Cost of Interrupted Work: More Speed and Stress*, CHI](https://ics.uci.edu/~gmark/chi08-mark.pdf) — [research]
18. [Phys.org report on Leroy & Glomb's ready-to-resume study (Organization Science)](https://phys.org/news/2018-01-strategy-recover.html) — [research]
19. [*EEG Correlates of Cognitive Dynamics in Task Resumption After Interruptions: The Impact of Available Time and Flexibility*](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11851001/) — [research]
20. [ADDitude, *Hyperfocus and the ADHD Brain* (medically reviewed; quotes Barkley, Nadeau, Silver)](https://www.additudemag.com/understanding-adhd-hyperfocus/) — [clinical]
21. [CHADD, *How Does Fidgeting Enhance Focus for Individuals with ADHD?*](https://chadd.org/attention-article/how-does-fidgeting-enhance-focus-for-individuals-with-adhd/) — [clinical]
22. [UC Davis Health, *Does fidgeting help people with ADHD focus?* (2024)](https://health.ucdavis.edu/news/headlines/does-fidgeting-help-people-with-adhd-focus-/2024/10) — [clinical]
23. [PsyPost report on the Nigg et al. noise meta-analysis, incl. stated limitations](https://www.psypost.org/white-and-pink-noise-show-promise-in-enhancing-attention-in-those-with-adhd/) — [research]
24. [ADDA, *The ADHD Body Double: A Unique Tool for Getting Things Done*](https://add.org/the-body-double/) — [clinical]
25. [oberien, *Interruptions cost 23 minutes 15 seconds, right?* — source trace of the Gloria Mark figure](https://blog.oberien.de/2023/11/05/23-minutes-15-seconds.html) — [community]
26. [ADDitude, *ADHD Hyperfocus Let-Down: Avoiding the Crash* (Douglas Cootey — lived experience, no research cited)](https://www.additudemag.com/adhd-hyperfocus-crash/) — [community]
27. [ADDitude, *Managing Transitions for Children with ADHD*](https://www.additudemag.com/managing-transitions-adhd-children/) — [clinical]
28. [Medical News Today, *Body doubling for ADHD* (notes absence of formal research)](https://www.medicalnewstoday.com/articles/body-doubling-adhd) — [clinical]
29. [Simply Psychology summary of Xu et al. (2025), *Psychology Research and Behavior Management* — ADHD symptoms and problematic short-video use (N=563)](https://www.simplypsychology.org/news/how-adhd-symptoms-fuel-compulsive-short-video-scrolling) — [research]
30. [Mark, Gonzalez & Harris (2005), *No Task Left Behind? Examining the Nature of Fragmented Work*, CHI 2005 (24 information workers; ~11-min working spheres, 57% interrupted, 52% internal / 48% external, 77% resumed same day)](https://www.ics.uci.edu/~gmark/CHI2005.pdf) — [research]
31. [Gilbert, S. J., et al. (2022), *Outsourcing memory to external tools: A review of "intention offloading"*, Psychonomic Bulletin & Review](https://pubmed.ncbi.nlm.nih.gov/35789477/) — [research]
32. [American Psychological Association, *Speaking of Psychology: Why our attention spans are shrinking, with Gloria Mark, PhD* (reports her observational finding of ~2.5-min screen attention in 2004 falling to ~47 sec)](https://www.apa.org/news/podcasts/speaking-of-psychology/attention-spans) — [research]
