---
title: "ADHD: What It Is — Consensus, Presentations, Prevalence, Comorbidity, Strengths, Myths"
area: foundations
file: research/foundations/adhd-overview.md
tags: [adhd-basics, diagnosis, prevalence, comorbidity, neurobiology, strengths, myths]
related:
  - research/foundations/executive-function.md
  - research/foundations/emotional-regulation-and-rsd.md
  - research/foundations/dopamine-and-motivation.md
  - research/daily-life/daily-life-impact.md
  - research/strategies/evidence-based-strategies.md
sources: 26
updated: 2026-07-25
summary: >
  The shared factual foundation for the whole corpus: what ADHD is under current
  scientific consensus, how the three presentations differ in daily life, prevalence
  and diagnosis trends, comorbidity rates, neurobiology at overview level, the
  strengths debate, and the myths Klyr's copy must never reproduce. Read this first.
---

# ADHD: What It Is — Consensus, Presentations, Prevalence, Comorbidity, Strengths, Myths

## TL;DR

- **ADHD is a neurodevelopmental condition of self-regulation**, not an attention deficit in the literal sense. DSM-5-TR defines it by inattention and/or hyperactivity-impulsivity; the working model most useful for product design (Barkley) frames it as a disorder of **performance, not knowledge** — a gap between what someone knows to do and what they can execute at the moment it matters [1][10].
- DSM-5-TR **did not change ADHD's diagnostic criteria** from DSM-5; it updated context around sex, gender, and ethnoracial issues. Criteria have been criticized by researchers as "ambiguous, redundant, and arbitrary," especially for adults [8].
- The **three presentations** (inattentive, hyperactive-impulsive, combined) are snapshots, not types. DSM-5 deliberately renamed "subtypes" to "presentations" because people move between them, typically drifting toward inattentive with age [8][3].
- **Prevalence:** ~11.4% of US children aged 3–17 have ever been diagnosed (7.1 million, 2022) [4]; worldwide adult prevalence is ~3.1% (95% CI 2.6–3.6) [3], with ~2.5% persistent adult ADHD declining to ~1% by age 60 [2]. In the US, 6.0% of adults (15.5 million) report a current diagnosis and **about 56% of them were diagnosed as adults** [5].
- **Rising diagnosis rates ≠ rising prevalence.** A meta-regression across three decades found true prevalence stable once methods are controlled; the increase reflects awareness, access, and broadened recognition [7].
- **Sex ratio collapses with age**: roughly 1.8:1 boys:girls in US childhood diagnoses [4], approaching 1:1 in adults [2]. Girls and women are diagnosed later, often after being treated for anxiety or depression first, and masking plus inattentive presentation are the leading explanations [17].
- **Comorbidity is the default, not the exception.** 77.9% of US children with current ADHD have at least one co-occurring condition [4]; in adults, odds ratios versus non-ADHD populations are ~5.0 for anxiety, 4.5 for major depression, 8.7 for bipolar, 4.6 for substance use disorders [2]. Up to ~78% of adults with ADHD show delayed sleep timing [16].
- **Neurobiology, honestly:** fronto-striatal and fronto-parietal circuit differences, insufficient suppression of the default mode network during demanding tasks, delayed (not deviant) cortical maturation, and catecholamine — dopamine *and* norepinephrine — signaling differences. Group-level brain differences are real but **small and not diagnostic for individuals** [12][13].
- **Heritability is high**: ~74% mean across 37 twin studies; common genetic variants explain only 14–22%, so ADHD is highly polygenic rather than caused by one gene [11].
- **Strengths are real but oversold.** Divergent thinking associates more reliably with *subclinical* ADHD traits than with clinical ADHD; hyperfocus is poorly operationalized and not ADHD-exclusive; "crisis performance" is largely community observation, not established finding [19][20][21].
- **Treatment context (not medical advice):** stimulants show the largest effect sizes (~0.39–0.71 at ~12 weeks); NICE positions environmental modification as something to implement and review alongside medication decisions. About 36.5% of US adults with a diagnosis received no treatment in the past year [2][22][5]. Klyr is a tool, never a treatment.
- **What this means for Klyr:** design for a user whose capability fluctuates hour to hour, who probably has at least one co-occurring condition, who has likely been failed by other systems, and who does not need more information — they need the right cue at the point of performance.

