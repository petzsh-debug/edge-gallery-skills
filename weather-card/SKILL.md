---
name: weather-card
description: Show current weather and 3-day forecast as a visual card. Use when user asks about weather, temperature, rain, snow, wind, or forecast.
---

# Weather Card

Shows current weather and a 3-day forecast as a visual card in chat.

## Examples

- "погода"
- "какая погода?"
- "будет дождь?"
- "прогноз на три дня"
- "погода в Москве"

## Instructions

Call `run_js` with:
- scriptName: `index.html`
- data: a JSON string with field `location` — the city name from the user's message. Use `"Екатеринбург"` if no city was specified.

Example data: `{"location":"Екатеринбург"}`

Present the result as-is — a weather card will appear in chat.
