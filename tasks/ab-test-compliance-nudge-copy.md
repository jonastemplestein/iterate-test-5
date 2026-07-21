---
state: in-review
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

### 2026-07-21T15:45:20.570Z — /agents/repos/config/tasks/tasks-ab-test-compliance-nudge-copy

Ready for human review. Added a deployed compliance nudge A/B flow at [compliance--task-demo.iterate.app](https://compliance--task-demo.iterate.app/) with persistent random assignment, exact approved copy for variants A and B, and variant-tagged exposure and participation events on `/experiments/compliance-nudge-copy`. Event idempotency is tied to the browser assignment, preventing duplicate exposure or participation counts.

Validated the live deployment at commit `94f3bf3b4056824aa7998773f342cdfd201fd5b9`: assignment persisted across requests without resetting the cookie, the assigned copy remained stable, participation was recorded, and repeat participation was disabled. The experiment now needs traffic and analysis before selecting a variant; a winner should be shipped only if its relative participation-rate lift is at least 4%.
