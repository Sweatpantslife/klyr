---
title: "When Klyr Should Back Off: Depressive Episodes, Burnout, and Safety Boundaries"
area: product
file: research/product/when-to-back-off.md
tags: [back-off, burnout, depression, comorbidity, crisis-resources, regulatory-boundaries, maintenance-mode, digital-phenotyping]
related:
  - research/foundations/adhd-overview.md
  - research/daily-life/daily-life-impact.md
  - research/foundations/emotional-regulation-and-rsd.md
  - research/product/app-landscape.md
  - research/product/ux-design-for-adhd.md
sources: 18
updated: 2026-07-25
summary: >
  How Klyr should behave when a user's capacity collapses — depressive episodes, burnout,
  overwhelm — including what usage signals can and cannot tell us, the FDA/app-store lines Klyr
  must not cross, crisis-resource requirements, maintenance-mode and check-in design, and copy
  rules for bad weeks. Read before designing any adaptive behavior, wellbeing feature, or
  low-activity response.
---

# When Klyr Should Back Off: Depressive Episodes, Burnout, and Safety Boundaries

## TL;DR

- For Klyr's median user, capacity collapse is **a scheduled event, not an edge case**: comorbid anxiety and depression are the norm in adult ADHD (see [adhd-overview](../foundations/adhd-overview.md)), and boom-bust cycles are the documented rhythm of ADHD life (see [daily-life-impact](../daily-life/daily-life-impact.md)). A productivity tool that only models "on weeks" will hurt people on "off weeks."
- **Software cannot reliably distinguish a depressive shutdown from a busy week.** Passive-sensing research is promising at group level (sleep, home-stay, activity correlate with depression) but studies are small (median n=58), short (median 9 days), heterogeneous, and rarely externally validated; reviewers call results "hypothesis generation," not deployable detection.
- The false-positive math is brutal: for rare states, even excellent classifiers mostly flag people who are fine (one analysis: population screening would need ~99.4% specificity to avoid false positives dominating). Guessing wrong costs trust twice — it feels like **surveillance** and it **pathologizes** an ordinary week.
- Therefore Klyr's rule is asymmetric: **automatically reduce pressure without asking; never escalate, label, or interpret without asking.** Wrongly quieting notifications costs almost nothing; wrongly implying "you seem depressed" costs the relationship.
- **Productivity pressure is a plausible depressant, but the evidence is occupational, not app-level**: high demands, effort-reward imbalance, and low control show moderate-evidence links to depression and anxiety. Meanwhile behavioral activation — gentle, graded re-engagement — is an evidence-based depression treatment. So "backing off" means removing pressure and shrinking demands, **not** removing all structure.
- **ADHD burnout is a real community phenomenon but not a validated clinical construct.** The nearest peer-reviewed anchor is autistic burnout (chronic exhaustion, loss of skills, reduced stimulus tolerance, typically 3+ months) plus qualitative evidence that working ADHD adults overcommit, mask, and cycle into exhaustion and sick leave.
- Regulatory line: under the FDA's general-wellness policy (updated January 2026), Klyr may claim stress management, relaxation, self-esteem, and "living well with anxiety, as part of a healthy lifestyle" — but the moment its **UI, labeling, or alerts reference a specific disease, use diagnostic thresholds, or prompt clinical action**, it is outside the wellness safe harbor. No PHQ-9, no "depression detected," ever.
- App stores add their own floor: Apple scrutinizes medical claims and bans ad-use of health data; Google Play requires a health-apps declaration and a "not a medical device" posture. An audit of 69 depression/suicide apps found 6 shipped **wrong crisis numbers** (two with 1M+ installs each) — crisis resources are a maintenance liability, not a checkbox.
- Shipped precedents prove low-power modes retain users: Finch (no punishment for missed goals, first-aid toolkit), Daylio (two-tap logging, on-device data), Bearable (few-tap tracking built for low-energy chronic-illness users).
- The deliverable pattern: **soft triggers → consent-first check-in → user-owned maintenance mode → tiny anchors kept → shame-free restart**, with crisis resources always passively reachable and never algorithmically sprung on the user.

