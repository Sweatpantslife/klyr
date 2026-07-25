---
title: "Time Perception and Time Blindness in ADHD"
area: foundations
file: research/foundations/time-perception.md
tags: [time-blindness, temporal-discounting, deadlines, scheduling, chronotype, waiting-mode, time-estimation]
related:
  - research/foundations/executive-function.md
  - research/foundations/dopamine-and-motivation.md
  - research/foundations/memory-and-object-permanence.md
  - research/daily-life/task-initiation-and-paralysis.md
  - research/strategies/evidence-based-strategies.md
sources: 22
updated: 2026-07-25
summary: >
  How ADHD alters the perception, estimation, and use of time — from lab timing
  deficits and steep delay discounting to chronic lateness, "waiting mode," and
  delayed chronotypes. Read this before designing anything in Klyr that involves
  clocks, durations, deadlines, scheduling, or the shape of a day.
---

# Time Perception and Time Blindness in ADHD

## TL;DR

- **Time blindness** is a descriptive term, not a DSM-5-TR or ICD-11 diagnosis. Russell Barkley called it **temporal myopia** — nearsightedness for time. It is a real, measurable cluster of timing problems, but no clinician can bill for it. [1][15]
- Meta-analyses find timing deficits in ADHD across *all four* lab paradigms — discrimination, estimation, production, reproduction — with medium effects on discrimination and reproduction and small-to-medium effects on estimation and production. Task type does not much moderate it. [2][3]
- A lifespan meta-analysis of 824 effect sizes found a mean **g = 0.688** for time-perception deficits, moderated by age and (in under-18s) working memory. Adult-specific evidence is much thinner and mixed. [4][5]
- Time in ADHD is often experienced as a binary: **now** and **not-now**. Something two weeks out and something two hours out can feel equally unreal. [1][13]
- People with ADHD discount delayed rewards more steeply than controls — meta-analytic **d = 0.43** across 25 case-control comparisons (N = 3,913), with no significant moderation by age, real vs hypothetical rewards, or comorbid conduct disorder. [6][7]
- Steep (hyperbolic-shaped) discounting predicts the lived pattern of **nonlinear deadline salience**: a deadline is nearly weightless for weeks, then becomes overwhelming in the last hours. Panic is a *late-arriving* motivational signal, not a personality flaw.
- A 2025 VR study found children with ADHD checked the clock *as often* as peers but **less strategically** — fewer checks in the critical window before the target time. Strategic monitoring fully mediated the ADHD effect on time-based prospective memory (22.1% of variance). Timing of the prompt matters more than the number of prompts. [8]
- **Waiting mode** — being unable to start anything before a scheduled event — is a widely reported community concept with essentially *no direct research*. Treat it as strong UX truth, weak science. [11][12][16]
- ADHD is strongly associated with a delayed circadian phase: dim-light melatonin onset delayed roughly **45 minutes in children and 90 minutes in adults**, delayed sleep-wake timing in 73–78%, and ~33% of one adult ADHD clinical sample meeting criteria for delayed sleep phase disorder vs roughly 0.2–1.5% in general adult populations. [9][10][17]
- **Externalizing** time works better than trying harder to feel it. An RCT of time-skill training plus time-assistive devices in children with ADHD improved time-processing ability (d = 0.38) and parent-rated daily time management (d = 1.0) — though children's *self*-ratings did not improve. [18]
- Design consequence for Klyr: never assume the user can feel duration, sequence a day, or notice a deadline approaching. The app must hold time for them — visibly, ambiently, and without punishing them for needing it.

---

## 1. What "time blindness" is — and what it is not

**Time blindness** describes a cluster of difficulties in perceiving, estimating, tracking, and acting on time. It is not a formal diagnosis in DSM-5-TR or ICD-11, and it is not a named ADHD criterion. [15] Use it as a shared vocabulary word, not a claim of clinical status.

The conceptual anchor is Russell Barkley's account of ADHD as a disorder of self-regulation across time. In his 1997 unifying theory, deficient behavioral inhibition undermines four executive functions — nonverbal working memory (which is where a sense of hindsight and forethought lives), self-regulation of affect/motivation/arousal, internalized speech, and reconstitution — with the net effect that behavior is governed by the immediate context rather than by internally represented future events. [14] Barkley later popularized **temporal myopia**: like nearsightedness, the further away an event is, the blurrier it gets, and the less it can steer present behavior. [1][15]

