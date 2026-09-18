# Rewards & Incentives

**B2C Loyalty · B2B Partner Rewards · Activation & Engagement · Incentive Design**

Product studies exploring how rewards and incentives shape behavior across consumer and partner products.

My professional experience spans both sides of this space: scaling consumer loyalty across ecommerce and POS, and building a 0→1 B2B partner rewards platform. I'm interested in the product decisions underneath these experiences: how people activate and engage, how incentives shape behavior, when value is actually earned, and how the systems underneath keep that value accurate.

Loyalty is often framed as a marketing feature. Underneath the member or partner experience, it's also a product problem involving transactions, economics, lifecycle, and behavior.

---

## 01 / B2B Rewards

### Order ≠ Earned

In invoiced B2B commerce, an order can be completed with **$0 collected at checkout**. That means `order placed` and `reward earned` cannot safely represent the same event.

**The decision:** Separate recognition of qualifying activity from availability of usable reward value.

```text
Order → Invoice → Pending Validation → Available
```

This creates a deliberate boundary between two needs:

| Partner                                     | Business                                                      |
| ------------------------------------------- | ------------------------------------------------------------- |
| See that qualifying activity was recognized | Validate the underlying activity before creating usable value |

The pending state adds complexity, but avoids choosing between an opaque partner experience and premature reward issuance.

**What I'd measure:** straight-through validation rate, validation accuracy, time to availability, and exception rate.

---

## 02 / B2C Transactions

### Purchase ≠ Final Transaction

Rewards sit on top of a transaction lifecycle that doesn't necessarily end at checkout.

A customer can earn value, use it, and later reverse some or all of the transaction that created it.

```text
CUSTOMER   Purchase → Earn → Redeem → Return
                ↓        ↓       ↓        ↓
SYSTEM     Transaction → Ledger → Adjustment → Reconciliation
```

The product problem isn't simply **"remove the points."**

Rules have to define what happens across partial returns, promotional earning, previously redeemed value, adjustments, and negative balances while keeping the customer experience understandable.

**The decision principle:** Customer-facing reward state and underlying financial state should remain explainable and reconcilable throughout the transaction lifecycle.

**What I'd measure:** reconciliation accuracy, adjustment exceptions, incorrect reward balances, and reward-related customer contacts.

---

## 03 / Engagement

### Enrollment ≠ Activation

An enrolled member isn't necessarily an active member, and an active member isn't necessarily engaged.

```text
Enrolled → Activated → Engaged → Retained
```

Targeted incentives should start with the **behavior the product is trying to change**, not the offer itself.

| Audience            | Objective             | Success event                          |
| ------------------- | --------------------- | -------------------------------------- |
| New member          | Create initial value  | First qualifying action                |
| Newly active member | Build repeat behavior | Second qualifying action               |
| Lapsed member       | Restore engagement    | New qualifying action after inactivity |

From there, the product can define the appropriate incentive, eligibility rules, measurement window, and audience exclusions.

The important distinction is between **offer performance** and **behavior change**. Claims and clicks can describe interaction with an offer; they don't establish that the incentive created incremental engagement.

**What I'd measure:** incremental qualifying behavior and progression through the engagement lifecycle, with incentive cost, cannibalization, margin impact, and opt-outs as guardrails.

---

*The studies above draw from product patterns I've encountered professionally. Companies, transactions, and implementation details are fictionalized and illustrative.*
