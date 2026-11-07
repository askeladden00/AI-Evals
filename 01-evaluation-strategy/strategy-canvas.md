# AI Evaluation Strategy Canvas

> Repo file `ai-evals/01-evaluation-strategy/strategy-canvas.md` (the repo is your submission).

## 1. Product Strategy, The Context

**Who it's for:** VP-level strategists and product leaders at Fortune 500 companies who pay upward of $50,000 a year for verified market intelligence.

**What they use it for:** Asking plain-language questions, like “Compare the pricing models of Stripe and Adyen,” and getting answers in seconds instead of digging through the platform.

**What's at stake:** Engagement is dropping, Q4 retention is at risk, and the CPO wants Ascend IQ live for the top 50 enterprise accounts next month. One poor answer to the wrong client can do lasting damage to the relationship.

## 2. Measurements, The Execution

**User promise.** For [VP-level strategist and product leaders], Ascend IQ promises to [provide verified market intelligence such as comparable pricing models] so that [engagement and retention of enterprise accounts can be tracked and flagged accurately and quickly when engagement is dropping].

**Top 3 trust metrics:**
- **Hallucination Rate**, % of outputs that are confidently false or fabricated.
- **Fairness**, Quality consistency across user groups, geos, languages.
- **Robustness**, Coherence on messy, adversarial, out-of-scope inputs.

**Why these three:** Hallucination Rate - decisions need to be made on verifiable accurate and not made up information

Fairness - the information provided across different cuts need to "add up" for consistent insights

Robustness - there needs to be guardrails on what can or cannot be input which will warn the user to prevent downstream false information

## 3. Strategic Trade-Offs, The Cost

### Trade-off 1 · Hallucination Rate ↔ Robustness
We prioritize Hallucination over Robustness because inaccurate information will lead to wrong business decision that will have long term effects on bottom line

### Trade-off 2 · Fairness ↔ Robustness
We prioritize Fairness over Robustness because data needs to be consistent (avoid double counting or missing data) across the platform and accounts

---
_Generated from the AI Evaluation Strategy Canvas, M1 lab tool, AI Evals Certification._