# Module 4 · Launch Strategy · Ascend IQ Copilot

## 4.0 Release Criteria

| Gate | Failure | Metric | Threshold | Dataset | Method | Runs at |
|---|---|---|---|---|---|---|
| Hard | Invented Suggestions and Information (#HALLUCINATION) | Hallucination Rate | < 5% | Ascend IQ golden set | LLM judge | Staging |
| Soft | Row 3 · Latency: exceeded the maximum response time | Latency | > 2 ms | Ascend IQ golden set | Code-based check | Pull Request |
| Advisory | Row 17 · Tone: slang detected | Count of slang keywords | >= 1 | Ascend IQ golden set | Human review | Staging |

## CI Gate Request for Engineering

- **Hard gate · Invented Suggestions and Information (#HALLUCINATION).** Check: the LLM judge, run on the Ascend IQ golden set at Staging. Measures: Hallucination Rate. Passes when: < 5%. On a fail: block the merge.
- **Soft gate · Row 3 · Latency: exceeded the maximum response time.** Check: the code-based check, run on the Ascend IQ golden set at Pull Request. Measures: Latency. Passes when: > 2 ms. On a fail: pause the release until the PM signs off on an override.
- **Advisory gate · Row 17 · Tone: slang detected.** Check: the human review, run on the Ascend IQ golden set at Staging. Measures: Count of slang keywords. Passes when: >= 1. On a fail: post a warning, and don't block.

## Mitigation Plan · Soft Gate

If our Soft gate fails (latency is 2 ms or more), I recommend a staged rollout because it will allow us to limit the slow answers to our internal team while we collect more data.
