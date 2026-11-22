# Ship-or-Hold Memo · Ascend IQ

> **Decision:** HOLD

## The Answer

I recommend we hold the Ascend IQ release and approve the $85,000 hallucination eval, and ship once hallucinations fall below 5%. Today 9 of 20 answers invent information.

## The Arguments

### 1. It fails our release bar.

Evidence: The hallucination rate is 9 of 20 answers. That is nine times our 5% hard-gate limit, and a hard-gate failure blocks the merge.

### 2. Fixing hallucinations alone won't clear our quality bar.

Evidence: Two more of the 20 answers failed for other reasons: 1 on robustness and 1 on UX trust. Both are P1 risks.

### 3. We can afford to measure the fix.

Evidence: The $85,000 hallucination eval fits inside our $200,000 quarterly cap, even alongside the $70,000 robustness eval. Engineering removes the hallucinations, and this eval tells us whether the fix worked.

## Next Step · Decision Needed

Twenty answers is a small sample, but the gap is too wide to be chance. To get under 5% on 20 answers we would need zero hallucinations, and we got 9. The online eval will also test far more answers before we ship.

Please approve the hold and the $85,000 eval by November 27, 2026. I'll re-run the eval on the Ascend IQ golden set and bring you a ship-or-hold call by December 11, 2026.
