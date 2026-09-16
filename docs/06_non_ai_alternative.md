# 06. Non-AI Alternative

## Simpler solution to consider first

Improve document standardization and intake structure without introducing AI:

- Require applicants to submit financial information through a structured online form with defined fields (income, employer, account balances) *in addition to* uploading source documents, rather than relying on the underwriter to extract those numbers from the documents themselves.
- Provide applicants with a standardized checklist and document template guidance up front, to reduce the ~15% resubmission rate caused by missing or illegible documents.
- Use basic template-matching or fixed-position OCR (not a learned model) for the small number of documents that already follow a consistent, known layout.

## Why this might solve part of the problem

- A structured intake form removes some transcription work entirely for fields the applicant enters directly, at much lower cost and risk than a document-extraction model.
- Better upfront guidance could meaningfully reduce the resubmission rate, which is a real driver of cycle time today.

## Why it likely isn't sufficient on its own

- It doesn't solve the underlying cross-check problem: the underwriter still needs to verify the applicant-entered numbers against the actual source documents (pay stubs, bank statements), since the whole point of underwriting is not to simply trust self-reported figures.
- Document formats vary by employer/bank, so fixed-position template matching would only work for a subset of documents, not the full variety underwriters see.

## Standard this proposal must meet

Per the course framework, the AI-based proposal must demonstrably outperform this simpler, lower-risk alternative — not just be technically interesting — before it's worth prototyping.

