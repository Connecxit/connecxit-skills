# ConnecXit skills

Sample skills for using [ConnecXit](https://connecxit.com) from your AI
assistant. They pair with the ConnecXit connector (`https://connecxit.com/api/mcp`),
which gives the assistant access to your ConnecXit account after you sign in
and approve it.

| Skill | For | What it does |
|---|---|---|
| [event-briefing](plugins/connecxit/skills/event-briefing/SKILL.md) | Planners | Status of your events: bookings, gaps, budget, next actions |
| [budget-check](plugins/connecxit/skills/budget-check/SKILL.md) | Planners | Estimates vs actuals, overruns, unbudgeted commitments |
| [vendor-shortlist](plugins/connecxit/skills/vendor-shortlist/SKILL.md) | Planners | Find and compare marketplace vendors for an event |
| [rfp-quote](plugins/connecxit/skills/rfp-quote/SKILL.md) | Vendors | Review RFPs and send quotes (asks before sending) |
| [listing-refresh](plugins/connecxit/skills/listing-refresh/SKILL.md) | Vendors | Improve offerings and pricing (asks before changing) |
| [availability-sync](plugins/connecxit/skills/availability-sync/SKILL.md) | Vendors | Block/unblock dates from a list or calendar (asks first) |

The connector can't make payments, payouts or refunds, or change a booking's
status; skills point you to connecxit.com for those. Vendor changes need the
"Update your vendor offerings…" permission, which you choose when connecting.

## Claude Code

```
/plugin marketplace add connecxit/connecxit-skills
/plugin install connecxit@connecxit
```

This installs the skills and the ConnecXit connector. Run `/mcp` and sign in
to ConnecXit when prompted. Then ask, for example, "brief me on my events" or
"what RFPs am I invited to?".

## Claude (claude.ai, desktop, mobile)

1. Add the connector: **Settings → Connectors → Add custom connector**, URL
   `https://connecxit.com/api/mcp`, then **Connect** and approve.
2. Add skills: zip a skill folder (e.g. `plugins/connecxit/skills/event-briefing`)
   and upload it under **Settings → Capabilities → Skills**.

## ChatGPT

Add the connector (Settings → Apps & Connectors; developer mode may be
required), then paste the instructions from [chatgpt/instructions.md](chatgpt/instructions.md)
into a Project or custom GPT's instructions.

## Writing your own

Each skill is a folder with a `SKILL.md`: YAML front matter (`name`,
`description` saying when to use it) and plain-language steps that name the
ConnecXit tools to call. Tools available:

- Everyone: `list_events`, `get_event`, `get_event_budget`, `list_bookings`,
  `get_booking`, `search_vendors`, `get_vendor`
- Vendors: `list_rfps`, `list_my_offerings`, `list_my_blocked_dates`
- Vendors with write access: `create_offering`, `update_offering`,
  `deactivate_offering`, `block_date`, `unblock_date`, `respond_to_rfp`,
  `update_my_profile`

Good practice: confirm with the user before any tool that changes data.

More: https://connecxit.com/connect · Support: support@connecxit.com
