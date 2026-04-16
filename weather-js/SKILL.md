---
name: weather-js
description: Get current weather and 3-day forecast as text. Use when user asks about weather, temperature, rain, snow, wind, or forecast.
---

# Weather

## When to use

Use this skill when user asks: "погода", "какая погода", "будет дождь", "прогноз", "температура", or any weather question.

## Instructions

Call run_js immediately with these exact parameters:
- skillName: `weather-js`
- scriptName: `index.html`
- data: `{"location":"Екатеринбург"}` — replace with the city the user asked about

**Do not write any text before calling run_js. Call run_js right away.**

After run_js returns, output the result text exactly as received. Do not change it.

## Examples

User says "погода" → call run_js, skillName=weather-js, scriptName=index.html, data={"location":"Екатеринбург"}

User says "погода в Москве" → call run_js, skillName=weather-js, scriptName=index.html, data={"location":"Москва"}

User says "погода в Сочи" → call run_js, skillName=weather-js, scriptName=index.html, data={"location":"Сочи"}
