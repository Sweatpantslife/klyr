# Klyr

**An ADHD-first life organizer, task manager, and project manager.**

Klyr is being designed from the ground up for people with ADHD — not a generic to-do app with an "ADHD mode" bolted on. The goal: a system that feels intuitive, stays easy to maintain, and helps you actually do what you need and want to do — without pressure, without shame, and without collapsing the first week you ignore it.

## Status: research complete · product vision written

Two things exist today. The **design-research corpus** — **29 documents, 553 cited sources**, produced by a multi-agent research pipeline (peer-reviewed studies, clinical experts, and labeled lived-experience sources) and audited in three independent passes for scientific accuracy, coherence, and navigability. And the **[product vision](product/vision.md)** — synthesized from four judged candidate visions, verified against the corpus's binding principles: Klyr as *the executive function you wear on the outside*, a push-first delivery layer judged by one gate — *if you ever have to remember to check Klyr, Klyr has failed.*

**Start at [`research/INDEX.md`](research/INDEX.md)** — or read the [10-minute executive summary](research/00-executive-summary.md), then the [vision](product/vision.md).

| If you want... | Go to |
|---|---|
| What we're building and why | [product/vision.md](product/vision.md) |
| The whole argument in 10 minutes | [research/00-executive-summary.md](research/00-executive-summary.md) |
| The binding design principles (20) | [research/product/design-principles.md](research/product/design-principles.md) |
| What Klyr must never do (24 anti-patterns) | [research/product/anti-patterns.md](research/product/anti-patterns.md) |
| 45 evidence-grounded feature directions | [research/product/feature-directions.md](research/product/feature-directions.md) |
| Why existing apps fail ADHD users | [research/product/app-landscape.md](research/product/app-landscape.md) |
| The science: EF, dopamine, time, memory, attention, emotion | [research/foundations/](research/foundations/) |
| Term lookup with evidence-status tags | [research/GLOSSARY.md](research/GLOSSARY.md) |

## The one-paragraph thesis

ADHD is a performance problem, not a knowledge problem — people know exactly what to do and cannot reliably make themselves do it at the right time. Mainstream productivity tools assume the opposite: they externalize nothing, punish inconsistency, demand maintenance rituals, and turn every lapse into a wall of red overdue badges. That is why the median tool is abandoned within days, and why the ADHD community cycles through system after system. Klyr's bet, grounded in this corpus: act as an external executive system (hold time, memory, and motivation in the environment, at the point of performance), make starting trivial, make coming back after a lapse the celebrated core loop — and never, ever ship shame.

## Repo map

- `product/` — product definition: what we've decided to build (start at [`vision.md`](product/vision.md))
- `research/` — the design-research corpus: what we know (start at [`INDEX.md`](research/INDEX.md))
- `research/_meta/` — corpus conventions and provenance
- `CLAUDE.md` — working guide for AI agents contributing to this repo

## Planned next phases

1. ~~Product vision~~ — done: [`product/vision.md`](product/vision.md)
2. Design system and prototypes, bound by [`design-principles.md`](research/product/design-principles.md) and [`anti-patterns.md`](research/product/anti-patterns.md)
3. Build the v1 spine (see the vision's §7 scope and cut-order)
