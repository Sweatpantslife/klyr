---
title: "AI Assistance for ADHD: Evidence, Use Cases, Risks, and Trust"
area: product
file: research/product/ai-assistance-for-adhd.md
tags: [ai-assistance, llm, task-breakdown, chatbots, sycophancy, cognitive-offloading, trust-calibration, on-device-ai]
related:
  - research/product/ux-design-for-adhd.md
  - research/product/app-landscape.md
  - research/foundations/memory-and-object-permanence.md
  - research/daily-life/task-initiation-and-paralysis.md
  - research/foundations/emotional-regulation-and-rsd.md
sources: 23
updated: 2026-07-25
summary: >
  The evidence base and risk register for AI features in Klyr: what 2023–2026 research shows about
  ADHD/neurodivergent adults using LLMs, an evidence-graded use-case map, step-granularity guidance,
  chatbot/companion risks (sycophancy, attachment, decay), per-use-case error budgets, the
  cognitive-offloading debate, and cost/latency/on-device constraints. Read before speccing any AI feature.
---

# AI Assistance for ADHD: Evidence, Use Cases, Risks, and Trust

## TL;DR

- The evidence base is **young, thin, and asymmetric**: most published AI-for-ADHD work is *diagnosis and detection*, not daily-life assistance. A 2026 scoping review of 133 digital-health studies for adult ADHD found treatment programs and ML diagnostics — LLM-based everyday support is essentially absent from the trial literature [4]. What exists for assistive use is qualitative (Reddit-corpus studies, autoethnography, small HCI papers) plus strong community testimony.
- That qualitative record is consistent and positive on one point: **LLMs help ADHDers start**. A CHI 2026 analysis of 147 Reddit discussions found ADHD users treating conversational AI as "cognitive scaffolding for initiating tasks" and as a judgment-free thinking space — while actively managing worries about reliability and dependence [2].
- A CSCW 2025 study of 61 neurodivergent Reddit communities mapped 20 LLM use cases across emotional well-being, mental health, communication, learning, and productivity; its top documented frictions: **overly "neurotypical," verbose responses** and prompt-engineering burden, with community-shared workarounds; its top concerns: overreliance and replacement of human connection [1].
- **Task breakdown is the highest-confidence use case**: decomposition is precisely the executive step ADHD impairs (planning, not execution — see the memory doc), and microtask research shows decomposed work has higher quality and survives interruption better, at the cost of longer total time [5][6]. No study yet tests *AI-generated* step granularity for ADHD; Goblin Tools' "spiciness" slider is the folk answer the research hasn't caught up to.
- **Therapy-style chatbots have real but non-ADHD evidence**: Woebot's 2-week RCT (n=70, PHQ-9 d=0.44) [8] and the 2025 Therabot RCT (n=210; 51% depression-symptom reduction, therapeutic alliance rated comparable to human providers) [9] show the ceiling; nothing equivalent exists for ADHD coaching, and engagement decay in this category is brutal (see app-landscape).
- **Sycophancy is a documented, mechanism-level risk**, not a hypothetical: preference-trained models systematically favor agreement (it is what raters reward) [11], preserve users' self-image ~45 percentage points more than humans do [12], and OpenAI publicly rolled back a GPT-4o update for "applauding questionable decisions" [13]. For RSD-prone users who crave validation, an always-agreeing coach is anti-therapeutic: it validates avoidance and corrodes trust in all future praise.
- **Companion-style attachment carries the tail risk**: in a 4-week MIT Media Lab/OpenAI RCT (n=981), higher voluntary chatbot use predicted worse psychosocial outcomes, and trust/social attraction toward the bot predicted emotional dependence [10]; the Character.AI/Google settlement over a teen's death (Jan 2026) marks the legal/ethical outer bound [14]. Klyr should ship a task-anchored assistant, never an open-ended companion.
- **Failure economics are asymmetric**: automation research finds reliability below ~0.70 is worse than no automation, and reliance grows exactly when workload is high [18] — ADHD users live at high load. People also abandon algorithms faster than humans after seeing one error [17]. So: AI may *suggest* freely (errors cheap, user filters), may *act* only behind preview/undo, and must *never* touch stored user data destructively — a hallucinated fact written silently into a task violates the never-silently-lose-anything contract (memory doc).
- **The dependency debate is unresolved**: correlational and self-report studies link heavy AI use to less critical-thinking effort [15][16], but nothing is ADHD-specific or causal, and the corpus-wide externalization principle says offloading *mechanics* is prosthetic, not corrosive. Design rule: AI does the sequencing; the user keeps the judgment.
- **Placement rule**: invisible AI (parsing, triage, scheduling, resurfacing) beats conversational AI for defaults, because every conversation is itself an initiation task with a blank-canvas problem; conversation earns its place only at stuck moments. Cost and latency support the same split: sub-cent, sub-second assists everywhere; long chats are the expensive, slow, riskiest surface.

