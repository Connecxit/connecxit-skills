---
name: vendor-shortlist
description: Build a shortlist of ConnecXit marketplace vendors for an event need (e.g. caterers in Austin under a budget), comparing ratings, offerings and price ranges. Use when a planner asks to find, compare or recommend vendors.
---

# Vendor shortlist

Find and compare vendors with `search_vendors` and `get_vendor`.

## Steps

1. Pin down the need: category, city, date, budget, guest count. Ask once if category or city is missing; otherwise use the event's details (`get_event`).
2. `search_vendors` with `category` and `city` (add `verified: true` if the user wants only verified vendors).
3. For the top five or so, call `get_vendor` to read offerings (price type and range), reviews, and blocked dates near the event date.
4. Rank by fit: available on the date, price within budget (per-person prices × guest count), rating and review count.

## Output

A comparison table — vendor, rating (reviews), relevant offering, estimated cost for this event, available on the date — then a recommended top three with one line each on why.

## Notes

- Read-only. To contact or book a vendor, the planner uses connecxit.com (send an enquiry or post an RFP there).
- Estimated cost is an estimate from listed prices; say so.
