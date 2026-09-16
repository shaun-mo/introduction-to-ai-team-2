# Week 3 — Language, Data & AI Readiness

> **Source:** `MIS_7397_Week_3_Language_Data_AI_Readiness.pdf` (40 slides)
> **Session:** Thursday, September 10, 2026 · 3-hour graduate session
> **Topic:** Chapter 3 — Natural Language Processing + Course Extension: Data Foundations & the AI Factory + Milestone 1 Prep
> **Tags:** `CHAPTER 3` · `DATA READINESS` · `CAPSTONE MILESTONE 1`
> **Course:** MIS 7397 · Introduction to Artificial Intelligence for Business · University of Houston, Bauer College of Business

---

## TL;DR — leave Week 3 with five ideas

1. **Language is data.** NLP turns messy language into labels, facts, summaries, or responses.
2. **Speech has two steps.** Hearing the words correctly and interpreting them correctly are separate risks.
3. **Prompts define the task.** Goal + Context + Expectations + Source improve clarity — but output still needs evaluation.
4. **Data must be fit for purpose.** Quality, labels, representativeness, access, and privacy shape feasibility.
5. **Milestone 1 = approval gate.** Do not prove the AI works yet. Prove the opportunity is worth investigating.

> ⚠️ **MILESTONE 1 IS DUE THURSDAY, SEPTEMBER 17 (Week 4).** This deck locks in the eight required components (slide 36) — see §13. It also adds a **data readiness scorecard** (§11) we should run against our proposal before submitting.

---

## 1. Bridge from Week 2

> *Last week: "Which business problem deserves AI?" This week: "What language and data does the system need to work?"*

| Week 2 | Week 3 | Week 4 |
|---|---|---|
| Problem → workflow → KPI → AI capability | Language → evidence → data quality → readiness | Supervised ML + **Milestone 1 submission** |

**A good AI opportunity is not only valuable. It must also have usable evidence.**

### Week 3 outcomes

| # | Verb | Outcome |
|:---:|---|---|
| 1 | **EXPLAIN** | What NLP does and why human language is difficult for machines |
| 2 | **DISTINGUISH** | Speech recognition from language understanding and downstream NLP tasks |
| 3 | **APPLY** | Prompting and multimodal Gemini concepts to a business-language task |
| 4 | **EVALUATE** | Recruiting and other NLP use cases for value, bias, privacy, and failure consequences |
| 5 | **MAP** | Structured/unstructured data, quality, ownership, labels, and readiness |
| 6 | **PREPARE** | A complete Milestone 1 Opportunity Proposal for Week 4 |

---

## 2. AI Now — three current signals

| Signal | Story | Discussion question |
|---|---|---|
| **CAPABILITY** | Google introduced Gemini 3.8 Flash and 3.8 Flash Cyber for faster agentic workflows and cybersecurity tasks | What new tasks become practical when speed + reasoning improve? |
| **ADOPTION** | Large employers are moving AI agents from pilots into everyday employee workflows | What changes when AI is part of the process — not a separate chatbot? |
| **GOVERNANCE** | The EU AI Act became broadly applicable on Aug. 2, 2026; governance is now an operating requirement for many organizations | Who owns compliance when AI touches a workflow? |

*Same ritual as Weeks 1–2: keep the headline in context, not in hype.*

---

## Part I — Chapter 3: Natural Language Processing

> *Making headway with language: text, speech, multimodality, prompting, and recruitment.*

## 3. What NLP is (3.1)

> **NLP helps systems process, interpret, transform, and generate human language.**

| Stage | What it covers |
|---|---|
| **READ** | Emails · reports · reviews · contracts |
| **LISTEN** | Speech · calls · meetings · voice requests |
| **UNDERSTAND** | Intent · meaning · entities · sentiment |
| **TRANSFORM** | Summarize · translate · extract · classify |
| **GENERATE** | Draft · answer · explain |

> **Business lens:** NLP turns language into something a workflow can use.

---

## 4. Why language is hard (3.2)

> **The same words can mean different things; different words can mean the same thing.**

