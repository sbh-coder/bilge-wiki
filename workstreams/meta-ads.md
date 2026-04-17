---
summary: Meta is the primary performance channel; iOS budget consolidated here from Google, Arab ad sets saturated, revenue parameter accuracy under review.
status: Active
last_updated: 17.04.2026
---

# Meta Ads

## Current Status

- Primary channel for HC and KSA iOS campaigns after ~$22K/week Google iOS budget moved to Meta (Apr 9).
- HC iOS CPA: $72 — improved.
- Arab ad sets: frequency 19x and 28x — heavily saturated (threshold: 3.5). Ameya decision: continue till Thu Apr 17. Review results Fri Apr 18.
- PMAX equivalent: not Meta-native; see [[workstreams/google-ads]].
- Vertical purchaser segments: now sent directly from DB to Meta — added to campaigns by Eda (Apr 14). Confirm with Satpal + Ishika + Yana.

## Key Initiatives

- **Meta revenue parameter check**: Verify value/revenue being sent with purchase event (app + web). Critical for ROAS accuracy. With Eda — follow up on status.
- **HC A/B creative test**: 9 creatives (6 new + 3 existing). Setup Apr 15 as high priority. See [[experiments/hc-creative-ab-test]].
- **Lookalike audiences**: Re-created 2 lookalike audiences after Baris flagged issue — explanation provided.
- **iOS TEMU campaign**: Clicks but 0 installs (0.29-0.45% install rate) — Ameya context: Meta budget moved here. Monitor.
- **Meta API cost stitch**: Sent to Melanie — awaiting reply for dashboard integration.

## Blockers

- Revenue parameter accuracy unconfirmed — ROAS numbers may be unreliable until resolved.
- FB events vs real events hygiene check still pending.

## Open Items

| Item | Owner | Status |
|---|---|---|
| Meta revenue parameter check (app + web) | Eda | In progress |
| Arab ad sets saturation review | Bilge | Due Fri Apr 18 |
| FB events vs real events hygiene check | Bilge | Pending |
| Meta API cost stitch | Melanie | Awaiting reply |
| Vertical purchaser segment confirmation | Satpal/Ishika/Yana | Pending |

## Backlinks

- [[workstreams/hc-campaigns]] — Primary HC channel
- [[workstreams/ksa-campaigns]] — iOS budget moved here
- [[experiments/hc-creative-ab-test]] — Active creative test
- [[people/eda]] — Ads implementation
- [[people/ameya]] — Performance lead
