# Module 5 · Eval Budget · Ascend IQ

**Quarterly budget cap:** $200,000
**Online eval spend:** $155,000 (2 of at most 3 online evals)

## Budget

| Failure | Trust metric | Risk | Level | Cost |
| --- | --- | :---: | :---: | ---: |
| Data Fabrication | Hallucination Rate | P0 | Online eval | $85,000 |
| Context Specificity | Robustness | P1 | Online eval | $70,000 |
| Overconfident Tone | UX Trust | P1 | Periodic audit | $6,500 |
| Data Bias | Fairness | P2 | Code-based check | $2,750 |
| Slow Answers | Latency | P3 | Code-based check | $1,250 |

## Downgrades

### Periodic audit · Overconfident Tone (UX Trust · P1)
- **Cheaper check:** Each week review 50 answers and check each sited source
- **Why it’s enough:** With enough sample set, we will understand a pattern that the agent is doing and can course correct if it is biased towards certain sources and answers. It also allows us to see whether the training data is gravitating the agent to certain answers.

### Code-based check · Data Bias (Fairness · P2)
- **Cheaper check:** On a monthly basis, run compare the data sets (prior month vs. current month) that the agent is using to see whether updates are needed
- **Why it’s enough:** By comparing the delta between the months, we will understand whether the agent is biased towards one or the other data sets and the necessary updates to the training data can be done.

### Code-based check · Slow Answers (Latency · P3)
- **Cheaper check:** Establish SLAs on how soon answers need to be given (in tiers). If the high risk SLA is triggered, it will be routed to necessary engineers. The lower tier SLAs will be counted and reviewed on a weekly basis to improve performance 
- **Why it’s enough:** With the lower tier SLA counts, the code can be updated to get faster responses to the customer.