---

## 1. What ADHD actually is

**Attention-deficit/hyperactivity disorder (ADHD)** is a neurodevelopmental condition characterized in DSM-5-TR by a persistent pattern of **inattention** and/or **hyperactivity-impulsivity** that interferes with functioning or development. The criteria require: several symptoms present before age 12; symptoms present in **two or more settings** (e.g., home and work); clear evidence of interference with functioning; and symptoms not better explained by another condition. Adults (17+) need five symptoms in a domain rather than the six required for children [8].

Two things about this definition matter enormously for anyone building a tool:

**First, the label is misleading.** People with ADHD do not have a deficit of attention; they have difficulty *allocating* attention according to intention rather than according to interest, urgency, novelty, or salience. The same person who cannot read one page of a lease can read four hours of documentation about something that grabbed them.

**Second, the checklist is a description, not a theory.** The mechanistic account with the most product leverage is Russell Barkley's: ADHD is fundamentally a disorder of **executive function and self-regulation** — the brain's system for directing behavior toward future goals. Barkley's central clinical claim is that ADHD is *not a disorder of knowing what to do*; it is a disorder of **doing what you know at the point of performance**. Knowledge-delivery interventions therefore underperform, while interventions that alter the environment where and when the behavior must occur do better [10]. This is the single most important research fact in this corpus for Klyr's design, and it is developed in depth in [executive-function.md](executive-function.md).

**ICD-11** (code 6A05) covers the same construct with a different philosophy: it keeps the three presentations but does not bind them to fixed symptom counts, instead asking clinicians to synthesize symptom pattern, developmental history, and functional impact. Both systems require developmentally inappropriate, persistent symptoms with onset in childhood [9]. The practical consequence: two clinicians in two countries can reach different conclusions about the same borderline adult — diagnosis is a judgment, not a measurement.

Researchers themselves are not uncritical of the criteria. A 2023 analysis of DSM-5-TR's ADHD section concluded the criteria "remained identical" to DSM-5 and described them as ambiguous, redundant, and arbitrary, with insufficient attention to context [8]. **Design consequence: never let Klyr's copy imply that a diagnosis is a precise biological fact or that undiagnosed users are illegitimate.**

## 2. The three presentations in daily life

DSM-5 replaced "subtypes" with "presentations" precisely because they are unstable: many children diagnosed combined or hyperactive-impulsive shift toward the inattentive picture in adolescence and adulthood [8][3].

| Presentation | Core pattern | How it shows up in an ordinary week | What it stresses in a task app |
|---|---|---|---|
| **Predominantly inattentive** | Difficulty sustaining attention, disorganization, forgetfulness, losing things, avoiding sustained mental effort | Twelve half-finished tabs; the renewal letter still unopened; "I did read that message, I just never replied" | Capture and retrieval. Things must not disappear. Long lists become invisible. |
| **Predominantly hyperactive-impulsive** | Restlessness, internal motor, talking/acting before deliberating, difficulty waiting | Reorganizing the whole kitchen at 11pm instead of doing the tax form; buying the tool before scoping the project | Impulse routing. Needs a fast, low-friction place to dump the new idea so it doesn't hijack the day. |
| **Combined** | Meaningful symptoms in both clusters — the most commonly diagnosed presentation in children | Both of the above, on alternating days | Everything above, plus volatility: the same user needs different affordances on different days. |

Adults with ADHD show hyperactivity less as visible motion and more as **internal restlessness**, over-scheduling, and difficulty being unoccupied — a distinction that matters because "sit still and plan your week" is exactly the posture many adults with ADHD cannot hold.

The practical takeaway is that **Klyr cannot ship one persona.** The same feature set must serve someone whose failure mode is "I forgot it existed" and someone whose failure mode is "I abandoned it for something shinier." Detail on how these patterns hit chores, admin, work, and money lives in [daily-life-impact.md](../daily-life/daily-life-impact.md).

## 3. Prevalence and the diagnosis surge

