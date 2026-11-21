# Module 5 · Coverage Matrix · AI Voice Agent

## Coverage Row

| Product | Hallucination Rate | Fairness | Latency | UX Trust | Robustness |
|---|---|---|---|---|---|
| AI Voice Agent | ⚠️ Partial | ✅ Covered | ❌ Gap | ✅ Covered | ⚠️ Partial |

## What Runs Today

- An eval gate tests its answers to 300 billing questions before every release.
- A supervisor listens to 10 random calls a week for tone.
- A drift monitor alerts when callers start asking about things the agent wasn’t tested on.

## Accepted Gap

**Latency.** The response time when people are on the phone varies and people expect to wait on the phone, so a little more time will not affect user experience

We’ll look again: If the user drops the call or hangs up because they are waiting too long for a response.

## Critical Gap

We’ve flagged Latency as the most critical gap for AI Voice Agent because we saw an increase in dropped calls or customer hanging up due to unresponsiveness from the agent

## After the Pressure Test

Fairness should be changed because people's accents may affect how the agent responds to questions and may give the wrong answer or inaccurate information. Quality is of the most important feature of the agent.

UX Trust is covered because it is not applicable as these are actual phone calls and not on a screen unless we are judging the whole user journey during the call. If that is the case, then UX needs to be partial because each user journey is different and only 10 random checks will likely miss edge cases.