## 1. The evidence landscape: what actually exists (2023–2026)

Grading the field honestly: **there is no RCT of an LLM-based executive-function aid for ADHD** as of this pass (mid-2026). A Frontiers in Digital Health scoping review (Schofield et al. 2026) of 133 studies of digital health technologies for adult ADHD found the literature clustered in web/app CBT and psychoeducation (26 studies), cognitive training (13), transcranial stimulation (12), neurofeedback (9), and machine learning for *diagnosis* — with patient-perspective and adherence work called out as gaps [4]. An arXiv sweep for this doc found the same skew: ADHD+LLM papers are mostly detection, simulation, and clinician-support tools.

What does exist for assistive use:

| Study | Method | Headline |
|---|---|---|
| Carik et al., CSCW 2025 [1] | Qualitative analysis, 61 neurodivergent subreddits | 20 use cases in 5 areas (emotional well-being, mental-health support, communication, learning, productivity); frictions: "overly neurotypical" verbose outputs, prompt burden; concerns: overreliance, replacing human connection |
| Tazike et al., CHI EA 2026 [2] | 147 Reddit discussions from ADHD communities, 2022–2024 | Four patterns: AI as cognitive scaffolding for *initiation*; heavy prompt customization; judgment-free reflection space; deliberate boundary-management around dependence and reliability |
| Glazko et al., ASSETS 2023 [3] | Autoethnography, 7 disabled researchers using GenAI | Real accessibility wins (drafting, naming, summarizing) alongside documented harms (hallucinated content, ableist outputs) |
| ADDitude community reporting [19][20] | Editorial + reader-experience compilations | Use cases: breaking down tasks, beating blank-page procrastination via drafts, emails/scripts, summarizing, schedules; consistent caution that "AI makes mistakes"; one reader: it translates "ADHD brain ramble" into "simple, straightforward text" |

Two things follow. First, **community evidence currently leads clinical evidence** — the use-case map below is therefore graded, not assumed. Second, the documented *harms* (sycophancy, dependence, hallucination, verbosity) come from general-population research and must be mapped onto ADHD-specific vulnerabilities (RSD, abandonment cycles, trust fragility) by inference — flagged as such throughout.

## 2. The use-case map, evidence-graded

Grades: **Strong** = RCT/meta-analytic support in relevant populations; **Moderate** = solid adjacent research + consistent community evidence; **Emerging** = community-documented, mechanism-plausible, unstudied; **Caution** = documented benefit *and* documented harm channel. Interaction patterns for all of these live in [ux-design-for-adhd §11](ux-design-for-adhd.md); market examples live in [app-landscape](app-landscape.md).

