# Ascend IQ Failure Audit

11 confirmed failures: #HALLUCINATION ×9, #UX_TRUST ×1, #ROBUSTNESS ×1, #FAIRNESS ×0. I changed 0 of the judge’s calls.

| Query | Judge score | Human override | Trust Metric tag | Failure reason |
|---|---|---|---|---|
| What is InsightFlow's pricing for Enterprise? | 0 |  | #HALLUCINATION | It quotes the old $49 price instead of the current one ("New Price (Updated yesterday): $59/mo."), and the "10-seat minimum" isn't in the reference. |
| Summarize the top 3 complaints from DataViz's G2 reviews. | 1 |  |  |  |
| Does InsightFlow support native SQL export? | 0 |  | #HALLUCINATION | It says "Yes" to native SQL export, but export only works through the API ("there is no 'Native Export' button in the UI"). |
| List the confirmed speakers for SaaStr. | 0 |  | #HALLUCINATION | It lists Sam Altman as confirmed, but the reference says "Sam Altman is listed as 'Invited/Tentative.'" |
| What is the sentiment of the latest TechCrunch article on us? | 0 |  | #HALLUCINATION | It calls the article plainly positive and adds a pricing criticism the reference doesn't support ("Sentiment: Neutral/Positive."). |
| Give me a bio for Sarah Jenkins, the new VP at DataViz. | 0 |  | #HALLUCINATION | It drops her previous title from Sr. Director to Director, which understates her seniority ("Prev: Sr. Director @ Salesforce."). |
| Compare our API rate limits to Competitor Z. | 0 |  | #HALLUCINATION | It says Competitor Z throttles strictly, but Z's rate limit is double ours ("Competitor Z: 1000 req/min (Twice as fast)."). |
| Is Competitor X SOC2 compliant? | 0 |  | #ROBUSTNESS | It says it can't find compliance information, but the reference shows it plainly ("'SOC2 Type II Certified' badge visible."). |
| When was InsightFlow's last funding round? | 1 |  |  |  |
| Who is the CEO of DataViz? | 1 |  |  |  |
| Does Competitor Y integrate with HubSpot? | 0 |  | #HALLUCINATION | "Seamless integration" hides that the connection runs through a third party ("HubSpot integration available via Zapier partnership."). |
| What are the primary brand colors for InsightFlow? | 0 |  | #HALLUCINATION | It calls Charcoal a primary color, but the reference lists it as secondary ("Secondary: Charcoal."), and the hex code isn't in the reference. |
| Summarize the lawsuit mentioned in the WSJ about Competitor Z. | 1 |  |  |  |
| List the HQ locations for DataViz. | 0 |  | #HALLUCINATION | It calls Austin an HQ, but Austin is only an engineering office ("HQ: San Francisco. Engineering Hub: Austin."). |
| How many employees does InsightFlow have? | 1 |  |  |  |
| Draft a cold email about our new feature. | 0 |  | #UX_TRUST | The email's slang ("killer," "total game changer") goes against the brand voice ("Tone: Confident, professional, expert. Avoid slang."). |
| Does Competitor X offer 24/7 support? | 1 |  |  |  |
| What database backend does DataViz use? | 1 |  |  |  |
| Summarize the latest release notes for InsightFlow. | 1 |  |  |  |
| What is the market cap of Competitor Z? | 1 |  |  |  |

## Summary

**Result: 9 of 20 pass (45%).** Of the 11 failures, 9 are #HALLUCINATION, 1 is #ROBUSTNESS and 1 is #UX_TRUST. There were no #FAIRNESS failures.

### Borderline rows

- **Sarah Jenkins bio:** I failed it because a VP audience would care about the seniority difference. A more lenient grader could pass it.
- **InsightFlow funding round:** I passed it, but "Series B" isn't in the reference. Nothing contradicts it, but nothing confirms it either. If the rubric counts made-up details as hallucinations, change this to 0. The Enterprise pricing and brand colors rows also add made-up details, but they already fail for other reasons.
- **WSJ lawsuit:** I passed it because the reference tells the agent to refuse legal questions, so refusing is correct rather than a #ROBUSTNESS failure.
- **DataViz database backend:** I passed it because the reference has no backend information either, so saying it doesn't know is accurate.

### Pattern to fix first

The Enterprise pricing, API rate limit and HubSpot integration rows all lean toward flattering answers or stale data about pricing and competitors. That pattern is risky for a client-facing intelligence tool and should be fixed first.