**Children.** In the 2022 US National Survey of Children's Health, 11.4% of children aged 3–17 (7.1 million) had ever been diagnosed with ADHD by a health care provider, and 10.5% (6.5 million) had current ADHD. Prevalence rose with age: 2.4% at ages 3–5, 11.5% at 6–11, 15.5% at 12–17. Boys 14.7% vs girls 8.1% ever-diagnosed. Among children with current ADHD, 58.1% were rated moderate or severe [4].

**Adults.** A 2023 umbrella review and meta-analysis (57 studies, >21 million participants) put worldwide adult prevalence at **3.1% (95% CI 2.6–3.6)** [3]. A 2025 World Psychiatry review gives ~2.5% for persistent adult ADHD, declining to about 1% by age 60 — but notes prevalence reaches **about 9% in early adulthood if the childhood-onset criterion is ignored** [2]. That gap between "2.5%" and "9%" is the entire adult-ADHD controversy in one number.

**US self-reported diagnosis is much higher than clinical prevalence**: a CDC Rapid Surveys System report (Oct–Nov 2023) found 6.0% of adults — roughly 15.5 million, one in sixteen — reported a current ADHD diagnosis, with **55.9% diagnosed at age 18 or older**. Only 33.4% had taken stimulant medication in the past year; **36.5% received no treatment at all**; and among stimulant users, 71.5% had trouble filling a prescription because the medication was unavailable [5]. That last number is a real product fact: a meaningful share of Klyr's users will have weeks where their medication is simply not obtainable and their baseline capability drops.

**Persistence.** About 71% of children with ADHD retain symptoms into adulthood and about 65% retain functional impairment, though most no longer meet full diagnostic criteria by age 30 [2]. "Outgrowing it" is mostly an artifact of criteria written for children.

**Are rates really rising?** Diagnoses are rising; prevalence appears not to be. Polanczyk et al.'s meta-regression across three decades (1985–2012) found prevalence estimates stable once methodological differences were controlled, attributing rising clinical rates to awareness and access [7]. Adult diagnosis is the fastest-growing segment, aided by telehealth [5]. Simultaneously, social media has become a primary information channel of variable quality — cross-sectional analyses of popular #ADHD content have found around half or more of examined claims to be misleading or inaccurate [24]. Both under-diagnosis and over-diagnosis are live concerns at once.

**Sex ratio.** ~1.8:1 boys to girls in US childhood diagnoses [4], but "by adulthood it is close to 1" [2] — a strong signal that childhood identification, not underlying biology, drives much of the childhood gap.

## 4. Women, girls, and late diagnosis

Women and girls are diagnosed less often and later. The dominant explanations in the literature are: (a) historical criteria derived from studies of hyperactive boys; (b) a more common inattentive presentation that is quiet and non-disruptive; (c) **masking** — strong adherence to social norms and compensatory effort that hides impairment at the cost of exhaustion and accumulated secondary problems; and (d) help-seeking that lands on anxiety or depression first, so ADHD is treated as a downstream symptom rather than the upstream driver [17][23].

**Hormonal interaction — real signal, thin evidence base.** Estrogen modulates dopaminergic function, and clinicians widely report symptom worsening in low-estrogen phases. A 2025 review of female ADHD reports survey findings including markedly elevated premenstrual depressive symptoms in women with ADHD (~45% vs ~28%), mixed pregnancy effects (~20% improved focus, ~44% no change, ~36% worse), and high self-reported impact during perimenopause. The authors are explicit that "current knowledge is relatively limited" and largely cross-sectional or survey-based [17]. Treat this as **emerging evidence, clinically credible, not settled**.

**Late diagnosis has an emotional signature** that product copy must respect. Community and clinical accounts converge on a simultaneous relief-and-grief response: relief at an explanation, grief for decades misattributed to character. ADDitude's reporting on undiagnosed adult women emphasizes long-run damage to self-esteem and mental health from years of "you're smart, you're just not trying" [23]. See [emotional-regulation-and-rsd.md](emotional-regulation-and-rsd.md).

## 5. Neurobiology at overview level

Accurate, readable, and deliberately hedged:

