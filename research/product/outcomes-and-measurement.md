---
title: "Outcomes and Measurement: How Klyr Knows It's Working"
area: product
file: research/product/outcomes-and-measurement.md
tags: [measurement, kpis, outcomes, validated-instruments, ema, engagement-metrics, regulatory, ab-testing]
related:
  - research/strategies/evidence-based-strategies.md
  - research/product/when-to-back-off.md
  - research/foundations/executive-function.md
  - research/product/app-landscape.md
  - research/foundations/dopamine-and-motivation.md
sources: 5
updated: 2026-07-25
summary: >
  What Klyr should actually measure to know it is helping — a metric hierarchy that
  puts functional outcomes above throughput, validated instruments stress-tested for
  app use, honest behavioral proxies vs. vanity metrics, EMA feasibility, an anti-metrics
  list of KPIs that structurally manufacture shame, and the FTC/DTx floor plus an
  honest-claims checklist before Klyr ever says it "helps." Read before defining any
  KPI, success dashboard, A/B test, or marketing claim.
---

# Outcomes and Measurement: How Klyr Knows It's Working

## TL;DR

- The corpus repeatedly disqualifies the obvious KPIs — engagement (novelty-confounded; every app works for two weeks, see [dopamine-and-motivation](../foundations/dopamine-and-motivation.md)) and global self-rating (positive illusory bias) — but never says what to measure instead. This doc is the answer, so the team does not default to exactly the wrong dashboard.
- **"Working" for Klyr means improved real-world function and a lighter maintenance burden — not more app usage and not more tasks closed.** The single orienting target is **return-after-lapse**: of users who go quiet, how many come back and do something meaningful without being guilt-tripped into it ([app-landscape](app-landscape.md) names this the positioning).
- **Validated instruments exist and some are app-feasible.** ASRS v1.1 (18 items, 6-item screener, free, WHO/Kessler) measures *symptoms*; WFIRS-S (~70 items, function across 7 life domains), BDEFS-SF (~20 items, everyday executive function), and AAQoL (29 items, ADHD quality of life) measure what actually matters. All are self-report and inherit self-report bias — use them periodically and in aggregate, never as gates.
- **Everyday-function ratings beat lab tests, but self-rating of "am I improving?" is unreliable.** ADHD carries a documented **positive illusory bias** (people over-rate their own competence), so global "how productive were you?" prompts measure mood weather, not benefit. Prefer validated scales anchored to concrete behaviors, and prefer behavioral evidence over self-report where you can get it.
- **In-app behavior can be a proxy for benefit, but the link to real-world function is largely unproven.** Candidate proxies that plausibly track benefit: self-nominated-important-task completion, resurfaced-item action rate, restart latency after an absence, capture-to-next-action. Vanity proxies that do not: total throughput, DAU, streak length, time-in-app.
- **Engagement and outcome are decoupled in mHealth.** Median 15-day retention for mental-health apps is ~3.9% ([app-landscape](app-landscape.md)); more engagement is not more benefit, and for an overwhelm-reducing tool, *more time in app is often worse*. Optimizing engagement optimizes the wrong thing.
- **EMA (micro-check-ins) is feasible but fragile.** Compliance is decent in well-designed studies but degrades with burden and over time, and ADHD samples are exactly the population most sensitive to prompt fatigue. Keep it optional, tiny, and never punitive.
- **The metric hierarchy:** North Star (return-after-lapse) → functional outcomes (validated, slow, opt-in) → behavioral proxies (in-app, hypothesis-grade) → guardrails (engagement + shame-risk, watched not optimized) → operational (engineering health). **Rule: decide at the highest trustworthy tier; lower tiers may veto, never justify.**
- **Anti-metrics list:** streaks, DAU, throughput, overdue counts, time-in-app, honeymoon NPS, and un-substantiated symptom "improvement" are banned as success measures — several structurally manufacture shame.
- **If Klyr ever claims benefit:** the FTC requires *competent and reliable scientific evidence* (RCT-grade for health claims; testimonials never suffice). Disease claims cross into medical-device / **digital therapeutic** territory (EndeavorRx is the precedent — FDA-authorized, prescription, RCT-backed). Wellness/lifestyle claims are allowed only inside the general-wellness safe harbor ([when-to-back-off](when-to-back-off.md) owns that line). Ship an **honest-claims checklist**.
- **Never A/B test shame.** Experimenting with pressure/guilt variants on a rejection-sensitive population can cause real harm; guardrails must be pre-registered stopping conditions, and no arm may ship to a test group that you would not ship to someone on their worst day.

