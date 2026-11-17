---
name: event-briefing
description: Summarize where a ConnecXit planner's events stand — dates, bookings by status, what's still unbooked, and budget health. Use when a planner asks "where are we with my events", "what's still open", or wants a weekly status update.
---

# Event briefing

Give a ConnecXit planner a short, scannable status of their events, using the ConnecXit tools (`list_events`, `get_event`, `list_bookings`, `get_event_budget`).

## Steps

1. Call `list_events`. If the user named an event, work on that one; otherwise cover upcoming events (soonest first, at most five).
2. For each event, call `get_event` for its date and bookings, and `get_event_budget` if it has a budget.
3. Group bookings by status:
   - **Confirmed / deposited**: locked in.
   - **Enquiry / negotiating**: waiting on the vendor.
   - **Missing**: typical categories for this event type with no booking (for a wedding: venue, catering, photography, florals, music; for a corporate event: venue, catering, AV).
4. Budget: total, sum of estimates and actuals, and any line where the actual exceeds the estimate.

## Output

One block per event:

```
Spring Product Launch — Mar 4 (in 62 days), Austin
Booked: Lakeside Venue ($7,500, confirmed)
Waiting: Sunrise Catering (enquiry, no price yet)
Not started: AV, photography
Budget: $25,000 · estimated $24,100 · spent $7,500 — on track
Next: chase Sunrise Catering for a quote; shortlist AV vendors.
```

End with the two or three most urgent next actions across all events.

## Notes

- Read-only: this skill never changes anything.
- Payments and booking status changes aren't available through the connector; if the user asks, point them to connecxit.com.