## 1. Why "back off" is a core behavior, not a safety appendix

Two corpus facts set the stage. First, comorbidity is the default: adults with ADHD carry roughly 4–9× odds of anxiety, depression, and bipolar disorder relative to non-ADHD adults ([adhd-overview](../foundations/adhd-overview.md) owns the numbers). Second, ADHD capacity is cyclical — masking and hyperfocus fund overcommitment, which collapses into a crash ([daily-life-impact](../daily-life/daily-life-impact.md) owns the boom-bust description). Put together: over a year of use, Klyr **will** hold the task list of someone in a depressive episode, a burnout trough, or a post-boom crash. Repeatedly.

Most tools respond to collapsing engagement with re-engagement pressure: streak warnings, "we miss you" pushes, red overdue counts. For this population that is precisely backwards — the corpus documents that guilt-displaying apps become shame artifacts that users stop opening and then delete ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md), [app-landscape](app-landscape.md)). This doc specifies what to do instead, and where the legal and ethical walls are.

## 2. What a capacity collapse is (and how it differs from a bad Tuesday)

### 2.1 Depressive episodes

In a depressive episode, the problem is not "tasks are boring"; it is anhedonia, fatigue, psychomotor slowing, and self-critical cognition. The practical signature users describe: basics (shower, food, replying) become the whole day's work. A task app's normal value proposition — organize, prioritize, plan — is temporarily irrelevant; its failure modes — displaying deficit, quantifying falling-behind — are amplified. Note the trap: ADHD-driven avoidance and depression-driven shutdown look similar from the outside but respond differently (novelty/interest can pull an ADHDer into motion; it does little against anhedonia). Klyr cannot tell these apart and must not try to (Section 3); it can only make both states cheaper to survive.

### 2.2 Burnout — and whether "ADHD burnout" is a distinct construct

**Occupational burnout** (WHO/ICD-11 framing) is a work-context syndrome: exhaustion, cynicism, reduced efficacy. **Autistic burnout** now has a peer-reviewed definition from community-based research (Raymaker et al., 2020, 19 interviews + 19 public accounts): *chronic exhaustion, loss of skills, and reduced tolerance to stimulus*, typically lasting 3+ months, arising from "chronic life stress and a mismatch of expectations and abilities without adequate supports." Participants distinguished it from depression and from job burnout: it spans all life domains, and its drivers are masking, cumulative life stressors, and barriers to support. What helped: reduced expectations, time off, unmasking, accommodations, acceptance [2].

**"ADHD burnout" has no equivalent validated paper.** It is a community construct (widely used on r/ADHD, coaching sites, ADDitude) that borrows the autistic-burnout shape. ADDitude's clinical-adjacent coverage is explicit: "Neurodivergent burnout is not a clinical diagnosis, but it is a real phenomenon," driven substantially by masking and overcommitment [13]. The nearest peer-reviewed neighbor is qualitative: a 2022 Swedish interview study of 20 working adults with ADHD (BMC Psychiatry) found recurring exhaustion, persistent anxiety, compensatory over-thoroughness and overtime, impulsive overcommitment, and hyperfocus-fed workaholism; its background literature notes adults with ADHD average 8–34 excess sickness-absence days per year [12]. Treat "ADHD burnout" the way the corpus treats RSD: **scientifically unvalidated, experientially load-bearing** — never use it diagnostically, but design for the pattern users mean by it: a weeks-long trough where previous commitments exceed present capacity.

Design-relevant difference from a bad day: bad days need a lighter *today*; burnout/depressive troughs need a lighter *system* — fewer active commitments, paused recurrences, shrunken surface area — for weeks, with recovery aided by *reduced expectations*, per Raymaker [2].

## 3. Can Klyr detect any of this? Grading digital phenotyping honestly

**Digital phenotyping** — inferring mental state from device data — and **JITAIs** (just-in-time adaptive interventions, which time support using sensed "vulnerability" and "receptivity" states [3]) are the relevant literatures. Honest read as of 2026:

