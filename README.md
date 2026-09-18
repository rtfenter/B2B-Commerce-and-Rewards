# B2B Commerce & Rewards

### Order ≠ Earned

In invoiced B2B commerce, placing an order doesn't necessarily mean money has changed hands. An order can be completed with **$0 collected at checkout**, while invoicing and financial validation happen later.

That creates a product question:

> **When should a partner see, earn, and be able to use their reward?**

---

## Where Should Value Become Real?

There are several reasonable points in the commercial lifecycle where a reward could be recognized. Each solves a different problem.

| Event | Advantage | Problem |
| --- | --- | --- |
| **Order placed** | Immediate partner feedback | Financial activity hasn't been validated |
| **Invoice created** | Connects the reward to billing | Qualifying value can still change |
| **Financial validation** | Strongest source of truth | Partner receives no acknowledgement while waiting |

The product decision isn't just which event is technically available. It's which event should determine **what the partner sees** and which should determine **when value becomes usable**.

---

## Approaches Considered

### Make the reward available at order

**Benefit:** Immediate value and the simplest partner experience.

**Tradeoff:** Creates spendable value before the underlying financial activity has been validated.

### Wait until validation

**Benefit:** Usable reward value always reflects validated activity.

**Tradeoff:** Qualifying activity can appear to produce nothing while the commercial lifecycle progresses.

### Recognize now, make available later

**Benefit:** Acknowledges qualifying activity immediately while preserving financial validation before value becomes usable.

**Tradeoff:** Introduces another lifecycle state that partners and internal teams need to understand.

---

## The Product Decision

**Separate reward recognition from reward availability.**

Qualifying activity creates reward value in **Pending Validation**.

Once the underlying activity is validated, that value becomes **Available**.

**Order → Invoice → Pending Validation → Available**

This creates a deliberate boundary between two needs:

| Partner | Business |
| --- | --- |
| See that qualifying activity was recognized | Validate the underlying activity before creating usable value |
| Understand the current reward state | Avoid issuing value against activity that changes or becomes invalid |
| Know when value becomes usable | Keep reward value aligned with the transaction lifecycle |

The additional state creates some product complexity, but avoids choosing between an opaque partner experience and premature reward issuance.

---

## Commercial Lifecycle ↔ Reward Lifecycle

*[Lifecycle visual: commercial events across the top, corresponding reward states underneath.]*

The two lifecycles are related, but they are not the same.

The commercial system establishes what happened financially. The rewards system translates those events into a partner-facing value state.

That separation allows the reward experience to acknowledge activity without treating every upstream event as final.

---

## Designing for Change

The original order isn't necessarily the final source of truth. The product also needs deterministic behavior when the underlying activity doesn't follow the happy path.

| Transaction outcome | Reward behavior |
| --- | --- |
| Activity validates | Pending Validation → Available |
| Qualifying value changes | Recalculate while Pending |
| Activity becomes ineligible | Pending Validation → Ineligible |
| Validation is delayed | Remain Pending |
| Account state changes | Evaluate against separate account lifecycle rules |

The core rule stays consistent:

> **Usable reward value represents validated qualifying activity, not simply an order event.**

Separating account-state behavior is also deliberate. A transaction changing and an account becoming suspended are different product events with different consequences, even when both affect the same reward.

---

## Measurement

### Primary

**Straight-through validation rate**

The percentage of qualifying rewards that progress accurately from Pending Validation to Available without manual intervention.

A high straight-through rate indicates that normal qualifying activity can move through the lifecycle without operational repair.

### Supporting measures

- **Validation accuracy** — does available value reflect the validated qualifying activity?
- **Time to availability** — how long does qualifying value remain pending?
- **Exception rate** — how often does the normal lifecycle require intervention?
- **Reward-related support contacts** — where is the lifecycle creating partner confusion?

### Guardrails

- Incorrect reward value issued
- Usable value created against invalid activity
- Reconciliation exceptions

---

## What I'd Validate

The lifecycle solves the system problem, but the partner experience still needs validation.

- Do partners understand what **Pending Validation** means?
- Does showing pending value reduce uncertainty compared with showing nothing?
- How frequently does qualifying value change before validation?
- At what validation delay does the experience begin creating confusion or support demand?

Those findings would inform how prominently pending value should appear, what explanation it needs, and whether different transaction conditions require different expectations.

---

*This is a fictionalized product study based on product patterns I've encountered professionally. Companies, transactions, and implementation details are illustrative.*
