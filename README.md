# Popote: one coupon budget that keeps customers

Group 7   Members: Saumya Joshi, Miguel Negron, Louise Caquelin, Carla Chaume

**In one sentence:** one weekly coupon budget, spent where it actually keeps customers: first a gesture for
customers delivered late, sized to the delay and their churn risk, then coupons for at-risk customers worth
winning back, until the budget is spent. Nobody gets two gestures in the same week.

- **Modules:** card D (the late-delivery apology) + card C (the coupon budget optimiser).
- **The decision it changes:** who gets a gesture or a coupon this week, and how much (the nightly pipeline,
  read by marketing every morning).
- **The KPI:** customers still ordering 30 days later per 1,000 € spent, targeted vs a held-out group.
- **The guardrails:** budget never exceeded; no customer with two gestures in a week; no gesture for an order
  that was not late; no decision on a score older than 24 h.
- **How it runs:** one more step in the nightly pipeline of lab 2, after `decide.py`. Batch, not real time.

## The repository

```
your-repo/
  PLAN.md                  our business case, one page, Mon 16 Nov (not graded); then three lines per session
  packaged_app/            our product: docker-compose.yml, README.md, the service folders we kept
  docs/BUSINESS.md         the pain, the decision, the KPIs, the value line, wrong by half
  docs/ARCHITECTURE.md     the functional view, the system view, the detailed architecture
  docs/DECISIONS.md        one record per trade-off; our numbers live here too
  docs/OPERATIONS.md       what we watch, the three likeliest failures, what ages
  docs/CLOUD.md            box by box in the cloud, the monthly bill (session 7)
  world/                   copied from the course, unchanged (the compose file reads it as ../world)
  platform/hub/            only if we keep the Control Room (read as ../platform/hub)
```

## Who owns what

| Part | Owner |
| --- | --- |
| `packaged_app/` (the product and its README) | ........ |
| `docs/BUSINESS.md` (and `PLAN.md`) | ........ |
| `docs/ARCHITECTURE.md` and `docs/CLOUD.md` | ........ |
| `docs/OPERATIONS.md` | ........ |

`docs/DECISIONS.md` is shared: each member writes the decisions of their part. Each member owns one part and
answers the question on it at the oral. The curveballs are not a file: we prepare them as a group
(`PROJECT.md`, section 10), one is picked live at the oral.

## Start here

1. [`PLAN.md`](PLAN.md): our business case, one page, sent Mon 16 Nov, before session 3.
2. [`packaged_app/README.md`](packaged_app/README.md): how to start the product with one command
   (`docker compose up` in `packaged_app/`).
3. `PROJECT.md` at the root of the course: the calendar and the oral (Fri 27 Nov).

## Status

| Date | Done | Next |
| --- | --- | --- |
| Mon 16 Nov | `PLAN.md` sent | `docs/BUSINESS.md`, first `DECISIONS.md` entry (batch vs real time) |