| Difficulty | Example |
|---|---|
| **AMBIGUITY** | "That charge is sick." — meaning depends on context |
| **CONTEXT** | "Cancel it." — what is "it"? An order? Subscription? Meeting? |
| **VARIATION** | Accents · slang · typos · jargon · multiple languages |
| **IMPLICIT MEANING** | Tone · sarcasm · urgency · unstated assumptions |

> NLP performance depends on context, task definition, and the data/examples the system sees.

### The textbook preprocessing pipeline — a mental model

Before a system can use language, it must turn messy input into signals useful for the task.

| # | Step | What it does |
|:---:|---|---|
| 1 | **LOWERCASE** | Normalize letter case |
| 2 | **TOKENIZE** | Split text into smaller units |
| 3 | **FILTER** | Remove low-information / filler words |
| 4 | **STEM** | Reduce words toward a root form |
| 5 | **POS TAG** | Identify grammatical roles (part of speech) |
| 6 | **ENTITIES** | Find names, dates, amounts, organizations |
| 7 | **SENTIMENT** | Estimate emotional tone |
| 8 | **CONTEXT / INTENT** | Interpret the overall meaning and goal |

> ⚠️ **Instructor's caveat (slide 8):** this is a useful textbook pipeline — *not* a claim that every modern NLP/LLM system literally executes these as eight separate modules.

### The practical NLP task map

> **Do not start with "NLP." Start with the specific language task.**

| Task | Question it answers | Examples |
|---|---|---|
| **CLASSIFY** | What category? | intent · topic · spam |
| **EXTRACT** | What facts are present? | names · dates · amounts |
| **SENTIMENT** | What attitude/tone? | positive · negative · urgency |
| **SUMMARIZE** | What is the essence? | meetings · reports · cases |
| **TRANSLATE** | Same meaning, new language | customers · global teams |
| **ANSWER / GENERATE** | What response is useful? | Q&A · drafts · explanations |

### From language to business action

```
LANGUAGE INPUT  →  CONTEXT          →  NLP TASK       →  OUTPUT           →  WORKFLOW
text · speech ·    conversation ·      classify ·        label · entity ·    route · review ·
document           policy · history    extract ·         summary ·           respond ·
                                       summarize         response            escalate
```

**Worked example:** customer voice message → account context → intent + urgency → "billing / high" → priority routing

---

## 5. The NLP tasks, one at a time

### Classification — turning language into a category

*Useful when the business needs consistent routing, prioritization, or tagging.*

| Input | Possible outputs |
|---|---|
| "I was charged twice and need this fixed today." | Intent: **Billing** · Issue: **Duplicate charge** · Urgency: **High** · Escalation: **Yes** |

> **Management question:** what categories are useful enough to change the workflow?

### Sentiment — useful, but easy to oversimplify

> **Positive / negative is not the same as business urgency.**

| Message | Sentiment reading | What actually matters |
|---|---|---|
| **A** — "I love your product, but my renewal failed and I present to a client in 30 minutes." | Positive-ish tone | Extremely urgent; high risk |
| **B** — "Fine. Cancel it whenever." | Negative / resigned | Churn signal, but low urgency |

> Tone, intent, urgency, and risk are **different signals**. Do not reduce a workflow to one sentiment score. A better design separates *the signal you need* from *the language feature you can estimate*.

### Information extraction — finding facts inside language

*Turn unstructured text into fields that systems can use.*

| Email | Extracted fields |
|---|---|
| "Please update PO 8841. The supplier is Northstar Components, the revised total is $18,740, and delivery moves to Oct. 6." | PO: **8841** · Supplier: **Northstar Components** · Amount: **$18,740** · Delivery date: **Oct. 6** |

> Value comes when extraction reduces manual entry **without silently introducing bad data.**

### Summarize, translate, and answer — generative tasks still need verification

| Task | Transformation | Risk |
|---|---|---|
| **SUMMARIZE** | Meeting transcript → decisions, owners, deadlines | Omitted nuance |
| **TRANSLATE** | Customer message → another language | Tone / domain terminology |
| **ANSWER / DRAFT** | Question + context → useful response | Fabricated or unsupported detail |

> **"Fluency is an interface property. Accuracy is an evaluation property."**

---

## 6. Speech recognition ≠ language understanding (3.3)

> **Automatic speech recognition (ASR) converts audio to text; NLP interprets or transforms the language.**

