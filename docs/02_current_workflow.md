[02_current_workflow.txt](https://github.com/user-attachments/files/32310971/02_current_workflow.txt)
# 02. Current Workflow

## Steps today

1. **Application + document submission** � Applicant submits the loan application along with supporting documents (pay stubs, bank statements, W-2s/tax returns) through a portal or email.
2. **Completeness check** � A loan processor reviews the submitted documents for completeness. If items are missing or illegible, the processor sends a request back to the applicant and waits for resubmission.
3. **Manual data extraction** � An underwriter opens each document and manually transcribes key figures (gross income, account balances, existing monthly debt obligations) into the LOS or an underwriting worksheet.
4. **Manual cross-check** � The underwriter compares the transcribed figures against what the applicant stated on the application, checking for discrepancies (e.g., stated income vs. pay-stub income).
5. **Discrepancy handling** � If a mismatch is found, the underwriter documents the discrepancy and either resolves it from other evidence in the file or escalates it back to the applicant/processor for clarification.
6. **Decision or exception routing** � Once the file is internally consistent, the underwriter proceeds to a decision or routes the file to exception review if red flags remain.

## Where the friction is

- **Delay**: waiting on missing or illegible documents restarts part of the cycle (step 2 ? step 1).
- **Repeated work**: the same categories of documents (pay stubs, bank statements, W-2s) are transcribed by hand on every single file, with no reuse of extraction logic across files.
- **Handoffs**: processor ? underwriter ? (sometimes) back to applicant creates multiple touchpoints per file.
- **Error-prone manual entry**: transcription by hand introduces the risk of keystroke errors that a downstream cross-check may or may not catch.

## What does NOT change in this proposal

The underwriting decision logic, credit policy, and final approval authority remain fully with the underwriter. This workflow only concerns the document intake, extraction, and cross-check steps that happen *before* judgment is applied.

