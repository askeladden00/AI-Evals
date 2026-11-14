# Eval Suite · Invented Suggestions and Information

## P0 failure (carried from Module 2)

**Failure:** Invented Suggestions and Information (#HALLUCINATION). It lists Sam Altman as confirmed, but the reference says "Sam Altman is listed as 'Invited/Tentative.'"

- **Row:** 4
- **Query:** List the confirmed speakers for SaaStr.
- **Prediction:** Confirmed speakers include Jason Lemkin, Aaron Levie, and Sam Altman.
- **Reference:** Source: Agenda. Lemkin and Levie confirmed. Sam Altman is listed as "Invited/Tentative."

## The three checks

**Rule check.** Looks at: question, answer, reference. Passes when: Check speakers against official confirmed speakers Fails when: If the speaker is not on the official confirmed speaker list, then it is a fail

**Safety rule.** Looks at: answer, reference. Passes when: The speaker is on official confirmed list Fails when: If the speaker is NOT on the official confirmed list. If the speaker's status is "invited", "tentative", or "declined"

**Judge.** Looks at: question, answer, reference. Passes when: looks at the question, the answer and the official confirmed speaker list. It passes when the answer matches the official confirmed speaker list. Fails when: It fails when the answer and reference contradicts the official confirmed speaker list OR the speaker has the status of "invited", "tentative", or declined.

## Results on the 20 Ascend IQ answers

| Check | Caught | Missed (rows) | False alarms (rows) | My P0 row |
|---|---|---|---|---|
| Rule check | 1 of 1 | None | None | Caught it |
| Safety rule | 1 of 1 | None | None | Caught it |
| Judge | 1 of 1 | None | None | Caught it |

**Judge on my P0 row:** Sam Altman is listed as confirmed, but the reference marks him "Invited/Tentative"; only Lemkin and Levie are confirmed.

## Where the failure was caught

The failure were caught by all three checks: Rule Check, Safety Rule, and the Judge. It means that the the Rule Check, Safety Rule and the Judge had very robust language/instructions to catch the failure

## What I'd ship next

I would look at edge cases such as speaker responses from other mediums such as email or text to confirm whether he/she had already replied/confirmed than the official list.

## Row by row

| Row | Rule | Safety | Judge | Judge reason |
|---|---|---|---|---|
| 1 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 2 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 3 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 4 | 0 | 0 | 0 | Sam Altman is listed as confirmed, but the reference marks him "Invited/Tentative"; only Lemkin and Levie are confirmed. |
| 5 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 6 | 1 | 1 | 1 | Sarah Jenkins is named as an executive, not as a speaker, so there's no speaker status to check. |
| 7 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 8 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 9 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 10 | 1 | 1 | 1 | Mark Johnson is named as CEO, not as a speaker, so there's no speaker status to check. |
| 11 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 12 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 13 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 14 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 15 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 16 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 17 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 18 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 19 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
| 20 | 1 | 1 | 1 | No speakers named, so nothing contradicts a confirmed speaker list. |
