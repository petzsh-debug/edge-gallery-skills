---
name: multi-pin-map
description: Shows multiple addresses or locations as numbered pins on an interactive map.
---

## Instructions

When the user provides multiple addresses, places, or locations to display on a map, call the `run_js` tool with:
- script name: `index.html`
- data: A JSON string with field:
  - `locations`: an array of objects, each with `label` (short name) and `address` (full address including city and country)

Use this skill when the user says things like:
- "show these addresses on a map"
- "pin these locations"
- "покажи на карте"
- "отметь адреса"

Example invocation:
```json
{"locations": [{"label": "Kremlin", "address": "Red Square, Moscow, Russia"}, {"label": "Hermitage", "address": "Palace Square 2, Saint Petersburg, Russia"}]}
```

Always include city and country in addresses for accurate geocoding.