```
AUDIO                        →  SPEECH RECOGNITION          →  NLP
"Please cancel order            Audio → words                  Intent: cancel order
 eighty-four B."                "Please cancel order 84B."     Entity: 84B
                                                               Action: verify + route
```

> **Two separate error opportunities:** hearing the words incorrectly *and* interpreting them incorrectly.

### Where speech recognition fails before NLP even begins

| Failure source | Examples |
|---|---|
| **NOISE** | Background conversations · poor microphone |
| **ACCENTS / DIALECTS** | Pronunciation variation · code-switching |
| **JARGON** | Product names · technical terms · acronyms |
| **NUMBERS / NAMES** | 84B vs 80-4B · similar names |
| **TURN-TAKING** | Interruptions · overlap · incomplete sentences |
| **PRIVACY** | Voice can contain sensitive information |

*Audio quality and language variation can change the downstream business decision.*

### Gemini as a multimodal example

> One model can work across multiple forms of input — text, voice, images, documents, and more.

| Modality | Examples |
|---|---|
| **TEXT** | Typed request · email · document |
| **VOICE / AUDIO** | Spoken question · meeting · call |
| **IMAGE / VISUAL** | Photo · chart · screenshot |
| **COMBINED CONTEXT** | "Look at this chart and explain what I should tell the client." |

> **Multimodal does not mean infallible.** Each modality adds information — and new failure modes.

---

## 7. Prompt engineering does not disappear in voice (3.4)

> Good spoken instructions still define the task, context, expectations, and source. **The interface changes. The discipline does not.**

| Component | Question | Voice example |
|---|---|---|
| **GOAL** | What do you want done? | "Classify this customer request." |
| **CONTEXT** | What situation matters? | "Routing for SaaS customer support." |
| **EXPECTATIONS** | What format / limits? | "Intent, urgency, one-sentence reason." |
| **SOURCE** | What evidence may it use? | "Use only the message I provide." |

*Same four components introduced in Week 2 §10 — now applied to spoken input.*

### The reusable business-language prompt (slide 18)

This is the structured prompt used in the live demo **and in the at-home activity** (§14). Say it or type it — the structure stays the same.

```
GOAL:          Classify the customer message for routing.
CONTEXT:       We are a fictional SaaS support team.
EXPECTATIONS:  Return intent, sentiment, urgency, and extracted entities in a table.
SOURCE:        Use only the message provided. Do not invent missing facts.

MESSAGE: "I cannot access my account and I present to a client in 30 minutes."
```

> **Evaluation question:** is the output useful for a routing decision — and what could still be wrong?

### Live demo — one message, two input modes

*Uses UH Gemini for Education. If voice is unavailable, both examples run as text.*

| Step | Action | What to observe |
|:---:|---|---|
| **1 · TYPE** | Paste the structured prompt + customer message | Output structure and any assumptions |
| **2 · SPEAK** | Use microphone / voice input with the same intent | Compare transcription and interpretation |
| **3 · CRITIQUE** | Did it hear the words correctly? Did it classify correctly? Did it invent anything? Would you automate the route? | |

> ⚠️ **Never use real customer, employee, health, financial, or confidential data in the demo.**

---

## 8. NLP and GenAI in recruiting (3.5)

> Recruiting is a useful case because the value is real — **and so are the consequences of mistakes.**

| Stage | What NLP/GenAI does |
|---|---|
| **JOB POSTS** | Draft / simplify · identify skills |
| **RESUMES** | Parse fields · summarize experience |
| **MATCHING** | Compare skills · rank / recommend |
| **INTERVIEWS** | Transcribe · summarize notes |
| **COMMUNICATION** | Draft outreach · answer FAQs |

> **The higher the decision consequence, the stronger the evidence and human oversight should be.**

### Value, evidence, and risk must travel together

> **A faster hiring workflow is not automatically a better hiring workflow.**

| Potential value | Risks | Control ideas |
|---|---|---|
| Less repetitive screening | Historical bias | Job-related criteria |
| Faster candidate communication | Proxy discrimination | Human review |
| Consistent extraction | Privacy / sensitive data | Audit outcomes by group |
| Recruiter capacity | False confidence | Data minimization |
| | Explainability | Appeal / override |

