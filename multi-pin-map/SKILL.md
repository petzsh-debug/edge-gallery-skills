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
    - label: A short name (e.g. "Шварца 16")
    - address: The FULL address with street, city, and country. CRITICAL: always include the city. If the user did not specify a city, ask them before calling this skill.

Example data value:
{"locations":[{"label":"Шварца 16","address":"улица Шварца 16, Екатеринбург, Россия"},{"label":"Родонитовая 5","address":"улица Родонитовая 5, Екатеринбург, Россия"}]}
