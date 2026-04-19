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
    - address: The FULL address. CRITICAL rules:
      1. Format MUST be: `улица Название, номерДома, Город, Россия` — street first, then house number, then city, then country.
      2. Always include the city. If the user did not specify a city, ask them before calling this skill.
      3. Do NOT put city before street name.
      4. Do NOT put house number before street name.
      5. Use Russian street type prefix: "улица", "проспект", "переулок", "бульвар" etc.

Correct examples:
- "улица Ленина, 5, Каменск-Уральский, Россия"
- "проспект Победы, 12, Екатеринбург, Россия"
- "переулок Газетный, 3, Ростов-на-Дону, Россия"

WRONG (never do this):
- "Каменск-Уральский, улица Ленина 5" ← city must not be first
- "5 улица Ленина, Каменск-Уральский" ← number must not be first

Example data value:
{"locations":[{"label":"Шварца 16","address":"улица Шварца, 16, Екатеринбург, Россия"},{"label":"Родонитовая 5","address":"улица Родонитовая, 5, Екатеринбург, Россия"}]}