> **Manager question:** what evidence would justify using AI at *each step* of the hiring process?

### Chapter 3 checkpoint (MindTap-style)

*Explain each in your own words — no memorized definitions.*

| | Topic | Question |
|:---:|---|---|
| **A** | NLP | What does NLP enable a business system to do with human language? |
| **B** | Speech | What is the difference between speech recognition and language understanding? |
| **C** | Multimodal | Why can combining voice, text, and visuals help — and what new risks appear? |
| **D** | Prompting | How do Goal, Context, Expectations, and Source improve a voice/text request? |
| **E** | Recruiting | Why does faster screening not necessarily mean better hiring? |

---

## Part II — Data Foundations & the AI Factory

> *Course extension — this is the syllabus's "Week 3: Data Foundations and the AI Factory" material, layered under the Chapter 3 content.*

## 9. Language is data — usually unstructured data

> AI projects often combine clean database fields with messy documents, messages, audio, and images.

| Structured data | Unstructured data |
|---|---|
| Rows / columns / defined fields | Free-form content |
| `customer_id` · `date` · `amount` · `product` · `outcome` | email · PDF · chat · call audio · image · video |
| Easy to filter and aggregate | Meaning must be interpreted or extracted |

> **Most useful business AI combines both.**

### The AI factory — evidence must move through a pipeline

> A business AI system depends on **repeatable** data and evaluation processes.

```
SOURCE      →  COLLECT   →  PREPARE     →  LABEL /     →  LEARN /      →  EVALUATE   →  DEPLOY +
Where          Capture /     clean ·        CONTEXT        RETRIEVE        test           MONITOR
evidence       access        normalize ·    outcomes ·     model learns    against        use + watch
originates                   chunk          tags ·         or system       evidence       change
                                            policies       retrieves
```

> ⚠️ **The pipeline is also where many AI failures begin:** inaccessible data, weak labels, stale evidence, or poor monitoring.

### What kind of evidence does the task need?

> Match evidence to the question — not every AI project needs the same data.

| Project type | Evidence required | Example |
|---|---|---|
| **PREDICTIVE ML** | Historical examples + outcomes | Customers + whether they churned |
| **LANGUAGE / NLP** | Text or audio + task labels / evaluation examples | Support messages + intent |
| **KNOWLEDGE ASSISTANT** | Trusted documents + questions + expected grounded answers | Policies + test questions |

> **"We have lots of data" is not a feasibility argument.** Data readiness is task-specific.

---

## 10. Train / validate / test — and labels

### Training, validation, and test data

> Keep the final test separate so performance is measured on examples the model did not learn from.

| Split | Purpose |
|---|---|
| **TRAIN** | Used to learn patterns. Largest share of examples. |
| **VALIDATE** | Used to tune choices and compare approaches. |
| **TEST** | Used at the end for an honest estimate of performance. |

> ⚠️ If the test set influences training decisions, the final score can look better than reality.

*This sets up Week 4 (Supervised ML).*

### Labels and ground truth — what counts as the "right" answer?

> Many AI projects quietly inherit human judgment through their labels.

| Example | Label | The hidden question |
|---|---|---|
| Email text | → "Billing" | Who decided the category? |
| Applicant | → "Strong candidate" | What criteria produced that label? |
| Transaction | → "Fraud" | Was it confirmed — or only suspected? |

> **Bad labels teach the wrong target consistently.**

---

## 11. Data quality, representativeness, and permissions

### Six dimensions of data quality

> A dataset can be large and still be unfit for the task.

| Dimension | Question |
|---|---|
| **ACCURATE** | Correct? |
| **COMPLETE** | Missing key fields / examples? |
| **CONSISTENT** | Same definitions / formats? |
| **RELEVANT** | Matches the decision? |
| **TIMELY** | Current enough? |
| **TRACEABLE** | Source / provenance known? |

**+ one more:** **REPRESENTATIVE** of the people and conditions where the system will be used?

### Representativeness — who and what is missing?

> A model can perform well on the dataset and poorly in the population that actually matters.

