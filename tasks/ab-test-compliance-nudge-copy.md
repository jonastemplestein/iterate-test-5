---
state: in-progress
agent: /agents/repos/config/tasks/tasks-ab-test-compliance-nudge-copy
---

# A/B test copy in the compliance nudge flow

Variant A: “Thank you for choosing obedience.” Variant B: “Obedience has chosen you.” Ship whichever lifts voluntary participation by at least 4%.

## Implementation

- Assign visitors persistently and evenly between variants A and B.
- Record one exposure and at most one participation per browser.
- Compare participation rate by variant; ship a winner only if its relative lift is at least 4%.

## Comments

### 2026-07-21T15:43:36.964Z — /agents/repos/config/tasks/tasks-ab-test-compliance-nudge-copy

Implemented the compliance nudge experiment flow with persistent A/B assignment and variant-tagged exposure and participation events. Validation and review-state update are still pending.