- **Group-level correlations exist.** A systematic review of 51 passive-monitoring-of-depression studies (De Angel et al., 2022) found the most consistent depression correlates were *home-stay/mobility* (all included studies significant), *sleep stability and efficiency*, and *reduced physical activity*. Phone-usage features had almost no evidence (3 studies); circadian features mostly showed no association [4].
- **The evidence base is thin and fragile.** Same review: median sample 58 participants, median follow-up 9 days, heavy student/North-American sampling, incompatible feature definitions, missing-data handling rarely described. The authors' own verdict: results are "a starting point for hypothesis generation" — not clinical readiness [4]. A 2025 systematic review of wearable-based monitoring (22 studies) could not even meta-analyze due to heterogeneity, and did not assess external validation at all [5].
- **False positives dominate at population scale.** For rare states, base rates crush classifiers: one npj Digital Medicine analysis calculated that population screening for bipolar disorder would need ~99.4% specificity (with perfect sensitivity) to keep false positives from dominating; it also warned that models trained on narrow samples (students) show "unacceptable bias in real-world applications," and that users are notably wary of sharing location data — the single most informative sensor stream [6]. Commercial attempts to productize consumer-grade mental-state inference have so far not survived contact with reality.
- **JITAI theory itself warns against untimely intervention.** Nahum-Shani et al. emphasize that prompting a person who is not *receptive* actively harms engagement — intervention fatigue, habituation, disengagement — and that a legitimate intervention option is "provide nothing" [3].

And all of that is about **rich sensor data** (GPS, actigraphy, sleep). Klyr's native signal — in-app behavior — is far weaker. A completion-rate collapse or a week of not opening the app is consistent with: depression, burnout, vacation, a newborn, hyperfocus on a thrilling project, exams, or having migrated to paper (the standard ADHD app lifecycle; see [app-landscape](app-landscape.md)). **Within-app signals can detect "something changed"; they cannot detect *what*.**

### 3.1 The false-positive cost is not symmetric with the false-negative cost

Guessing "you seem depressed" and being wrong does three kinds of damage: it reveals surveillance ("it's watching how I use it"), it pathologizes normal variance ("my app thinks a busy week is a mental-health event"), and — for a shame-primed, rejection-sensitive user ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)) — it lands as judgment from the one tool that promised not to judge. Missing a real episode, by contrast, costs little *provided the app's default behavior is already gentle and support is passively discoverable*. This yields the doc's central rule:

> **The asymmetry principle.** Actions that only *reduce* pressure (quieting nudges, hiding overdue counts, softening copy) may be triggered automatically on weak signals — the cost of a false positive is a few missed notifications. Actions that *interpret, label, escalate, or expose* (naming a state, suggesting help, surfacing crisis resources modally, changing what others/integrations see) require explicit user input first — the cost of a false positive is trust, dignity, and possibly the user's safety narrative.

## 4. Does productivity pressure actually make things worse?

What the evidence supports, graded:

- **Occupational-stress research (moderate evidence, analog domain).** A systematic meta-review of 37 reviews found moderate evidence from prospective studies that high job demands, low control, **effort-reward imbalance** (sustained high effort without adequate reward — a fair description of ADHD life-admin), low procedural justice, and low support increase risk of depression and anxiety [10]. This is workplaces, not apps; the mechanism (chronic demand > resource, effort > reward) plausibly transfers to a tool that manufactures felt demands, but no RCT tests "app pressure → depression" directly. Say so honestly.
- **App-level evidence is behavioral, not clinical.** What is documented is that guilt-inducing productivity surfaces drive avoidance and abandonment in ADHD users (corpus: [app-landscape](app-landscape.md) abandonment lifecycle; [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md) shame spiral). An app the user flees cannot help them; harm-via-pressure and product-death-via-pressure point the same direction.
- **The counterweight: doing nothing is not therapeutic either.** **Behavioral activation (BA)** — structured, *graded* re-engagement with valued activities — is an established depression treatment: a Cochrane review (53 RCTs, 5,495 participants) found moderate-certainty evidence of short-term benefit vs. treatment-as-usual (RR 1.40, 95% CI 1.10–1.78) and no detectable difference vs. CBT, with confidence tempered by sensitivity analyses [11]. Raymaker's burnout participants likewise recovered via *reduced* — not zero — expectations [2].