## Method note (read this)

This doc was written in a pass where live web search was unavailable. Five sources were fetched and verified directly (FTC guidance; and tertiary summaries of the ASRS, EndeavorRx, digital-therapeutics, and EMA literatures). Instrument specifics (BDEFS/WFIRS/AAQoL item counts and licensing), EMA compliance percentages, and the positive-illusory-bias finding rest on **established knowledge and are marked "not verified against a source in this pass"** wherever a live citation is missing. Treat every un-cited number as *verify-before-shipping*, especially licensing terms and any figure that would appear in marketing. This is a hedged draft by design; a missing doc would be worse.

## 1. The trap: why the default dashboard is the wrong dashboard

A product team building a task app will reach, by reflex, for the standard product KPIs: daily active users, retention curves, tasks completed, streak length, session length, notification open rate. For an ADHD tool, **each of these is either confounded, meaningless, or actively harmful as a success measure.**

Two corpus findings do the disqualifying:

- **Engagement is novelty-confounded.** ADHD motivation responds to novelty, and novelty habituates; "every productivity app works for two weeks" and Klyr's single biggest risk is surviving month three ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)). Early engagement is therefore a *false positive machine* — it measures how new the app is, not how much it helps. Any metric read before ~month 3 is honeymoon noise.
- **Self-rating is biased upward.** ADHD carries a well-documented **positive illusory bias (PIB)** — a tendency to over-estimate one's own competence and performance relative to objective criteria (most studied in children; the pattern is established, *not re-verified against a source in this pass*). A global "how productive did you feel today?" prompt captures self-esteem weather and mood-congruent distortion far more than it captures benefit.

There is a third, subtler trap specific to this population: **measuring the wrong thing does not just mislead the team — it manufactures shame in the user.** A completion percentage, an overdue count, or a broken streak shown back to a rejection-sensitive user is not a neutral readout; it is a deficit display ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md), [app-landscape](app-landscape.md)). So Klyr's measurement problem is doubly constrained: the metric must be *valid* for the team **and** *safe* to reflect back to the user — and many popular metrics fail both tests at once.

## 2. What "working" should mean

Klyr's product goal is to help people *actually do what they need and want to do, with low maintenance burden and no shame*. That yields three legitimate outcome constructs, in priority order:

1. **Real-world function improved** — the person is getting the important things done and the ADHD tax (missed bills, dropped commitments, last-minute scrambles) is lower. This is what validated function scales measure.
2. **Maintenance burden is low and the tool survives neglect** — the person keeps the system with little upkeep and comes back after lapses instead of abandoning. This is the "returns after lapse, not streaks" north star from [app-landscape](app-landscape.md).
3. **The relationship is non-shaming** — usage does not cost the user self-esteem; bad weeks are survivable inside the tool ([when-to-back-off](when-to-back-off.md)).

Note what is *absent*: symptom counts, task throughput, and time-in-app. Symptoms are the medication layer's job, not an app's. Throughput and time are inputs the user spends, not benefits they receive — and a well-functioning ADHDer may complete *fewer, better-chosen* tasks. **User-defined success matters more than any global scale:** because ADHD impairment is idiosyncratic, the most valid single question is often "did the thing *you* said mattered this week actually happen?" — which points at behavioral proxies (§4) over generic scales.

## 3. Validated instruments, stress-tested for app use

Four instruments come up repeatedly for adult ADHD. Their relevance to Klyr is not "put a questionnaire in the app" — it is: *if Klyr ever wants defensible evidence it helps, these are the measuring sticks, and each has a length/licensing/validity profile that decides whether it is app-feasible.*

