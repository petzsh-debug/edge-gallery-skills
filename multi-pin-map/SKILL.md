---
name: multi-pin-map
description: Show multiple addresses or locations as numbered pins on an interactive map.
---

# Multi-Pin Map

## Examples

- "Show these addresses on a map"
- "Pin these locations on a map"
- "Покажи на карте"
- "Отметь адреса на карте"

## Instructions

Call the `run_js` tool with the following exact parameters:

- data: A JSON string with the following field:
  - locations: An array of objects, each with:
    - label: A short human-readable name for the location
    - address: The full address including city and country (for accurate geocoding)

Example data value:
{"locations":[{"label":"Kremlin","address":"Red Square, Moscow, Russia"},{"label":"Hermitage","address":"Palace Square 2, Saint Petersburg, Russia"}]}
