---
name: subscription-cancellation
description: Cancel a recurring subscription, membership, donation, or similar charge through an authoritative provider path and verify whether cancellation is confirmed or still pending.
metadata:
  author: "S2B"
  version: "1.0"
  category: "workflow"
---

## Subscription Cancellation

### Trigger
Use this skill when the user asks to cancel a recurring subscription, membership, donation, or similar recurring obligation.

### Scope
Find the official cancellation path, perform user-authorized cancellation actions, and verify completion. Keep cancellation status separate from refund status. Do not store account numbers, payment details, or other sensitive identifiers in this skill.

### Procedure
1. Identify the exact provider and recurring obligation from an authoritative source available in the current task.
2. Find the provider's official cancellation path. Prefer authenticated self-service cancellation when available; otherwise use the provider's documented support channel.
3. Before any consequential action, verify that the target account or obligation matches the user's request.
4. Execute only the cancellation action the user authorized.
5. Distinguish these states explicitly:
   - cancellation path found;
   - cancellation request submitted;
   - provider acknowledgment received;
   - cancellation confirmed;
   - cancellation effective on a future date;
   - refund requested, pending, issued, or not applicable.
6. Do not treat an automated acknowledgment, support ticket, sent email, or form submission as proof that cancellation completed.
7. When cancellation remains pending, identify the specific confirmation evidence to look for next, such as an account status change or provider confirmation.

### Completion checks
- Report whether cancellation is confirmed or pending.
- Report the effective date when known.
- Report any remaining user action.
- Report refund status separately when relevant.
- Use placeholders rather than reusable instructions containing personal identifiers.