| Instrument | Length | Measures | Licensing / cost | Sensitivity to change | App verdict |
|---|---|---|---|---|---|
| **ASRS v1.1** (Adult ADHD Self-Report Scale) | 18 items; **6-item Part A screener** | ADHD *symptom* frequency (DSM-based) | **Free**, public (WHO / Kessler 2005) [4] | Symptom-level; used as a trial outcome, moderately responsive | Cheapest to embed and validated as a *screener* — but it measures symptoms, not Klyr's value. Fine as light context; wrong as a success KPI. **(length/authorship verified)** |
| **WFIRS-S** (Weiss Functional Impairment Rating Scale, self-report) | ~70 items, 7 domains (family, work, school, life skills, self-concept, social, risk) | **Real-world functional impairment** | Freely available via CADDRA *(verify)* | Responsive to treatment in trials; function-level | **Best construct match** — function, not symptoms — but 70 items is far too long for routine in-app use. Use a domain subset, or full scale at most annually/opt-in. *(specifics: established knowledge, verify)* |
| **BDEFS-SF** (Barkley Deficits in Executive Functioning Scale, Short Form) | Long form ~89 items; **Short Form ~20 items** | **Everyday executive function** in daily life | Guilford Press, **licensed/paid** *(verify)* | Designed for daily-life EF; everyday-EF ratings predict impairment better than lab tests (see [executive-function](../foundations/executive-function.md)) | Closest to Klyr's *mechanism* (EF at the point of performance). Short Form is app-length. Costs: license fee + self-report bias. *(specifics: established knowledge, verify)* |
| **AAQoL** (Adult ADHD Quality-of-Life) | **29 items**, 4 subscales | ADHD-specific quality of life | Developed with industry; permission likely required *(verify)* | Responsive in medication trials | Quality of life is a defensible outcome; 29 items is borderline for routine use. Good for periodic opt-in "life check-ins." *(specifics: established knowledge, verify)* |

**Four rules for using any of them in Klyr:**

1. **They are outcome instruments, not features.** Do not gamify a WFIRS score or show a user their BDEFS trend as a progress bar — that recreates the deficit display. Administer periodically, in aggregate, ideally framed as "check in on *your life*," not "grade the app."
2. **Prefer function/QoL scales (WFIRS, AAQoL, BDEFS) over the symptom scale (ASRS) for the success question.** ASRS answers "how much ADHD," which an app should not claim to change; the others answer "how is life going," which is the point.
3. **Blunt the self-report bias.** PIB and mood-congruence mean a single self-rating is noisy. Mitigations: anchor items to concrete recent behaviors ("this week I paid bills on time") rather than global judgments; keep wording identical across administrations; read *change over months*, not absolute levels; and triangulate against behavioral proxies (§4).
4. **Length is a feature, not a footnote.** For a population with low tolerance for admin, a 70-item scale is itself a maintenance burden that will crater compliance. Short Form / screener / domain-subset versions exist precisely so you can trade a little validity for a lot of completion — usually the right trade in-app.

## 4. Behavioral proxies vs. vanity metrics

The most promising, lowest-burden signal Klyr owns is **behavior it already observes**. The honest caveat first: **there is little published literature directly tying in-app task-manager behavior to validated functional outcomes** — this is an inference, not a measured law, and Klyr should *validate its proxies against Tier-1 scales (§6) before trusting them*. With that flagged, some in-app signals plausibly track benefit and others plausibly track nothing.

**Proxies that plausibly track real-world benefit:**

- **Self-nominated-important-task completion rate.** Of the small set of items the *user* flagged as mattering, how many happened? This is the closest in-app analog to "did life go better," and it is resistant to list-padding.
- **Resurfaced-item action rate.** When Klyr brings back a dropped or out-of-sight item (see [memory-and-object-permanence](../foundations/memory-and-object-permanence.md)), what fraction gets acted on *or deliberately dismissed* — versus silently ignored? High action-or-dismiss = the capture/reminder system is doing real cognitive-offload work; high ignore = it is generating noise.
- **Restart latency after an absence.** Time from a lapse ending to the first meaningful action. Falling restart latency over the app's lifetime is direct evidence Klyr is achieving its differentiator: painless returns. (This is a *desirable falling number*, unlike streaks.)
- **Capture-to-clarity.** Of items captured, how many receive a concrete next action (vs. rotting as vague nouns). This tracks the CBT-style "make it doable" move ([evidence-based-strategies](../strategies/evidence-based-strategies.md)).

**Vanity proxies that do not track benefit (and often invert it):**

- **Total tasks completed / throughput.** Rewards volume and busywork; can climb while the important things rot and life gets worse.
- **DAU / open rate.** Conflates dependence with benefit, is novelty-inflated early, and rewards nagging.
- **Streak length.** Punishes the intermittent-by-design use pattern of ADHD and is the mechanical cause of the "miss one day → guilt → quit" spiral ([app-landscape](app-landscape.md)).
- **Session length / time-in-app.** For a tool meant to *reduce* overwhelm, longer sessions are frequently a failure signal, not a win.