Two clarifications that matter for product work:

- This is a **performance** problem, not a knowledge problem. People with ADHD usually know perfectly well that the report is due Friday. Barkley's "point of performance" argument — that support must be delivered *where and when* the behavior happens, not in advance as advice — is developed in [executive-function.md](./executive-function.md).
- It is not uniform. The 2023 review of a decade of adult time-perception research found only 9 studies met inclusion criteria out of 535 screened; some showed clear estimation and reproduction deficits, others found no significant difference from controls. The author concluded that time perception in adult ADHD has "very high complexity and variability." [5] Klyr should not build around a single assumed profile.

## 2. What the lab actually shows

Four standard paradigms are used. The 2021 meta-analysis by Marx, Cortese, Koelch, and Hacker in *JAACAP* pooled 55 studies (mean sample ages 8.3–41.8 years):

| Paradigm | What the participant does | Everyday analog | Meta-analytic result [2] |
|---|---|---|---|
| **Time discrimination** | Judge which of two intervals is longer | "That took longer than last time" | Medium effect; 25 studies, 1,633 participants. Deficits especially for sub-second intervals |
| **Time reproduction** | Reproduce an interval just experienced | "Do that again for about as long" | Medium effect on absolute error; 26 studies, 2,364 participants |
| **Time estimation** | Say how long an interval was | "How long was I in the shower?" | Small-to-medium effect on absolute error; 8 studies, 1,024 participants |
| **Time production** | Produce an interval of a stated length | "Tell me when 10 minutes are up" | Small effect on absolute error; 7 studies, 380 participants |

A child/adolescent meta-analysis (Zheng, Wang, Chiu & Shum, 2022; 27 studies, 2,869 participants) found deficits in both **accuracy** (g > 0.40) and **precision** (g = 0.66), unmoderated by task type or stimulus modality but moderated by age and gender. [3] A lifespan systematic review and meta-analysis (Metcalfe, McFeaters & Voyer, *Developmental Neuropsychology*, 2024) reported a mean **g = 0.688** across 824 effect sizes, moderated by age and — for under-18 samples only — working memory. [4]

**An important tension to hold.** Zheng et al. found children with ADHD had a *higher propensity to overestimate* intervals. [3] Yet the universal lived complaint is *underestimating* how long real tasks take. These are not the same measurement. Lab work mostly probes sub-second to tens-of-seconds intervals with a stimulus you are attending to; life asks you to forecast a multi-step, interruption-laden activity over 20 minutes to 3 hours. Prospective duration forecasting for real tasks recruits step enumeration, working memory, and retrieval of past instances — which is likely why it fails differently. **Klyr should not infer real-world estimation behavior from lab timing effect sizes.** It should learn each user's actual error empirically.

Direction of error also flips with attentional load: a widely used model of interval timing holds that when attention wanders, fewer "pulses" are accumulated and the interval feels shorter. This is a plausible mechanism, not a settled ADHD-specific finding.

## 3. "Now" and "not-now"

Clinically and in the community, ADHD time is often described as two zones: **now** (on the radar, actionable, emotionally real) and **not-now** (everything else, undifferentiated). [1][13] In that frame, "tomorrow at 4pm" and "the 14th of next month" occupy the same bucket. This is a heuristic model rather than a validated psychometric construct, but it maps well onto both Barkley's temporal myopia and the discounting literature below, and it is how many ADHDers actually describe their experience — which makes it useful copy language.

Its practical consequence: a list of undated tasks is not a plan, and a distant deadline written on a calendar does not create urgency. It creates a record.

## 4. Temporal discounting: why the future does not pull

**Delay discounting** (temporal discounting) is how sharply a reward loses subjective value as it gets further away. Jackson and MacKillop's 2016 meta-analysis of monetary discounting — 21 investigations, 25 case-control comparisons, N = 3,913 — found a medium effect (**d = 0.43**, p < 10⁻¹⁵), with minimal heterogeneity and no significant moderation by age, real versus hypothetical rewards, or comorbid conduct/oppositional disorders. [6] A comparative meta-analysis by Marx and colleagues across simple choice-delay and temporal discounting paradigms (37 group comparisons, 3,763 participants) found small-to-medium effects for both, and argued that **delay aversion** — an active dislike of waiting — contributes alongside pure discounting. [7]