**Synthesis for Klyr:** pressure (deadlines-as-threat, deficit displays, guilt copy) is the harmful ingredient; *structure* (a tiny, chosen, achievable next thing) is the helpful one. Backing off means shrinking and softening the ask, never deleting the scaffold. A maintenance mode that goes fully dark would abandon the user at the moment tiny wins matter most — this is the tension the design must hold.

## 5. The regulatory and policy walls

### 5.1 FDA: the general-wellness line (updated January 6, 2026)

The FDA's *General Wellness: Policy for Low Risk Devices* guidance (reissued January 2026, superseding the 2019 version) is the controlling document for what a US wellness app may claim and do [1]. The structure:

| Zone | What it covers | Examples from the guidance |
|---|---|---|
| **Category 1 — safe** | General-health claims with **no disease reference**: relaxation/stress management, mental acuity, self-esteem, sleep management, concentration | "Claims to promote relaxation or manage stress"; "improve mental acuity, concentration, problem-solving"; "track sleep trends" |
| **Category 2 — conditional** | Healthy-lifestyle claims that reference a disease only as *risk-reduction* or *living-well-with*, where the lifestyle link is well accepted | "Software Product V tracks and records your sleep, work and exercise routine which, as part of a healthy lifestyle, may help living well with **anxiety**" |
| **Outside the policy** | Diagnosis, treatment, mitigation claims | "A claim that a product helps **treat an anxiety disorder**"; treating an eating disorder; diagnosing autism |

The 2026 revision adds unusually concrete disqualifiers: a product is **not** a general wellness product if its *labeling, advertising, user interface, or functionality* includes (1) references to specific diseases or diagnostic thresholds, (2) alerts or prompts recommending specific clinical action, (3) treatment guidance, (4) "clinical grade" claims, or (5) intended-use statements targeting screening or monitoring of a condition [1]. Note that this reaches **UI and functionality**, not just marketing — an in-app PHQ-9 with cutoff scores, or a "your patterns suggest depression" alert, would cross the line even with disclaimers attached.

Critically, the guidance *explicitly permits* one thing Klyr wants: a notification that "evaluation by a healthcare professional may be helpful," provided it does not name a disease, characterize anything as abnormal or diagnostic, include clinical thresholds, or run ongoing condition-monitoring alerts [1]. That is the exact legal template for a well-built check-in escalation ("A lot of people find it helps to talk to someone — here are options"), and the exact prohibition of "your data looks like depression."

### 5.2 App stores

- **Apple** (App Store Review Guidelines): medical-ish apps get heightened scrutiny; accuracy claims need disclosed methodology; apps "should remind users to check with a doctor"; health/fitness data may never be used for advertising or data mining (5.1.3); health-research features require informed consent and IRB approval [8].
- **Google Play** (Health Content and Services): a mandatory health-apps declaration; prohibited "false or misleading health claims"; apps must present as "not a medical device… does not diagnose, treat, cure, or prevent any medical condition" unless actually cleared as one, with proof of regulatory approval on request [9].

### 5.3 Crisis-resource reality check

The strongest empirical warning about crisis features comes from Martinengo et al.'s audit of 69 depression and suicide-prevention apps (BMC Medicine, 2019): 46/69 offered a crisis helpline, but **six apps shipped erroneous or non-working numbers — two of them with more than a million installs each** — and only 5/69 implemented all six evidence-based strategies (mood/suicidal-ideation tracking, safety-plan development, activity recommendation, education, support-network access, emergency counseling). The authors called it a failure of app-industry self-governance [7]. Lessons: a crisis link is a **liability that must be maintained and localized** (numbers change; users travel; 988 is US-only — call/text 988 per SAMHSA [14]); and a wellness app that will not do crisis support *well* should do less of it, *reliably*: a small, hand-maintained, country-aware "get support now" surface rather than a sprawling stale directory.

## 6. Shipped precedents: low-power modes that users keep