**The engagement–outcome decoupling is not a hunch — it is the mHealth baseline.** Median 15-day retention for mental-health apps runs ~3.9% ([app-landscape](app-landscape.md) sources this), and the field's recurring finding is that usage volume and clinical benefit are only weakly related: some effective interventions need very little engagement, and some highly "engaging" apps produce no measurable benefit. Practically: **an A/B test that raises DAU has told you almost nothing about whether Klyr helped anyone.** Read behavioral proxies at **month 3+**, after the novelty confound decays ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)).

## 5. EMA and micro-check-ins: feasibility

**Ecological momentary assessment (EMA)** — asking users to report state/behavior in the moment, repeatedly, in daily life [5] — is the technique behind any in-app "how did that go?" check-in, and it is genuinely useful: it captures point-of-performance data validated scales miss, and it is far lighter than a 70-item questionnaire. Feasibility caveats for Klyr's population:

- **Compliance is decent but not free.** Well-designed EMA studies achieve reasonable completion (commonly reported in the ~70–90% range for motivated adult samples; youth meta-analytic averages sit near ~78% — *figures from established knowledge, not verified against a source in this pass*). But compliance **declines with burden and over time**, and unanswered prompts are informative-but-ambiguous exactly the way app disengagement is ([when-to-back-off](when-to-back-off.md)).
- **ADHD is the worst case for prompt fatigue.** The population most prone to notification habituation and demand-avoidance is the one you are sampling. Over-prompting to "measure engagement" will *destroy* engagement and pollute the measure — a self-defeating loop.

Design rules if Klyr uses EMA-style check-ins: keep them **tiny** (one tap, optional), **event-contingent** (after a self-nominated task, not on a fixed nag schedule), **never punitive** (a skipped check-in is data, not a failure), and treat non-response as *missingness to respect*, never as a trigger for a guilt push.

## 6. The Klyr metric hierarchy (deliverable 1)

Five tiers. **The governing rule: make each product decision at the highest tier that has a trustworthy signal; lower tiers may only *veto*, never *justify*.** A throughput gain (Tier 3) can never justify a change that harms function or a validated proxy (Tiers 1–2); but a guardrail breach (Tier 3) *can* kill a change that looked good on a proxy.

| Tier | Metric(s) | What it drives | Cadence / rules |
|---|---|---|---|
| **North Star** | **Return-after-lapse rate** — of users idle ≥N days, the share who return and take a meaningful action within N days *without* a guilt/streak prompt | Orients the whole product; the one number Klyr is uniquely trying to be great at | Watched, not gamed; read at month 3+; never shown to users as a score |
| **1 — Functional outcome** | WFIRS-S / AAQoL change over months; BDEFS-SF everyday-EF; ASRS as symptom *context* only | Whether Klyr actually improves life; the only tier that may back a benefit claim (with substantiation, §8) | Quarterly at most, **opt-in**, aggregate; never gates features; framed as "check in on your life" |
| **2 — Behavioral proxies** | Self-nominated-important-task completion; resurfaced-item action rate; restart latency; capture-to-next-action | Day-to-day feature decisions; ranked by whether they move *these*, not throughput | In-app, aggregate, **labeled hypothesis-grade**; validate against Tier 1 where possible; read at month 3+ |
| **3 — Guardrails** | Engagement (DAU, throughput, session length) **and** shame-risk (overdue-count growth, streak-break churn, negative check-in sentiment) | Confounds and stop-conditions only | **Watched, never optimized**; several are *inverted* (up = bad); breaches veto changes |
| **4 — Operational** | Crashes, latency, funnel drop-off | Engineering health | Standard eng practice; never reported as product success |

Two things make this hierarchy work. First, **shame-risk lives in the guardrail tier as a first-class metric** — Klyr explicitly watches whether a change grows overdue anxiety or breaks-and-churns users, and treats that as a failure regardless of what it did to engagement. Second, **the North Star is a forgiveness metric**, structurally impossible to game by nagging: you cannot boost return-after-lapse-without-prompting by adding prompts.

## 7. Anti-metrics: KPIs Klyr must not optimize (deliverable 2)

Metrics that are banned outright as success measures, with the reason each is disqualified. Several are not merely useless — they **structurally manufacture shame**.