That distinction matters for Klyr: delay aversion means waiting itself is *aversive*, not merely uninformative. A UI that makes the user sit in a delay is imposing a cost, not a neutral pause.

### Nonlinear deadline salience

Discounting curves are steep and convex near zero delay: value climbs slowly for weeks, then vertically in the final stretch. Combine a steeper-than-typical curve with blurry perception of *how far away* the deadline is, and you get the pattern every ADHD adult recognizes — three weeks of nothing, then a night of adrenaline-fueled, often genuinely good work. (The functional-form reasoning here is our synthesis of the discounting findings, not a directly measured ADHD result.)

Two design-relevant implications:
1. Panic is a real motivational mechanism, and it works. It also costs sleep, quality control, and self-esteem. The goal is not to shame it out of existence but to **manufacture earlier, cheaper urgency**.
2. Because value rises nonlinearly, a *linear* progress bar toward a due date is emotionally misleading — it reads as "plenty of time" right up until it doesn't.

More on the motivational machinery, including where popular "interest-based nervous system" framing sits scientifically, is in [dopamine-and-motivation.md](./dopamine-and-motivation.md).

## 5. Estimation failures and the planning fallacy

The **planning fallacy** (Kahneman & Tversky) is the general human tendency to predict task completion using a best-case, inside-view scenario. Everyone does it. Does ADHD amplify it? **I did not find a study in this pass that directly tests planning-fallacy magnitude in ADHD versus controls.** The inference is reasonable — lab timing deficits, weak working memory, and poor retrieval of prior durations all point that way — but treat "ADHD amplifies the planning fallacy" as clinically endorsed and mechanistically plausible rather than demonstrated.

What clinicians describe (Ari Tuckman, writing for ADDitude) is two compounding factors: time blindness warps the internal ruler so an hour does not *feel* the same, and tasks expand to fill available time. His recommendations are concrete and testable: measure recurring tasks a few times rather than estimating them, allocate fixed blocks for nebulous work instead of forecasting it, and always budget more than feels necessary because underestimation is more common than overestimation. [13][19]

Klyr's opportunity: users cannot introspect their error, but software can *measure* it. A per-user, per-category **correction factor** learned from actual start/stop data is a strictly better instrument than a self-report guess.

## 6. Strategic time monitoring — the most actionable finding in this doc

Seesjärvi et al. (2025, *Scientific Reports*) tested 71 children with ADHD and 71 typically developing peers (ages 9–13) in **EPELI**, a naturalistic VR apartment where children carry out everyday routines while a time-based prospective memory task requires acting at 15, 30, or 45 seconds. A virtual clock was available on demand.

Both groups checked the clock about **equally often**. What differed was *when*. Typically developing children showed a J-shaped curve — few checks early, exponentially more as the target approached. Children with ADHD spread checks across less critical moments. This "relative clock-checking" measure (β = −0.33) **fully mediated** the effect of ADHD on prospective memory performance and accounted for 22.1% of variance on its own; the full model explained 53.9%. The authors note monitoring strategies are trainable. [8]

This reframes the entire reminder problem. The deficit was **not** insufficient attention to time. It was **allocation** of attention to time. Software is unusually good at exactly this: an app can concentrate salience into the final window instead of spraying notifications evenly, or worse, sending one reminder a week out.

Prospective memory more broadly — remembering to do the thing — is covered in [memory-and-object-permanence.md](./memory-and-object-permanence.md).

## 7. Waiting mode

**Status: community term. Widely reported, essentially unstudied.** Healthline's ADHD explainer, medically reviewed by Bethany Juby, PsyD, states plainly that there is currently no research specifically examining waiting mode. [11]

The reported experience: with an appointment at 3pm, the entire day before it is unusable. Not relaxing, not productive — suspended. People describe anxiety, checking the clock, and refusing to start anything "because I'd just have to stop."

Proposed mechanisms across community and clinician-adjacent sources (all speculative, none tested):
- **Working memory occupancy** — holding the appointment in mind consumes the resource needed to start something else. [11][16]
- **Learned fear of hyperfocus** — refusing to start is a rational defense if you have missed appointments by getting absorbed. [12][16]
- **Transition cost** — starting means also planning the exit, which doubles the initiation problem. [12]
- **Anxious freeze / rumination** — a loop closer to rumination than to distractibility. [16]

