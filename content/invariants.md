+++
title = "Invariants"
description = "Implementations vary; invariants don't. The three invariants are the conformance test for the methodology."
weight = 3
+++

The methodology does not prescribe one way to structure the product definition. A single canonical artifact set would repeat waterfall's error one level down — one shape for all domains. But "implementation-defined" is not "unconstrained." **Implementations vary; invariants don't.**

Every conforming implementation must provide:

1. **Intent-like and behavior-like projections must exist.** The definition must carry an intent-like projection of the product — the why — and a behavior-like projection — the observable outcomes — because consensus binds to those, never to code.
2. **Both change regimes must exist.** Evolving artifacts that govern, and frozen records that explain. The return produces both outputs; an implementation with only one is missing half the model.
3. **Journeys carry deltas plus decision and provenance artifacts.** A journey must carry deltas to definition artifacts *and* the decisions and provenance made along the way — otherwise the review object collapses back to code, and the methodology degenerates.

Everything else — formats, layout, gate definitions, role sets, tooling — is the implementation's to choose.

Run the three invariants against any candidate and the result decides how much of the methodology it realizes. Under this test, the existing spec-driven tools land as partial implementations: strong on the projections and the delta design, silent on the provenance regime and the [consensus semantics](/deliberation/). See [Comparisons](/comparisons/).

**Any implementation missing one is a file format, not the methodology.**
