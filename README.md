# Introduction to AI — Group 2

**MIS 7397 · Introduction to Artificial Intelligence for Business**
University of Houston · Fall 2026 · Section 27425

---

## Purpose

This is the shared working repository for **Group 2** in MIS 7397. It is where our team keeps everything connected to the course in one place, so all three of us are always working from the same version:

- **Course reference** — the syllabus, schedule, grading breakdown, and policies, so nobody has to dig through Canvas mid-week.
- **Capstone work** — our AI Opportunity-to-Deployment capstone as it develops across its milestones, from opportunity proposal through prototype, feasibility analysis, governance plan, and final report.
- **Applied labs and assignments** — code, notebooks, and supporting files for the three applied labs and any team deliverables.
- **A shared history** — every change is tracked, so we can see who changed what and when, and roll back if something breaks.

Using git means we avoid the usual group-project mess of `final_v2_REAL_final.docx` files traded over email. One source of truth, always current.

---

## Team — Group 2

| Member | GitHub | School Email |
|---|---|---|
| **Shaun Morris** | [@shaun-mo](https://github.com/shaun-mo) | sbmorri2@cougarnet.uh.edu |
| **Tyler Drummond** | [@tdrummond91](https://github.com/tdrummond91) | tsdrummo@CougarNet.UH.EDU |
| **Sarah Toups** | [@sarahtoups](https://github.com/sarahtoups) | scepeda4@CougarNet.UH.EDU |

All three of us have write access to this repository.

---

## Contents

| File / Folder | Description |
|------|-------------|
| **`Class Notes/`** | One folder per week — each holds the lecture PDF plus a markdown outline of it |
| ↳ `Wk 1 - Aug 27 26/` | The AI Shift — AI, Business & Competitive Transformation |
| ↳ `Wk 2 - Sep 3 26/` | From Turing to Business Opportunity — Ch. 2 + **Capstone Milestone 1** |
| [`hello-world.html`](hello-world.html) | Starter page — confirms the repo is live |
| `[Syllabus] Intro to AI.pdf` | Full course syllabus (source document) |
| `.env.local.example` | Template for local secrets — copy to `.env.local` |

**Adding a new week:** create `Class Notes/Wk N - <Mon D YY>/`, drop the lecture PDF in, and add a `Week-N-Notes.md` outline beside it. The notes files are written so teammates *and* AI agents can pull the lecture content without parsing the PDF.

---

## Course Information

| | |
|---|---|
| **Course** | MIS 7397 — Selected Topics in Management Information Systems |
| **Title** | Introduction to Artificial Intelligence for Business |
| **Section** | 27425 — Face-to-Face |
| **Term** | Fall 2026 |
| **Credit Hours** | 3 (Graduate) |
| **Instructor** | Sina Asadi, Department of Decision & Information Sciences |
| **Office Hours** | Announced on Canvas |
| **Prerequisites** | Graduate standing and approval of chair or program director |

> No prior programming experience is required.

---

## Course Objectives

This course prepares graduate business students to understand, evaluate, design, and responsibly lead AI-enabled initiatives. It emphasizes business problem framing, technical intuition, model evaluation, implementation, economics, governance, cybersecurity, and organizational impact.

By the end of the course, students will be able to:

1. Distinguish AI from conventional analytics, business rules, automation, machine learning, deep learning, and generative AI.
2. Translate an organizational need into a clearly scoped AI use case, decision, workflow, user, and measurable business objective.
3. Assess whether an AI approach is appropriate — and identify when a non-AI alternative is preferable.
4. Evaluate data readiness: quality, representativeness, privacy, ownership, access, and potential bias.
5. Explain the intuition behind supervised and unsupervised learning, recommendation systems, neural networks, language models, computer vision, RAG, and AI agents.
6. Interpret model and system performance using metrics that reflect business consequences — false positives, false negatives, cost, latency, reliability, and human review.
7. Use approved no-code / low-code tools to construct and evaluate a basic AI prototype or workflow.
8. Analyze the strategic and economic value of an AI initiative — feasibility, ROI, build-vs-buy, and implementation tradeoffs.
9. Identify ethical, legal, privacy, security, and societal risks and recommend appropriate governance, monitoring, and human-oversight controls.
10. Communicate AI recommendations clearly to executive, operational, and technical audiences.

---

## Required Materials

**Required textbook & courseware**

- Corinne Hoisington and Mark Ciampa, *Introduction to Artificial Intelligence: A Business Perspective*, 1st Edition, Cengage, 2026.
- **MindTap** for Hoisington/Ciampa, 1-term Instant Access — ISBN `9798214024332` (**required**; integrated with Canvas).

**Recommended (optional)**

- Kamales Lardi, *Artificial Intelligence for Business: Harness AI for Value, Growth and Innovation*, 1st Edition, Kogan Page, 2025 — ISBN `9781398618008`.

**Technology**

Laptop with a modern web browser, Microsoft Office or equivalent, and university- or instructor-approved AI and analytics tools. Additional readings, cases, and articles are posted in Canvas.

---

## Course Schedule

| Week | Topic | Major Assignment / Assessment |
|:---:|---|---|
| 1 | AI, Business, and Competitive Transformation | AI opportunity observation |
| 2 | From Business Problem to AI Problem | Capstone opportunity proposal |
| 3 | Data Foundations and the AI Factory | Data readiness exercise |
| 4 | Supervised Machine Learning for Business | Applied Lab 1 |
| 5 | Unsupervised Learning, Recommendations, and Personalization | Executive Memo 1 |
| 6 | Model Evaluation and Experimentation | Applied Lab 2 |
| 7 | Deep Learning, Natural Language, and Computer Vision | Current AI briefing |
| 8 | Generative AI and Large Language Models | **Midterm AI decision case** |
| 9 | Retrieval-Augmented Generation, Agents, and Intelligent Workflows | Capstone prototype plan |
| 10 | From Prototype to Production | Vendor evaluation memo |
| 11 | AI Across Business Functions and Industries | Applied Lab 3 / case briefing |
| 12 | AI Strategy, Economics, and Competitive Advantage | Capstone feasibility and value analysis |
| 13 | Responsible AI, Law, Privacy, Security, and Governance | Capstone governance plan |
| 14 | The AI-Powered Organization | Capstone draft / peer review |
| 15 | Capstone Presentations and the Future of AI | **Final report and presentation** |
| Finals | Course Integration and Reflection | Final assessment / capstone evaluation (per Canvas) |

> Topics may be adjusted during the semester to incorporate significant developments in AI.

---

## Capstone Milestone 1 — AI Opportunity Clinic

*From the Week 2 lecture. This is our current deliverable.*

> **Goal: produce a defensible candidate, not a finished solution.**

| Step | What it means |
|:---:|---|
| **1 · CHOOSE** | One recurring decision or workflow. |
| **2 · FRAME** | Pain · actor · workflow · baseline. |
| **3 · MATCH** | Primary AI capability + non-AI alternative. |
| **4 · TEST** | Five green lights + evidence/data source. |
| **5 · DEFINE** | KPI · target · one risk/guardrail. |

**Submission:** 1–2 pages + a one-slide summary.

⚠️ **This is an approval gate** — it must be approved before any prototype work begins, so slipping this milestone blocks everything downstream. Per the syllabus, team milestones may carry stricter deadlines than individual work.

### Team checklist

- [ ] **Choose** the recurring decision/workflow we're targeting
- [ ] **Frame** it — who feels the pain, who acts, what the current workflow is, what the baseline performance is
- [ ] **Match** — name the primary AI capability, and the non-AI alternative we're comparing against
- [ ] **Test** — clear all five green lights, cite our evidence and data source
- [ ] **Define** — the KPI, the target number, and one named risk plus its guardrail
- [ ] Write the 1–2 page submission
- [ ] Build the one-slide summary
- [ ] Submit for approval before starting prototype work

---

## Grading

| Component | Weight |
|---|---:|
| Concept Checks and Reading Quizzes | 10% |
| Applied AI Laboratories | 20% |
| Business Cases and Executive Memos | 15% |
| Midterm AI Decision Case | 15% |
| **AI Opportunity-to-Deployment Capstone** | **30%** |
| Participation and Current AI Briefings | 10% |
| **Total** | **100%** |

The capstone runs across multiple milestones: opportunity identification, data and feasibility analysis, prototyping, evaluation and governance, the final executive report, and the executive presentation. Rubrics are provided in Canvas.

---

## Key Policies

**Attendance & participation** — Regular attendance and active participation are expected; many activities are live demos, cases, labs, and team workshops. Attendance alone does not earn full participation credit.

**Late work** — Work submitted within 48 hours of the deadline may be accepted with a **10% deduction per calendar day or portion of a day**. More than 48 hours late normally receives no credit. **Team milestones may have stricter deadlines** because delays affect other students.

**Collaboration** — Encouraged where an assignment is designated collaborative. Individual submissions must reflect each student's own analysis and writing. Teams are expected to establish roles, communication norms, deadlines, and a process for resolving disagreements.

**Use of AI tools** — Permission is **assignment-specific**; each assignment states the authorized level of AI use. When permitted, students may be required to disclose the tool/model used, the purpose, important prompts, which outputs materially influenced the submission, how information was verified, and what the student independently contributed. Students remain responsible for every claim, citation, calculation, and recommendation submitted. Fabricated sources or results are unacceptable.

**Data security & privacy** — Projects must use public, synthetic, de-identified, licensed, or instructor-approved data. Do not enter confidential, proprietary, personally identifiable, health, financial, regulated, client, or employer data into an AI service without authorization and an approved secure environment.

**Regrades** — Submit in writing within 7 calendar days of the posted grade, identifying the specific rubric criterion. Scores may increase, stay the same, or decrease on re-evaluation.

**Communication** — Via Canvas and UH email. Put `MIS 7397` in the subject line; expect a response within two business days.

**Academic honesty** — All work must comply with the UH Academic Honesty Policy.

---

## Team Notes

**Working in this repo**

```bash
# One-time: get a copy on your machine
git clone https://github.com/shaun-mo/introduction-to-ai-team-2.git

# Every time you start work: get the latest changes
git pull

# After you make changes: save and share them
git add .
git commit -m "Describe what you changed"
git push
```

**Secrets** — Copy `.env.local.example` to `.env.local` and put your own keys there. `.env.local` is gitignored and must never be committed. Do not commit datasets containing confidential, proprietary, or personally identifiable information — see the data policy above.

---

*This README summarizes the official syllabus for team reference. The syllabus posted in Canvas is the authoritative version, and the instructor may revise it during the semester.*