| Product | What it does when capacity is low | Verified design facts |
|---|---|---|
| **Finch** (self-care pet) | Goals scale down to "get out of bed"-sized; a "First Aid" section holds panic breathing and in-bed exercises; missed days carry **no penalty** — the pet never suffers; reviewers with depression/anxiety/ADHD explicitly credit the no-punishment design [15]. Community reports also describe quiet/rest affordances softening reminders (feature naming not verified in this pass). | App Store listing + reviews [15]; abandonment-proofing analysis in [app-landscape](app-landscape.md) |
| **Daylio** (mood micro-diary) | Two taps to log ("pick mood and activities"), zero typing required — an entry is possible from bed; data stays on device ("We don't send your data to our servers") [16]. | Product site [16] |
| **Bearable** (symptom tracker) | Built by/for chronically ill users; "a few taps each day" for mood/energy/symptoms; lets users hide triggering metrics; assumes brain fog and limited energy as the *default* user state [17]. | Product site [17] |

The shared lesson: these products assume the user's worst week as the baseline and make the minimum viable interaction nearly free. None of them punishes absence. Finch in particular demonstrates that warmth plus zero-penalty economics retains exactly the users Klyr targets ([app-landscape](app-landscape.md) covers its retention reputation).

## 7. The design pattern: triggers → consent → maintenance → restart

### 7.1 Back-off triggers (soft signals, cheap actions)

Tiered by the asymmetry principle:

1. **User-declared (gold standard, zero inference):** a persistent, one-tap **capacity control** — e.g., "Today is a low day" / a 3-level energy dial — plus a durable "I'm going through something, quiet things down" switch. Declaring low capacity must cost one tap and zero explanation.
2. **Behavioral (auto-de-escalate only):** completion rate collapsing vs. the user's own baseline; N days of non-opening after regular use; overdue count crossing a threshold; snoozing most notifications. Legitimate automatic responses: pause non-critical nudges, collapse the overdue pile into one neutral line ("Some things are waiting — whenever you're ready"), suppress streak-adjacent displays. Never a legitimate basis for: naming a state, "wellness" pop-ups, or emailing "we noticed you've been away."
3. **Calendar/context (user-supplied):** sick days, "off" periods the user marks. Honor them absolutely — zero notifications, zero accumulation displayed on return.

### 7.2 Consent-first check-ins

The check-in is Klyr's only bridge from "something changed" to "user tells us what." Rules derived from JITAI receptivity findings [3] and the FDA notification constraints [1]:

- **Consent is configured in calm weather:** during onboarding or settings, not mid-episode: "If your activity drops a lot, want Klyr to check in? (Ask me / Just go quiet / Do nothing)." Default: *Just go quiet*.
- **Ask about capacity, not condition:** "Looks like things have been a lot lately. Want to switch to Essentials mode?" — never "Are you depressed?", never symptom checklists, never mood inference.
- **Once, gently, dismissibly.** One check-in per episode; dismissal is answer enough; no follow-up nag ladder (intervention fatigue is documented [3]).
- **Every check-in offers a real gift, not a survey:** the immediately-actionable option (Essentials mode, one tap) — support offered at the point of need, not data extraction.

### 7.3 Maintenance mode ("Essentials")

A first-class, user-invokable mode — reachable from settings, from the check-in, and from the capacity dial:

- **Shrink the world:** show only 1–3 user-chosen anchor tasks (defaults offered: meds, food, one bill-class item — the health-critical categories that quietly fail per [daily-life-impact](../daily-life/daily-life-impact.md)). Everything else is stored, not shown.
- **Stop the meters:** recurring tasks stop generating visible instances; nothing accrues "overdue"; date-shame surfaces are frozen. Real-world recurrence is elastic — a missed cycle is skipped, not stacked ([daily-life-impact](../daily-life/daily-life-impact.md), [habits-and-routines](../daily-life/habits-and-routines.md)).
- **Keep tiny anchors, per BA evidence:** the mode is not "app goes dark." One small doable thing with a warm win state preserves the graded-activation channel [11][2] without pressure.
- **Time-bounded softly:** after a user-set interval (default ~2 weeks), one gentle "Still want Essentials, or ease back?" — because indefinite silent modes become forgotten graveyards, and because recovery per Raymaker is aided by *renegotiated*, not abandoned, expectations [2].
- **Exit is a celebration, not an audit:** returning shows "Welcome back — here's the little that actually needs you," never the backlog wall. Restart psychology is owned by [habits-and-routines](../daily-life/habits-and-routines.md); Essentials exit is its highest-stakes application.

