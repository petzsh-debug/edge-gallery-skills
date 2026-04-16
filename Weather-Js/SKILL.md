---
name: weather
description: Get current weather and short forecast for the requested location.
---

# Weather

Use this skill when the user asks about weather, temperature, rain, snow, wind, or a short forecast.

## Instructions

**If run_js is available** (offline/on-device chat): call run_js immediately with:
- skillName: `weather`
- scriptName: `index.html`
- data: `{"location":"Екатеринбург"}` — or replace with the city the user asked about

Then output the returned result text directly. Do not add anything before or after.

**If run_js is not available** (online chat with web fetch):
- Use web fetch to get weather data.
- Prefer Meteoblue for Yekaterinburg.
- If Meteoblue is unavailable, times out, returns invalid JSON, or does not contain the needed current/forecast fields, fallback to Open-Meteo.
- Answer in Russian.
- Keep the answer short and practical.
- Format the answer according to the output rules below.

## Sources

### Primary source for Yekaterinburg: Meteoblue

Use this source first for Yekaterinburg:
https://my.meteoblue.com/packages/basic-1h_basic-day?apikey=uf7AWT0t9lb3IeqZ&lat=56.8573&lon=60.6153&asl=278&format=json

### Fallback source: Open-Meteo

Use this only if Meteoblue is unavailable or incomplete:
https://api.open-meteo.com/v1/forecast?latitude=56.8573&longitude=60.6153&current=temperature_2m,apparent_temperature,wind_speed_10m,wind_direction_10m&daily=temperature_2m_max,temperature_2m_min,precipitation_sum,precipitation_probability_max,wind_speed_10m_max,wind_direction_10m_dominant&timezone=Asia%2FYekaterinburg&forecast_days=3

## Output rules

For a simple request like "погода", answer in this format:

Источник: meteoblue
Город 
Сейчас: X°C (ощущается как Y°C)

Пн
🌡️ День/ночь: A°C / B°C
🌬️ Ветер: N м/с, НАПР (градусы)
🌧️ Осадки: M мм (P%)

Вт
🌡️ День/ночь: A°C / B°C
🌬️ Ветер: N м/с, НАПР (градусы)
🌧️ Осадки: M мм (P%)

Ср
🌡️ День/ночь: A°C / B°C
🌬️ Ветер: N м/с, НАПР (градусы)
🌧️ Осадки: M мм (P%)

💡 Совет дня: короткий практичный совет по погоде.

## Field mapping

### Meteoblue
- Current temperature: current.temperature
- Feels like: current.feelslike
- Day max/min: daily.temperature_max / daily.temperature_min
- Wind: daily.windspeed_mean or daily.windspeed_max, plus daily.winddirection
- Precipitation: daily.precipitation
- Precipitation probability: daily.precipitation_probability

### Open-Meteo
- Current temperature: current.temperature_2m
- Feels like: current.apparent_temperature
- Day max/min: daily.temperature_2m_max / daily.temperature_2m_min
- Wind: daily.wind_speed_10m_max and daily.wind_direction_10m_dominant
- Precipitation: daily.precipitation_sum
- Precipitation probability: daily.precipitation_probability_max

## Fallback behavior

- Try Meteoblue first for Yekaterinburg.
- If Meteoblue fails, use Open-Meteo automatically.
- In the first line, write the actual source used:
  - `Источник: meteoblue`
  - `Источник: Open-Meteo`
- Preserve the same response format regardless of source.