| Anti-metric | Why it is banned |
|---|---|
| **Streak length / streak preservation** | Punishes intermittent-by-design ADHD use; is the mechanical cause of the "miss one day → quit" spiral. Shame engine. |
| **DAU / daily open rate as a goal** | Conflates dependence with benefit; rewards nagging; novelty-inflated. Optimizing it selects for dark patterns. |
| **Total tasks completed / throughput** | Vanity; rewards list-padding and busywork; can rise while the important things and real life get worse. |
| **Completion percentage shown to the user** | Turns an unfinished list into a visible deficit. Shame display. |
| **Overdue count / red badges (surfaced)** | The canonical shame artifact ([app-landscape](app-landscape.md)); the moment opening the app *is* the punishment. |
| **Session length / time-in-app** | For an overwhelm-reducer, more time is usually worse; optimizing it fights the product's purpose. |
| **Self-rated "how productive were you?" as an outcome** | Positive illusory bias + mood-congruence; measures self-esteem weather, not benefit. |
| **NPS / satisfaction during the honeymoon** | Novelty-inflated; says nothing about month-3 value; misleads roadmap. |
| **Symptom-scale "improvement" shown or marketed without an RCT** | False precision + FTC substantiation risk (§8); implies clinical benefit Klyr has not earned. |

Guardrail versions of some of these (DAU, throughput, overdue growth) are still *monitored* under Tier 3 — the ban is on *optimizing* or *displaying* them as success.

## 8. If Klyr ever claims benefit: the regulatory and ethical floor

The moment marketing copy, a store listing, or in-app text says Klyr *helps*, *improves focus*, *treats*, or *reduces symptoms*, three regimes engage. [when-to-back-off](when-to-back-off.md) owns the FDA general-wellness safe-harbor line (what UI/labeling may and may not reference); this section owns the *claims-substantiation* half.

- **FTC substantiation.** Health-benefit claims require **"competent and reliable scientific evidence"** — expert-conducted, generally-accepted research, *in most cases randomized controlled human clinical testing*. Anecdotes and testimonials **never** suffice; you may not cherry-pick favorable studies against a contrary body of evidence; and claims must match the strength and population of the data [1]. A vague "users feel more organized" backed by internal proxies is not substantiation for a health claim.
- **Wellness vs. digital therapeutic (DTx).** A **general-wellness** product makes lifestyle claims (organization, staying on top of tasks, feeling less overwhelmed) and no disease claims; a **digital therapeutic** claims to *prevent, manage, or treat* a disorder and therefore needs rigorous clinical evidence and typically FDA clearance as software-as-a-medical-device [3]. The distinction is the disease reference, not the technology.
- **The precedent: EndeavorRx.** The bar for a real ADHD *treatment* claim is set by EndeavorRx — FDA-authorized (De Novo, 2020) for ADHD in children 8–12, **prescription**, backed by controlled trials across ~600+ children showing improvement on an objective attention measure (with a later over-the-counter adult product, EndeavorOTC, in 2024) [2]. Klyr is not this and should not imply it is. EndeavorRx marks the wall: to say "treats ADHD," you need that class of evidence and that class of regulatory posture.

**Honest-claims checklist (deliverable 3) — run before any benefit claim ships:**

1. **Disease test.** Does the claim say/imply treat, cure, mitigate, prevent, or diagnose ADHD or its symptoms? If yes → you are claiming a medical device / DTx; stop unless you have EndeavorRx-class evidence + clearance.
2. **Safe-harbor test.** If it is a wellness/lifestyle claim, does it avoid *all* disease references and diagnostic thresholds? (Cross-check the FDA wellness line in [when-to-back-off](when-to-back-off.md).)
3. **Evidence test.** Do you hold competent and reliable scientific evidence for the claim *as worded* (RCT-grade for health benefits)? Testimonials and in-app proxies do not count [1].
4. **Match test.** Does the evidence's strength and population match the claim? No extrapolating a pilot to "clinically proven," no adult claim from a child study.
5. **Totality test.** Have you accounted for contrary evidence and avoided cherry-picking [1]?
6. **Testimonial test.** Is every testimonial typical and non-misleading, with no implied clinical outcome?
7. **Number-honesty test.** Are any figures shown to users framed as proxy vs. validated, never dressed up as clinical results?
8. **Worst-day test.** Would the claim (and any number attached) survive being read by a user on their worst day without landing as judgment?

## 9. The ethics of experimenting on a clinical-adjacent population

