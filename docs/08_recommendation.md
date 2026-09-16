# 08. Recommendation

## Recommendation: INVESTIGATE

## Why

- **Recurring, high-volume business pain**: manual document extraction and cross-checking happens on every loan file, every day — not an occasional inconvenience.
- **Measurable value**: a clear baseline (~25 min/file, ~8% rework rate, ~2.5 touches/file) and a concrete target (<10 min/file, rework rate held flat or improved, ≤1.5 touches/file) make this testable rather than aspirational.
- **Plausible, bounded AI capability**: document-grounded extraction and inconsistency detection is a well-matched capability for semi-structured financial documents, and it mirrors a capability already shown to work in adjacent tools (Copilot's document Q&A/table transformation).
- **Feasible evidence path**: sample/synthetic loan documents and existing time/error tracking data would support a prototype and evaluation without requiring real applicant data.
- **Controllable initial risk**: the identified failure mode (incorrect extraction) has a concrete, enforceable guardrail — mandatory human confirmation before any extracted figure is used — keeping the underwriter's judgment as the deciding factor.

## Why not the alternatives

- The **non-AI alternative** (structured intake form + document checklist) is worth pursuing regardless, but only addresses part of the problem — it does not remove the need to cross-check applicant-reported figures against source documents.
- **Fraud/anomaly detection** and other candidate ideas discussed by the team carry materially higher regulatory risk (see project overview) and are harder to control at this early stage; this idea offers a similar efficiency opportunity with a narrower, more controllable blast radius.

## Next step

Build a limited prototype using fictional/synthetic loan documents, and compare its extraction speed and accuracy against the structured-intake-form alternative as the non-AI baseline, before considering any broader rollout.

