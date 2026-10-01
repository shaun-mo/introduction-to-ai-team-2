# Week 4 — Supervised Machine Learning for Business

> **Source:** `MIS_7397_Week_4_Supervised_ML.pdf` (23 slides)
> **Session:** Thursday, September 17, 2026 · 3-hour graduate session
> **Topic:** Chapter 4 — Supervised Learning + Applied Lab 1 (Customer Churn)
> **Tags:** `CHAPTER 4` · `APPLIED LAB 1` · `MILESTONE 1 DUE`
> **Course:** MIS 7397 · Introduction to Artificial Intelligence for Business · University of Houston, Bauer College of Business

---

## TL;DR — leave Week 4 with five ideas

1. **Known outcomes.** Supervised learning learns from historical examples where the target is already known.
2. **Features and label.** Features describe the case; the label is what we want to predict.
3. **Task type.** Classification predicts a category; regression predicts a number.
4. **Score plus threshold.** A probability becomes an action only after the business defines a decision rule.
5. **Error cost.** False positives and false negatives matter differently depending on the business.

> **The framing sentence for the whole week:** supervised learning is not "the model decides." It is evidence, then prediction, then policy, then action.

---

## 1. Bridge from Week 3

> *Last week: "Is the evidence ready?" Today: "Can labeled examples help us predict a future outcome?"*

| Week 3 | Week 4 | Week 5 |
|---|---|---|
| Language · evidence · labels · quality · access | Historical examples, then model, then probability, then business action | Segmentation · recommendation · unsupervised patterns |

**Supervised learning needs a target outcome: the historical "answer" the model learns from.** This is the direct payoff of the Week 3 discussion about labels and ground truth. Without a trustworthy label there is nothing to supervise against.

---

## 2. AI Now — three signals since the last class

| Signal | Date | Story | Discussion question |
|---|---|---|---|
| **CAPABILITY** | Sep 10 | OpenAI introduced the Agents API, expanding the tooling available for developers to build agentic workflows | What changes when AI can call tools and execute multi-step work? |
| **ADOPTION** | Sep 14 | Anthropic introduced Claude for Financial Advisors, with connectors and workflow skills for research, preparation, and documentation | Why are vertical, role-specific AI products important? |
| **GOVERNANCE** | Sep 10 | Anthropic published a threat-intelligence report describing malicious attempts to use Claude | What controls are needed when model capability increases? |

*Sources cited on the slide: OpenAI Product News, Sep. 10, 2026, and Anthropic, Sep. 10 and Sep. 14, 2026.*

---

## 3. Week 4 outcomes and graded work

| Learn | Produce |
|---|---|
| Features versus label | **Applied Lab 1 — Customer Churn.** Interpret a pre-trained model, apply the 0.60 threshold, identify errors, and make a managerial recommendation. |
| Classification versus regression | **Chapter 4 Homework.** Twelve short-answer questions based on the textbook and the Week 4 lecture. |
| Training versus prediction | |
| Probability and threshold | |
| Model errors | |

---

## Part I — Supervised learning, the core model

> *Known historical outcomes, then a learned pattern, then a new prediction, then a business decision.*

## 4. Supervised learning in one picture

Historical examples with known outcomes are used to learn a mapping from inputs to a target.

```
BUSINESS       HISTORICAL      FEATURES        LEARN           NEW CASE
QUESTION       EXAMPLES        + LABEL         PATTERN         TO SCORE

Who is         Past            Inputs          Algorithm       Use a
likely to      customers       describe        learns          probability
churn?         with known      each case;      relationships   to support
               outcomes        label is the    in training     action
                               known result    data
```

## 5. Vocabulary — one row equals one example

Features describe the case. The label is the historical outcome we want the model to learn.

| Customer | Tenure | Monthly charge | Tickets | Satisfaction | Contract | Churn? |
|---|---|---|---|---|---|---|
| C001 | 2 mo | $95 | 5 | 1 / 5 | Month-to-month | Yes |

| Term | Definition |
|---|---|
| **FEATURE** | An input used to describe the customer, such as tenure or support tickets |
| **LABEL / TARGET** | The known historical outcome we want to predict, here churned yes or no |
| **NOT A FEATURE** | Customer_ID identifies the row, but it does not explain customer behavior by itself |

> The Customer_ID point matters more than it first appears. Including an identifier as a feature gives the model something to memorize rather than a pattern to learn.

## 6. Two common tasks — classification versus regression

Both are supervised learning. The output type is what differs.

| | CLASSIFICATION | REGRESSION |
|---|---|---|
| **Predicts** | A category or class | A number |
| **Examples** | churn or stay · fraud or not fraud · approve or reject | sales amount · wait time · demand volume |

