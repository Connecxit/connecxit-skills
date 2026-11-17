---
name: rfp-quote
description: Help a ConnecXit vendor review RFPs they're invited to and send well-priced quotes. Use when a vendor asks about new RFPs, leads or requests, or wants to quote on one.
---

# RFP quote assistant

For vendor accounts. Uses `list_rfps`, `list_my_offerings`, `list_my_blocked_dates`, and `respond_to_rfp` (needs the vendor write permission granted when connecting ConnecXit).

## Steps

1. `list_rfps`. Show invitations first (title, date, city, budget range, requirements), then open requests.
2. For the RFP the vendor picks:
   - Check `list_my_blocked_dates` against the event date. If blocked, say so and suggest declining (`available: false`).
   - Match requirements to `list_my_offerings` and draft a price: per-person offerings × guest count (ask if unknown), staying inside the RFP budget range where possible, and say if it can't.
   - Draft short notes for the planner: what's included, options, anything assumed.
3. **Show the draft and get an explicit yes** before calling `respond_to_rfp`. Re-sending updates the quote.

## Notes

- If `respond_to_rfp` isn't available, the vendor connected without write access; they can reconnect ConnecXit and tick "Update your vendor offerings…".
- Quotes go to the planner; bookings, deposits and payments happen in ConnecXit, not here.
