# Routing Policy

## Intent Classes

The workflow supports four top-level intents:

- `sales`
- `support`
- `faq`
- `unknown`

## Confidence Policy

Routing decisions use explicit confidence thresholds.

High-confidence classifications may proceed to deterministic routing.

Lower-confidence or ambiguous cases can be prevented from automatic routing and directed toward clarification or human handling.

## Sales

Sales enquiries are scored using deterministic rules based on extracted signals such as:

- budget
- deadline
- urgency
- scope clarity

The resulting route may include:

- `sales_high_value`
- normal sales handling

High-value leads require human review before consequential external communication.

## Support

Support scoring considers signals including:

- service outage
- reported data loss
- possible security exposure
- business impact

Critical incidents may be routed to:

`support_escalated`

These cases require human review.

## FAQ

FAQ answers are restricted to enabled approved knowledge entries.

The model cannot freely invent an FAQ answer.

Possible routes include:

- `faq_approved`
- `faq_human_fallback`

## Unknown

Requests that cannot be reliably assigned to sales, support, or FAQ are routed for clarification rather than being forced into an incorrect category.

Example route:

`unknown_clarification`