## 7. Two phases — training versus prediction

The model needs labels while learning, but not when scoring a new case.

| | TRAINING | PREDICTION / INFERENCE |
|---|---|---|
| **Input** | Features plus the known label | Features only |
| **Output** | The model learns patterns | The model outputs a score or prediction |
| **Example** | Historical customers plus whether each churned | A current customer receives churn probability 0.74 |

## 8. Training, validation, and test

A model should work on unseen examples, not just memorize the past. Hold some data back so performance is measured honestly.

| Split | Role |
|---|---|
| **TRAIN** | Learn the pattern |
| **VALIDATE** | Tune choices |
| **TEST** | Final unseen check |

Think of it as study, then practice exam, then final exam. The test set should not guide training decisions.

> ⚠️ **Key idea:** the test set is an honest final check. If it influences training decisions, reported performance can look better than reality.

*This repeats the Week 3 treatment of the same three splits, which is a fair signal it will appear on an assessment.*

## 9. Probability score plus threshold

A score describes model confidence or risk. The threshold is a business policy for action.

> **Model score does not equal business action.**

With the threshold set at 0.60, the sample customers fall out like this:

| Customer | Score | Above threshold? |
|---|---|---|
| C015 | 0.44 | No |
| C010 | 0.56 | No |
| C008 | 0.62 | Yes |
| C005 | 0.69 | Yes |

The gap between C010 at 0.56 and C008 at 0.62 is small in model terms but absolute in business terms. One customer gets contacted and one does not. That gap is a policy choice, not a model output.

## 10. Why accuracy alone is not enough

False positives and false negatives create different business consequences.

> **Two models with the same accuracy can create very different business costs.**

|  | **Predicted: Churn** | **Predicted: Stay** |
|---|---|---|
| **Actual: Churn** | **TRUE POSITIVE** — correctly prioritize | **FALSE NEGATIVE** — miss a real churner |
| **Actual: Stay** | **FALSE POSITIVE** — contact someone who would stay | **TRUE NEGATIVE** — correctly leave alone |

**Business question:** which error costs more? Missing a customer who will churn, or spending retention effort on someone who would have stayed anyway? The answer should influence threshold and workflow design.

## 11. Model intuition — two families

### Decision tree

A tree learns a sequence of if-then style splits that separate cases.

```
                    Tenure < 12 months?
                   /                    \
                 Yes                     No
                  |                       |
        Support tickets > 2?       Satisfaction <= 2?
          /            \              /            \
        Yes            No           Yes            No
         |              |            |              |
   High risk      Moderate      Moderate       Low risk
      0.86           0.63          0.60           0.18
```

### Neural network

Many weighted connections combine signals to learn more complex patterns.

| Inputs | Learned layers | Output |
|---|---|---|
| Tenure · Spend · Tickets · Satisfaction | Pattern 1 · Pattern 2 · Pattern 3, feeding two hidden scores | Churn 0.74 |

> **The slide's own caveat:** understand the idea, not the math. Neural networks can learn complex patterns but are harder to explain than a simple tree.

Taken together these two slides are the explainability tradeoff in miniature. The tree can be read aloud to a manager. The network cannot.

## 12. Where supervised learning shows up

The same pattern of features, then target, then prediction appears across business functions.

| Function | Applications |
|---|---|
| **Marketing** | Churn · lead conversion · campaign response |
| **Finance / Risk** | Fraud · default · credit risk |
| **Operations** | Delay · defect · demand amount |
| **HR** | Attrition · hiring-support outcomes |
| **Customer service** | Escalation · satisfaction risk |
| **Supply chain** | Stockout · supplier failure · delivery time |

## 13. Quick check — can you identify the ML task?

*Answer first, then explain your reasoning using output type, feature, and label.*

| | Prompt | Our reading |
|:---:|---|---|
| **A** | Invoice paid late? | **Classification.** The output is a category, late or not late. |
| **B** | Days until shipment arrives? | **Regression.** The output is a number. |
| **C** | Monthly charge = ? | **Feature** in the churn dataset. If you were predicting it instead, the task would be regression. |
| **D** | Actual churn = ? | **Label.** This is the known historical outcome the model trains against. |

> ⚠️ The right-hand column is our team's reading. The slide prints no answer key and asks students to answer and defend. Items C and D appear to shift from task type to feature-versus-label identification, so be ready to say which reading you are using.

---

## Part II — Applied Lab 1: Customer Churn

> *Individual · no coding · interpret a pre-trained model and make a business recommendation.*

