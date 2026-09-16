[04_ai_fit.txt](https://github.com/user-attachments/files/32310978/04_ai_fit.txt)
# 04. AI Fit

## Primary capability

**GENERATE / DETECT** � document-grounded data extraction (pulling structured fields such as income, account balances, and debt figures out of unstructured documents) combined with anomaly/inconsistency detection (flagging where extracted figures don't match the stated application values).

This maps to the same underlying capability shown in the Week 2 material as Copilot's "transform text into a table" and "ask about the document" functions � applied here to financial source documents instead of general office documents.

## Why AI is a plausible fit

- The documents involved (pay stubs, bank statements, W-2s) are semi-structured � the same handful of fields appear in predictable locations, which is exactly the kind of pattern extraction models handle well versus rigid, hand-coded rules that break on format variation.
- The task today is already "read a document, pull out known fields, compare to a reference value" � a repetitive pattern-matching task, not a judgment call. The underwriter's judgment stays downstream, on what to do once the comparison is made.
- Volume is high and recurring (every file, every day), which is where automation assistance produces compounding time savings versus a one-off task.

## What AI would NOT do

- AI would not make the credit decision, approve/deny a loan, or resolve a flagged discrepancy on its own.
- AI output (extracted figures + flags) would feed into the underwriter's existing review step, not replace it.

## Why this is not yet an AI project

Consistent with the course framework: this milestone does not prove the AI approach works. It establishes that there is a meaningful, recurring, measurable problem, and that a document-grounded extraction/detection capability is a reasonable, testable candidate to investigate � not a finished or validated solution.