### 7.4 Crisis escalation UX — and its own risks

Klyr is not a crisis app and must not simulate one. The design:

- **Passive, permanent, findable:** a quiet "Get support" item (settings + search + long-press on the check-in) with 988 call/text for US users [14], country-appropriate equivalents elsewhere, and a plain sentence that Klyr is an organizer, not care. Verified and re-verified on a maintenance schedule — wrong numbers shipped to millions is the documented industry failure mode [7].
- **No keyword surveillance:** Klyr must not scan task text ("kill", "end it", "hopeless") to trigger crisis interstitials. Task language is noisy ("kill this process"), scanning implies content surveillance of the user's outboarded mind ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md) explains why that store is intimate), and false-positive modals teach users to hide from their own tool. The only crisis-adjacent trigger permitted is **explicit user disclosure inside a Klyr-authored dialog** (e.g., a free-text check-in answer describing self-harm), which may warrantly surface the support card — softly, inline, non-modally, alongside a human-toned acknowledgment.
- **Escalation risks to design against:** over-triggering (trust collapse, habituation), stale/wrong resources (Martinengo [7]), tone whiplash (a cartoon confetti app suddenly delivering clinical crisis language), and legal drift (an "alert prompting clinical action" is an FDA disqualifier if pattern-triggered [1]). The support surface should feel like a kind friend's note, present since day one — not an alarm that proves the app was watching.

### 7.5 Copy rules for bad weeks

Grounded in the shame/self-compassion evidence ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)) and safe-framing norms:

| Never | Instead |
|---|---|
| "You're falling behind" / "17 tasks overdue!" | "Some things are waiting. They'll keep." |
| "Don't break your streak!" | (nothing — absence is not an event to copywrite) |
| "We miss you! Come back!" | Silence, or (if user opted into check-ins) "No pressure. Essentials mode is here if useful." |
| "You seem down/depressed/burned out" | "Sounds like a heavy stretch." (only ever *echoing* what the user declared) |
| "Just do one thing! You've got this!! 💪" (cheerleading at someone underwater) | "One tiny thing, only if you want. Resting counts too." |
| Clinical vocabulary: symptoms, episode, relapse, screening | Capacity vocabulary: low day, heavy week, quiet mode, essentials |
| Making rest conditional ("You've earned a break") | Rest as legitimate default ("Quiet mode on. Everything's saved.") |

Meta-rules: the app never diagnoses, never quantifies deficit during a trough, never frames the user's state as a problem *for the app* ("your streak," "your score"), and always leaves agency in the user's hands (offers, not prescriptions). Fuller tone architecture belongs to [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md) and [ux-design-for-adhd](ux-design-for-adhd.md).

### 7.6 The do-not-diagnose boundary, stated once and flatly

Klyr must never: name or imply a diagnosis or episode ("depression," "burnout detected"); administer clinical screeners (PHQ-9, GAD-7) or display diagnostic thresholds; claim to detect, monitor, or treat any condition; or auto-trigger clinical-action prompts from inferred states. Klyr may: let users self-describe in their own words, offer capacity modes, provide the FDA-conformant generic suggestion that talking to a professional can help (no disease named, nothing called abnormal) [1], and link verified support resources. This is simultaneously the FDA line [1], the app-store line [8][9], and the trust line.

## Design implications for Klyr