- **Fronto-striatal and fronto-parietal circuits.** The dominant pathophysiological models involve dysfunction in circuits connecting prefrontal cortex to striatum, which mediate inhibition, working memory, and goal maintenance [12][13].
- **Default mode network (DMN) intrusion.** The DMN is active during rest and self-referential thought and normally suppresses when you engage a demanding task. In ADHD, that suppression is insufficient, which is a plausible neural correlate of "I was reading and my mind was suddenly three topics away" [13].
- **Delayed, not deviant, maturation.** Longitudinal imaging (Shaw et al.) found cortical maturation in ADHD follows the normal sequence but reaches peak thickness later, most prominently in prefrontal regions — supporting a maturational-delay account rather than a damage account [14].
- **Catecholamine signaling.** Both **dopamine** and **norepinephrine** systems are implicated in ADHD, which is why the effective medications act on them. **Do not say "ADHD brains have no dopamine" or "low dopamine" as a flat fact** — the actual picture involves differences in signaling, receptor and transporter dynamics, and reward-timing sensitivity. See [dopamine-and-motivation.md](dopamine-and-motivation.md).
- **Group differences are small.** The ENIGMA mega-analysis (1,713 with ADHD, 1,529 controls, 23 sites) found reduced volumes in accumbens, amygdala, caudate, hippocampus, putamen, and intracranial volume — real at group level, with small effect sizes and heavily overlapping distributions. **No brain scan diagnoses ADHD in an individual** [12].
- **Heritability.** Mean heritability across 37 twin studies is ~74% [11]; the 2025 World Psychiatry review reports 70–80% in children and >70% in adults when multiple informants or clinical diagnosis are used [2]. Common variants (SNP heritability) explain only 14–22%, so ADHD is highly polygenic — many small-effect variants, not an "ADHD gene" [11].

**Product-relevant consequence:** ADHD is constitutional and lifelong, so Klyr should be designed as **permanent scaffolding**, not as training wheels the user is expected to outgrow.

## 6. Comorbidity: the default case

| Co-occurring condition | Approximate rate / effect | Source |
|---|---|---|
| Any co-occurring condition (US children with current ADHD) | 77.9% | [4] |
| Behavior/conduct problems (children) | 44.1% | [4] |
| Anxiety (children) | 39.1% | [4] |
| Learning disability (children) | 36.5% | [4] |
| Depression (children) | 18.9% | [4] |
| Autism spectrum disorder (children with ADHD) | 14.4% | [4] |
| Anxiety disorders (adults, vs non-ADHD) | OR 5.0 (95% CI 3.29–7.46) | [2] |
| Major depressive disorder (adults) | OR 4.5 (2.44–8.34) | [2] |
| Bipolar disorder (adults) | OR 8.7 (5.47–13.89) | [2] |
| Substance use disorders (adults) | OR 4.6 (2.72–7.80) | [2] |
| Adult prevalence ranges (SUD, mood, anxiety, personality) | Wide and study-dependent; SUD most frequent comorbidity across 32 studies | [15] |
| ADHD within autistic populations | ~38.5% current / 40.2% lifetime (pooled) | [18] |
| Delayed sleep timing in adults with ADHD | up to ~78%; insomnia symptoms up to ~80%; melatonin onset delayed ~90 min | [16] |
| Reading disorder with ADHD / math disorder with ADHD | ~30% / ~24% (approximate, older estimates) | [25] |

Choi et al.'s systematic review of 32 studies found such **heterogeneity across studies that meta-analysis was not possible** — adult comorbidity ranges are wide (e.g., anxiety 4.3–47.1% in general-population ADHD samples) and depend heavily on setting and instruments [15]. Report ranges, not false precision.

**Why comorbidity should shape a productivity app's assumptions:**

1. **The modal user is not "ADHD only."** Designing for a clean ADHD persona designs for a minority of actual users.
2. **Anxiety changes what pressure does.** Countdown timers, red overdue badges, and streak-loss warnings are motivating for some users and genuinely activating of anxiety for others. This is a real tension, not a solved question — see [motivation-and-gamification.md](../strategies/motivation-and-gamification.md).
3. **AuDHD (co-occurring autism and ADHD) creates a direct design tension.** Autistic preference for predictability, routine, and low sensory volatility pulls against ADHD's appetite for novelty and change. Klyr should let the user choose where on that axis they sit rather than picking for them.
4. **Sleep is not a side issue.** With up to ~78% of adults with ADHD showing delayed sleep timing [16], a meaningful share of usage happens at midnight and a meaningful share of morning plans fail on sleep debt, not on motivation. Morning-heavy designs and "you missed your 7am block" messaging punish a circadian pattern, not a character flaw.
5. **Depression and shame amplify punitive UI.** A user with depressive symptoms reading "You've completed 12% of your goals" is not receiving neutral data.
6. **Substance use and treatment gaps mean fluctuating baseline.** With 36.5% of diagnosed US adults untreated in the past year and widespread stimulant supply problems [5], capability varies week to week for reasons outside the app.