Klyr's users are shame-primed and rejection-sensitive ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)). That changes the ethics of A/B testing: an experimental arm that raises pressure, guilt, or deficit-visibility is not just "a variant that might lower a metric" — it can cause **real psychological harm** (self-criticism, disengagement, a shame spiral). The Facebook emotional-contagion study is the cautionary precedent for large-scale affect experiments run without meaningful consent.

Operating principles:

1. **Never A/B test shame.** No arm may deliberately increase guilt, pressure, or deficit displays to "see if completion goes up." The literature already answers whether nagging works for this population — it backfires ([evidence-based-strategies](../strategies/evidence-based-strategies.md)) — so there is no equipoise to justify the experiment.
2. **Guardrails are pre-registered stopping conditions.** Every experiment declares its Tier-3 shame-risk guardrails (overdue-anxiety, break-churn, negative sentiment) up front; a breach halts the test regardless of the primary metric.
3. **Equipoise / worst-day rule.** Only test variants you would be comfortable shipping to someone on their hardest day.
4. **Exclude vulnerable moments.** Users showing distress or a capacity-collapse signal are not subjects for pressure variants ([when-to-back-off](when-to-back-off.md)).
5. **Beware the optimizer's pull toward dark patterns.** Engagement-maximizing experimentation *structurally* selects for the manipulative mechanics [ux-design-for-adhd](ux-design-for-adhd.md) bans; anchoring experiments to Tier 1–2 outcomes, not Tier 3 engagement, is the structural defense.
6. **Prefer transparent/opt-in experimentation** for anything touching emotional framing, and default to the gentler arm when a test is inconclusive.

## Design implications for Klyr

1. **Klyr must adopt a written metric hierarchy and enforce the "highest trustworthy tier decides; lower tiers only veto" rule.** Without it, the team defaults to engagement and throughput — the exact confounded metrics the corpus disqualifies. Make return-after-lapse the North Star.
2. **Klyr must never display success/failure numbers back to the user as a score** — no completion percentages, overdue counts, or streak lengths surfaced as the user's grade. These are Tier-3 guardrails for the team, not user-facing feedback; surfaced, they become shame artifacts.
3. **Klyr should instrument behavioral proxies (self-nominated-important-task completion, resurfaced-item action rate, restart latency, capture-to-next-action) and validate them against a function scale before trusting them.** The proxy→function link is plausible but unproven; treat proxies as hypotheses until a Tier-1 scale confirms them.
4. **Klyr must treat restart latency as a headline success signal and design to make it fall** — it is the measurable form of Klyr's "expects you to disappear and makes coming back painless" positioning, and unlike streaks it cannot be gamed by nagging.
5. **If Klyr collects any validated instrument, prefer function/QoL scales (WFIRS-S, BDEFS-SF, AAQoL) over the symptom screener (ASRS), keep them short, opt-in, quarterly-at-most, and framed as a life check-in — never a feature gate.** Symptoms are the medication layer's domain; function is Klyr's.
6. **Klyr must not use global self-ratings ("how productive were you?") as an outcome.** Positive illusory bias and mood-congruence make them measure feelings, not benefit; anchor any self-report to concrete recent behaviors and read change over months.
7. **Klyr must read all metrics at month 3+ and distrust anything measured during the novelty honeymoon.** Early engagement is a false-positive machine ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)); a feature that "works" for two weeks has proven nothing.
8. **Klyr must keep any EMA/check-in tiny, event-contingent, optional, and non-punitive**, and treat non-response as missingness to respect — over-prompting to measure engagement destroys both the engagement and the measure in exactly this population.
9. **Klyr must add shame-risk metrics (overdue-anxiety growth, break-churn, negative check-in sentiment) to its guardrail tier as first-class, pre-registered stop conditions** — a change that grows engagement while growing shame has failed, full stop.
10. **Klyr must run the honest-claims checklist before any benefit language ships**, and must not make disease/treatment claims without EndeavorRx-class evidence and regulatory posture. Wellness-lifestyle framing only, substantiated to FTC's "competent and reliable scientific evidence" standard [1][2][3].
11. **Klyr must never A/B test a shame or pressure variant on users.** There is no equipoise — the literature already shows pressure backfires — so such experiments are unethical, not merely risky. Anchor experiments to Tier 1–2 outcomes so the optimizer does not drift toward dark patterns.
12. **Klyr should let users define their own success and measure against it** (the self-nominated-important-task construct), because ADHD impairment is idiosyncratic and "did *your* thing happen?" is more valid than any generic scale — while keeping validated scales in reserve for aggregate product learning and any future claim.

