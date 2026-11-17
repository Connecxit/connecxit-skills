---
name: availability-sync
description: Block or unblock dates in a ConnecXit vendor's availability, including from a pasted list or calendar export. Use when a vendor says they're booked, on holiday, or wants their ConnecXit availability to match their calendar.
---

# Availability sync

For vendor accounts. Uses `list_my_blocked_dates`, `block_date`, `unblock_date` (write permission).

## Steps

1. `list_my_blocked_dates` to see what's already blocked.
2. Turn the vendor's input into specific dates (YYYY-MM-DD). Accept ranges ("Dec 22–Jan 2"), weekdays ("every Sunday in March") or pasted calendar text; resolve relative dates against today and state the year.
3. Show the plan — dates to block, dates to unblock — and **confirm before changing anything**.
4. Apply with `block_date` (optional private reason) and `unblock_date` (using ids from step 1). Report successes and any failures.

## Notes

- Block reasons are private to the vendor; planners only see that the date is unavailable.
- Large ranges: confirm the count first ("this blocks 31 days").
