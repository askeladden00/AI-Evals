# Ascend IQ: Evaluating an AI Market-Intelligence Copilot

An end-to-end evaluation system for **Ascend IQ**, an LLM copilot that answers market-intelligence questions for enterprise strategy teams. It runs from trust metrics and a failure audit to automated checks, release gates, an eval budget and a ship-or-hold call. Built as the final project for Product School's AI Evals certification (November 2026), using the course's Ascend IQ case study.

> **Decision: HOLD.** Ascend IQ isn't ready to launch, because its 45% hallucination rate is nine times the limit our hard gate allows, and that alone blocks the release.

**[▶ View the final presentation](https://askeladden00.github.io/AI-Evals/06-culture/final-presentation.html)**

## Why it matters

Ascend IQ serves VP-level strategists at Fortune 500 companies who pay upward of $50,000 a year for verified market intelligence. They make decisions on its answers, so one made-up price or competitor fact can damage a key account. The audit found that 9 of 20 answers invented information, mostly flattering or out-of-date facts about pricing and competitors.

## How I evaluated it

| Step | What I did | Key result | Artifacts |
|---|---|---|---|
| **1. Strategy** | Defined the user promise, trust metrics and trade-offs | Hallucination rate is the top metric | [Strategy canvas](01-evaluation-strategy/strategy-canvas.md) · [Judge test](01-evaluation-strategy/eval-harness-proof.md) |
| **2. Failure audit** | Scored 20 real answers against their source material | 9 of 20 pass; 9 of the 11 failures are hallucinations | [Audit log](02-failure-discovery/audit-log.md) · [Failure taxonomy](02-failure-discovery/failure-taxonomy.md) |
| **3. Eval suite** | Built a rule check, a safety rule and an LLM judge for the top failure | All three caught it, with no false alarms | [Eval suite](03-eval-suites/eval-suite.md) · [Eval spec](03-eval-suites/eval-spec.md) |
| **4. Release gates** | Gave each failure a hard, soft or advisory gate | Hallucination must be under 5% or the release is blocked | [Gate map](04-eval-gates/gate-map.md) · [Launch strategy](04-eval-gates/launch-strategy.md) |
| **5. Scale** | Mapped coverage gaps and budgeted evals by risk | $165,500 planned within a $200,000 quarterly cap | [Coverage matrix](05-scale/coverage-matrix.md) · [Eval budget](05-scale/eval-budget.md) |
| **6. Decision** | Wrote the ship-or-hold memo for the CPO | Hold until the hallucination fix is measured | [Ship-or-hold memo](06-culture/ship-hold-memo.md) · [Presentation](06-culture/final-presentation.html) |

## Next steps

Hold the release and fund the $85,000 hallucination eval. Once engineering fixes the hallucinations, re-run the eval on the golden set and make a new ship-or-hold call by December 11, 2026.

**Limitations:** the audit covers 20 answers, and the checks were tested on one failing answer, so both need a larger sample before launch. The Module 5 coverage matrix uses the course's AI Voice Agent case rather than Ascend IQ.