| Gap | Example |
|---|---|
| **CUSTOMERS** | Training data overrepresents long-term customers and underrepresents new users |
| **LANGUAGE** | Examples reflect one accent, language variety, writing style, or region |
| **TIME / CONDITIONS** | Historical behavior came from a different policy, market, or economic environment |

> **Ask:** "Representative of *what* deployment population, under *what* conditions?"

### Ownership, access, privacy, and permissions

> **"The data exists" is different from "we can legally and responsibly use it."**

| Question | What to check |
|---|---|
| **OWNER** | Who controls the source? |
| **ACCESS** | Can the project team obtain it? |
| **PRIVACY** | Does it contain sensitive or personal information? |
| **PERMISSION** | Is this use allowed under policy, consent, contract, and tool rules? |

> ⚠️ **For class projects:** use public, fictional, synthetic, or instructor-approved data. Do not upload sensitive real data. *(Matches the syllabus data policy in the README.)*

### ⭐ Data readiness scorecard

> **Green does not mean "perfect."** It means feasible enough to investigate responsibly.

| Area | Green means… | Our proposal |
|---|---|:---:|
| **SOURCE** | We know where evidence comes from | ⬜ |
| **ACCESS** | We can obtain / use it appropriately | ⬜ |
| **QUALITY** | It is accurate / relevant enough | ⬜ |
| **COVERAGE** | It represents key cases / users | ⬜ |
| **TARGET** | We know the label / outcome or evaluation criterion | ⬜ |
| **PRIVACY** | Risks and permissions are understood | ⬜ |

> ⚠️ **If 2+ areas are red, Milestone 1 should usually be reframed before prototype work.** Fill in the right-hand column (🟢 / 🟡 / 🔴) for our candidate before we submit.

---

## Part III — Capstone Milestone 1: Opportunity Proposal

> **Due Week 4 · Thursday, September 17 · approval gate before prototype work.**
> **Teams are formed. This week = refine + validate.**

## 12. Milestone 1 — what changed since Week 2

Week 2 introduced Milestone 1 as a five-step "AI Opportunity Clinic" (Choose → Frame → Match → Test → Define). Week 3 restates the deliverable as **eight explicit components**, adds a due date, and adds the **evidence / data path** and **recommendation** pieces that come from this week's data-readiness content.

| Week 2 step | Where it lands in the Week 3 eight components |
|---|---|
| 1 · Choose | #1 Problem + Stakeholder |
| 2 · Frame | #1 Problem + Stakeholder · #2 Current Workflow · #3 Baseline + KPI |
| 3 · Match | #4 AI Fit · #6 Non-AI Alternative |
| 4 · Test | #5 Evidence / Data Path *(now backed by the readiness scorecard)* |
| 5 · Define | #3 Baseline + KPI · #7 Risk + Control |
| *(new)* | #8 Recommendation — investigate · reframe · reject |

---

## 13. ⭐ Exactly what Milestone 1 must contain (slide 36)

> **1–2 page Opportunity Proposal + one-slide executive summary. No prototype required yet. Worth 4% of the course.**

| # | Component | What it must answer |
|:---:|---|---|
| **1** | **PROBLEM + STAKEHOLDER** | Specific pain; who experiences it? |
| **2** | **CURRENT WORKFLOW** | What happens today? Where is the friction? |
| **3** | **BASELINE + KPI** | Current performance + measurable target |
| **4** | **AI FIT** | Primary capability and why it may help |
| **5** | **EVIDENCE / DATA PATH** | Likely sources, access, quality, and constraints |
| **6** | **NON-AI ALTERNATIVE** | Simpler solution considered |
| **7** | **RISK + CONTROL** | One meaningful failure + initial guardrail |
| **8** | **RECOMMENDATION** | Investigate · reframe · reject |

> **Approval standard:** meaningful + measurable + evidence-feasible + appropriately scoped.

### Weak idea vs. approvable opportunity

> The difference is not how impressive the technology sounds — it is how clear the business case is.

| ✕ WEAK | ✓ STRONGER |
|---|---|
| "We want to build an AI chatbot for HR using Gemini." | "Employees spend ~15 minutes locating benefits answers, while HR handles ~600 repetitive questions/month. Investigate whether a grounded knowledge assistant can cut search time below 5 minutes without increasing policy-error rate." |
| **Missing:** specific user/problem · baseline · KPI · evidence path · risk boundary · non-AI alternative | **Notice:** the stronger statement does not depend on a tool name. |