Suggested coping strategies from the same sources cluster around: brain-dumping the anxiety, scheduling appointments early in the day so waiting mode consumes less of it, backward-planning from the event, external alarms so the brain can stop holding the time, and keeping a list of low-stakes "waiting-sized" tasks. [11][12][16]

For Klyr, waiting mode is a **first-class day-shape problem**, not a mood. The user's calendar can be 95% empty and still yield zero output. It overlaps with, but is distinct from, general task paralysis — see [task-initiation-and-paralysis.md](../daily-life/task-initiation-and-paralysis.md); waiting mode is specifically *time-bounded* and resolves the moment the event passes.

## 8. Chronic lateness: the mechanics

Lateness in ADHD is rarely one failure; it is a stack of them. Kathleen Nadeau, Ph.D., writing for ADDitude, names: **"one-more-thing-itis"** (squeezing in a final task before leaving), underestimating both preparation and travel time, difficulty tolerating empty time (so arriving early feels intolerable and gets engineered away), and over-commitment. Her recommendations include *two* alarms — one five minutes before departure and one at departure — planning to arrive 15 minutes early, adding ten minutes per half hour of travel, and staging belongings the night before. [20]

Decomposed for software, a "leave at 3:00" event is really: stop current task → transition → prepare/gather → travel → buffer. Users typically schedule only the travel leg. **Transitions are the invisible, systematically unbudgeted segment.** Task-switching costs and interruption recovery are covered in [attention-and-hyperfocus.md](./attention-and-hyperfocus.md); the emotional aftermath of chronic lateness — the shame spiral, the partner who thinks it is disrespect — belongs to [emotional-regulation-and-rsd.md](./emotional-regulation-and-rsd.md) and [daily-life-impact.md](../daily-life/daily-life-impact.md).

## 9. Chronotype, sleep phase, and the usable day

The evidence here is strong and underused by productivity software.

- Sleep disturbance affects up to **80% of adults** and **82% of children** with ADHD; delayed sleep-wake timing occurs in **73–78%**. [9]
- **Dim-light melatonin onset (DLMO)** — the body's internal "night is starting" signal — is delayed by roughly **45 minutes in children and 90 minutes in adults** with ADHD relative to controls. [9]
- In a clinical sample of 102 adults diagnosed with ADHD in adulthood, **34 (~33%)** met criteria for delayed sleep phase disorder. [17] Population estimates of DSWPD in general adult samples run around **0.17%–1.51%**. [10] Caveat: the ADHD study had no control group, and prevalence estimates vary widely by diagnostic criteria — so treat the ratio as indicative, not exact.
- Chronotherapy findings are encouraging: low-dose melatonin (0.5 mg) advanced DLMO by 88 minutes in adults with a 14% reduction in ADHD symptoms; morning bright light plus melatonin produced roughly two-hour phase advances, with phase advancement correlating with symptom improvement. [9]

The design consequence is blunt: a large majority of ADHD users are **late chronotypes living in a morning-shaped world**. Apps that default to 8am daily planning rituals, "start your day" streaks, and morning-only review prompts are systematically mistimed for their core user.

### Medication windows (community-reported pattern, clinically grounded)

Stimulant coverage is uneven by design. Dan Shapiro, M.D., writing for CHADD, describes peaks and troughs as blood levels rise and fall through the therapeutic range: short-acting stimulants take effect in roughly 10–15 minutes, long-acting formulations in 30–60 minutes or longer, leaving three commonly unprotected windows — early morning, late afternoon/early evening, and bedtime. [21]

What is *community*-reported (not established in research) is the downstream behavior: many medicated adults describe an effective working window and deliberately schedule demanding cognitive work inside it, dumping admin into the tail. Klyr should support this pattern without ever asking about, storing, or naming medication as such — an "energy window" is the same tool with none of the sensitivity.

## 10. Does anything actually externalize time successfully?

Some, modestly, with honest caveats:

