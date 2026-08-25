+++
title = "The Core Model"
description = "Baseline, journey, return: trunk-based development with one lift — the trunk holds the whole product, and the branch is a deliberation journey."
weight = 1
+++

Trunk-based development won for humans: one trunk, short-lived branches, integrate back, and when branches collide, rebase and re-run. The Deliberation Journey keeps that topology exactly and applies one lift, uniformly:

> the trunk carries the whole product description, not just code — and the journey, taking the place of the branch, covers the whole product too.

Why the trunk had to widen: trunk-based development could keep the trunk code-only because human developers carried the rest of the product in their heads — the intent, the decisions, the behavior they promised. Agents don't have heads: whatever they must know has to be materialized. The **baseline** is the trunk widened into the agents' entire context: one knowledge body, under version control, from which every journey is provisioned at departure. The branch widening is not a second extension but a consequence — whatever the trunk carries, the branch must be able to propose changes to, or the widened trunk drifts unguarded.

**The model in three components.**

1. **The baseline** — the permanent, evolving description of the product: everything the product is described by. Its exact contents are up to a concrete implementation, constrained only by the keystone: it must include an intent-like projection (the why) and a behavior-like projection (the observable outcomes), because consensus binds to those — never to code.
2. **The journey** — branches off the baseline and carries two things: deltas to any of the baseline's artifacts (intent, scenarios, decisions — not just code), and the decision and provenance artifacts made along the way.
3. **The return** — consolidates the journey back into the baseline, with two outputs: the deltas fold into the evolving baseline, and the journey freezes into an immutable record — provenance that explains, never governs. Rejected journeys freeze too; not every journey returns with its deltas.

**The axiom.** Traditional SDLCs treat understanding as a phase that precedes development. It isn't: common understanding is a continuous, time-consuming process that co-evolves with the artifact, reached *through* building — the artifact is the only medium concrete enough for stakeholders to discover what they actually think. The keystone consequence: **consensus is always over intent and observable behavior; code is a disposable projection.** Implementations can be rebased, replaced, or merged away; what stakeholders agreed to — the why, and the observable outcomes — survives.

**Two change regimes.** The baseline's artifacts live in two regimes, mirroring git's own split between the working tree and the history: the **evolving** artifacts govern — the living contract every new journey measures its change against — and the **frozen** records explain — the product's memory of why it is the way it is. On divergence, the baseline wins; the record explains how it got there.

**A protocol, not a file format.** The methodology does not prescribe one shape for the baseline — a single canonical artifact set would repeat waterfall's error one level down, one shape for all domains. But the openness is constrained: every conforming implementation must provide the [three invariants](/invariants/). Everything else — formats, gate definitions, role sets, tooling — is the implementation's to choose, varying with domain gravity, stakeholder count, and autonomy level. That is the pluralism: implementations vary; invariants don't.