### Example executive summary (slide 38) — the one-slide template

> A good summary lets an executive understand the opportunity in 60 seconds.

| Block | Example content |
|---|---|
| **PROBLEM** | Employees lose time searching benefits policies; HR repeats common answers. |
| **BASELINE / KPI** | Baseline: ~15 min search; ~600 repeated HR questions/month. Target: <5 min; policy error not worse. |
| **AI FIT** | Language Q&A / knowledge assistance. AI may help interpret questions and retrieve relevant policy. |
| **EVIDENCE** | Policy PDFs; anonymized question categories; timing/volume estimates. Use fictional/public data for prototype. |
| **ALTERNATIVE** | Improve policy search/navigation + FAQ taxonomy without GenAI. |
| **RISK / CONTROL** | Risk: unsupported policy answer. Control: citation + "I don't know" + HR escalation for ambiguous cases. |
| **RECOMMENDATION** | **INVESTIGATE** — strong recurring problem with measurable value and controllable scope. |

*This six-block + recommendation layout is a ready-made structure for our one-slide summary.*

### Group 2 working checklist — updated for the eight components

- [ ] **#1 Problem + Stakeholder** — one specific pain, one named group who feels it
- [ ] **#2 Current Workflow** — what happens today, step by step; where the friction is
- [ ] **#3 Baseline + KPI** — a real baseline number, a target number, and a guardrail that must not get worse
- [ ] **#4 AI Fit** — primary capability from the six (classify / predict / recommend / generate / optimize / detect) and why it may help
- [ ] **#5 Evidence / Data Path** — sources, access, quality, constraints; **run the §11 readiness scorecard**
- [ ] **#6 Non-AI Alternative** — the simpler solution we are measured against
- [ ] **#7 Risk + Control** — one meaningful failure and its initial guardrail
- [ ] **#8 Recommendation** — investigate / reframe / reject, with a one-line reason
- [ ] Write the 1–2 page proposal
- [ ] Build the one-slide executive summary (use the slide 38 layout)
- [ ] Confirm no real customer, employee, health, financial, or confidential data is used
- [ ] **Submit by Thursday, September 17**

---

## 14. Assignments out of Week 3

### At-home activity — before Week 4

*Individual · ~30–45 minutes · use UH Gemini for Education with only the fictional data provided.*

| Step | Task |
|:---:|---|
| **A · MANUAL** | Write **six fictional customer messages** and classify each by hand: intent, sentiment, urgency, entities. **Generate them manually, not AI-generated** — we are evaluating the AI against our own judgment. |
| **B · GEMINI** | Run the provided structured prompt (§7, slide 18) on the messages. Compare AI output with your manual judgment. |
| **C · EVALUATE** | Identify **two disagreements/errors** and explain the **business consequence** of each. |

*Optional voice extension:* dictate one fictional message and compare the transcript with the original.

### Everything due before Week 4

- **MindTap Chapter 3**
- **At-home NLP activity** (above)
- **⭐ Milestone 1 — Opportunity Proposal + one-slide summary — due Thursday, September 17**
- **Next week:** Week 4 — Supervised Machine Learning for Business (Applied Lab 1 per syllabus)

---

## Key terms index

`NLP` · `natural language processing` · `ambiguity` · `tokenize` · `stem` · `POS tag` · `entity` · `named-entity extraction` · `sentiment` · `intent` · `urgency` · `classification` · `information extraction` · `summarization` · `translation` · `ASR` · `automatic speech recognition` · `speech recognition vs. language understanding` · `multimodal` · `Gemini` · `Goal/Context/Expectations/Source` · `structured data` · `unstructured data` · `AI factory` · `pipeline` · `train / validate / test` · `label` · `ground truth` · `data quality` · `accurate / complete / consistent / relevant / timely / traceable` · `representativeness` · `ownership / access / privacy / permission` · `data readiness scorecard` · `proxy discrimination` · `explainability` · `human review` · `Opportunity Proposal` · `investigate / reframe / reject`

---

*Notes generated from the Week 3 lecture PDF for team reference. The PDF in this folder is the authoritative source.*
