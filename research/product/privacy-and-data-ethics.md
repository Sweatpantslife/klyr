---
title: "Privacy and Data Ethics for Sensitive ADHD Data"
area: product
file: research/product/privacy-and-data-ethics.md
tags: [privacy, health-data, gdpr, ftc-enforcement, data-retention, consent, encryption, trust]
related:
  - research/product/ux-design-for-adhd.md
  - research/product/app-landscape.md
  - research/product/when-to-back-off.md
  - research/foundations/time-perception.md
  - research/daily-life/habits-and-routines.md
sources: 21
updated: 2026-07-25
summary: >
  When Klyr's task, mood, cycle, and medication-adjacent data legally becomes health data
  (GDPR Art. 9, Washington My Health My Data, FTC HBNR), what the BetterHelp/GoodRx/Cerebral
  enforcement wave teaches, data classification and retention principles, forgetting as a
  shame-reduction feature, consent UX for impulsive users, and privacy as positioning.
  Read before designing any data model, analytics plan, consent flow, or marketing claim.
---

# Privacy and Data Ethics for Sensitive ADHD Data

## TL;DR

- **Klyr's data is health data long before Klyr thinks of itself as a health app.** The CJEU has held that even ordering non-prescription pharmacy products online creates "data concerning health" under GDPR Article 9 [4]; Washington's My Health My Data Act (MHMD) explicitly covers mental-health information, medication use, and *inferences drawn from non-health data* [6]. Mood logs, cycle-aware modes, "energy windows," and even the fact of having an account in an ADHD-branded app sit inside this perimeter.
- **HIPAA will not apply to Klyr — and that gap is exactly what the FTC now polices.** The 2024 Health Breach Notification Rule covers health apps outside HIPAA and defines "breach" to include *unauthorized disclosure*, not just hacking, with 60-day notification duties [7].
- **The enforcement wave punished the marketing stack, not hackers**: GoodRx ($1.5M, medication lists uploaded to Facebook) [8], BetterHelp ($7.8M refunds, intake answers to Facebook/Snapchat) [9], Premom ($200K, cycle data to China-based analytics firms) [10], Cerebral ($7M, ~3.2M mental-health/ADHD patients' data to LinkedIn/Snapchat/TikTok via pixels) [11], Flo (100M-user period tracker sharing "app events" with Facebook and Google) [12]. Every case began with ordinary ad/analytics SDKs plus a privacy promise the product didn't keep.
- **The category's baseline is rotten and users know it**: 92% of top depression/smoking-cessation apps transmitted data to third parties, only ~59% disclosed it [16]; Mozilla gave 28 of 32 mental-health apps its *Privacy Not Included* warning label and called the category "exceptionally creepy" [14][15].
- **ADHD-specific disclosure fear is real but documented indirectly**: workplace disclosure risk is a top strain in [daily-life-impact](../daily-life/daily-life-impact.md); stimulant prescriptions are controlled substances entangled with law-enforcement attention (Cerebral's DOJ probe) [13]; the post-Dobbs period-tracker panic (Flo shipping "Anonymous Mode" [20]) shows how fast app data becomes disclosure risk. No peer-reviewed study of ADHD users' app-data fears surfaced in this pass — mark as inference.
- **Privacy is a trust floor, not an engagement driver**: in a small mHealth abandonment survey, privacy didn't rank among top quit reasons (novelty loss did) [21] — but privacy failure is unrecoverable and headline-generating. Sell warmth; enforce privacy in architecture.
- **Local-first/E2E is a proven niche demand** (Lunatask markets "not even us" encryption directly at ADHD users [19]), but full E2E collides with Klyr's never-silently-lose-anything trust contract ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md)): ADHDers lose passwords, and unrecoverable data is its own betrayal. Resolution: tiered sensitivity, E2E for the health-adjacent layer, recoverable encryption for the task graph.
- **A permanent failure archive is a shame liability as well as a legal one.** GDPR's storage-limitation principle requires retention limits anyway [2]; the FTC now writes retention schedules into consent orders [9][10]. Age out behavioral exhaust by default; make "forget this period" a first-class amnesty feature — user-controlled forgetting is not the same as silently losing data.
- **Consent must survive impulsivity without exploiting it**: 56% of Americans routinely click "agree" without reading [17]; GDPR Article 9 demands *explicit* consent for specified purposes [1]; the EDPB treats deceptive consent design as a data-protection violation [18]. Just-in-time, per-category, default-off, revocable-in-one-tap consent is the only defensible pattern.

## 1. Why this doc exists

The corpus keeps touching a wire and pulling back. [time-perception](../foundations/time-perception.md) designs "energy windows" *specifically so Klyr never stores medication data* (implication #10). [habits-and-routines](../daily-life/habits-and-routines.md) proposes cycle-aware modes, then leaves "supportive vs. surveilled" as an open question (implication #12). [when-to-back-off](./when-to-back-off.md) warns that inferring user state "feels like surveillance." This doc owns the wire: what the law actually says, what enforcement actually punished, and which data-handling principles turn privacy from a compliance chore into product character.

**Klyr's planned surface generates health-adjacent data by design**: free-text tasks that will contain "refill Vyvanse" and "therapy @ 3"; completion/deferral rhythms that mirror symptom severity; optional mood logs; optional cycle-aware pacing; energy windows shaped like stimulant coverage; and a longitudinal record of every plan that didn't happen. None of this requires Klyr to *claim* to be a health product. Sensitivity follows from what the data reveals, not from what the app calls itself.

## 2. When Klyr's data legally becomes health data

### 2.1 GDPR (EU/UK): Article 9 and the breadth of "data concerning health"

**Article 9(1)** prohibits processing of special categories — including "data concerning health" — unless an exception applies; for a consumer app the only realistic gate is **9(2)(a) explicit consent** "for one or more specified purposes" [1].

The decisive question is how far "data concerning health" stretches, and the Court of Justice of the EU (CJEU) has answered: far. In ***Lindenapotheke*** (C-21/23, 2024), the Court held that when a pharmacy sells *pharmacy-only but non-prescription* products online, the customer's name, delivery address, and product details "constitute[] data concerning health" under Article 9(1) — "even where the sale of those medicinal products does not require a prescription," and regardless of whether the products are for the purchaser or someone else [4]. Earlier, in C-184/20, the Court treated name-specific data about a spouse as "liable to reveal" sexual orientation and therefore a serious interference with privacy rights; the ruling is widely read as bringing indirectly revealing data under Article 9, though the judgment's operative text could not be retrieved in this pass [5].

The transfer to Klyr is uncomfortable but direct. If buying an over-the-counter product is health data because of what it *implies*, then a mood log in an ADHD-branded organizer is health data without argument; an "energy windows" feature marketed to ADHD users plausibly is too; and the mere existence of an account in an app "designed for ADHD brains" is at minimum a strong health inference. Renaming medication windows to "energy windows" (time-perception #10) removes *stored diagnosis-and-dose facts* — a genuine and worthwhile minimization — but it does **not** move the surrounding data outside Article 9's likely reach. Klyr should assume Article 9 applies to its sensitive tier and build the explicit-consent machinery, rather than litigating the boundary with its users' data.

Two adjacent GDPR principles do real design work here: **data minimization** ("adequate, relevant and limited to what is necessary") and **storage limitation** (kept identifiable "no longer than is necessary") — Article 5(1)(c) and (e) [2] — plus the **right to erasure** when data is no longer necessary or consent is withdrawn (Article 17) [3]. Section 6 turns these into features.

### 2.2 United States: the post-HIPAA patchwork

A common user assumption — and a trap — is that "health app = HIPAA." **HIPAA covers providers, insurers, and their business associates; a direct-to-consumer organizer is none of these.** The regime that actually applies:

- **FTC Health Breach Notification Rule (HBNR)**, finalized 2024: covers vendors of personal health records and "health apps and similar technologies" outside HIPAA. A breach is the "unauthorized acquisition of identifiable health information" arising from a security incident **or an unauthorized disclosure** — sharing with an ad platform without authorization counts, which is how GoodRx was charged. Notification to users, the FTC, and sometimes media is due within 60 days, and notices must name the third parties that got the data [7][8].
- **Washington's My Health My Data Act (MHMD)**, in force since 2024 (small businesses June 30, 2024): covers "consumer health data" including mental health and "use and purchase of prescribed medication," and — critically — **inferences drawn even from non-health data** (the AG's illustration is a retailer's "pregnancy prediction score" from purchase patterns). It applies to any business targeting Washington consumers, requires separate valid authorization before *selling* health data and consent for collection/sharing beyond necessity, mandates a distinct health-data privacy policy linked from the homepage, and — uniquely — carries a **private right of action** via Washington's Consumer Protection Act [6]. Similar consumer-health-privacy laws have followed in other states (e.g., Nevada; not re-verified in this pass).
- **FTC Act §5 deception**: every enforcement case below rests partly on the gap between privacy promises and practice. A privacy policy is a set of enforceable product claims.

Practical consequence: because MHMD reaches any US-facing product and GDPR reaches any EU-facing one, **"build to the strictest standard once" is cheaper than geo-fencing compliance**, and the strictest standard is roughly: explicit, purpose-specific, revocable consent for anything health-adjacent; no sharing for advertising at all; minimization and scheduled deletion by default.

### 2.3 Klyr data classification

| Data Klyr might hold | What it can reveal | Legal status (realistic reading) | Default posture |
|---|---|---|---|
| Task/note free text | Medications, diagnoses, appointments, finances | Health data *when it reveals health* — and free text will | Encrypt at rest; no server-side mining by default; sensitive-string awareness in any AI pipeline |
| Completion/deferral timestamps, usage rhythms | Symptom severity, episodes, crashes (see [when-to-back-off](./when-to-back-off.md)) | "Inferences" under MHMD once used to infer state | Compute on device where possible; aggregate; age out (§6) |
| Energy windows (neutral labels) | Stimulant coverage pattern by correlation | Borderline; inference-rich | Keep neutral naming (per time-perception #10) **and** treat as sensitive tier anyway |
| Mood logs | Mental health, squarely | GDPR Art. 9; MHMD core | Opt-in, sensitive tier, local-first/E2E preferred |
| Cycle-aware mode | Reproductive health | Art. 9; MHMD core; post-Dobbs precedent | Opt-in, local-only by default, one-tap off **and purge** |
| Failure/restart history | Longitudinal struggle record | Inference-rich; also a shame artifact | Retention-limited by design (§6) |
| Account data + "ADHD app" membership | Probable diagnosis, by *Lindenapotheke* logic | Likely health inference | Collect "just an email" (Lunatask's posture [19]); never share or sell user lists; no ad-network SDKs |

## 3. What enforcement teaches: anatomy of the scandal pattern

| Case | Year | What happened | Outcome | Lesson for Klyr |
|---|---|---|---|---|
| **Flo** (period tracker, 100M+ users) | 2021 | Shared pregnancy status etc. as "app events" with Facebook/Google analytics, AppsFlyer, Flurry despite promises; exposed by journalists | Consent + notification obligations; third parties ordered to destroy data [12] | "Analytics" is disclosure; promises bind |
| **GoodRx** | 2023 | Compiled lists of users buying specific medications; uploaded to Facebook for ad targeting; shared with Google, Criteo, Branch, Twilio | **First-ever HBNR action**; $1.5M penalty; permanent ban on ad disclosure of health data [8] | Medication-adjacent data + ad stack = per-se disaster |
| **BetterHelp** | 2023 | Intake questionnaire answers, emails, IPs to Facebook, Snapchat, Criteo, Pinterest after promising confidentiality during signup | $7.8M for **consumer refunds**; ban; mandated retention schedule and third-party deletion [9] | Sign-up-flow promises are the most binding copy in the product |
| **Premom** (ovulation tracker) | 2023 | Health data to AppsFlyer/Google; social identifiers, precise geolocation, device data to China-based Umeng and Jiguang | HBNR violation; $100K FTC + $100K to states; retention limits imposed [10] | Your SDKs' data flows are your liability, wherever they go |
| **Cerebral** (telehealth incl. ADHD care) | 2024 | Tracking pixels sent names, medical and prescription histories, insurance details of ~3.2M consumers to LinkedIn, Snapchat, TikTok; plus "cancel anytime" claims hiding a multi-day cancellation maze (an easier cancel button was removed when cancellations rose) | ~$7M ($5.1M refunds + civil penalty largely suspended); ban on marketing use of health data [11] | Privacy abuse and dark-pattern retention are one enforcement package; ADHD patients were the population harmed |

Structural readings:

1. **The breach vector is the growth stack.** No case above involved hackers. Pixels, SDKs, and "custom audiences" did it all. An ADHD organizer with Meta/TikTok pixels in its funnel is running the exact configuration that produced every one of these orders.
2. **Deception, not collection, triggers liability.** "We never share your data with advertisers" followed by Google Analytics is the pattern the FTC punished. Klyr's privacy copy must be written *from* the architecture, not aspirationally.
3. **Regulators now impose what good products should have shipped**: affirmative express consent, retention schedules, third-party deletion, easy cancellation. Building these first is cheaper than having them ordered.
4. **The category's reputation is pre-damaged.** Huckvale et al. (JAMA Netw Open, 2019) found 33 of 36 top depression/smoking apps (92%) transmitted data to third parties; 29/36 sent data to Google or Facebook for ads/analytics; only 17 of those 29 (59%) disclosed it [16]. Mozilla's *Privacy Not Included* reviews (32 apps, 255 research hours) slapped warning labels on 28 of 32 mental-health apps, found 25 failing minimum security standards, named BetterHelp, Talkspace, Woebot and others, and concluded the majority "track, share, and capitalize on users' most intimate personal thoughts" [14]; its 2023 re-review ("Some are better! Many are worse.") found roughly 17 of 27 re-reviewed apps unimproved or worse [15]. Klyr will be shelved next to these apps and inherits their suspicion by default.

## 4. Do ADHD users specifically fear disclosure?

**Directly documented:** disclosure fear offline. [daily-life-impact](../daily-life/daily-life-impact.md) records workplace disclosure risk as a top strain — *"every mistake I made would be associated with my ADHD."* ADHD adds two sharpeners general mental-health stigma lacks: (a) **stimulant medication is a controlled substance**, culturally entangled with abuse narratives and literal law-enforcement attention — Cerebral spent 2022–2024 under a DOJ controlled-substances investigation it settled for $3.65M [13]; (b) ADHD disclosure is routinely read as a *competence* claim ("excuse-making"), which for a population primed by [RSD and shame](../foundations/emotional-regulation-and-rsd.md) makes exposure feel character-level, not medical.

**Documented by natural experiment:** the post-Dobbs period-tracker panic. When reproductive-health data became legally dangerous overnight in parts of the US, the market response was immediate — Flo shipped an "Anonymous Mode" [20], and Washington legislated MHMD. Cycle data in Klyr's cycle-aware mode is *that* data class; Klyr inherits the precedent whether or not it thinks of itself as a period tracker.

**Documented at population level:** Pew (2023) finds 73% of Americans feel they lack control over company data collection, 67% understand little or nothing about what companies do with it, and 72% want more regulation [17].

**Not directly documented:** a peer-reviewed measure of ADHD users' fear about *app* data specifically. No such study surfaced in this pass; treat "ADHD users fear app-data disclosure" as a well-supported inference (offline disclosure fear + category betrayal record + demonstrated market demand for private alternatives), not an established finding.

**A nuance that shapes strategy:** in a small mHealth abandonment survey (n=209, 2020–21), the top quit reasons were loss of interest (31.6%), app-shopping (21.5%), and missing features (18.7%) — privacy didn't make the list [21]. Privacy is best modeled as a **trust floor with catastrophic failure mode**: it will not drive daily engagement, and most users will never read the policy (56% click "agree" without reading [17]) — but a single credible story of Klyr leaking "their mess" to advertisers ends the relationship for exactly the users who most needed a shame-free tool, and puts Klyr in the Mozilla/FTC headline machine. You cannot win on privacy alone; you can absolutely die on it.

## 5. Architecture: local-first, E2E, and the never-lose-anything guarantee

**Lunatask is the market signal**: an explicitly ADHD-marketed task manager + habit/mood tracker whose pitch is end-to-end encryption — "no one has access to your tasks, notes, and other sensitive data … not even us," "we don't sell your data," "no in-app product analytics or tracking," "we ask just for the email address" [19] (see [app-landscape](./app-landscape.md) for its market position). Demand exists, and it exists *inside* Klyr's exact niche.

But full E2E collides with two corpus commitments:

1. **"Klyr must never silently lose anything"** ([memory-and-object-permanence](../foundations/memory-and-object-permanence.md), implication #2). E2E without escrow means a forgotten master password destroys the external memory the user was told to trust. For a population defined partly by losing credentials (69% of Americans already feel overwhelmed by passwords [17]; ADHD working memory makes it worse), "your data is unrecoverable by design" is not a privacy feature — it's a scheduled betrayal, an [ADHD tax](../daily-life/daily-life-impact.md) collected at the worst moment.
2. **Server-side intelligence.** Auto-parsing, resurfacing, cross-device search, and the AI assists in [ai-assistance-for-adhd](./ai-assistance-for-adhd.md) are cheapest server-side; blanket E2E forces them on-device or kills them.

The resolution is **tiered, not total**:

- **Task graph tier (default):** encrypted in transit and at rest, provider-side keys, full recovery, sync that never loses data. Hard commitments at this tier are *organizational*: no third-party ad/analytics SDKs, no sale or sharing, subpoena-resistance via minimization rather than cryptography.
- **Sensitive tier (opt-in fields — mood, cycle, energy windows, any "health" field):** local-first by default; if synced, E2E-encrypted per-field with an explicitly user-held recovery key, or not synced at all. On-device processing for any inference over this tier (a direction [when-to-back-off](./when-to-back-off.md) independently requires for its back-off triggers).
- **Truth-in-labeling rule:** never say "we can't see it" unless cryptography makes it true; never say "encrypted" to imply E2E when it means TLS. Overclaiming encryption is the GoodRx/BetterHelp deception pattern wearing a security costume [8][9].

## 6. Retention and the right to be forgotten as shame reduction

Is a permanent failure archive harmful? The corpus answer is yes-when-visible: the documented abandonment lifecycle turns the app into "evidence of failure" that hurts to open ([app-landscape](./app-landscape.md)); shame is the engine of the Wall of Awful ([emotional-regulation-and-rsd](../foundations/emotional-regulation-and-rsd.md)); and restart psychology depends on the fresh start actually feeling fresh ([habits-and-routines](../daily-life/habits-and-routines.md)). A complete, resurfaceable ledger of every deferred task and broken routine is a Wall-of-Awful construction kit.

Law and therapy point the same direction, which is rare and should be exploited:

- **Storage limitation is already the law** — data kept identifiable "no longer than is necessary" [2] — and the FTC now writes retention schedules directly into consent orders [9][10]. A "keep everything forever" analytics posture is a liability even before it's a cruelty.
- **Erasure is already a right** when data is no longer necessary or consent is withdrawn [3]. MHMD adds its own deletion rights with a private right of action behind them [6].

The design move is to split what the memory doc's trust contract protects from what it doesn't:

- **Content** (tasks, notes, projects — the user's externalized mind): keep by default, forever, user-deletable. This is what "never silently lose anything" protects.
- **Behavioral exhaust** (deferral counts, abandoned streaks, completion-rate history, lapse timelines): Klyr's *own* observations, not the user's memories. Aggregate what the product genuinely needs ("this task has bounced 12 times → offer to shrink it"), then **age out the raw ledger on a published schedule**. No user ever asked an organizer to remember every failure verbatim.
- **Amnesty as a feature:** "Forget this month," "clear my slate, keep my projects," a lapse-return flow that archives rather than displays debt (the [app-landscape](./app-landscape.md) re-entry requirement, made literal in the data model). Deletion must be honest — real erasure propagating to backups within a stated window — because a fake fresh start discovered is worse than none.
- **The reconciliation rule:** *user-controlled forgetting is a feature; system-controlled losing is a betrayal.* Everything Klyr forgets is either (a) requested by the user or (b) governed by a visible, plain-language retention policy. Nothing disappears silently; nothing shameful persists pointlessly.

## 7. Consent UX that respects impulsivity

The baseline: 56% of Americans frequently click "agree" without reading [17], and ADHD's now-bias and initiation friction (see [time-perception](../foundations/time-perception.md)) make onboarding the *worst* moment for meaningful consent — the user is impatient to reach value, and every gate is an abandonment risk ([ux-design-for-adhd](./ux-design-for-adhd.md) owns onboarding mechanics and the dark-pattern ban list).

The legal bar runs opposite to the temptation: Article 9 demands **explicit consent for specified purposes** [1]; MHMD requires consent separate from general ToS and distinct authorization for anything resembling sale [6]; and the EDPB has dedicated guidelines (03/2022, v2.0 2023) on deceptive design patterns that undermine data-protection principles — consent extracted through manipulation is not valid consent [18]. Cerebral's order shows the FTC treating consent/cancellation asymmetry as core wrongdoing [11].

Principles that satisfy both the law and the user:

1. **Just-in-time, not up-front.** Ask for mood-log consent the first time the user opens mood logging, with a two-sentence plain-language explanation of what's stored, where, and for how long. Onboarding asks for nothing sensitive (matching ux-design's "configuration harvested from use").
2. **Per-category, default-off, independently revocable.** Mood, cycle, energy windows, and any AI processing of sensitive fields are separate switches; withdrawing one never degrades core task management.
3. **Symmetry as a hard rule.** Revoking consent, downgrading tiers, deleting data, and canceling subscriptions each take no more steps than granting/subscribing did. (The Cerebral removed-cancel-button move is the canonical anti-pattern [11].)
4. **Impulsivity-aware, not impulsivity-exploiting.** A user racing "agree-agree-agree" toward value must land in the *most* protective state, not the least. That inverts the industry default, where speed harvests maximal permissions — precisely the deceptive-design territory the EDPB polices [18].
5. **Consent that stays informed.** For sensitive tiers, an occasional low-key "you're still sharing mood data — still okay?" respects the reality that a choice made once, impulsively, two years ago is not ongoing consent. Frequency must respect notification-fatigue limits (ux-design).

## 8. Privacy as positioning

The evidence assembled here supports a specific stance: **privacy as character, not as feature list.** The category is pre-disgraced (Mozilla's "exceptionally creepy" [14], five FTC health-app orders since 2021), users are fatalistic rather than activated (73% feel no control [17]), and one ADHD-native competitor already wins a niche on "not even us" [19]. Klyr's positioning opportunity is emotional, matching its product thesis: *this is the one place your mess is safe* — no employer, no advertiser, no algorithm grading you. Klyr sells safety-to-be-unfinished; data safety is the same promise at the infrastructure layer, and hedging on one corrodes the other.

Claims Klyr can make **only if architecture enforces them**: no ad or third-party analytics SDKs; we never sell or share your data; sensitive data can stay on your device; export everything, anytime, in open formats (portability also answers the data-lock-in abandonment theme in [app-landscape](./app-landscape.md)); we delete on schedule and on request, for real. Each claim is a future FTC exhibit — GoodRx and BetterHelp were prosecuted on the gap between copy and conduct [8][9]. The privacy policy should be treated as product copy, written by the same voice, and audited against actual data flows every release.

## Design implications for Klyr

1. **Classify task, mood, cycle, energy-window, and behavioral data as health data now, by default** (per the §2.3 table), because CJEU breadth [4] and MHMD's inference rule [6] will classify it that way regardless of Klyr's self-image. Retrofitting Article 9 machinery after launch is the expensive order.
2. **Klyr must never embed third-party advertising or analytics SDKs/pixels in app or web funnel.** Every FTC health-app order (GoodRx, BetterHelp, Premom, Cerebral, Flo) began exactly there [8][9][10][11][12]. First-party, privacy-reviewed telemetry only — and minimal.
3. **Build a two-tier data architecture**: recoverable encrypted-cloud for the task graph (the never-lose-anything tier), local-first/E2E-optional for sensitive fields (mood, cycle, energy windows), with per-field encryption boundaries designed into the schema from day one. Rationale: §5's collision between Lunatask-style demand [19] and the memory doc's trust contract.
4. **Keep energy windows neutral and never ask why** (upholds time-perception #10) — but store and process them in the sensitive tier anyway, because correlated timing data is inference-rich and MHMD covers inferences [6].
5. **Cycle-aware mode ships opt-in, local-only by default, with one-tap disable-and-purge** (answers habits-and-routines #12's open question). The post-Dobbs record — Flo's Anonymous Mode [20], MHMD itself — shows this data class can become legally radioactive overnight.
6. **Publish a plain-language retention schedule inside the app, and age out raw behavioral exhaust (deferral logs, lapse ledgers, streak history) by default** while keeping user content forever. Rationale: storage limitation [2], FTC-ordered retention schedules [9][10], and the shame-artifact mechanism (§6).
7. **Ship "amnesty" as a first-class flow** — "forget this month," "clear my slate, keep my projects" — with honest, propagating deletion. Right-to-erasure [3] reframed as the restart mechanic the abandonment lifecycle demands ([app-landscape](./app-landscape.md)).
8. **Consent is just-in-time, per-category, default-off, and never gates core task management.** Onboarding collects nothing sensitive. Rationale: explicit-consent standards [1][6], EDPB deceptive-design guidance [18], and the 56%-click-agree reality [17].
9. **Enforce grant/revoke symmetry as a release-blocking rule**: revoking any consent, deleting any data, or canceling payment takes ≤ the steps of the corresponding grant. Cerebral's cancellation maze is the named anti-pattern [11]; [ux-design-for-adhd](./ux-design-for-adhd.md) owns the broader ban list.
10. **Compute state inferences on-device wherever feasible, and never persist them as a server-side "user mental-state" profile.** Deferral-pattern inferences are MHMD consumer health data (§2.2) and the trust risk [when-to-back-off](./when-to-back-off.md) documents; sensitive fields stay out of any model-training pipeline, stated explicitly ([ai-assistance-for-adhd](./ai-assistance-for-adhd.md)).
11. **One-tap full export in open formats, forever free.** Portability is a trust signal, an anti-lock-in answer to a documented abandonment driver, and a GDPR obligation anyway.
12. **Copy discipline: the product may only claim what the architecture enforces**, with a per-release audit of privacy copy against actual data flows. "We can't see it" requires real E2E; "we don't share" must survive an SDK inventory. The enforcement record is a record of broken sentences [8][9][12].
13. **Build to the strictest standard once** (GDPR explicit consent + MHMD authorization + HBNR breach machinery) rather than geo-fencing; MHMD alone already reaches any US-facing product [6], and its private right of action means plaintiffs, not just regulators.
14. **Design account recovery for people who lose things**: recovery paths for the default tier, and for the E2E tier an explicit, ADHD-honest tradeoff screen ("if you lose this key, this data is gone — here are three places to keep it") plus printable/escrowable recovery codes. Privacy architecture must never manufacture the data loss the memory doc forbids.
15. **Pre-write the breach playbook**: HBNR's 60-day, name-the-third-parties notification duty [7] is not the moment to improvise. A tested notify-fast posture is also the only reputation-preserving move in a category where cover-ups made the headlines worse.

**Tensions to hold honestly:** maximal privacy (E2E everything) vs. never-lose-anything and server-side intelligence — resolved by tiering, but the boundary needs user testing (§Open questions). Retention limits vs. "never silently lose" — resolved by the content/exhaust split and visible policy, but the split's edges (are notes on a failed project "content" or "failure record"?) will need judgment calls. Privacy marketing vs. fear-mongering — leading with threat scenarios would import anxiety into a product whose promise is calm; privacy should be discoverable character, not a scare pitch.

## Open questions

- **Would ADHD users choose E2E over recoverability if the tradeoff were framed honestly?** No data exists. Needs prototype testing with real users — including whether the recovery-key ritual itself is an abandonment cliff.
- **Does seeing one's own historical failure data harm or help?** The shame mechanism predicts harm; some users report wanting honest mirrors. What retention default (30/90/365 days) for behavioral exhaust feels supportive rather than either surveillant or gaslighting? Pair with habits-and-routines' restart-nudge question.
- **Is an ADHD-branded account itself Article 9 / MHMD data?** *Lindenapotheke* logic says plausibly yes [4]; no ruling or enforcement action yet tests an organizer app. Legal counsel should scope this before EU launch, along with the likely DPIA (Art. 35; not re-verified in this pass).
- **Will users pay for a privacy tier?** Lunatask proves demand exists [19]; nobody has measured its price elasticity in the ADHD niche, and privacy-as-paid-upsell risks reading as "safety for the rich." Consider privacy-by-default with E2E as free architecture, not premium feature — but that has real infra costs.
- **How often can sensitive-tier consent be re-confirmed before it becomes nagging?** No literature found on re-consent cadence for impulsive populations; needs testing against notification-fatigue findings in ux-design-for-adhd.
- **Do ADHD users' disclosure fears measurably extend to app data?** The inference in §4 is strong but indirect; a small survey/interview study during beta would convert it to product knowledge (and be publishable).

## Sources

1. [GDPR Article 9 — Processing of special categories of personal data (gdpr-info.eu, official text)](https://gdpr-info.eu/art-9-gdpr/) [research]
2. [GDPR Article 5 — Principles relating to processing (data minimisation, storage limitation) (gdpr-info.eu)](https://gdpr-info.eu/art-5-gdpr/) [research]
3. [GDPR Article 17 — Right to erasure ("right to be forgotten") (gdpr-info.eu)](https://gdpr-info.eu/art-17-gdpr/) [research]
4. [CJEU Judgment C-21/23 (Lindenapotheke), 2024 — online orders of pharmacy-only, non-prescription products constitute "data concerning health" under Art. 9(1) (EUR-Lex)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:62023CJ0021) [research]
5. [CJEU Judgment C-184/20 (OT v Vyriausioji tarnybinės etikos komisija), 2022 — name-specific spouse data "liable to reveal" sexual orientation; operative part not retrievable in this pass (EUR-Lex)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:62020CJ0184) [research]
6. [Washington State Attorney General — My Health My Data Act overview (scope, inferences, consent, private right of action, effective dates)](https://www.atg.wa.gov/protecting-washingtonians-personal-health-data-and-privacy) [research]
7. [FTC — FTC Finalizes Changes to the Health Breach Notification Rule (April 2024)](https://www.ftc.gov/news-events/news/press-releases/2024/04/ftc-finalizes-changes-health-breach-notification-rule) [research]
8. [FTC — Enforcement Action to Bar GoodRx from Sharing Consumers' Sensitive Health Info for Advertising (Feb 1, 2023; first HBNR action; $1.5M)](https://www.ftc.gov/news-events/news/press-releases/2023/02/ftc-enforcement-action-bar-goodrx-sharing-consumers-sensitive-health-info-advertising) [research]
9. [FTC — FTC to Ban BetterHelp from Revealing Consumers' Data, Including Sensitive Mental Health Information, to Facebook and Others (Mar 2, 2023; $7.8M refunds)](https://www.ftc.gov/news-events/news/press-releases/2023/03/ftc-ban-betterhelp-revealing-consumers-data-including-sensitive-mental-health-information-facebook) [research]
10. [FTC — Ovulation Tracking App Premom Will be Barred from Sharing Health Data for Advertising (May 17, 2023)](https://www.ftc.gov/news-events/news/press-releases/2023/05/ovulation-tracking-app-premom-will-be-barred-sharing-health-data-advertising-under-proposed-ftc) [research]
11. [FTC — Proposed Order Will Prohibit Telehealth Firm Cerebral from Using or Disclosing Sensitive Data for Advertising; ~$7M (Apr 15, 2024)](https://www.ftc.gov/news-events/news/press-releases/2024/04/proposed-ftc-order-will-prohibit-telehealth-firm-cerebral-using-or-disclosing-sensitive-data) [research]
12. [FTC — Developer of Popular Women's Fertility-Tracking App (Flo Health) Settles FTC Allegations (Jan 13, 2021)](https://www.ftc.gov/news-events/news/press-releases/2021/01/developer-popular-womens-fertility-tracking-app-settles-ftc-allegations-it-misled-consumers-about) [research]
13. [Wikipedia — Cerebral (company): DOJ controlled-substances investigation and Nov 2024 $3.65M settlement](https://en.wikipedia.org/wiki/Cerebral_(company)) [community]
14. [Mozilla *Privacy Not Included — Top Mental Health and Prayer Apps Fail Spectacularly at Privacy, Security (2022; 28 of 32 warning-labeled)](https://www.mozillafoundation.org/en/privacynotincluded/articles/top-mental-health-and-prayer-apps-fail-spectacularly-at-privacy-security/) [research]
15. [Mozilla *Privacy Not Included — Are Mental Health Apps Better or Worse at Privacy in 2023?](https://www.mozillafoundation.org/en/privacynotincluded/articles/are-mental-health-apps-better-or-worse-at-privacy-in-2023/) [research]
16. [Huckvale K., Torous J., Larsen M.E. (2019). Assessment of the Data Sharing and Privacy Practices of Smartphone Apps for Depression and Smoking Cessation. *JAMA Network Open*](https://jamanetwork.com/journals/jamanetworkopen/fullarticle/2730782) [research]
17. [Pew Research Center (2023). How Americans View Data Privacy](https://www.pewresearch.org/internet/2023/10/18/how-americans-view-data-privacy/) [research]
18. [EDPB Guidelines 03/2022 on deceptive design patterns in social media platform interfaces, v2.0 (Feb 2023)](https://www.edpb.europa.eu/our-work-tools/our-documents/guidelines/guidelines-032022-deceptive-design-patterns-social-media_en) [research]
19. [Lunatask — official site: end-to-end encryption, "not even us," no analytics, ADHD-focused marketing](https://lunatask.app/) [product]
20. [Flo Health press center — Flo Launches Anonymous Mode](https://flo.health/press-center/flo-launches-anonymous-mode) [product]
21. [Amagai S. et al. — User Engagement and Abandonment of mHealth: A Cross-Sectional Survey (PMC8872344)](https://pmc.ncbi.nlm.nih.gov/articles/PMC8872344/) [research]