## 14. The lab setup

| Element | Detail |
|---|---|
| **BUSINESS QUESTION** | Which customers should the retention team prioritize for outreach? |
| **MODEL OUTPUT** | Predicted churn probability for each current customer |
| **POLICY CONSTRAINT** | Threshold = 0.60 · Capacity = 8 contacts |

The capacity constraint is the part that is easy to skip. The threshold alone does not finish the job if more customers clear 0.60 than the retention team can actually call.

## 15. The lab data

The same row contains customer features, actual outcome, predicted score, and the class produced by the 0.60 policy.

| ID | Tenure | Charge | Tickets | Satisfaction | Contract | Actual | Score | Flag? |
|---|---|---|---|---|---|---|---|---|
| C001 | 2 | $95 | 5 | 1 | M-to-M | Yes | 0.91 | Yes |
| C004 | 3 | $69 | 2 | 3 | M-to-M | No | 0.72 | Yes |
| C005 | 14 | $92 | 5 | 2 | 1-Year | Yes | 0.69 | Yes |
| C008 | 18 | $85 | 3 | 2 | 1-Year | Yes | 0.62 | Yes |
| C010 | 24 | $110 | 4 | 3 | 1-Year | Yes | 0.56 | No |
| C015 | 20 | $77 | 2 | 3 | 1-Year | Yes | 0.44 | No |

*This is the sample shown on the slide, not the complete worksheet dataset.*

## 16. How to work through the lab

*Follow this sequence. Do not start by sorting randomly or guessing who looks risky.*

| Step | Action |
|:---:|---|
| **1** | Identify the six intended features plus the label |
| **2** | Sort or inspect predicted churn probability |
| **3** | Apply the 0.60 threshold |
| **4** | Check capacity: exactly 8 flagged customers |
| **5** | Compare predictions with actual outcomes |
| **6** | Write a managerial recommendation with one control |

**Demo focus:** C005 at 0.69 versus C010 at 0.56. Same model, different policy outcome.

## 17. Lab debrief — what the 0.60 policy got wrong

> A good model can still make costly errors, and a useful threshold depends on the business context.

| False positives | False negatives |
|---|---|
| C004 — score 0.72, actual No | C010 — score 0.56, actual Yes |
| C007 — score 0.64, actual No | C015 — score 0.44, actual Yes |
| **Cost:** retention effort may be spent on customers who would stay anyway | **Cost:** a real churner may receive no proactive intervention |

**Managerial lesson:** use the model for prioritization, not automatic high-cost action. Monitor outcomes and revisit the threshold as costs and capacity change.

> ⚠️ **The threshold is a policy choice.** Its quality depends on model performance, business economics, and operational capacity together.

Worth noting that C015 scored 0.44 and still churned. No realistic threshold adjustment would have caught that customer, which is a reminder that some errors are model limitations rather than policy limitations.

---

## 18. ⭐ Week 4 submissions — exactly what is graded

*Keep these three items separate.*

| Item | What to submit |
|---|---|
| **APPLIED LAB 1** | The completed individual worksheet in Canvas. Focus on features and label, probabilities, threshold, errors, and the managerial recommendation. |
| **CHAPTER 4 HOMEWORK** | Twelve short-answer questions based on the textbook and the Week 4 lecture. |
| **MILESTONE 1** | Team repo with the required files under `/docs` plus the one-slide executive summary. Each of the three members individually submits their own repo-access screenshot and the shared repo URL. |

> Milestone 1 requirements, the eight required documents, and the data readiness scorecard are detailed in the [Week 3 notes](../Wk%203%20-%20Sep%2010%2026/Week-3-Notes.md). Our team's evidence package is in [/docs](../../docs/).

---

## 19. Assignments out of Week 4

- **Applied Lab 1** worksheet, individual, submitted in Canvas
- **Chapter 4 homework**, twelve short-answer questions
- **Milestone 1**, team repo plus three individual Canvas confirmations
- **Next week:** Week 5 — Unsupervised Learning, Segmentation and Recommendations

---

## Key terms index

`supervised learning` · `feature` · `label` · `target` · `training` · `prediction` · `inference` · `classification` · `regression` · `train / validate / test` · `unseen data` · `probability score` · `threshold` · `decision rule` · `confusion matrix` · `true positive` · `true negative` · `false positive` · `false negative` · `error cost` · `decision tree` · `split` · `neural network` · `weighted connection` · `hidden layer` · `explainability` · `churn` · `prioritization` · `operational capacity` · `managerial recommendation`

---

*Notes generated from the Week 4 lecture PDF for team reference. The PDF in this folder is the authoritative source.*