**Tensions to hold:** (a) validated function scales are the most defensible outcome but are long and self-report-biased, while short behavioral proxies are low-burden but unproven — Klyr needs both, each checking the other. (b) Measuring outcomes at all requires some data collection, which trades against the surveillance/privacy concerns in [when-to-back-off](when-to-back-off.md); default to aggregate, on-device where possible, and opt-in. (c) Not measuring risks flying blind and shipping a pretty app that helps no one; over-measuring risks burden and shame — resolve toward the lightest measurement that still distinguishes "helped" from "was merely used."

## Open questions

- **Does any in-app behavior actually predict validated functional improvement in ADHD?** No literature was found this pass tying task-manager behavior to WFIRS/AAQoL change. This is Klyr's most important internal study to run: correlate the §4 proxies against a periodic function scale in real users.
- **What is the minimal clinically important difference for WFIRS-S / AAQoL in a self-tracked, non-clinical app context?** Trial-derived MCIDs may not transfer to at-home, self-administered use.
- **Real EMA compliance in an unpaid, in-the-wild ADHD app population** (vs. paid research samples) is unknown and likely lower — needs measurement before any check-in feature is relied upon.
- **Can return-after-lapse be operationalized without it degrading into a disguised retention/DAU metric?** The threshold (N days) and the "without a prompt" condition need real-user calibration.
- **Where exactly is Klyr's wellness/DTx line in practice?** The general-wellness safe harbor ([when-to-back-off](when-to-back-off.md)) plus FTC substitution standards give the walls, but specific copy needs legal review before launch.
- **How should Klyr weight user-defined success against validated scales** when they disagree (a user feels helped; the scale is flat, or vice versa)? Both are real; the resolution is untested.

## Sources

1. [FTC — Health Products Compliance Guidance](https://www.ftc.gov/business-guidance/resources/health-products-compliance-guidance) — [product] (US regulatory guidance on substantiation of health claims; "competent and reliable scientific evidence," RCT standard, testimonials insufficient, totality-of-evidence). *Fetched and verified this pass.*
2. [EndeavorRx (FDA De Novo authorization; Kollins et al. STARS-ADHD)](https://en.wikipedia.org/wiki/EndeavorRx) — [product] (tertiary summary of the FDA-authorized prescription digital therapeutic for pediatric ADHD; ~600+ children, improvement on an objective attention measure; EndeavorOTC 2024). *Fetched and verified this pass; primary trial details not independently confirmed.*
3. [Digital therapeutics — evidence and regulatory boundary](https://en.wikipedia.org/wiki/Digital_therapeutics) — [product] (tertiary summary; Digital Therapeutics Alliance distinction between DTx requiring clinical evidence/FDA SaMD oversight and unregulated wellness apps). *Fetched and verified this pass.*
4. [Adult ADHD Self-Report Scale (ASRS v1.1)](https://en.wikipedia.org/wiki/Adult_ADHD_Self-Report_Scale) — [clinical] (tertiary summary of the WHO/Kessler 2005 instrument; 18 items, 6-item Part A screener, free/public; screener performance). *Fetched and verified this pass.*
5. [Ecological momentary assessment](https://en.wikipedia.org/wiki/Ecological_momentary_assessment) — [research] (tertiary summary of EMA/experience-sampling methodology; real-time repeated in-context reporting, passive vs. active data, reactivity). *Fetched and verified this pass.*

*Cross-referenced from the corpus (sourced in their own docs): median 15-day mental-health-app retention ~3.9% and the return-after-lapse positioning ([app-landscape](app-landscape.md)); the FDA general-wellness safe-harbor line and digital-phenotyping/JITAI limits ([when-to-back-off](when-to-back-off.md)); everyday-EF ratings vs. lab tests and the point of performance ([executive-function](../foundations/executive-function.md)); novelty decay and "survive month three" ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)); pressure-backfire and if-then/CBT ingredients ([evidence-based-strategies](../strategies/evidence-based-strategies.md)); dark patterns to ban ([ux-design-for-adhd](ux-design-for-adhd.md)).*

*Established-knowledge claims not re-verified against a live source this pass (verify before shipping): BDEFS long/short-form item counts and Guilford licensing; WFIRS-S item count and CADDRA availability; AAQoL item count and licensing; EMA compliance percentages; the positive illusory bias finding in ADHD.*
