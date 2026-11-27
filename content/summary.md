+++
title = "The Five-Minute Version"
description = "The whole methodology on one page: the problem, the one lift, the four artifact regimes, two gates, and the return — with links into the depth."
weight = 0
+++

If you read one page, read this one. Everything here is developed properly in [the model](/methodology/) and [deliberation](/deliberation/); nothing here is a simplification that gets contradicted there.

## The problem

Trunk-based development won because it keeps one trunk, branches briefly, integrates constantly, and when branches collide it rebases and re-runs the tests. It worked because the trunk only had to hold code — human developers carried the rest of the product in their heads: why the thing exists, what was decided, what behavior was promised.

Agents have no heads. Whatever they must know has to be written down, versioned, and reviewed like code. Anything left implicit is left to chance, and chance at machine speed is drift.

## The one lift

Apply the trunk-based topology unchanged, and widen what the trunk carries: **the whole product description, not just code.** Call that the **Product Definition**. The branch widens with it — it must be able to propose changes to any part of the definition, or the widened trunk drifts unguarded. Call the branch a **Journey**.

So: a journey proposes *deltas* to the definition — to intents, scenarios, decisions, tests, not only code — and carries the evidence behind them. When it finishes it does two things at once: the deltas fold into the definition, and the journey freezes into an immutable **record**.

> **Consensus is always over intent and observable behavior. Code is a disposable projection.**

## Four kinds of artifact

The distinction is not how long something lives, but what may happen to it.

| | Question | Rule |
|---|---|---|
| **Maintained** | What is the product now? | Kept current in place. The charter, requirements, specs, acceptance criteria, tests, code. |
| **Provenance** | Why does it look like this? | Never edited. A later change replaces it. Intents, plans, results, reviews, records. |
| **Derived** | How is it produced? | Rebuilt from the definition. Build outputs, binaries, generated code. |
| **Meta** | How does the repo apply the methodology? | Versioned, edited in place; the commit message is the record. The journey registry, the confidence dial. |

The Product Definition is exactly the **Maintained** artifacts. It wins on divergence; the record explains, never governs.

**What decides the type is regeneration confidence, not the artifact's kind.** If you don't trust the compiler, the binary joins the definition. If you trust the agent and its specification, the code becomes derived. Every demotion is a bet, and it is recorded as one.

## Two gates

A journey earns its right to change the definition at exactly two points.

- The **intent gate**: stakeholders agree on what the journey is trying to achieve, in prose. Cheap to cross; the intent is stable afterwards and gets cited, not edited.
- The **behavior gate**: stakeholders agree on observable outcomes — "when I do X, I see Y" — backed by tests, analyzers, or demonstrated behavior. A customer who approved a mockup approved a mockup. This is the gate to completion.

Everything between them is iteration space, and it is deliberately the largest part: that is where the artifact climbs the fidelity ladder and where people discover what they actually think.

Consensus is **per gate and per role**, and it is not unanimity. Each role holds a veto exactly where its accountability lives — the architect on structure, the tester on executability, the customer on observed behavior. Gates reopen only on new evidence that changes the basis on which they passed, and always scoped to the delta that evidence implicates. A gate that cannot pass goes `blocked` and escalates; it does not decay into "fine".

## Type and risk are independent

**Type** is what the journey publishes — `feature > decision > refactoring > trivial` — and names the path, not the artifact list. **Risk** is what is at stake, and it sets the evidence floor, the roles required, and how much autonomy may stand in for a human decision.

Ceremony scales with evidence and risk, never with gate count. Unclear risk is high risk until evidence resolves it, and reclassification is auditable — so the cheap lanes can't become the place where risk hides. A high-risk trivial change is not a contradiction; it is the system working.

## The return

The deltas fold into the definition; the journey freezes into its record. Rejected journeys freeze too — the record of a rejected journey is what stops the same ground being re-walked blindly. A decision that is hard to reverse, surprising without context, and the result of a real trade-off is promoted out of the record into the repository as an ADR.

**Return is the full act; merge is the mechanic it culminates in.**

## What an implementation must satisfy

The definition's shape is yours to choose. Three things are not:

1. An **intent-like** and a **behavior-like** projection exist — consensus binds to those, never to code.
2. **Both regimes** exist — artifacts that evolve and govern, records that freeze and explain.
3. Journeys carry **deltas plus decision and provenance artifacts**, or the review object collapses back to code.

Anything missing one of these is a file format, not the methodology. [The invariants](/invariants/) are the test.

## Next

- [The Core Model](/methodology/) — the full statement, including the regeneration-confidence dial.
- [Deliberation](/deliberation/) — the gates, the role table, the state machine, the return.
- [Comparisons](/comparisons/) — how trunk-based development, OpenSpec, Spec Kit, and Kiro each implement part of this, and where they stop.