## 7. Strengths: what is evidenced, what is romanticized

| Claim | Evidence status |
|---|---|
| ADHD is associated with **divergent thinking** | **Mixed/qualified.** A review of behavioral studies found associations with divergent thinking more consistently for *subclinical* ADHD traits than for clinical ADHD, and no reliable association with convergent thinking [20]. |
| ADHD is associated with **real-world creative achievement** | **Suggestive.** Creative abilities and achievements rate high in both clinical and subclinical groups in several studies, but designs are largely cross-sectional and self-report [20][21]. |
| **Hyperfocus** is a reliable ADHD asset | **Weak as stated.** Ashinoff & Abu-Akel's review argues hyperfocus is under-operationalized, inconsistently measured, and not exclusive to ADHD; the debate about whether it is the same phenomenon as flow is unresolved. Critically, it is **not summonable on demand** and often lands on the wrong task [19]. |
| ADHD confers **crisis / emergency performance** | **Community observation, not established finding.** Widely reported by ADHDers and coaches; the plausible mechanism (urgency-driven arousal and dopaminergic salience) is coherent but not directly evidenced. Label as lived experience. |
| ADHD is a **superpower** | **Rejected as framing.** A non-pathologizing, strengths-aware framing is valuable for self-concept and engagement (evidence: clinical and community consensus rather than trial data), but clinicians and disability advocates warn that "gift" framing can undercut the recognition and accommodations that follow from disorder status, and erases people for whom ADHD is genuinely disabling. A 2026 scoping review finds creativity the most-studied strength category while flagging the literature's methodological limits [21][6]. |

The honest position: **strengths-aware, not strengths-inflated.** ADHD in the UK is associated with materially worse outcomes — a matched cohort study of 30,039 UK adults with diagnosed ADHD versus 300,390 matched comparators estimated reduced life expectancy of roughly 4.5–9 years for men and 6.5–11 years for women [6]. A product that tells users ADHD is a gift while they are drowning is not being kind; it is being unhelpful. A product that treats them as broken is worse.

The productive framing, borrowed from the community and best expressed by Jessica McCabe (*How to ADHD*): **work with the brain, not against it** — "forget 'try harder,' try different" [26]. That is a design instruction, not a slogan, and it is the closest thing this corpus has to a one-line product brief.

## 8. Myths Klyr must never reproduce

| Myth | Reality |
|---|---|
| "It's laziness / lack of willpower." | ADHD produces a knowledge-performance gap; people usually know exactly what to do and cannot deploy it at the point of performance [10]. Effort is often *higher*, not lower. |
| "Everyone is a little ADHD." | Traits are dimensional, but diagnosis requires developmental onset, cross-setting presence, persistence, and **functional impairment** [8]. Occasional distraction is not the condition, and the phrase erases impairment. |
| "It's a boys' condition." | ~1.8:1 in US childhood diagnoses [4] narrowing to about 1:1 in adults [2] — a detection artifact more than a biological one. |
| "You outgrow it." | ~71% retain symptoms and ~65% retain functional impairment into adulthood [2]. |
| "It's overdiagnosed / a fad." | Diagnoses rose; measured prevalence has been stable across three decades once methods are controlled [7]. Over- and under-diagnosis coexist. |
| "ADHD brains have no dopamine." | Pop-neuroscience oversimplification. Catecholamine signaling differs; it is not an empty tank, and "dopamine detox" has no basis. See [dopamine-and-motivation.md](dopamine-and-motivation.md). |
| "The right system will fix it." | No planner cures a neurodevelopmental condition. Systems reduce load; they do not remove the condition — and systems requiring high executive function to maintain fail exactly when needed most. |

