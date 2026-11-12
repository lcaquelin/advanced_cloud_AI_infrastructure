# Business case (one page, send it Mon 16 Nov, before session 3)

Group 7   Members: Saumya Joshi, Miguel Negron, Louise Caquelin, Carla Chaume

One page, short lines, not graded. Keep it at the root of your repository: it stays alive until the oral (the
session log at the bottom).

## The idea and its twist

- **Modules:** card D (the late-delivery apology) + card C (the coupon budget optimiser).
- **The idea:** one weekly coupon budget, spent where it actually keeps customers. First, customers delivered
  late get a gesture sized to the delay and their churn risk. The rest of the budget goes to at-risk customers
  worth winning back, the most valuable first, until the budget is spent.
- **Our twist:** delay gestures and retention coupons share **one** budget and **one** decision per customer:
  nobody gets two gestures in the same week, and the budget is never overspent.

## The pain (step 1)

- **Whose problem:** marketing and support, and Popote's margin. Illustrative: 2,000 € a week of coupons sent
  to everyone or at random. Many go to loyal customers who would order anyway, or to customers already gone.
  Late deliveries are compensated only when the customer complains, the same for everyone.
- **What it costs:** each customer lost is about 100 € of future margin; each wasted coupon is 8 €.
- **The decision that changes:** who gets a gesture or a coupon this week, and how much. Who decides: the
  nightly pipeline, read by marketing every morning.

## The KPIs (step 2)

- **Business metric:** customers still ordering 30 days later, per 1,000 € spent, targeted vs a held-out group
  that gets nothing. Target (illustrative): 1.5× better than coupons sent at random.
- **Value line:** customers kept × 100 € − gestures and coupons used × their cost. Wrong by half: if only half
  as many customers are kept, does it still pay?
- **Guardrails:** weekly budget never exceeded; 0 customers with two gestures in a week; 0 gestures for orders
  that were not late; no decision made on a score older than 24 h.
- **How we show it moved:** a held-out group, randomly chosen, gets nothing (A/B test, session 3). Compare its
  30-day churn with the targeted group's, on the same weeks.

## The bricks you think you'll use (step 5)

| Brick (and its session) | Why you need it |
| --- | --- |
| churn model (S1) | the churn risk of every customer, scored every night |
| database, ingest (S2) | delivery events: promised vs actual minutes, to spot late orders |
| pipeline, data tests (S2) | one more nightly step after `decide.py`: late gestures first, then coupons, within budget |
| decisions table (S2) | one action per customer, with `scored_at`, read by marketing in the morning |
| A/B + notify (S3) | the held-out group; send the gesture or coupon by push |
| dashboard (S3) | weekly spend, gestures sent, customers kept: targeted vs held-out |

**First choice (to record in DECISIONS.md):** everything runs in the nightly batch, not in real time. The
gesture arrives the next morning, not at delivery; in exchange, no new real-time box.

## Who owns what

| Member | Part owned |
| --- | --- |
| ........ | `packaged_app/` |
| Carla Chaume | `docs/BUSINESS.md` (and this PLAN.md) |
| ........ | `docs/ARCHITECTURE.md` and `docs/CLOUD.md` |
| ........ | `docs/OPERATIONS.md` |

---

## Session log (three lines after each session)

What you learnt today that's worth bringing into your product · what to watch out for (what could break, cost
or age) · what you change in your plan, if anything.

| Session | Worth bringing in | To watch out for | What we change |
| --- | --- | --- | --- |
| S3 | | | |
| S4 | | | |
| S5 | | | |
| S6 | | | |
| S7 | | | |
| S8 | | | |
