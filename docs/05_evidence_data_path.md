[05_evidence_data_path.txt](https://github.com/user-attachments/files/32310981/05_evidence_data_path.txt)
# 05. Evidence / Data Path

## What evidence/data would be needed

- Sample loan document sets: pay stubs, bank statements, W-2/tax forms, representing the document types underwriters currently handle.
- The corresponding loan application field values those documents are checked against (stated income, stated assets, stated debts).
- Current time-per-file and rework/error-rate figures, broken down by document type if available, to validate/refine the baseline in `03_baseline_kpi.md`.
- A taxonomy of the most common discrepancy types (e.g., income mismatch, stale bank statement, missing signature) to understand what "detect" needs to catch.

## Source, access, and constraints

- **Source**: hypothetical/synthetic document sets only � this is a fully hypothetical scenario with no real company or applicant data. Any prototype would use fictional or publicly available sample loan-document templates, not real borrower information.
- **Access**: no access constraints apply in this hypothetical scenario, since no real institutional systems or applicant data are involved.
- **Privacy**: financial documents of this type are highly sensitive (income, account numbers, SSNs on tax forms). If this were pursued with real data, it would require strict data handling: redaction/masking of account numbers and SSNs, and restricted access � this is flagged now so it isn't overlooked later.
- **Quality**: real-world document quality varies (scan quality, handwriting, non-standard formats), which is a known limitation of document-extraction approaches and would need to be tested against realistically messy fictional samples, not only clean examples.

## Prototype scope

Any future prototype work would use fictional or synthetic documents only � never real applicant financial data � consistent with the fully hypothetical framing of this project.