## 9. Treatment landscape (product context only — not medical advice)

**This section exists so Klyr's builders understand the user's environment. Klyr is not a treatment, must not claim clinical benefit, and must not give medical advice.**

Care is typically multimodal. Medication has the strongest evidence: stimulants show effect sizes around **0.39–0.71** for symptom reduction at roughly 12 weeks, atomoxetine **0.38–0.51**, and in one synthesis stimulants and atomoxetine were the only treatments outperforming placebo on both clinician-rated *and* self-reported measures [2]. Non-pharmacological approaches (CBT adapted for ADHD, coaching, skills training) show benefit but generally smaller than medication in head-to-head evidence; NICE recommends offering medication to adults when symptoms still cause significant impairment in at least one domain **after environmental modifications have been implemented and reviewed**, and positions non-pharmacological treatment for those who decline, can't tolerate, or need more than medication [22]. Interventions and their evidence grades are covered in [evidence-based-strategies.md](../strategies/evidence-based-strategies.md).

Two facts with direct product consequences: **36.5% of US adults with a current ADHD diagnosis received no treatment in the past 12 months**, and **71.5% of those on stimulants had difficulty filling a prescription due to unavailability** [5]. Klyr's users include untreated, partially treated, and intermittently treated people. Design for the bad weeks as the default case, not the exception.

---

## Design implications for Klyr

1. **Design for the point of performance, not the planning session.** Barkley's core finding is that ADHD is a performance disorder; interventions work when they change the environment where the action must occur [10]. Klyr's highest-value surfaces are therefore the ones present at the moment of doing — a widget, a lock-screen cue, a physical-world reminder — not a beautifully organized project tree the user visits on Sunday.
2. **Assume co-occurring conditions in every default.** With 77.9% of children and the large majority of adults carrying at least one comorbidity [4][2], the default experience must be safe for a user with anxiety and depression: no punitive overdue states, no loss-framed streaks by default, no red as the resting color of an unfinished list. Surface-level rules for this live in [ux-design-for-adhd.md](../product/ux-design-for-adhd.md).
3. **Make pressure a user-chosen setting, not a product-wide assumption.** Urgency helps some ADHDers activate and harms anxious ones. Ship both modes, make the choice reversible in one tap, and never A/B users into high-pressure UI without consent — this is the clearest evidence-based tension in the corpus.
4. **Never require the user to have been diagnosed.** ~56% of US adults with ADHD were diagnosed as adults, many after years of self-recognition [5], and diagnostic access is uneven. Copy should say "if this sounds like your brain," never "if you have been diagnosed with."
5. **Treat scaffolding as permanent, never as training wheels.** ADHD is ~74% heritable and lifelong [11][2]. Klyr must never imply the user should eventually "graduate" from supports, and must never quietly reduce prompting as a reward for consistency.
6. **Support both failure modes in one product.** Inattentive-pattern users lose things that leave the screen; hyperactive-impulsive-pattern users abandon the system for the new shiny thing. That means (a) nothing captured ever silently disappears, and (b) capture must take under three seconds with zero required fields.
7. **Do not build around a morning-first, calendar-first default.** Up to ~78% of adults with ADHD have delayed sleep timing [16]. Let users define their own day boundary, avoid "good morning, here's your plan" as the only entry point, and never mark a plan failed because it slipped past midnight.
8. **Assume fluctuating capability and design an explicit low-capacity mode.** Medication access is unreliable (71.5% reported fill problems) and 36.5% are untreated [5]. A one-tap "low-capacity day" state that shrinks the visible surface to one or two items respects reality better than any prioritization algorithm.
9. **Give AuDHD users a predictability/novelty dial.** Autism co-occurs at meaningful rates [4][18], and its preference for routine and sensory calm directly opposes ADHD-friendly novelty. Make animation, color intensity, layout stability, and "surprise me" behavior user-controlled rather than choosing a single house style.
10. **Ban shame-shaped feedback in every surface, including empty states and analytics.** Late diagnosis and years of moral misattribution mean many users arrive with accumulated self-blame [23][17]. No completion percentages presented as verdicts, no "you've been away for 9 days" guilt copy, no comparison to other users.
11. **Be strengths-aware without romanticizing.** Evidence supports interest-driven engagement and creative association, especially for subclinical traits [20][21]; it does not support "ADHD is a superpower." Klyr's voice should say "your brain runs on interest and urgency — let's use that," never "your ADHD is a gift."
12. **Never make hyperfocus a feature promise.** Hyperfocus is poorly operationalized, not ADHD-exclusive, and not summonable [19]. Klyr can help users *notice and exit* an unplanned deep session (a genuine unmet need), but must never claim to induce one.
13. **Write copy that survives the myth screen.** No "just build the habit," no "everyone gets distracted," no "no dopamine," no 21-day claims. Anything in Klyr's onboarding, notifications, or marketing that would embarrass a clinician is a defect.
14. **Position Klyr as a tool, never as care.** Given the treatment landscape [22][2], Klyr should have a clear, non-preachy stance: it does not diagnose, does not treat, does not track medication adherence as a compliance metric, and points users to real resources without gatekeeping.
15. **Expect maintenance burden to be the thing that kills adoption.** A system requiring executive function to maintain fails hardest during the periods it is most needed. Every new feature should be evaluated against one question: *what does this cost the user on their worst week?*

