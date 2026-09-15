# Test Scenarios

## 1. High-Value Sales Lead

Input characteristics:

- recruitment automation request
- n8n and OpenAI
- approximately €5,000 budget
- three-week target

Expected result:

- intent: `sales`
- route: `sales_high_value`
- priority: `high`
- human review: required
- Gmail draft: created

## 2. Critical Support Incident

Input characteristics:

- production workflow unavailable
- possible missing customer records
- possible credential exposure
- business operations blocked

Expected result:

- intent: `support`
- route: `support_escalated`
- priority: `critical`
- human review: required
- Gmail draft: created

## 3. Approved FAQ

Question:

`What services do you provide?`

Expected result:

- intent: `faq`
- route: `faq_approved`
- response sourced from approved FAQ knowledge
- human review: not required
- draft: not required

## 4. Unsupported FAQ

Example:

A refund-policy question where no approved refund-policy knowledge exists.

Expected result:

- no unsupported answer generated
- route: `faq_human_fallback`
- human review required

## 5. Ambiguous Request

Input does not clearly indicate sales, support, or FAQ intent.

Expected result:

- route: `unknown_clarification`
- clarification requested

## 6. Invalid Input

Example:

Empty customer message.

Expected result:

- rejected before AI processing
- structured validation error returned

## 7. Invalid AI Output

Malformed or schema-invalid model output.

Expected result:

- AI validation failure path
- downstream automated routing blocked
- controlled error response returned