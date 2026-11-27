+++
title = "The Core Model"
description = "The product is its definition: four artifact regimes, one journey, one return — trunk-based development with the trunk widened to the whole product."
weight = 1
+++

Trunk-based development won for humans: one trunk, short-lived branches, integrate back, and when branches collide, rebase and re-run. The Deliberation Journey keeps that topology exactly and applies one lift, uniformly:

> the trunk carries the whole product description, not just code — and the journey, taking the place of the branch, covers the whole product too.

Why the trunk had to widen: trunk-based development could keep the trunk code-only because human developers carried the rest of the product in their heads — the intent, the decisions, the behavior they promised. Agents don't have heads: whatever they must know has to be materialized. The **Product Definition** is the trunk widened into the agent's entire context: one knowledge body, under version control, from which every journey is provisioned at departure. The branch widening is not a second extension but a consequence — whatever the trunk carries, the branch must be able to propose changes to, or the widened trunk drifts unguarded.

**The model in three components.**

1. **The Product Definition** — the permanent, evolving description of the product: everything the product is described by. Its exact contents are up to a concrete implementation, constrained only by the axiom: it must include an intent-like projection (the why) and a behavior-like projection (the observable outcomes), because consensus binds to those — never to code.
2. **The Journey** — branches off the definition and carries two things: deltas to any of the definition's artifacts (intent, scenarios, decisions — not just code), and the decision and provenance artifacts made along the way.
3. **The Return** — consolidates the journey back into the definition, with two outputs: the deltas fold into the evolving definition, and the journey freezes into an immutable Journey Record — provenance that explains, never governs. Rejected journeys freeze too; not every journey returns with its deltas.

## Four regimes, not one

Every artifact belongs to one of four types. The distinction is not how long it lives but what may happen to it.

| Type | Question it answers | Change regime |
|---|---|---|
| **Maintained** | What is the product now? | Kept current in place, through explicit change. The charter, requirements, specifications, acceptance criteria, tests, code. |
| **Provenance** | Why does the product look like this? | Revised while its journey runs, frozen at the return. A later change replaces it rather than editing it. Intents, plans, results, reviews, Journey Records, Product Definition Snapshots. |
| **Derived** | How is the product produced? | Rebuilt from the definition. Build outputs, binaries, generated code. No gate owns a derived artifact. |
| **Meta** | How does the repository apply the methodology? | Versioned with the repository and edited in place; the commit message is the record. The journey registry, the confidence dial. |

The **Product Definition is exactly the Maintained artifacts** — their sum. Meta artifacts frame the definition: they decide what counts as Maintained and how change is tracked, but they are not part of it.

**Regeneration confidence sets the type, not the artifact's kind.** If you do not trust your compiler, the binary joins the definition. If you trust the agent and its specification, the code becomes a derived artifact. A demotion is a bet, and it is recorded as one.

The separation is the core of the methodology. A maintained artifact stays short and current; it holds no history of the work. A provenance artifact records one moment in the work and is never edited to match the product. And because each step of a journey names the artifacts it needs as evidence, the process is measurable.

## The axiom

Traditional lifecycles treat understanding as a phase that precedes building: understand first, then build. It is not a phase. Common understanding is a continuous process that co-evolves with the artifact, and it is reached *through* building — the artifact is the only medium concrete enough for stakeholders to discover what they actually think. Waterfall assumes the understanding can be complete upfront; agile accepts iteration but institutionalizes it around ceremonies instead of around the formation of understanding itself.

Agentic coding changes the economics: when writing code is nearly free, the constraint is no longer producing artifacts — it is reaching agreement about which ones should exist.

> **Consensus is always over intent and observable behavior; code is a disposable projection.**

Implementations can be rebased, replaced, or merged away. What stakeholders agreed to — the why, and the observable outcomes — survives.

## The definition wins, the record explains

The four regimes map onto git's own split. The evolving definition is the working state that governs; journey records are the immutable history that explains. On divergence the definition wins, and influence runs one way: a changed definition shapes only the journeys that come after it.

The next page takes the other half of the model — [how a journey reaches agreement](/deliberation/): the two gates, who signs off, what evidence admits them, and how much ceremony a change deserves.