1. **Klyr must treat low-capacity behavior as a first-class product state with its own designed experience (Essentials mode), not as churn.** Comorbidity odds and boom-bust cycles make capacity collapse a certainty over any user-year ([adhd-overview](../foundations/adhd-overview.md), [daily-life-impact](../daily-life/daily-life-impact.md)).
2. **Klyr must implement the asymmetry principle: auto-de-escalate freely, never auto-escalate.** Quieting notifications on weak signals is cheap; interpreting or labeling on weak signals costs trust and dignity — digital-phenotyping accuracy does not support inference, and base rates guarantee false positives [4][5][6].
3. **Klyr must never infer or name mental-health states from usage, and must never ship clinical screeners or diagnostic thresholds.** This is the FDA general-wellness disqualifier list nearly verbatim (UI and functionality included), plus Google Play's not-a-medical-device posture [1][9].
4. **Klyr should provide a one-tap, no-explanation capacity control** (low-day toggle / energy dial) so the user, not an algorithm, is the sensor. User declaration has 100% precision and doubles as the consent event for everything that follows.
5. **Check-ins must be opt-in (configured in calm moments), capacity-framed, single-shot, and dismissible without consequence.** JITAI research shows mistimed prompts breed fatigue and disengagement; "provide nothing" is a valid intervention [3].
6. **Essentials mode must shrink the visible system to 1–3 user-chosen anchors and freeze all deficit meters — but never go fully dark.** Reduced-not-zero expectations track both burnout recovery testimony and behavioral-activation evidence that tiny graded engagement helps depression [2][11].
7. **Recurring tasks must skip, not stack, during troughs.** Elastic recurrence matches real-world chore physics and prevents the return-to-a-wall-of-overdue moment that drives permanent abandonment ([daily-life-impact](../daily-life/daily-life-impact.md), [app-landscape](app-landscape.md)).
8. **Re-entry after absence must be engineered as the product's best moment:** neutral acknowledgment, no backlog wall, no summary of missed items, immediate small win. Optimize the "returns after lapse" metric, not DAU ([app-landscape](app-landscape.md)).
9. **Klyr must maintain a small, verified, country-aware "Get support" surface (988 call/text in the US), reachable passively at all times — and must put crisis-link verification on a release checklist.** Six of 69 audited apps shipped wrong crisis numbers, two with 1M+ installs [7][14].
10. **Klyr must not scan user content for crisis keywords or spring algorithmic crisis interstitials.** The only crisis-adjacent trigger is explicit disclosure within a Klyr-authored dialog, answered inline and gently; anything else is surveillance theater with documented false-positive costs [6] and FDA exposure (pattern-triggered clinical-action alerts) [1].
11. **All bad-week copy must pass the shame test: no deficit quantification, no guilt hooks, no cheerleading, no clinical vocabulary, agency always with the user.** Guilt surfaces are the documented abandonment engine and plausibly a depressant under demand-without-reward dynamics [10] ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).
12. **Marketing and store listings must stay inside Category 1/Category 2 wellness claims** ("manage stress," "may help living well with anxiety, as part of a healthy lifestyle") and never use "treat," "diagnose," "detect," or condition-monitoring language — including in screenshots and App Store copy [1][8][9].
13. **If Klyr ever adds mood/energy logging, it must follow the shipped-precedent bar: ≤2 taps, no typing required, no streak penalty, user-hideable, and ideally on-device/private by default** (Daylio's "we don't send your data to our servers" is the trust benchmark; Apple bans ad-use of health data outright) [15][16][17][8].
14. **Tension to hold in testing:** backing off too aggressively can read as the app giving up on the user ("even my app thinks I can't do anything"), while any check-in can read as surveillance. The resolution candidate — user-configured policies executed predictably — must itself be validated with real ADHD users in real troughs.

## Open questions

- Where exactly do real users want the line between "it noticed and quietly adapted" (comforting) and "it noticed" (creepy)? Does disclosed, user-configured adaptation eliminate the surveillance feel, or merely reduce it?
- What Essentials-mode default duration and re-check cadence feel supportive rather than nagging — and do users ever *want* an auto-exit, or must exit always be manual?
- Do tiny-anchor wins during troughs actually produce BA-like benefit in a task app context, or does any task representation read as demand during a depressive episode? (No app-level trial exists; this needs careful, ethically reviewed testing.)
- Is a fully dark mode (zero anchors) ever the right offer for severe episodes, despite the BA logic — i.e., should "go completely silent until I return" be a user option?
- How should Essentials mode interact with genuinely hard deadlines (rent, court dates, meds refills)? "Freeze everything" can cause real-world harm; "keep critical deadlines" requires Klyr to know which is which — who decides, and when?
- Can lapse-return rate and post-trough retention be measured well enough to serve as the north-star metric this doc implies, without building the very engagement surveillance it warns against?
- Non-US crisis resources: what maintenance process (and legal review) keeps a country-aware support directory correct at small-team scale?

## Sources

1. [FDA — General Wellness: Policy for Low Risk Devices (guidance, issued January 6, 2026; supersedes 2019 version)](https://www.fda.gov/media/90652/download) [clinical] — see also the [guidance landing page](https://www.fda.gov/regulatory-information/search-fda-guidance-documents/general-wellness-policy-low-risk-devices)
2. [Raymaker et al., 2020 — "Having All of Your Internal Resources Exhausted Beyond Measure and Left with No Clean-Up Crew": Defining Autistic Burnout (Autism in Adulthood)](https://pmc.ncbi.nlm.nih.gov/articles/PMC7313636/) [research]
3. [Nahum-Shani et al. — Just-in-Time Adaptive Interventions (JITAIs) in Mobile Health: Key Components and Design Principles (Annals of Behavioral Medicine)](https://pmc.ncbi.nlm.nih.gov/articles/PMC5364076/) [research]
4. [De Angel et al., 2022 — Digital health tools for the passive monitoring of depression: a systematic review of methods (npj Digital Medicine)](https://pmc.ncbi.nlm.nih.gov/articles/PMC8752685/) [research]
5. [Key Features of Digital Phenotyping for Monitoring Mental Disorders: Systematic Review (JMIR, 2025)](https://pmc.ncbi.nlm.nih.gov/articles/PMC12588392/) [research]
6. [Toward clinical digital phenotyping: a timely opportunity to consider purpose, quality, and safety (npj Digital Medicine, 2019)](https://pmc.ncbi.nlm.nih.gov/articles/PMC6731256/) [research]
7. [Martinengo et al., 2019 — Suicide prevention and depression apps' suicide risk assessment and management: adherence to clinical guidelines (BMC Medicine)](https://pmc.ncbi.nlm.nih.gov/articles/PMC6921471/) [research]
8. [Apple — App Store Review Guidelines (§1.4 Physical Harm; §5.1.3 Health and Health Research)](https://developer.apple.com/app-store/review/guidelines/) [product]
9. [Google Play — Health Content and Services policy](https://support.google.com/googleplay/android-developer/answer/12261419) [product]
10. [Harvey et al., 2017 — Can work make you mentally ill? A systematic meta-review of work-related risk factors for common mental health problems (Occupational & Environmental Medicine)](https://europepmc.org/article/MED/28108676) [research]
11. [Cochrane Review, 2020 — Behavioural activation therapy for depression in adults](https://pmc.ncbi.nlm.nih.gov/articles/PMC7390059/) [research]
12. [Stress and work-related mental illness among working adults with ADHD: a qualitative study (BMC Psychiatry, 2022)](https://pmc.ncbi.nlm.nih.gov/articles/PMC9714234/) [research]
13. [Marschall, A. — When Neurodivergent Burnout Reaches Its Breaking Point (ADDitude)](https://www.additudemag.com/autistic-adhd-burnout-neurodivergent-masking/) [community]
14. [SAMHSA — 988 Suicide & Crisis Lifeline Partner Toolkit](https://www.samhsa.gov/mental-health/988/partner-toolkit) [clinical]
15. [Finch: Self-Care Widget Pet — App Store listing and review themes](https://apps.apple.com/us/app/finch-self-care-widget-pet/id1528595748) [product]
16. [Daylio — product site (two-tap logging; on-device data)](https://daylio.net/) [product]
17. [Bearable — product site (low-effort symptom/mood tracking for chronic illness)](https://bearable.app/) [product]
18. [ADDitude search: ADHD burnout coverage (construct status and community framing)](https://www.additudemag.com/?s=adhd+burnout) [community]
