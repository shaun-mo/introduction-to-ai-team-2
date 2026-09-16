[03_baseline_kpi.txt](https://github.com/user-attachments/files/32310974/03_baseline_kpi.txt)
# 03. Baseline + KPI

> Figures below are hypothetical planning estimates for a fictional scenario, not real production data. They are directionally reasonable for a mid-size underwriting team and are meant to establish a testable baseline, not to be cited as fact.

## Baseline (current, estimated)

| Metric | Estimated current value |
|---|---|
| Manual document review + data-entry time | ~25 minutes per loan file |
| Files requiring resubmission due to missing/illegible documents | ~15% of files |
| Rework/error rate (transcription or missed inconsistency caught downstream) | ~8% of files |
| Average number of touches before a file is decision-ready | ~2.5 touches |

## KPI targets

| KPI | Target |
|---|---|
| Document review + data-entry time | Reduce from ~25 min to **< 10 min** per file |
| Rework/error rate | **Hold flat or reduce below 8%** — must not increase |
| Touches per file before decision-ready | Reduce from ~2.5 to **≤ 1.5** |

## Guardrail

Any efficiency gain is void if it comes at the cost of accuracy. The error/rework rate is a hard guardrail, not just a target: if extraction errors increase, the project does not count as a success regardless of time savings.

## How this would be measured

- Time-per-file: instrumented via timestamps in the LOS (document received → file marked decision-ready).
- Rework/error rate: existing QA sampling process already tracks post-decision corrections; the same definition would be reused so the before/after comparison is apples-to-apples.

