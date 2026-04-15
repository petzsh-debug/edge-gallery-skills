---
name: weather-card
description: Show current weather and 3-day forecast as a visual card. Use when user asks about weather, temperature, rain, snow, wind, or forecast.
---

# Weather Card

## When to use

Use this skill when user asks: "погода", "какая погода", "будет дождь", "прогноз", "температура", or any weather question.

## Instructions

After loading this skill, call run_js immediately with these exact parameters:
- skillName: `weather-card`
- scriptName: `index.html`
- data: `{"location":"Екатеринбург"}` — or replace with the city the user asked about

**Important:** Do not write any text before calling run_js. Call run_js right away.

## Examples

User says "погода" → call run_js, skillName=weather-card, scriptName=index.html, data={"location":"Екатеринбург"}

User says "погода в Москве" → call run_js, skillName=weather-card, scriptName=index.html, data={"location":"Москва"}
