---
name: budget-check
description: Review a ConnecXit event budget — estimates vs actuals, overruns, contingency left, and committed booking spend. Use when a planner asks how a budget is tracking, whether they can afford something, or where money is going.
---

# Budget check

Analyze one ConnecXit event's budget with `get_event_budget`, cross-checked against `get_event` bookings.

## Steps

1. Identify the event (`list_events` if the user didn't say which).
2. `get_event_budget` for line items; `get_event` for bookings and their agreed prices.
3. Work out:
   - Total budget, contingency (contingency % of total), and budget available after contingency.
   - Sum of estimates, sum of actuals, and remaining = available − max(estimate, actual) per line.
   - Lines over estimate, and by how much.
   - Bookings whose agreed price isn't reflected in a budget line (unbudgeted commitments).
4. If the user asks "can I afford X", compare X to the remaining amount and say what would have to give.

## Output

A small table (line, estimate, actual, variance), then three bullets: overall position, biggest risk, one suggestion. Use the event's currency.

## Notes

Read-only. Never invent numbers: if a line has no actual yet, say "not yet spent".
