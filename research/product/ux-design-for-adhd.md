---
title: "UX and Interaction Design for ADHD: Cognitive Load, Notifications, Accessibility, Dark Patterns"
area: product
file: research/product/ux-design-for-adhd.md
tags: [ux, cognitive-load, choice-architecture, notifications, accessibility, dark-patterns, onboarding, friction]
related:
  - research/product/app-landscape.md
  - research/foundations/memory-and-object-permanence.md
  - research/foundations/attention-and-hyperfocus.md
  - research/strategies/motivation-and-gamification.md
  - research/foundations/emotional-regulation-and-rsd.md
sources: 37
updated: 2026-07-25
summary: >
  How to design Klyr's interface: cognitive-load budgeting, choice architecture and defaults,
  onboarding, information density, typography/motion/color, notification science, friction
  asymmetry, forgiveness patterns, COGA and GOV.UK accessibility guidance, banned dark patterns,
  and AI-assist trust. Read before designing any screen, flow, notification, or pricing surface.
---

# UX and Interaction Design for ADHD: Cognitive Load, Notifications, Accessibility, Dark Patterns

## TL;DR

- ADHD taxes **extraneous cognitive load** at a premium: working-memory constraints mean every decorative element, badge, and unnecessary decision competes directly with the user's task. Minimize extraneous load ruthlessly; let Klyr absorb complexity (Tesler's law) instead of exporting it to the user.
- **Choice overload is real but conditional** (Chernev meta-analysis: 99 studies): it bites hardest under decision difficulty, complex options, and uncertain preferences — precisely the ADHD profile. Opinionated defaults and zero-config value beat "flexible and powerful"; the Notion-style blank canvas is a documented abandonment engine for ADHD users.
- Onboarding must deliver value in the first minutes: industry analyses report most app abandonment happens within days, and long setup flows kill adoption. First capture within ~60 seconds; configuration harvested from use, never asked up front.
- The **information-density debate** ("I need everything visible" vs. "dense UIs shut me down") resolves via progressive disclosure with guaranteed resurfacing, user-controlled density, and a one-thing-now focus mode — visibility of the right thing, not of everything.
- Typography must assume comorbid dyslexia (25–40% bidirectional overlap): sans serif, ~16–19 px minimum, 1.5 line spacing, left-aligned, no italics/all-caps for emphasis, user-adjustable.
- Motion: small purposeful celebration is fine; ambient/looping/autoplaying motion is an attention thief. `prefers-reduced-motion` support is mandatory (WCAG 2.3.3 territory), and motion must never be the only signal.
- Notifications die by **habituation**: research finds alert fatigue and attention disruption — not raw frequency — predict harm, and batching non-urgent notifications improves well-being. Klyr needs actionable, batched, context-triggered notifications with an escalation ladder and an explicit answer to **snooze-death**.
- **Friction asymmetry**: capture must cost nearly nothing (voice, natural language, widget, no filing decisions); friction is legitimately spent only on destruction and self-identified distraction, never on capture, completion, or coming back after a lapse.
- **Forgiveness by default**: undo instead of confirmation dialogs, archive instead of delete, autosave everything, zero data loss on timeout, and zero punishment for absence.
- Adopt W3C COGA "Making Content Usable" and the GOV.UK accessibility posters as a design floor; notably, no dedicated ADHD poster exists — Klyr's design system fills a real gap.
- Ban the dark patterns that exploit ADHD specifically: fake urgency, guilt copy, streak hostage-taking, hard-to-cancel subscriptions and silent trial conversions (the FTC's Amazon "Iliad Flow" case shows the legal and reputational stakes). The ethical stance is a genuine differentiator.
- AI assists (auto-breakdown, auto-scheduling) must target **calibrated trust**: suggest visibly, preview before acting, undo after, never silently rearrange the user's external memory.

## 1. Cognitive load: the budget every screen spends

**Cognitive load theory** (Sweller) splits mental effort into **intrinsic load** (the task itself — deciding what to do today), **extraneous load** (effort imposed by presentation — finding the button, parsing the layout, ignoring the upsell), and **germane load** (building understanding). UI design cannot remove intrinsic load, but it fully controls extraneous load.

For ADHD this is not a nicety. Working-memory limitations (see [memory-and-object-permanence](../foundations/memory-and-object-permanence.md)) mean the mental workspace is smaller and more volatile; anything the interface spends, the task loses. Practitioner guidance on ADHD accessibility converges on the same point: visual clutter and excess information produce cognitive overload and "interfaces full of distractions," and users may abandon mid-flow rather than push through [26][27].

What extraneous load looks like in a task manager, concretely: unread badges on four tabs, a sync banner, an empty state with six suggested actions, a "upgrade to Pro" card between task groups, seven metadata fields on the add-task form, and a settings tree with 40 switches. Each element is a micro-decision ("is this relevant?"), and micro-decisions are exactly what executive-function-taxed users are rationing (see [executive-function](../foundations/executive-function.md)).

**Tesler's law** (conservation of complexity) is the strategic frame: every system has irreducible complexity — the only question is who pays for it [11]. Klyr should pay wherever possible: parse the date instead of showing a date picker, choose a sensible list instead of asking "where should this go?", compute "what's next" instead of displaying everything and letting the user derive it.

Working rule: **every screen has one job**, states it, and spends its remaining pixels on nothing.

## 2. Choice architecture: defaults beat options

**Hick–Hyman law** (Hick 1952): decision time grows with the number and complexity of choices, approximately T = a + b·log₂(n) in simple stimulus–response tasks [10][11]. Its lab origins matter — familiarity, grouping, and clear hierarchy soften the effect for well-learned menus — so the lesson is not "remove features" but "never present ungrouped, unranked options" [10].

**Choice overload** research adds the conditions. Chernev, Böckenholt & Goodman's meta-analysis (99 observations, N = 7,202) found no universal "more is worse" effect; overload reliably appears under four moderators: **choice-set complexity**, **decision-task difficulty**, **preference uncertainty**, and a weak **decision goal** [9]. Map those onto ADHD: decision difficulty is elevated (executive load, decision fatigue), preference uncertainty is elevated (emotion and interest shift hour to hour), and commitment wavers mid-decision. ADHD users sit in the exact region of parameter space where choice overload is strongest — this mapping is an inference from the moderator structure, but a well-grounded one.

This is the mechanism behind the **Notion problem**, extensively documented in community and competitor writing (vendor-authored, but consistent with long-running r/ADHD sentiment): a blank canvas plus infinite configuration produces blank-page paralysis ("should this be a table, board, gallery, timeline?"), a **setup tax** on every capture ("what should have taken 2 seconds becomes a 5-minute decision"), and **over-customization paralysis** — hours spent building the system as a form of productive procrastination, followed by abandonment when maintenance exceeds executive budget [28][29][30]. See [app-landscape](./app-landscape.md) for the market pattern and [planning-methodologies-and-adhd](../strategies/planning-methodologies-and-adhd.md) for the methodology-level version.

Design consequences:

- **Zero-config value**: Klyr must be fully useful with nothing configured. Defaults are the product; settings are an escape hatch.
- **Opinionated first, flexible later**: expose one good way to do each thing; unlock alternatives only when a user demonstrates the need.
- **Klyr decides, user corrects**: capture goes to an inbox and Klyr proposes the sorting; correcting a guess is far cheaper than answering a question.
- Choices, when unavoidable, come **ranked, grouped, and defaulted** — never as a flat wall of equal options.

## 3. Onboarding: time-to-first-value is the whole game

Industry analytics are blunt about early abandonment: commonly cited figures include ~25% of users abandoning an app after a single use, up to 80% churning within the first three days, ~72% abandoning when onboarding has too many steps, and top-quartile products reaching first value in under five minutes [32][33][37]. These are vendor-aggregated numbers, not peer review — treat magnitudes, not decimals, as the signal.

ADHD sharpens all of it. The first session rides the novelty/interest wave (see [dopamine-and-motivation](../foundations/dopamine-and-motivation.md)); if that wave is spent on account creation, permission dialogs, a personality quiz, and an empty dashboard, the product has consumed its one guaranteed engagement on bureaucracy. Worse, a long setup turns adoption itself into a multi-step project — and stalled initiation on multi-step projects is the core ADHD failure mode Klyr exists to address (see [task-initiation-and-paralysis](../daily-life/task-initiation-and-paralysis.md)).

**Progressive disclosure** is the standard resolution, and Nielsen Norman Group's framing is precise: show novices only the primary features, defer the rest to explicit "more" moments; this improves learnability, efficiency, and error rates at once. Its success conditions: the primary set must genuinely cover frequent needs, and the path to "more" must be obvious and honestly labeled [12]. **Staged disclosure** (one step at a time) fits linear flows like first-run [12].

Rules for Klyr's first run:

1. **Capture before configure**: the user should have entered a real task within ~60 seconds of opening the app, before any account wall if at all feasible.
2. **No questionnaire-gated value**: preference questions are deferred and optional; personalization is inferred from behavior.
3. **Teach one gesture per session**, in context, not via a 12-screen tour.
4. An **empty inbox is never blank**: show one obvious action ("say or type anything you need to do"), not six.

## 4. The information-density debate: visible or overwhelming?

Two truths collide in ADHD UX research and community testimony. First: **out of sight is out of mind** — hidden tasks functionally cease to exist, which is why ADHDers pile papers on desks and distrust apps that tuck things into folders (mechanism in [memory-and-object-permanence](../foundations/memory-and-object-permanence.md)). Second: dense, everything-visible interfaces produce overwhelm, avoidance, and shutdown — the wall-of-tasks effect that triggers emotional flooding rather than action (see [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md); overwhelm-driven abandonment is a constant in ADHD app reviews [28][30]).

The resolution is that the debate is miscast. Users do not need *everything* visible; they need *the right things reliably surfaced* and a guarantee that hidden ≠ lost. Four complementary patterns:

| Pattern | What it does | Key requirement |
|---|---|---|
| **Progressive disclosure with guaranteed resurfacing** | Hide the long tail, but the *system* remembers and resurfaces it at the right time | Hiding is only safe because resurfacing is trustworthy; a "nothing is ever lost" promise must be visible and true |
| **User-controlled density** | Compact/comfortable/spacious views per screen | Density is a per-context preference, not a global personality trait; COGA Objective 8 ("Support Adaptation and Personalization") [1] |
| **One-thing-now mode** | Full-screen single task; everything else gone | The escape hatch from overwhelm and the entry ramp to action; pairs with timers and body-doubling (see [evidence-based-strategies](../strategies/evidence-based-strategies.md)) |
| **Ambient externalization** | Widgets, lock screen, always-visible today strip | Puts cues at the **point of performance** without requiring an app-open (see [executive-function](../foundations/executive-function.md)) |

COGA Objective 2 ("Help Users Find What They Need" — "Make it Easy to Find the Most Important Tasks and Features of the Site") is the standards-level statement of the same idea [1].

## 5. Visual hierarchy, color, typography, motion

**Hierarchy.** One primary action per screen, visually unmistakable. The **Von Restorff effect** — the distinctive item is the remembered one — only works if distinctiveness is scarce [11]. An interface where five things are highlighted has zero highlights. Position, size, and contrast should encode Klyr's actual opinion about what matters now.

**Color semantics without alarm fatigue.** Reserve a strict, small vocabulary: one color for "true deadline in jeopardy," used rarely enough to retain meaning. If every overdue chore glows red, red stops meaning anything (the habituation logic of §6 applies to pixels too) and the screen becomes a shame wall — which ADHD users avoid opening (see [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)). Urgency should read as *salience* (weight, position, a single accent), not as *alarm*. Never encode meaning in color alone (WCAG baseline; also a color-blindness requirement).

**Typography.** Dyslexia and ADHD co-occur at high rates — both affect 5–10% of the population with a bidirectional comorbidity around 25–40% [22][23] — so Klyr's text defaults must be dyslexia-friendly out of the box, per the British Dyslexia Association style guide [24]:

- Sans serif faces; body text 12–14 pt (~16–19 px) minimum; headings ≥20% larger.
- Line spacing ~1.5; generous letter and word spacing.
- Left-aligned, ragged right; no justified text.
- **No italics, underlines, or ALL CAPS for emphasis** — use bold.
- Sentence case, short lines, chunked content; user-adjustable text size respected app-wide.

The GOV.UK dyslexia poster adds one directly product-relevant rule: **don't rely on accurate spelling** — provide autocorrect and suggestions [5]. For Klyr: search and natural-language parsing must be typo-tolerant.

**Motion.** Motion is the highest-salience channel and therefore the most dangerous for distractible users: auto-playing media, looping ambience, and parallax are consistently listed among the worst offenders in ADHD-focused guidance [25][26]. Yet micro-moments of motion at completion are genuinely valuable (peak-end: end interactions on a small win [11]). Policy: motion only at user-triggered moments, short and stoppable; **`prefers-reduced-motion` honored everywhere** with equivalent non-animated feedback (WCAG 2.3.3 "Animation from Interactions" is AAA, but vestibular and attention costs make it table stakes for this audience) [2][3]; nothing autoplays; nothing loops; motion is never the sole signal.

## 6. Notification design: fighting habituation

Smartphone users receive tens of push notifications per day (industry estimates run 46–63) [15], and the psychology is unforgiving: repeated, identical, low-value alerts produce **habituation** — the response extinguishes while the stress does not. A recent mixed-methods study of university students found that *notification frequency itself did not significantly predict cognitive or emotional outcomes; alert fatigue and attention disruption did* [14]. Quality and timing, not count, are the levers. Complementarily, a field experiment by Fitz and colleagues found that **batching** notifications into periodic digests reduced stress and interruptions relative to as-they-arrive delivery [13]; secondary coverage of the same study reports that silencing notifications entirely backfired for some users via anticipatory checking (that detail not re-verified against the primary source in this pass).

For ADHD the stakes are doubled: reminders are load-bearing prosthetic memory (see [memory-and-object-permanence](../foundations/memory-and-object-permanence.md)), so Klyr cannot simply notify less — it must notify *better*. Klyr's notification stack:

1. **Two-class system.** Point-of-performance reminders ("leave now," "meds," a hard deadline) interrupt. Everything else batches into 1–3 daily digests at user-chosen times [13].
2. **Actionable from the shade.** Done / snooze / open — completing a task from the notification without app-launch. Every extra step is a lost action.
3. **Context triggers beat clock triggers**: location, calendar adjacency ("after your 3pm ends"), and device-state cues fire when action is possible, which is what point of performance means.
4. **Quiet hours on by default**, aligned to sleep — ADHD sleep problems are the norm, not the edge case (see [daily-life-impact](../daily-life/daily-life-impact.md)).
5. **Anti-habituation variation.** Vary copy and presentation of recurring reminders within a calm register; identical daily strings train blindness. (Extrapolated from habituation research; needs testing.)
6. **An escalation ladder, not a louder alarm.** Critical items escalate through channel and salience; routine items never do.
7. **Kill snooze-death.** "Snooze-death" (community/practitioner term): a reminder snoozed repeatedly until it is dismissed reflexively and the task silently dies. After N snoozes (~3), Klyr should change the question — "Reschedule properly, shrink it, or let it go?" — converting a nag into a triage decision, with "let it go" as a legitimate, shame-free option.
8. **A visible notification budget.** Klyr states why each notification fired ("you asked to be reminded when you got home") and lets users tune per-category volume in one screen — trust is the scarce resource notifications spend.

## 7. The friction asymmetry principle

A thought's lifetime in ADHD working memory is seconds; ADHD-productivity writing converges on capture needing to complete in roughly the time the thought survives — "under 3 seconds" is common community lore (heuristic, not a measured constant) [31]. Meanwhile, impulsive detours (opening a distracting app, deleting a project in frustration) benefit from a moment of resistance: a peer-reviewed field study of the "one sec" self-nudge app found that inserting a brief deliberation delay before a target app opens leads users to abandon a substantial share of opening attempts (PNAS 2023; recalled from prior knowledge — not re-verified against a source in this pass, so no numbers are quoted).

Hence the **friction asymmetry principle**: *make the desired rare-window behaviors (capturing, starting, finishing, returning) as close to zero-cost as possible; spend friction only on impulsive or destructive ones.*

- **Zero-friction side**: global quick-add from anywhere; home-screen/lock-screen widget; share-sheet capture; voice capture; natural-language parsing; and critically **capture without classification** — no project, date, or tag questions at capture time (that's the setup tax, §2).
- **Deliberate-friction side (all opt-in or reversible)**: leaving a user-started focus session gets a one-breath pause, not a lock; bulk-delete gets an undo window; a user-configured "speed bump" before self-identified distractions. Friction must never be applied to capture, task completion, or reopening the app after an absence.

## 8. Forgiveness patterns: nothing is ever lost

ADHD interaction is characterized by slips, mid-flow abandonment, and long lapses; the interface must make all three cost-free. COGA Objective 4 is the standards anchor: "Help Users Avoid Mistakes and Know How to Correct Them," with named patterns "Make it Easy to Undo Form Errors," "Avoid Data Loss and Timeouts," and "Provide Feedback" [1]. The GOV.UK anxiety poster adds: give users enough time, let them check answers before submitting, explain consequences and next steps [6].

Klyr's forgiveness contract:

- **Undo everywhere, confirmations almost nowhere.** Confirmation dialogs get habituated past (users click through on autopilot — same mechanism as §6); undo preserves flow and actually recovers mistakes. Reserve confirm dialogs for the truly irreversible.
- **Archive, not delete.** Deletion is soft, with a long-retention trash. "I deleted my whole system in a bad week" must be recoverable.
- **Autosave all input**; drafts persist across crashes, navigation, and time. No session timeouts that discard work [1].
- **Lapse amnesty.** After a week or month away, the return screen is a calm "welcome back, here's what matters now" — never a pile of red overdue badges or a dead streak (restart psychology in [habits-and-routines](../daily-life/habits-and-routines.md); streak ethics in [motivation-and-gamification](../strategies/motivation-and-gamification.md)).
- **Postel's law for input**: liberal in what Klyr accepts [11] — typos, fragments, "thing for mom thurs" — conservative and structured in what it stores.

## 9. Standards to build on: W3C COGA and GOV.UK

**W3C's "Making Content Usable for People with Cognitive and Learning Disabilities"** (COGA, Working Group Note, 2021) is the most complete standards-level treatment of cognitive accessibility — supplemental to WCAG and directly applicable to ADHD [1]. Its eight objectives, translated to Klyr:

| COGA objective | Klyr application |
|---|---|
| 1. Understand what things are and how to use them | One job per screen; familiar layout (Jakob's law); controls look like controls |
| 2. Help users find what they need | Most important task first; search everywhere; shallow hierarchy |
| 3. Clear and understandable content | Plain words, short text, summaries; no productivity jargon |
| 4. Avoid mistakes, easy correction | Undo-first design; forgiving forms; no data loss (§8) |
| 5. Help users focus | "Limit Interruptions" and "Make Short Critical Paths" — batched notifications, one-thing-now mode |
| 6. Don't rely on memory | Accessible authentication (no memorized codes); context shown, never recalled |
| 7. Provide help and support | Help findable in one step; "Provide Reminders" is a named COGA pattern — reminders are accessibility, not nagging |
| 8. Adaptation and personalization | Density controls, text controls, simplification mode |

**GOV.UK / Home Office accessibility posters** distill dos and don'ts for seven groups. Notably, **there is no dedicated ADHD poster** — ADHD expertise informed the set's creation, but designers must assemble ADHD guidance from the dyslexia, anxiety, and autistic-spectrum posters [4][7][8]. Most Klyr-relevant items: dyslexia — no large text blocks, left-align, consistent layout, "don't force users to remember things from previous pages — give reminders and prompts," don't rely on accurate spelling [5]; anxiety — enough time, clear consequences, check-before-submit, easy-to-find support [6]. The GDS principle that accessible design helps everyone holds; the gap in ADHD-specific official guidance is an opportunity for Klyr to publish its own.

## 10. Dark patterns: the ban list

ADHD users are disproportionately exposed to manipulative design: impulsivity converts urgency cues into purchases, prospective-memory failures convert free trials into months of unwanted charges (a core component of the community-termed **ADHD tax** — see [daily-life-impact](../daily-life/daily-life-impact.md)), and rejection sensitivity makes guilt copy land harder (see [emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)).

Regulators have moved. The FTC's 2022 staff report groups dark patterns into four families: design that misleads (including **fake countdown timers**), obscured subscription cancellation, hidden fees/buried terms, and manipulated privacy choices [16]. Enforcement is real: the FTC's case over Amazon Prime's internally named "**Iliad Flow**" — a four-page, six-click, fifteen-option cancellation gauntlet — ended in a reported $2.5 billion settlement in September 2025 [17][18]. The FTC's "click-to-cancel" rule was vacated on procedural grounds in 2025, but enforcement continues under FTC Act Section 5, and cancellation-parity remains the compliance expectation [19].

Klyr's hard bans, each both an ethical and a legal-risk position:

| Banned pattern | Why it specifically harms ADHD users |
|---|---|
| Fake urgency (countdowns, "only 2 left") | Weaponizes impulsivity and time blindness; destroys the trust Klyr's *real* deadline signals depend on |
| Guilt/confirmshame copy ("No thanks, I like being disorganized") | Feeds the shame spiral that drives app abandonment |
| **Streak hostage-taking** | Loss aversion (losses weigh roughly twice gains) makes broken streaks punishing; Duolingo's streak system — with paid streak freezes and documented user anxiety, controversial even internally — is the cautionary case [20][21]; ADHD lapses are guaranteed, so streak punishment is a scheduled shame event (red lines in [motivation-and-gamification](../strategies/motivation-and-gamification.md)) |
| Hard-to-cancel subscription, silent trial conversion | The ADHD tax, monetized; cancellation must be as easy as signup, with loud pre-conversion warnings and a genuinely useful free tier so lapsed payment ≠ data hostage |
| Notification spam for engagement metrics | Burns the alert-trust budget Klyr's prosthetic-memory function requires (§6) |
| Pay-to-recover progress or data | Converts executive-function failures into revenue; unacceptable |

The positive framing matters commercially: for an audience burned repeatedly by productivity tools and subscription traps, *demonstrated* safety — plain pricing, one-tap cancel, export anytime, lapse amnesty — is a differentiator competitors structurally resist copying.

## 11. Voice, natural language, and AI assist

**Capture channels.** Typing while structuring is a dual task; voice collapses it to one step, which is why voice and natural-language entry recur across well-reviewed ADHD tools ("pay rent Friday" auto-parsed to a dated task) [31]. Klyr should treat voice, free-text NLP, and share-sheet capture as first-class, with parsing that tolerates fragments and misspellings (§5, §8). Transcription/parse results must be shown and editable — silent misparses corrupt the external memory users are trusting Klyr to be.

**AI assists** most relevant to Klyr: automatic task breakdown (directly attacks initiation paralysis), auto-scheduling ("when will I actually do this?"), and inbox auto-triage (kills the setup tax). The design risk is **trust calibration**. Human–automation research frames the goal as *appropriate reliance*: avoiding both misuse (over-reliance) and disuse (under-reliance) [35]; studies of AI-assisted decisions show users over-weight confident, fluent outputs relative to actual reliability, and miscalibrated confidence degrades decisions [34]. For ADHD users the failure modes are sharper: over-trust means not noticing the AI scheduled the wrong thing (and missing something real); under-trust (often after one bad experience) means abandoning the assist entirely.

Calibration patterns for Klyr:

- **Suggestion boundaries**: AI output is visibly a *proposal* (the Grammarly underline pattern — mark, don't silently correct) until accepted [36].
- **Preview → one-tap accept → undo**: every automated action reviewable before, reversible after.
- **Brief rationale** ("scheduled Thursday because Friday is full"), and honest uncertainty — no confident hallucinated precision [34].
- **Predictability of the external memory**: Klyr never silently moves, merges, or rewrites user data; anything AI touched is labeled and revertible. Automation earns scope gradually, starting with low-stakes drafts.

## 12. The twelve UX laws of Klyr

Canonical laws [10][11][12], each with its Klyr-specific ruling:

| # | Law | Klyr ruling |
|---|---|---|
| 1 | **Hick's law** — decision time grows with number/complexity of choices | Never more than ~3 undifferentiated choices at once; everything ranked, grouped, defaulted |
| 2 | **Tesler's law** — complexity is conserved | Klyr absorbs complexity (parsing, sorting, scheduling); the user never pays the setup tax |
| 3 | **Jakob's law** — users expect familiar patterns | Novelty in *what Klyr does*, never in how buttons work; standard gestures only |
| 4 | **Miller's law** — working memory holds ~7±2 items (modern estimates are lower) | Chunk everything; "today" views cap visible items; the screen remembers so the user doesn't |
| 5 | **Fitts's law** — big, close targets are faster | Primary actions are large, thumb-reachable, and stationary; capture is the biggest target in the app |
| 6 | **Doherty threshold** — interaction pace <400 ms keeps engagement | Capture, open, and complete must feel instant; spinners are attention leaks |
| 7 | **Zeigarnik effect** — unfinished tasks occupy the mind | Klyr holds the open loops visibly so the user's head doesn't have to; closure moments are explicit |
| 8 | **Goal-gradient effect** — motivation rises near completion | Show progress and proximity ("2 of 3 done"), especially on broken-down tasks |
| 9 | **Peak-end rule** — experiences are judged by peak and end | Every session ends on a win (completion moment, calm summary) — never on a guilt screen |
| 10 | **Von Restorff effect** — the distinctive item is remembered | Exactly one highlighted thing per screen; salience is a strictly rationed budget |
| 11 | **Postel's law** — liberal in what you accept | Accept fragments, typos, voice mumbles; store clean structure; never reject user input |
| 12 | **Aesthetic–usability effect** — beautiful feels usable | Calm, uncluttered beauty buys patience and daily-open willingness — but never at the cost of load (§1) |

House principles that sit above these: friction asymmetry (§7), forgiveness by default (§8), visibility without clutter (§4).

## Design implications for Klyr

1. **Klyr must deliver value with zero configuration**: a usable capture-and-today experience on first open, no account/questionnaire gate before the first task is captured. Rationale: choice-overload moderators and first-session abandonment data both concentrate risk in setup (§2–3).
2. **Every screen gets one job and one visually primary action**; salience (color, motion, highlight) is a rationed budget with roughly one spend per screen. Rationale: Von Restorff dilution and extraneous-load costs (§1, §5).
3. **Capture must complete in seconds with zero required decisions** — global quick-add, widget, share sheet, voice, typo-tolerant NLP, classification deferred to Klyr. Rationale: working-memory volatility; setup tax as documented abandonment driver (§2, §7).
4. **Klyr must never lose or punish**: undo instead of confirmations, archive instead of delete, autosave, no data-losing timeouts, and a calm lapse-return experience with no overdue shame wall. Rationale: COGA Objective 4, anxiety-poster guidance, restart psychology (§8).
5. **Ship a one-thing-now focus mode and user-controlled density**, with progressive disclosure backed by guaranteed resurfacing ("hidden, not lost" made visible as a promise). Rationale: resolves the visibility-vs-overwhelm tension instead of picking a side (§4).
6. **Notifications: two classes only** — point-of-performance interrupts and batched digests — every one actionable from the shade, quiet hours on by default, with per-category volume control and "why this fired" transparency. Rationale: alert-fatigue evidence says relevance and timing, not count, determine harm; batching evidence supports digests (§6).
7. **Implement a snooze-death breaker**: after ~3 snoozes, convert the reminder into a triage choice (reschedule / shrink / let it go), with "let it go" shame-free. Rationale: habituation kills repeated identical alerts; a dead reminder is worse than a renegotiated one (§6). Needs user testing for the right N and tone.
8. **Typography defaults follow the BDA guide** (sans serif, ≥16 px, 1.5 line spacing, left-aligned, bold-not-italics) with app-wide user text controls. Rationale: 25–40% dyslexia comorbidity makes this a default, not a setting (§5).
9. **Honor `prefers-reduced-motion` everywhere; nothing autoplays or loops**; motion appears only at user-triggered moments and is never the sole signal. Rationale: motion is the top-salience distractor; WCAG 2.3.3/C39 (§5).
10. **Adopt COGA's eight objectives as an explicit design-review checklist** (the table in §9), and audit each release against them. Rationale: it is the closest thing to an official cognitive-accessibility standard, and no ADHD-specific official guidance exists to compete with it.
11. **Ban list, enforced in writing**: no fake urgency, no guilt/confirmshame copy, no streak punishment or paid streak repair, no engagement-bait notifications, no pay-to-recover data. Rationale: these patterns monetize the exact vulnerabilities Klyr exists to protect; regulatory direction (FTC) adds legal risk (§10).
12. **Cancellation must be as easy as signup** — in-app, ≤2 steps — with loud advance warning before any trial converts and full data export always available. Rationale: the ADHD tax on forgotten subscriptions is well documented; Amazon's Iliad Flow shows the downside case (§10). Tension: this measurably reduces short-term revenue retention; it is the price of the trust positioning.
13. **AI acts only through visible suggestion → preview → accept → undo**, with brief rationale and labeled provenance on anything it changed; automation scope expands only with earned trust. Rationale: trust-calibration research on over-reliance on fluent output; external-memory predictability is Klyr's core contract (§11).
14. **Instrument time-to-first-value and first-week return as primary UX metrics**, targeting first capture <60 s and first *completed* task in session one. Rationale: abandonment concentrates in the first sessions; for ADHD users the novelty window is the adoption window (§3).
15. **Speed is a feature**: capture, open, and complete interactions target sub-400 ms feedback. Rationale: Doherty threshold; any wait is an exit ramp for a distractible attention system (§12).

## Open questions

1. What is the *measured* capture-time threshold below which ADHD users reliably retain and record a thought — is the community "3-second rule" approximately right? No direct study found.
2. Does anti-habituation variation in reminder copy actually extend reminder effectiveness for ADHD users, or does inconsistency erode trust/recognition? Needs an A/B with lapse-rate outcomes.
3. Where is the optimal point on the density dial for the *default* (not customized) Today view — and does the right default differ between inattentive and combined presentations? COGA says personalize; the empty-default question remains.
4. Snooze-death breaker: at what snooze count, and with what wording, does triage feel supportive rather than confrontational? High RSD-sensitivity risk; needs qualitative testing.
5. Do deliberation-delay speed bumps (one-sec-style) retain effectiveness for ADHD users over months, or do users habituate/uninstall? The PNAS finding needs ADHD-specific replication.
6. Voice capture in public/work contexts: how much of the ADHD user base can actually use it day-to-day, and does embarrassment gate adoption? Determines how much to invest in silent equivalents (fast fuzzy text).
7. Can calibrated-trust UI (preview/accept/undo) stay low-friction enough that ADHD users don't just disable AI review — i.e., is there a version of "human in the loop" that survives an executive-function budget?

## Sources

1. [W3C — Making Content Usable for People with Cognitive and Learning Disabilities (Working Group Note)](https://www.w3.org/TR/coga-usable/) [clinical]
2. [W3C WAI — Technique C39: Using the CSS prefers-reduced-motion query to prevent motion](https://www.w3.org/WAI/WCAG21/Techniques/css/C39) [clinical]
3. [web.dev — Learn Accessibility: Animation and motion](https://web.dev/learn/accessibility/motion) [product]
4. [UK Home Office — Designing for accessibility (poster set index)](https://ukhomeoffice.github.io/accessibility-posters/) [clinical]
5. [UK Home Office — Designing for users with dyslexia (poster)](https://ukhomeoffice.github.io/accessibility-posters/dyslexia) [clinical]
6. [UK Home Office — Designing for users with anxiety (poster)](https://ukhomeoffice.github.io/accessibility-posters/anxiety) [clinical]
7. [Home Office Digital — Illustrating the importance of accessible design](https://hodigital.blog.gov.uk/2018/05/17/illustrating-the-importance-of-accessible-design/) [clinical]
8. [GOV.UK Accessibility blog — Dos and don'ts on designing for accessibility](https://accessibility.blog.gov.uk/2016/09/02/dos-and-donts-on-designing-for-accessibility/) [clinical]
9. [Chernev, Böckenholt & Goodman (2015) — Choice overload: A conceptual review and meta-analysis, Journal of Consumer Psychology](https://myscp.onlinelibrary.wiley.com/doi/10.1016/j.jcps.2014.08.002) [research]
10. [Interaction Design Foundation — The Hick-Hyman Law: An Argument Against Complexity in User Interface Design](https://ixdf.org/literature/article/the-hick-hyman-law-an-argument-against-complexity-in-user-interface-design) [product]
11. [Laws of UX (Jon Yablonski) — collected principles](https://lawsofux.com/) [product]
12. [Nielsen Norman Group — Progressive Disclosure](https://www.nngroup.com/articles/progressive-disclosure/) [product]
13. [Fitz et al. (2019) — Batching smartphone notifications can improve well-being, Computers in Human Behavior](https://www.sciencedirect.com/science/article/abs/pii/S0747563219302596) [research]
14. [Alert Fatigue and Smartphone Notifications: A Mixed-methods Study of Attention Disruption and Mental Well-being among University Students — Asian Journal of Education and Social Studies](https://journalajess.com/index.php/AJESS/article/view/2743) [research]
15. [Courier — How to Reduce Notification Fatigue: 7 Proven Product Strategies](https://www.courier.com/blog/how-to-reduce-notification-fatigue-7-proven-product-strategies-for-saas) [product]
16. [FTC — Report Shows Rise in Sophisticated Dark Patterns Designed to Trick and Trap Consumers (2022)](https://www.ftc.gov/news-events/news/press-releases/2022/09/ftc-report-shows-rise-sophisticated-dark-patterns-designed-trick-trap-consumers) [clinical]
17. [WilmerHale — FTC Targets "Dark Patterns" in Actions Against Amazon and Publishers Clearing House](https://www.wilmerhale.com/en/insights/client-alerts/20230814-ftc-targets-dark-patterns-in-actions-against-amazon-and-publishers-clearing-house) [product]
18. [Berkeley Technology Law Journal — Trapped By Design: How Dark Patterns Manipulate Your Choices](https://btlj.org/2025/11/trapped-by-design-how-dark-patterns-manipulate-your-choices-and-the-regulators-fighting-back/) [research]
19. [Pandectes — Dark Patterns in 2026: What the FTC's New Rules Mean](https://pandectes.io/blog/dark-patterns-in-2026-what-the-ftcs-new-rules-mean/) [product]
20. [Just Another PM — The Psychology Behind Duolingo's Streak Feature](https://www.justanotherpm.com/blog/the-psychology-behind-duolingos-streak-feature) [product]
21. [Screenwise — Duolingo Streaks and the 'Loss Aversion' Trap: A Parent's Guide](https://screenwiseapp.com/guides/duolingo-streaks-and-anxiety-in-kids) [community]
22. [McGrath & Stoodley (2019) — Are there shared neural correlates between dyslexia and ADHD? A meta-analysis, Journal of Neurodevelopmental Disorders](https://link.springer.com/article/10.1186/s11689-019-9287-8) [research]
23. [ADDitude — The Dyslexia-ADHD Overlap: Why Evaluators Confuse the Conditions](https://www.additudemag.com/dyslexia-evaluation-adhd-comorbidity-overlap/) [clinical]
24. [British Dyslexia Association — Dyslexia Style Guide 2023](https://cdn.bdadyslexia.org.uk/uploads/documents/Advice/style-guide/BDA-Style-Guide-2023.pdf?v=1680514568) [clinical]
25. [Stéphanie Walter — Neurodiversity and UX: Essential Resources for Cognitive Accessibility](https://stephaniewalter.design/blog/neurodiversity-and-ux-essential-resources-for-cognitive-accessibility/) [community]
26. [Welcoming Web — How to design for ADHD and neurodiversity in UX](https://welcomingweb.com/learn/designing-for-neurodiversity-adhd-ux) [community]
27. [Carlo Ciccarelli — Software accessibility for users with attention deficit disorder](https://www.carlociccarelli.com/post/software-accessibility-for-users-with-attention-deficit-disorder) [community]
28. [AFFiNE — Notion Templates For ADHD: Why Your Brain Keeps Abandoning Systems](https://affine.pro/blog/notion-templates-for-adhd) [product]
29. [MindStash — Why Your ADHD Brain Hates Notion](https://www.mindstash.app/blogs/why-your-adhd-brain-hates-notion-and-what-actually-works-instead) [product]
30. [Ultrathink — Notion alternative: how ADHD made me ditch Notion](https://tryultrathink.com/blog/notion-alternative) [product]
31. [Saner.AI — 7 Best ADHD Task Management Apps (Tested & Reviewed)](https://blog.saner.ai/best-adhd-task-management-apps/) [product]
32. [UserGuiding — 100+ User Onboarding Statistics (2026)](https://userguiding.com/blog/user-onboarding-statistics) [product]
33. [Zigpoll — Optimizing app onboarding to reduce first-week drop-off](https://www.zigpoll.com/content/how-can-we-optimize-the-app's-onboarding-process-to-reduce-user-dropoff-rates-within-the-first-week-of-installation) [product]
34. [Understanding the Effects of Miscalibrated AI Confidence on User Trust, Reliance, and Decision Efficacy (arXiv)](https://arxiv.org/pdf/2402.07632) [research]
35. [Okamura & Yamada — Adaptive trust calibration for human-AI collaboration (PLOS ONE, via PMC)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7034851/) [research]
36. [UXmatters — UX Research Insights: Balancing AI Automation and Human Oversight](https://www.uxmatters.com/mt/archives/2025/12/ux-research-insights-balancing-ai-automation-and-human-oversight-in-it-operations.php) [product]
37. [SundaySky — 50 customer onboarding statistics (2026)](https://sundaysky.com/blog/customer-onboarding-statistics/) [product]