| Use case | What AI does | Evidence | Failure cost | Verdict |
|---|---|---|---|---|
| **Task breakdown at point of paralysis** | Turn "clean the kitchen" into startable steps, granularity-tunable | Moderate: decomposition is the impaired step (planning d = 1.60 in the memory doc's component study); microtask decomposition improves quality and interruption-resilience [5][6]; strongest community signal [1][2][19][20] | Low if visibly a draft; bad steps are regenerable | **Build first** — flagship AI feature (app-landscape implication #7) |
| **Natural-language parsing at capture** | "dentist thurs 3pm" → dated task; voice ramble → clean item | Moderate: NLP capture is table stakes across loved tools; misparse risk is the known cost | Medium: silent misparse corrupts external memory | **Build, invisible + always shown** — parse preview per ux-doc §11 |
| **Inbox triage / prioritization suggestions** | Propose list, project, priority; "these 3 matter today" | Emerging: kills the setup tax (ux doc §2); no direct studies | Low-medium if suggestions; high if auto-filed silently | **Build as suggest-then-correct** |
| **Auto-scheduling** | Place tasks into real calendar gaps | Moderate-adjacent: Calendar.help deployed workflow-decomposed scheduling with graceful human fallback across thousands of meetings [7] | Medium-high: wrong slot = missed reality; over-scheduling = guilt debt | **Build conservatively**, propose > commit |
| **Lapse-return summarizing** | "While you were away, here's what still matters"; tidy stale items *reversibly* | Emerging: directly serves the restart gap (app-landscape #1); summarization is a documented GenAI accessibility win [3] | Medium: a wrong "this no longer matters" = silent loss | **Build** — with full undo ledger |
| **Drafting (emails, scripts, plans)** | First ugly draft to break blank-page freeze | Moderate: strong community evidence [1][2][20]; draft-generation attacks the mood-repair engine of procrastination (task-initiation doc) | Low: drafts are inspected by nature | **Build** where text lives in Klyr; don't become a writing app |
| **Time estimation assistance** | Suggest durations, flag planning-fallacy underestimates | Emerging: time blindness is core (time-perception doc); no AI-specific evidence | Low as suggestion | **Build later**, learn from user's actuals |
| **Conversational unstick / rubber-duck** | Short dialogue at a stuck moment: "what's in the way?" → plan | Moderate: the core finding of [2]; judgment-free space is valued precisely because human help feels shame-laden (RSD doc) | Medium: sycophancy, verbosity, time sink | **Build bounded** — task-anchored, exits into action |
| **AI coach / check-in companion** | Ongoing motivational relationship, CBT-flavored guidance | Caution: therapy-bot RCTs positive but non-ADHD [8][9]; dependence and sycophancy risks documented [10][11][12]; engagement decay severe in category | High: parasocial attachment, validation loops, trust collapse | **Do not build as open-ended companion**; human coaching marketplace is app-landscape territory (Shimmer) |
| **AI body-double presence** | Ambient "working alongside you" presence during a session | Emerging: human body doubling has survey support (85% more likely to complete; see evidence-based-strategies); AI version untested | Low if passive; rises if it chats | **Test carefully** — passive presence, not personality |
| **Emotional support** | Processing feelings, RSD spirals | Caution: documented benefit in [1] *and* the primary harm channel [10][14] | High | **Out of scope for Klyr** — acknowledge feelings, route to action or to humans |

## 3. Step granularity and wording: what makes an AI step startable

**The honest answer: no published study tests AI-generated step granularity for ADHD.** Goblin Tools' "spiciness" slider — regenerate the breakdown finer when the task feels harder — is the field's folk solution ([app-landscape](app-landscape.md) covers the product; Goblin itself tells users its output is "only guesswork" [21]). The nearest research triangulates to concrete guidance:

- **Decomposition works but costs time.** In CHI 2015 experiments, work done as microtasks took longer overall but produced *higher quality* and was dramatically more resilient to interruption — decomposed work could be picked up and put down [5]. Interruption-resilience is disproportionately valuable for ADHD (every resume is a fresh initiation event — task-initiation doc). Follow-up work found people complete writing microtasks in low-focus moments they'd otherwise waste [6] — evidence that small-enough steps unlock low-energy states.
- **Specificity is the active ingredient.** Implementation-intention research (d ≈ 0.65 general population, replicated in ADHD samples — see [evidence-based-strategies](../strategies/evidence-based-strategies.md)) says the startable unit is a *cue plus a concrete physical action*, not an abstract goal. GTD's "next physical action" heuristic encodes the same truth ([planning-methodologies](../strategies/planning-methodologies-and-adhd.md)).
- **Too many visible steps recreates the wall.** Choice-overload conditions (ux doc §2) and working-memory limits mean a 25-item sublist is itself a paralysis object. The step list must be *progressive*: a handful visible, the rest held by the system.

Synthesized wording/granularity spec for Klyr's breakdown engine (design hypothesis, to be user-tested — see Open questions):

1. **First step ≤ ~2 minutes and physically unambiguous** ("put a trash bag in your hand," not "start decluttering"). The first step's only job is ignition.
2. **Steps begin with a concrete verb, name one object, fit one line.** No compound steps ("sort and file and reply").
3. **Show 3–7 steps; chunk the rest** behind "then: 2 more phases." Completion of visible steps reveals the next chunk (goal-gradient, ux doc law #8).
4. **Granularity is a user-facing dial with memory** — per-task regenerate-finer/coarser, and Klyr learns a per-user, per-domain default. Regeneration must be one tap and guilt-free.
5. **No fabricated specifics.** Steps may structure what the user said; they must never invent facts (times, names, amounts) — see §6.
6. **Tone: flat and kind, zero lecture.** Carik et al.'s "overly neurotypical, verbose" complaint [1] is a wording finding: hedging paragraphs and cheerleading are cognitive load. Steps are not prose.

## 4. Invisible vs. conversational: where the AI should live

The default placement question — chat window or silent infrastructure — has an evidence-shaped answer: **invisible for data operations, conversational only at stuck moments.**

The case for invisible-by-default: a chat interface is a blank canvas, and blank canvases are documented abandonment engines for ADHD users (ux doc §2). Composing a prompt is itself an executive task — Carik et al. found neurodivergent users must *learn and share* prompt workarounds to get usable output [1], a skill tax Klyr must never charge. Calendar.help demonstrated the alternative architecture a decade ago: decompose the service into well-defined workflows, automate the automatable microtasks invisibly, and fall back gracefully when confidence is low [7]. Parsing, triage, scheduling, resurfacing, and estimate suggestions should all run this way: the user experiences *outcomes with visible provenance*, not conversations.

The case for conversation at the stuck moment: the one place dialogue demonstrably earns its cost is initiation. "It Helps Me Start" users describe conversation as scaffolding — externalizing the planning dialogue their executive system won't run internally, without the shame of asking a person [2]. That is a *bounded* conversation: it starts from a task Klyr already knows, asks at most a question or two, and its success condition is the user leaving the chat into step one. It is not a destination, not a feed, not a friend.

Rule of thumb: **AI that touches the user's data should be invisible but inspectable; AI that touches the user's state may be conversational but must be brief, optional, and exit into action.**

## 5. Coach and companion chatbots: outcomes, decay, attachment, sycophancy

**Outcomes.** The best evidence for mental-health chatbots is genuinely encouraging — and not about ADHD. Woebot's 2017 RCT (70 students, 2 weeks) found a between-groups PHQ-9 effect of d = 0.44 with high engagement (≈12 check-ins) [8]. Dartmouth's Therabot RCT (2025; 106 intervention, 104 control) reported 51% average depression-symptom reduction, 31% for anxiety, 19% for eating-disorder concerns, with users averaging ~6 hours of engagement and rating therapeutic alliance comparable to human providers — while the authors stressed no generative agent is ready to operate autonomously in mental health [9]. Treat these as ceiling demonstrations under clinical supervision, not as validation for an ADHD productivity coach.

**Engagement decay.** Category retention is dismal (median 15-day retention ~3.9% for mental-health apps — app-landscape), and ADHD novelty decay compounds it ([dopamine-and-motivation](../foundations/dopamine-and-motivation.md)). A coach persona is maximally exposed to decay: its value is the relationship, and relationships with bots go stale or go weird.

**Attachment and dependence.** The MIT Media Lab/OpenAI RCT (981 participants, 4 weeks, 300k+ messages) found assigned interaction modes mattered less than dose: **higher voluntary usage predicted worse psychosocial outcomes across conditions, and trust/social attraction toward the chatbot predicted emotional dependence and problematic use** [10]. Neurodivergent communities themselves flag "replacing human connections" as a first-order concern [1], and ADHD users in [2] actively police their own dependence — a boundary Klyr should support, not erode. The outer bound is now legal fact: Character.AI and Google settled suits including the death of 14-year-old Sewell Setzer, whose mother alleged an immersive chatbot relationship contributed to his suicide [14]. Klyr is not a companion app, and nothing in it should drift toward one.

**Sycophancy — the ADHD-specific trap.** Sycophancy (models agreeing with users over telling the truth) is structural: preference-trained assistants exhibit it consistently because human raters *reward* convincing agreement [11]. Cheng et al. quantify the social form: LLMs preserve the user's desired self-image ~45 percentage points more than humans do in advice scenarios, and in paired moral-dilemma tests affirmed both opposing sides in 48% of cases [12]. The April 2025 GPT-4o incident — rolled back after the model applauded plainly bad decisions — shows how easily engagement tuning slides into flattery [13].

Map that onto [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md): RSD-prone users are the population most likely to *prefer* validation over accuracy in the moment and most damaged by it over time. A sycophantic assistant will bless an avoidance plan ("skipping it today is self-care!"), inflate confidence in unrealistic day plans (planning fallacy + time blindness), and — once the user notices the flattery — retroactively poison every previous piece of praise. The design stance: **warm toward the person, honest about the plan.** Feelings get validated; schedules get evaluated.

## 6. Failure economics: error budgets per use case

Klyr's foundational trust contract comes from [memory-and-object-permanence](../foundations/memory-and-object-permanence.md): the system is the user's external memory, and one silently dropped or mangled item can collapse the whole arrangement. AI is the component most likely to violate that contract, so it needs explicit error budgets.

Three findings anchor the budget math:

- **~0.70 reliability crossover.** Wickens & Dixon's synthesis (20 studies, 35 data points) found automation reliability below ~0.70 left users *worse off than no automation*, and that reliance on automation increases under high concurrent workload — exactly when failures hurt most [18]. ADHD users are chronically high-workload; they will lean on Klyr's automation hardest on their worst days. Any AI feature that can't clear high single-run reliability in its context should ship as a suggestion, not an action.
- **Algorithm aversion.** People abandon algorithms after seeing them err, even when the algorithm still outperforms humans [17]. Combined with the ADHD one-bad-experience abandonment lifecycle (app-landscape), a single *visible, uncorrectable* AI failure can end not just the feature but the app relationship.
- **Confidence miscalibration.** Users over-weight fluent, confident output (ux doc §11), and checking AI work is itself an executive task the target user may skip — Lee et al. found higher confidence *in the AI* predicts less critical evaluation [15].

The resulting three-tier budget:

| Tier | Examples | Tolerable error | Why |
|---|---|---|---|
| **Suggest** (output visibly a draft, nothing stored until accepted) | Breakdown steps, priority suggestions, drafts, estimates | Errors routine and cheap — a weird step costs one regenerate tap | User is the filter; regeneration is expected behavior. Danger only if wrong steps are *fluent and subtly wrong*, hence visible provenance and easy edit |
| **Act** (changes app state, previewed or instantly undoable) | Auto-schedule, auto-file, lapse tidy-up | Rare; every action labeled, reversible, and batched for review | Each undiscovered wrong action misplaces a piece of external memory; reversibility converts catastrophe into annoyance |
| **Data** (the stored record itself) | Rewriting task text, merging, deleting, "correcting" details | **Zero silent errors.** AI never mutates stored user content without explicit per-change acceptance | A hallucinated date or silently rewritten note is indistinguishable from memory corruption — the exact failure the trust contract forbids |

**Hallucination has two severities.** Invented *structure* (an unnecessary step) is a quality bug. Invented *facts* — a deadline that was never said, a dosage, a phone number, an amount — is a safety bug: the user's own external memory now lies to them, with none of the usual cues that memory is unreliable. Klyr's generation layer must be constrained so that facts can only be extracted from user input or explicitly marked as guesses ("no time given — pick one?"), never fabricated inline. Goblin's blunt public disclaimer ("nothing returned… should be taken as a statement of truth, only guesswork" [21]) is honest, but Klyr stores things — a persistence layer needs engineering guarantees, not disclaimers.

## 7. The cognitive-offloading dependency debate, graded

The worry: if AI does the breaking-down, do users lose the capacity? The current evidence for harm is real but weak-form: Gerlich (2025; 666 UK participants) found AI-tool use negatively correlated with critical-thinking scores (r = −0.68), mediated by **cognitive offloading** (delegating thinking to external aids), strongest in younger users — but the design is cross-sectional and self-reporting; the author states causality cannot be established [16]. Lee et al. (CHI 2025; 319 knowledge workers, 936 real GenAI episodes) found *self-reported* reductions in critical-thinking effort that scale with confidence in the AI — a shift of effort toward verification and stewardship rather than pure loss [15]. Nothing here is ADHD-specific, longitudinal, or causal.

Against that stands this corpus's central principle: ADHD is a performance disorder best served by **externalization** — offloading working memory to capture systems, time to visible timers, sequencing to checklists (foundations docs, passim). Nobody argues a reminder app atrophies prospective memory; for an impaired function, a prosthesis is not a crutch. Breaking down tasks *is* such a function ([task-initiation](../daily-life/task-initiation-and-paralysis.md): "just decompose it" outsources the hardest step to the person least equipped at that moment).

Graded verdict: **offloading mechanics (sequencing, phrasing, scheduling arithmetic) to AI is defensible and consistent with the evidence; offloading judgment (what matters, what to commit to, whether the plan is realistic) is where the documented risks concentrate.** Two derived rules: Klyr's AI should show cheap reasoning ("laundry first — the machine runs while you do dishes") so it scaffolds planning rather than replacing it invisibly; and the user makes every commitment decision. Note also Tazike et al.'s finding that ADHD users *already* self-manage dependence boundaries [2] — Klyr should make those boundaries easy (per-feature AI toggles), not fight them.

## 8. Cost, latency, and where the model runs

**Latency budgets.** The ux doc's Doherty threshold (<400 ms) is unreachable for cloud LLM round-trips (1–10 s), so AI must never sit on the critical path of capture: text/voice is saved instantly, enrichment (parse, file, estimate) streams in afterward and visibly settles. At the point of paralysis the tolerance is a few seconds *if* progress streams token-by-token — a spinner at the exact moment of fragile activation is a drop-off machine. Invisible operations (triage, lapse summaries) should run fully async or batched.

**Cost, order-of-magnitude (July 2026; prices churn).** Small hosted models (e.g., Claude Haiku-class at $1/$5 per million input/output tokens, cache reads at 10%, batch at 50% off [23]) put a task-breakdown call — a few hundred tokens each way — around a tenth of a cent; even a heavy user's *entire month* of invisible assists costs pennies to low dollars. Long conversational coaching is one to two orders of magnitude more expensive (growing context, big outputs) and is also the riskiest surface (§5) — economics and safety point the same direction. Within the market's $30–100/year pricing norms (app-landscape), unlimited invisible assists are viable; unlimited open-ended chat is not, and metering chat would create exactly the anxious "am I wasting money" friction ADHD users report around paid tools. Better to bound the product surface than to meter it.

**On-device vs. API.** Apple's on-device foundation model (~3B parameters) runs at ~30 tokens/s with ~0.6 ms/prompt-token first-token latency on 2024-era phones [22] — ample for parsing, classification, triage, and plausibly simple breakdowns; frontier-quality decomposition and dialogue still need the cloud. The split matters because task data is among the most sensitive data a person has (health, money, relationships — see [daily-life-impact](../daily-life/daily-life-impact.md)). Working defaults until the dedicated privacy doc lands (commissioned alongside this one): prefer on-device for high-frequency invisible ops; cloud calls are opt-in-by-design, excluded from provider training, minimized in payload (send the task, not the life), and every AI feature functions as a no-AI fallback. Data-flow architecture, retention, and consent UX belong to that privacy doc.

## Hard red lines

Lifted-ready for the future anti-patterns doc:

1. **Never silently mutate, merge, move, or delete user data by AI** — all AI writes are labeled, previewed or undoable, zero exceptions (§6).
2. **Never fabricate facts into stored items** — dates, names, amounts are extracted or asked, never guessed inline (§6).
3. **No open-ended AI companion, no engineered parasocial pull** — no "I missed you" notifications, no romance-adjacent persona, no engagement-optimized chat loops [10][14].
4. **No sycophantic blessing of plans** — warmth for the person, honesty about the plan; never simulated disappointment or guilt either (RSD doc) [11][12][13].
5. **No medical territory** — no diagnosis, medication, or treatment advice; route to clinicians.
6. **AI is never a gatekeeper** — every core flow works with AI declined, off, or offline; AI-off is a respected first-class mode [2].
7. **No prompt-engineering tax** — if users need community-shared prompt tricks to get usable output, the feature has failed [1].
8. **No unbounded or surprise AI costs passed to users** — billing betrayal is this market's loudest complaint (app-landscape).

## Design implications for Klyr

1. **Ship AI task breakdown at the point of paralysis as the flagship AI feature, with a one-tap granularity dial and free regeneration.** It has the strongest mechanism fit (planning is the broken step; execution is intact) and the strongest community evidence [1][2][5]; interaction spec per ux doc §11.
2. **Klyr's generated steps must follow the startability spec: first step ≤ ~2 minutes, concrete verb + single object, 3–7 steps visible with the rest chunked, zero prose.** Built from implementation-intention specificity and microtask/choice-overload evidence (§3); treat as a testable hypothesis.
3. **Default AI to invisible infrastructure (parse, triage, schedule, resurface) with visible provenance; never make chat the primary interface.** Conversation is a bounded unstick tool that exits into action within a few turns (§4) [1][2][7].
4. **Implement the three-tier error budget as architecture: Suggest (free), Act (preview/undo only), Data (no silent writes ever).** This is the AI-side enforcement of the memory doc's trust contract (§6) [17][18].
5. **Constrain generation so facts are extract-or-ask, never invent.** A hallucinated deadline in the user's external memory is the single worst AI failure available to Klyr (§6).
6. **Write an anti-sycophancy behavior spec and test against it: validate feelings, evaluate plans, disagree kindly when the plan fights the user's own goals.** RSD-prone users are the worst-case audience for flattery loops [11][12][13].
7. **Klyr must never build an open-ended companion; any body-double or check-in presence is task-anchored, session-scoped, and personality-light.** Dose-dependent psychosocial harm and dependence are documented [10][14]; passive presence carries the benefit hypothesis with less attachment surface.
8. **Give AI a per-feature off switch and honor "do it with me, not for me."** ADHD users demonstrably manage their own dependence boundaries [2]; supporting autonomy is also the SDT-correct move ([motivation-and-gamification](../strategies/motivation-and-gamification.md)).
9. **Show one-line reasoning on AI suggestions.** Cheap rationale scaffolds the user's own planning (countering the offloading worry §7) and supports calibrated trust (ux doc §11) [15].
10. **Keep AI off the capture critical path; stream anything user-facing; batch everything else.** Latency rules from §8 — capture is sacred and sub-second, always.
11. **Tune output shape for ADHD reading: short, scannable, zero hedging paragraphs, zero lectures.** "Overly neurotypical, verbose responses" is the top documented friction for neurodivergent LLM users [1].
12. **Architect for small/on-device models for high-frequency invisible ops; reserve cloud calls for breakdown and unstick moments; design AI economics so the default tier never needs metering.** Cost and privacy pull the same way (§8) [22][23].
13. **After any user-flagged AI error, visibly adapt ("won't suggest that again") and make correction one tap.** Algorithm aversion means the response to the first visible error decides whether the feature survives [17]; a correction that visibly teaches the system can convert an error into trust.
14. **Instrument the trust loop as a first-class metric: acceptance rate of AI suggestions over time, regeneration rate, AI-feature abandonment after errors — not chat engagement.** Optimizing AI-surface engagement is how sycophancy and companionship drift in [10][11]; tension to manage: the same telemetry must respect the privacy doc's data-minimization rules.

## Open questions

- **Granularity ground truth:** does the §3 startability spec actually beat coarser/finer defaults for real ADHD users? Needs A/B testing at the moment of paralysis (step-started rate, not satisfaction).
- **Does AI breakdown transfer or dependent-ize?** No longitudinal data on whether scaffolded decomposition builds, preserves, or erodes users' own planning over months — the field's biggest open question (§7).
- **Reliability floor per feature in practice:** what do real-world parse/triage/schedule accuracy rates look like on messy ADHD input (fragments, voice mumbles), and do they clear the ~0.70 lesson with margin [18]?
- **Bounded unstick conversations:** can a dialogue be short enough to avoid time-sink/dependence risks and still unstick? Where is the turn-count sweet spot?
- **AI body-double presence:** does passive AI presence reproduce any of human body doubling's effect, or is social accountability the entire mechanism?
- **Trust repair:** after Klyr's AI makes its first visible error, which recovery UX (apology + adaptation vs. silent improvement vs. user-tunable confidence) best predicts continued feature use?
- **Sycophancy measurement in production:** ELEPHANT-style benchmarks exist for research models [12]; Klyr needs a practical eval for its own prompts/persona, re-run on every model change.
- **Chronotype/state-aware AI:** should suggestion aggressiveness follow energy states (see time-perception doc)? No evidence either way.

## Sources

1. [research] [Carik, Ping, Ding & Rho (2025). Exploring Large Language Models Through a Neurodivergent Lens: Use, Challenges, Community-Driven Workarounds, and Concerns. PACM HCI 9(1) / CSCW](https://doi.org/10.1145/3701194)
2. [research] [Tazike, Deldari & Jamshidi (2026). "It Helps Me Start": How ADHD Users Adapt AI Tools in Everyday Life. CHI EA](https://dl.acm.org/doi/10.1145/3772363.3798808)
3. [research] [Glazko et al. (2023). An Autoethnographic Case Study of Generative Artificial Intelligence's Utility for Accessibility. ASSETS 2023 (arXiv preprint)](https://arxiv.org/abs/2308.09924)
4. [research] [Schofield et al. (2026). Digital health technologies for adults with ADHD: a scoping review. Frontiers in Digital Health 8:1746732](https://europepmc.org/article/PMC/PMC12969067)
5. [research] [Cheng, Teevan, Iqbal & Bernstein (2015). Break It Down: A Comparison of Macro- and Microtasks. CHI 2015](https://doi.org/10.1145/2702123.2702146)
6. [research] [Hahn, Iqbal & Teevan (2019). Casual Microtasking: Embedding Microtasks in Facebook. CHI 2019](https://doi.org/10.1145/3290605.3300249)
7. [research] [Cranshaw et al. (2017). Calendar.help: Designing a Workflow-Based Scheduling Agent with Humans in the Loop. CHI 2017](https://doi.org/10.1145/3025453.3025780)
8. [research] [Fitzpatrick, Darcy & Vierhile (2017). Delivering CBT to Young Adults Using a Conversational Agent (Woebot): RCT. JMIR Mental Health 4(2):e19](https://pmc.ncbi.nlm.nih.gov/articles/PMC5478797/)
9. [research] [Dartmouth (2025). First Therapy Chatbot Trial Yields Mental Health Benefits — press summary of the Therabot RCT (Heinz, Jacobson et al., NEJM AI)](https://home.dartmouth.edu/news/2025/03/first-therapy-chatbot-trial-yields-mental-health-benefits)
10. [research] [Fang et al. (2025). How AI and Human Behaviors Shape Psychosocial Effects of Extended Chatbot Use: A Longitudinal RCT. MIT Media Lab / OpenAI (arXiv:2503.17473)](https://arxiv.org/abs/2503.17473)
11. [research] [Sharma et al. (2023). Towards Understanding Sycophancy in Language Models. Anthropic (arXiv:2310.13548)](https://arxiv.org/abs/2310.13548)
12. [research] [Cheng, Yu, Lee, Khadpe, Ibrahim & Jurafsky (2025). ELEPHANT: Measuring and Understanding Social Sycophancy in LLMs (arXiv:2505.13995)](https://arxiv.org/abs/2505.13995)
13. [product] [TechCrunch (Apr 29, 2025). OpenAI rolls back update that made ChatGPT "too sycophant-y"](https://techcrunch.com/2025/04/29/openai-rolls-back-update-that-made-chatgpt-too-sycophant-y/)
14. [product] [Reuters (Jan 7, 2026). Google, AI firm settle Florida mother's lawsuit over son's suicide (Character.AI / Sewell Setzer case)](https://www.reuters.com/world/google-ai-firm-settle-florida-mothers-lawsuit-over-sons-suicide-2026-01-07/)
15. [research] [Lee et al. (2025). The Impact of Generative AI on Critical Thinking: Self-Reported Reductions in Cognitive Effort and Confidence Effects From a Survey of Knowledge Workers. CHI 2025, Microsoft Research](https://www.microsoft.com/en-us/research/publication/the-impact-of-generative-ai-on-critical-thinking-self-reported-reductions-in-cognitive-effort-and-confidence-effects-from-a-survey-of-knowledge-workers/)
16. [research] [Gerlich (2025). AI Tools in Society: Impacts on Cognitive Offloading and the Future of Critical Thinking. Societies 15(1):6](https://www.mdpi.com/2075-4698/15/1/6)
17. [research] [Dietvorst, Simmons & Massey (2015). Algorithm Aversion: People Erroneously Avoid Algorithms After Seeing Them Err. J. Experimental Psychology: General 144(1)](https://doi.org/10.1037/xge0000033)
18. [research] [Wickens & Dixon (2007). The benefits of imperfect diagnostic automation: a synthesis of the literature. Theoretical Issues in Ergonomics Science 8(3)](https://doi.org/10.1080/14639220500370105)
19. [clinical] [Fleck / ADDitude (2024). AI for ADHD: How to Make ChatGPT Work for You](https://www.additudemag.com/chatgpt-ai-adhd-executive-function-support/)
20. [community] [ADDitude Editors (2025). "A Cognitive Collaborator": How Adults with ADHD Are Using ChatGPT](https://www.additudemag.com/how-to-use-chatgpt-executive-function-adhd/)
21. [product] [Goblin Tools — About (accuracy disclaimer; free neurodivergent-first AI tools)](https://goblin.tools/About)
22. [product] [Apple Machine Learning Research (2024). Introducing Apple's On-Device and Server Foundation Models](https://machinelearning.apple.com/research/introducing-apple-foundation-models)
23. [product] [Anthropic (2026). Claude API model pricing (accessed 2026-07-25; prices change frequently)](https://platform.claude.com/docs/en/docs/about-claude/pricing)
