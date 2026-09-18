# B2B Commerce & Rewards

### Order ≠ Earned

In invoiced B2B commerce, placing an order doesn't necessarily mean money has changed hands. An order can be completed with **$0 collected at checkout**, while invoicing and financial validation happen later.

That creates a product question:

> **When should a partner see, earn, and be able to use their reward?**

---

## The Product Problem

If usable reward value is created when the order is placed, the reward can exist before the underlying financial activity has been validated.

If nothing appears until validation is complete, the partner has no acknowledgement that their qualifying activity was recognized.

The product has to separate **recognition of activity** from **availability of value**.

**Order → Invoice → Pending Validation → Available**

| Partner | Business |
| --- | --- |
| See that qualifying activity was recognized | Validate the underlying activity before creating usable value |
| Understand the current reward state | Avoid issuing value against activity that changes or becomes invalid |
| Know when value becomes usable | Keep reward value aligned with the transaction lifecycle |

---

## The Product Decision

**Separate reward recognition from reward availability.**

Qualifying activity creates reward value in **Pending Validation**.

Once the underlying activity is validated, that value becomes **Available**.

The pending state introduces additional lifecycle complexity, but avoids choosing between an opaque partner experience and premature reward issuance.

---

## Designing for Change

The original order isn't necessarily the final source of truth. The lifecycle also needs deterministic behavior when the underlying activity changes.

| Transaction outcome | Reward behavior |
| --- | --- |
| Activity validates | Pending Validation → Available |
| Qualifying value changes | Pending value recalculates before becoming available |
| Activity becomes ineligible | Pending Validation → Ineligible |

The rule stays consistent: **usable reward value represents validated qualifying activity, not simply an order event.**

---

## Measurement

### Primary

**Straight-through validation rate**

The percentage of qualifying rewards that progress accurately from Pending Validation to Available without manual intervention.

### Supporting measures

- Validation accuracy
- Time to availability
- Exception rate
- Reward-related support contacts

### Guardrails

- Incorrect reward value issued
- Usable value created against invalid activity
- Reconciliation exceptions

---

## The Broader Product Problem

A reward may look simple to the partner while depending on commerce, invoicing, financial validation, lifecycle state, and operational rules underneath it.

The product decision isn't simply **when to give someone a reward**. It's defining when that value becomes real, what the partner experiences before then, and how the system behaves when the transaction changes.

---

*This is a fictionalized product study based on product patterns I've encountered professionally. Companies, transactions, and implementation details are illustrative.*
