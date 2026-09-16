# 07. Risk + Control

## Meaningful risk

**Incorrect field extraction leading to a flawed underwriting input.** If the system misreads a figure from a document (e.g., extracts $4,500 in monthly income when the pay stub actually shows $4,050) and that error is not caught, it could feed an inaccurate number into a credit decision — a materially worse outcome than the manual-entry errors happening today, since a wrong-but-confident automated output could be trusted more than it should be.

## Initial guardrail

- **No figure is decision-usable until the underwriter confirms it.** Every extracted value is shown side-by-side with the source document image; the underwriter must visually confirm or correct each extracted figure before it can be used in the decision — the AI never writes directly into the system of record unconfirmed.
- **Low-confidence extractions are auto-flagged for mandatory manual review**, rather than silently presented as equally reliable as high-confidence extractions.
- **Discrepancy flags require human resolution.** When extracted figures don't match stated application values, the system surfaces the discrepancy — it does not attempt to resolve it or decide which number is "correct."

## Why this guardrail is appropriate for Milestone 1

This is a single, concrete initial control (human confirmation before use) rather than a vague statement like "AI may fail." It directly targets the specific risk identified above and keeps the underwriter's judgment as the final authority, consistent with what does not change in `02_current_workflow.md`.

