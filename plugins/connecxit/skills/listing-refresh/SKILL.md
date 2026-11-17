---
name: listing-refresh
description: Review and improve a ConnecXit vendor's marketplace listing — offerings, descriptions and pricing — and apply agreed changes. Use when a vendor wants to update prices, add a package, retire an offering, or make their listing more appealing.
---

# Listing refresh

For vendor accounts. Uses `list_my_offerings`, `get_vendor` (their public profile as planners see it), `search_vendors` (comparable vendors), and `create_offering`, `update_offering`, `deactivate_offering`, `update_my_profile` (write permission).

## Steps

1. Read the current listing: `list_my_offerings`, and `get_vendor` for how it looks publicly.
2. Optionally compare with similar vendors in the same city (`search_vendors`, then `get_vendor` on two or three) for price ranges and how offerings are described.
3. Propose concrete changes as a list: offering, field, current value → new value, and why.
4. **Apply only what the vendor approves**, one tool call per change, and report each result. Use `deactivate_offering` (not deletion) to retire an offering; existing bookings keep their reference.

## Notes

- Prices are in the offering's currency; `priceFrom`/`priceTo` must be 0 or more.
- Don't copy competitors' descriptions; write the vendor's own.