- **Wennberg et al. (2017), *European Child & Adolescent Psychiatry***: RCT, 38 children with ADHD aged ~8.6–15.1, 12-week intervention plus 12-week implementation. Time-skill training plus time-assistive devices (visual timers, electronic day schedules, weekly/annual schedules, synced mobile calendars) improved time-processing ability (Cohen's d = 0.38), time orientation (d = 0.42), and parent-rated daily time management (**d = 1.0**). Time *management* subscale and children's self-ratings did not significantly improve. [18] Note the split: adults around the child saw large gains; the children did not report feeling better. Small sample, no blinding.
- **Let's Get Organized (LGO-S)**, a manualized 10-week group time-management intervention: in a 2026 multi-centre pragmatic RCT (n = 75 adults with ADHD, autism, or mental disorders), both LGO-S and treatment-as-usual individual occupational therapy improved time-management skills, organization/planning, emotional regulation, and self-efficacy — but **the between-group difference was not statistically significant**. [22] Structured time-management support helps; this particular format is not proven superior.

Intervention evidence in general — CBT, coaching, body doubling, implementation intentions, and what reliably fails — is the domain of [evidence-based-strategies.md](../strategies/evidence-based-strategies.md), and system-level approaches like time blocking are stress-tested in [planning-methodologies-and-adhd.md](../strategies/planning-methodologies-and-adhd.md).

---

## Design implications for Klyr

1. **Show duration as space, not as arithmetic.** Render remaining time as a shrinking wedge, bar, or arc alongside the numeral, so reading it is a perceptual judgment rather than a subtraction. Lab deficits are in *interval perception* [2][3]; converting a temporal judgment into a spatial one sidesteps the weakest channel.

2. **Learn a per-user, per-category correction factor and apply it silently.** Track estimate versus actual for repeated task types; after enough samples, show "you usually say 30 min — it's taken you ~50." Clinicians already recommend measuring instead of estimating [19]; software can do it without the user maintaining a log. Never present it as a failure metric — present it as calibration.

3. **Concentrate reminder salience into the final window rather than spreading it.** Seesjärvi et al. found ADHD monitoring failed on *allocation*, not frequency [8]. Klyr should mimic the J-curve: near-silent early, escalating sharply in the last 10–20% of the runway. Uniform daily nags are the exact anti-pattern.

4. **Make deadline pressure nonlinear and honest.** A linear countdown misrepresents felt urgency under steep discounting [6][7]. Consider a curve-shaped urgency indicator plus system-suggested **intermediate commitments** (a self-set soft deadline days before the real one) so urgency arrives early and cheap instead of late and expensive.

5. **Budget transitions explicitly; never schedule back-to-back by default.** Model any timed commitment as stop → transition → prepare → travel → buffer, and auto-insert a default buffer users can tune. Nadeau's clinical guidance — two alarms, arrive 15 minutes early, add 10 minutes per half hour of travel — is directly implementable. [20]

6. **Ship a "leaving soon" mode, not just an event reminder.** The failure is the last task before departure ("one-more-thing-itis") [20]. In the pre-departure window Klyr should stop offering new work, surface only the departure checklist, and give a visible shrinking countdown to *stop-doing-things* time — which is earlier than departure time.

7. **Design explicitly for waiting mode.** When a user has a commitment later with a gap before it, Klyr should (a) state the usable working time in plain words ("you have 2h 10m before you need to leave"), (b) offer only tasks that fit that window with buffer, and (c) guarantee the interrupt — "I will tell you at 2:35, you can stop watching the clock." The mechanism is unproven [11] but the behavior pattern is near-universal in community reports [12][16], so treat this as a testable hypothesis with high expected value.

8. **Offer a "waiting-sized tasks" bucket.** Users should be able to tag tasks as low-stakes, interruptible, and short. Klyr surfaces exactly these during pre-event gaps and genuine waiting (queues, transit). This directly implements the most-repeated community coping strategy. [11][12]

9. **Default the day's shape to the user's chronotype, and never moralize about mornings.** With delayed sleep phase common in ADHD [9][17], morning-anchored defaults, "early bird" badges, and 6am streak resets penalize the majority of the target user base. Ask once for a rough energy window, or infer it from usage, and anchor planning and review prompts to that.

10. **Provide neutral "energy windows" instead of anything medication-shaped.** Let users mark 1–2 daily windows for demanding work and route cognitively heavy tasks into them; route admin to the tails. This supports the community-reported practice of planning around stimulant coverage [21] without storing health data or naming medication anywhere in the product.

11. **Timed sessions must be optional, resumable, and non-punitive.** Countdown timers create pressure that can itself block initiation (community-reported, and consistent with delay aversion [7]). Offer count-**up** ("just start, I'll track it") as a first-class alternative to count-down, allow extending without ending the session, and never mark an unfinished session as failed.

12. **Never let time-related failure generate shame copy.** Missed events, blown estimates, and overdue items should be restated as data, never as verdicts. Wennberg et al. is a warning here: parents rated large improvement while the children's own ratings did not improve [18] — externally visible success does not automatically produce internal relief, and a scolding tone would guarantee the opposite. See [emotional-regulation-and-rsd.md](./emotional-regulation-and-rsd.md).

13. **Give every task a place in time, not just a place on a list.** Undated items live in "not-now" and are functionally invisible [1][13]. Klyr should make scheduling frictionless and reversible — but must **never** force a date at capture time, because that friction kills capture (see [memory-and-object-permanence.md](./memory-and-object-permanence.md)). Capture free, schedule later, nudge gently.

14. **Ambient time display beats interruptive time reminders.** A persistent, glanceable representation of "time left in this block" (widget, lock screen, menu bar) externalizes time continuously without demanding a context switch. Interruption recovery is expensive; see [attention-and-hyperfocus.md](./attention-and-hyperfocus.md).

15. **Tension to resolve with users, not in a spec:** urgency helps ADHDers start, and urgency also harms them. Manufacturing pressure (countdowns, escalation, artificial deadlines) is the most effective activation lever available and the most likely to produce anxiety, avoidance, and app abandonment. Klyr should make urgency *adjustable per user and per task*, default it low, and measure abandonment against activation in testing.

## Open questions

- **Does ADHD measurably amplify the planning fallacy beyond baseline human optimism?** I found no direct head-to-head study. Worth testing in-product: compare users' estimate/actual ratios against published general-population planning-fallacy magnitudes.
- **How many samples does a personal correction factor need before it beats a self-report guess?** Unknown; determine empirically, and decide whether to correct per category, per context (morning vs evening, medicated window vs not), or globally.
- **Does an escalating J-curve notification schedule outperform fixed reminders for real ADHD adults?** Seesjärvi et al. is a VR study in children with second-scale intervals [8]. The generalization to adults and multi-hour intervals is a hypothesis, and a highly testable one.
- **Does an explicit waiting-mode feature relieve waiting mode, or make people more aware of the wait?** There is no research to lean on [11]. Needs A/B testing with qualitative follow-up.
- **Count-up versus count-down:** which produces more starts, and for whom? Community reports conflict; likely moderated by anxiety and by task type.
- **Where is the line between helpful urgency and harmful pressure**, and can users self-report it accurately in advance — or does it need to be learned from behavior?
- **Chronotype defaults:** should Klyr infer the user's window from usage data (fast, possibly creepy) or ask (slower, more transparent)? And should it ever encourage phase advance, given chronotherapy evidence [9], or is that firmly out of a task app's lane? *(Our current view: out of lane. Klyr accommodates the chronotype; it does not treat it.)*
- **Do timing measures predict anything Klyr can act on?** Effect sizes are group-level; individual variability is high [5]. Personalization should be driven by each user's observed behavior, never by an assumed ADHD profile.

## Sources

1. [ADHD and Time Blindness — Understood (Sarah Greenberg, MA, MEd)](https://www.understood.org/en/articles/adhd-time-blindness) [clinical]
2. [Meta-analysis finds consistent time perception impairments in persons with ADHD — ADHD Evidence Project summary of Marx, Cortese, Koelch & Hacker (2021), *JAACAP*](https://www.adhdevidence.org/blog/time-blindness-found-to-be-a-consistent-feature-of-adhd) [research]
3. [Zheng Q., Wang X., Chiu K.Y., Shum K.K. (2022). Time Perception Deficits in Children and Adolescents with ADHD: A Meta-analysis. *Journal of Attention Disorders* 26(2), 267–281](https://journals.sagepub.com/doi/abs/10.1177/1087054720978557) [research]
4. [Metcalfe, McFeaters & Voyer (2024). Time-Perception Deficits in Attention-Deficit/Hyperactivity Disorder: A Systematic Review and Meta-Analysis. *Developmental Neuropsychology* 49(1)](https://www.tandfonline.com/doi/full/10.1080/87565641.2023.2293712) [research] *(abstract only; full text paywalled)*
5. [Mette C. (2023). Time Perception in Adult ADHD: Findings from a Decade — A Review. *Int. J. Environ. Res. Public Health*](https://pmc.ncbi.nlm.nih.gov/articles/PMC9962130/) [research]
6. [Jackson J.N.S. & MacKillop J. (2016). ADHD and Monetary Delay Discounting: A Meta-Analysis of Case-Control Studies. *Biological Psychiatry: CNNI*](https://pubmed.ncbi.nlm.nih.gov/27722208/) [research]
7. [Marx I., Hacker T., Yu X., Cortese S., Sonuga-Barke E. (2021). ADHD and the Choice of Small Immediate Over Larger Delayed Rewards: A Comparative Meta-Analysis. *Journal of Attention Disorders*](https://journals.sagepub.com/doi/10.1177/1087054718772138) [research]
8. [Seesjärvi E. et al. (2025). A naturalistic virtual reality task reveals difficulties in time-based prospective memory and strategic time-monitoring in children with ADHD. *Scientific Reports*](https://pmc.ncbi.nlm.nih.gov/articles/PMC12241525/) [research]
9. [Luu B. & Fabiano N. (2025). ADHD as a circadian rhythm disorder: evidence and implications for chronotherapy. *Frontiers in Psychiatry*](https://pmc.ncbi.nlm.nih.gov/articles/PMC12728042/) [research]
10. [Nesbitt A.D. Delayed sleep-wake phase disorder. *Journal of Thoracic Disease*](https://jtd.amegroups.org/article/view/18434/html) [research]
11. [ADHD Waiting Mode — Healthline (medically reviewed by Bethany Juby, PsyD)](https://www.healthline.com/health/adhd/adhd-waiting-mode) [community]
12. [Stuck in waiting mode? ADHD tips for managing time and focus — Tiimo](https://www.tiimoapp.com/resource-hub/stuck-in-waiting-mode-adhd-tips) [community]
13. [How ADHD Warps Time Perception — ADDitude (Ari Tuckman, Psy.D.; quoting Russell Barkley, Ph.D.)](https://www.additudemag.com/wasting-time-adhd-and-time-perception/) [clinical]
14. [Barkley R.A. (1997). Behavioral inhibition, sustained attention, and executive functions: Constructing a unifying theory of ADHD. *Psychological Bulletin* 121(1), 65–94](https://psycnet.apa.org/doiLanding?doi=10.1037%2F0033-2909.121.1.65) [research]
15. [Time Blindness in ADHD: What It Is and Evidence-Based Strategies — Simply Psychology](https://www.simplypsychology.com/articles/adhd-time-blindness-management) [clinical]
16. [Waiting mode: why your ADHD brain has time anxiety — Inflow (Leslie Hughes)](https://www.getinflow.io/post/waiting-mode-hard-to-be-productive-when-you-have-plans) [community]
17. [Spera V. et al. (2020). Adult attention-deficit hyperactivity disorder and clinical correlates of delayed sleep phase disorder. *Psychiatry Research*](https://pubmed.ncbi.nlm.nih.gov/32554185/) [research]
18. [Wennberg B., Janeslätt G., Kjellberg A., Gustafsson P.A. (2017). Effectiveness of time-related interventions in children with ADHD aged 9–15 years: a randomized controlled study. *European Child & Adolescent Psychiatry*](https://pmc.ncbi.nlm.nih.gov/articles/PMC5852175/) [research]
19. [Why Time Estimation Stumps ADHD Minds: Our Planning Fallacy — ADDitude (Ari Tuckman, Psy.D.)](https://www.additudemag.com/time-estimation-planning-fallacy-adhd/) [clinical]
20. [Chronic Lateness: Causes and Solutions — ADDitude (Kathleen Nadeau, Ph.D.)](https://www.additudemag.com/chronic-lateness/) [clinical]
21. [Peaks and Troughs: Uneven Medication Coverage & ADHD — CHADD (Dan Shapiro, M.D.)](https://chadd.org/attention-article/peaks-and-troughs-uneven-medication-coverage-adhd/) [clinical]
22. [Lidström Holmqvist K., Wingren M., Udumyran R., Holmefur M. (2026). Effectiveness of a group-based time-management intervention ("Let's Get Organized"): a pragmatic randomised controlled trial. *Disability & Rehabilitation*](https://pubmed.ncbi.nlm.nih.gov/41527987/) [research]
