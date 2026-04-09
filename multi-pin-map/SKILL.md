---
name: Multi-Pin Map
description: Shows multiple addresses or locations as pins on an interactive map. Use this skill whenever the user provides a list of addresses, places, or locations they want to see on a map.
version: 1.0.0
author: custom
---

## Instructions

When the user provides multiple addresses, places, or locations (2 or more), extract all of them and invoke this skill.

Also use this skill if the user says things like:
- "show these addresses on a map"
- "pin these locations"
- "where are these places"
- "покажи на карте"
- "отметь адреса на карте"

Extract a short human-readable label for each location (street name, place name, or just a number if no name is given).

Invoke the skill using this exact JSON format inside a skill block:

```skill
{
  "locations": [
    { "label": "Название 1", "address": "полный адрес 1" },
    { "label": "Название 2", "address": "полный адрес 2" }
  ]
}
```

Always include as much address detail as possible (city, country) for accurate geocoding.
After invoking the skill, briefly confirm to the user how many locations you found.