## Open questions

- **Presentation-specific defaults:** would inattentive-pattern and hyperactive-impulsive-pattern users benefit from measurably different default configurations, or does the instability of presentations over time make that segmentation useless? Needs testing.
- **Where exactly is the urgency line?** Research does not tell us how much time pressure is activating versus anxiety-provoking for a given ADHD+anxiety user. This needs empirical work with real users, not a design decision.
- **Does non-diagnostic language reduce or increase perceived legitimacy?** Building for "brains that work this way" widens the audience but may weaken the feeling of being seriously understood. Test both framings.
- **Hormonal cycling support:** the evidence is emerging and clinically credible but thin [17]. Would optional cycle-aware capacity planning help, or would it feel invasive and deterministic? Unknown; ask users before building.
- **Late-diagnosed onboarding:** does naming the grief/relief response explicitly during onboarding build trust or feel presumptuous? Community writing suggests the former; untested for a product context.
- **Long-run efficacy:** no evidence exists that any consumer task app improves ADHD functional outcomes over time. Klyr should treat that as an open research question it could help answer, not a claim it can make.

## Sources

1. [The World Federation of ADHD International Consensus Statement: 208 evidence-based conclusions about the disorder (Faraone et al., 2021)](https://pubmed.ncbi.nlm.nih.gov/33549739/) — [research]
2. [Attention-deficit/hyperactivity disorder (ADHD) in adults: evidence base, uncertainties and controversies (Cortese et al., World Psychiatry, 2025)](https://pmc.ncbi.nlm.nih.gov/articles/PMC12434367/) — [research]
3. [New Global Estimate of Adult ADHD Prevalence (summary of Ayano et al., Psychiatry Research, 2023) — ADHD Evidence Project](https://www.adhdevidence.org/blog/new-global-estimate-of-adult-adhd-prevalence-a-comprehensive-review) — [research]
4. [ADHD Prevalence Among U.S. Children and Adolescents in 2022: Diagnosis, Severity, Co-Occurring Disorders, and Treatment (Danielson et al.)](https://pmc.ncbi.nlm.nih.gov/articles/PMC11334226/) — [research]
5. [ADHD Diagnosis, Treatment, and Telehealth Use in Adults — NCHS Rapid Surveys System, United States, October–November 2023 (MMWR, 2024)](https://pmc.ncbi.nlm.nih.gov/articles/PMC11466376/) — [research]
6. [Life expectancy and years of life lost for adults with diagnosed ADHD in the UK: matched cohort study (O'Nions et al., British Journal of Psychiatry, 2025)](https://www.cambridge.org/core/journals/the-british-journal-of-psychiatry/article/life-expectancy-and-years-of-life-lost-for-adults-with-diagnosed-adhd-in-the-uk-matched-cohort-study/30B8B109DF2BB33CC51F72FD1C953739) — [research]
7. [ADHD prevalence estimates across three decades: an updated systematic review and meta-regression analysis (Polanczyk et al., Int J Epidemiol, 2014)](https://pubmed.ncbi.nlm.nih.gov/24464188/) — [research]
8. [ADHD in the DSM-5-TR: What has changed and what has not](https://pmc.ncbi.nlm.nih.gov/articles/PMC9871920/) — [research]
9. [ADHD: ICD-11 criteria and differences from the DSM-5-TR — Shanghai Archives of Psychiatry](https://shanghaiarchivesofpsychiatry.org/adhd-icd-11-criteria-and-differences-from-the-dsm-5-tr-what-has-changed-and-how-this-impacts-adult-diagnosis/) — [clinical]
10. [The Important Role of Executive Functioning and Self-Regulation in ADHD (Russell A. Barkley, fact sheet)](https://www.russellbarkley.org/factsheets/ADHD_EF_and_SR.pdf) — [clinical]
11. [Genetic architecture of ADHD and overlap with other psychiatric disorders and cognition-related phenotypes (Neurosci Biobehav Rev, 2023)](https://www.sciencedirect.com/science/article/pii/S0149763423002828) — [research]
12. [Subcortical brain volume differences in participants with ADHD in children and adults: a cross-sectional mega-analysis (Hoogman et al., Lancet Psychiatry, 2017)](https://pubmed.ncbi.nlm.nih.gov/28219628/) — [research]
13. [A review of attention-deficit/hyperactivity disorder from the perspective of brain networks (Frontiers in Human Neuroscience)](https://www.frontiersin.org/journals/human-neuroscience/articles/10.3389/fnhum.2013.00192/full) — [research]
14. [Neuroanatomic evidence for the maturational delay hypothesis of ADHD (Shaw et al., PNAS)](https://www.pnas.org/doi/10.1073/pnas.0710329105) — [research]
15. [The prevalence of psychiatric comorbidities in adult ADHD compared with non-ADHD populations: a systematic literature review (Choi et al., PLOS One, 2022)](https://pmc.ncbi.nlm.nih.gov/articles/PMC9635752/) — [research]
16. [ADHD as a circadian rhythm disorder: evidence and implications for chronotherapy](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12728042/) — [research]
17. [Research advances and future directions in female ADHD: the lifelong interplay of hormonal fluctuations with mood, cognition, and disease (Frontiers in Global Women's Health, 2025)](https://pmc.ncbi.nlm.nih.gov/articles/PMC12277363/) — [research]
18. [Prevalence of attention-deficit/hyperactivity disorder in individuals with autism spectrum disorder: a meta-analysis](https://www.sciencedirect.com/science/article/abs/pii/S1750946721000349) — [research]
19. [Hyperfocus: the forgotten frontier of attention (Ashinoff & Abu-Akel, Psychological Research, 2019)](https://pure-oai.bham.ac.uk/ws/files/81055948/Ashinoff_Abu_Akel_2019_Hyperfocus_the_forgotten_frontier_of_attention_Psychological_Research.pdf) — [research]
20. [Creativity and ADHD: a review of behavioral studies, the effect of psychostimulants and neural underpinnings (Neurosci Biobehav Rev, 2020)](https://www.sciencedirect.com/science/article/abs/pii/S0149763420305935) — [research]
21. [ADHD-Related Strengths in Adults: A Scoping Review (Rafael et al., Journal of Attention Disorders, 2026)](https://journals.sagepub.com/doi/10.1177/10870547261425737) — [research]
22. [Attention deficit hyperactivity disorder: diagnosis and management — NICE guideline NG87, Recommendations](https://www.nice.org.uk/guidance/ng87/chapter/recommendations) — [clinical]
23. [ADHD Symptoms in Adult Women Include Poor Self-Esteem, Mental Health — ADDitude](https://www.additudemag.com/adhd-symptoms-adult-women-undiagnosed/) — [clinical]
24. [Quality and Perception of ADHD Content on TikTok: Cross-Sectional Study (JMIR Infodemiology, 2025)](https://infodemiology.jmir.org/2025/1/e75973) — [research]
25. [The Role of Co-Morbidity in the Identification and Treatment of Dyslexia — Colorado Department of Education Dyslexia Handbook](https://www.cde.state.co.us/node/43723) — [clinical]
26. [How to ADHD: An Insider's Guide to Working with Your Brain (Not Against It) — Jessica McCabe](https://howtoadhdbook.com/) — [community]
