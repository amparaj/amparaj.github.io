---
layout: default
title: Projects
permalink: /projects/
---

# Projects

These are side projects I've built outside work. Both the code and the write-ups are public.

{% for project in site.data.projects %}
{% include project-card.html project=project %}
{% endfor %}

## More about xP-FPL

xP-FPL is my personal FPL "assistant manager". It predicts how many points each player is likely to score, then uses those forecasts to plan the team week to week.

**What it does**

- **Team selection:** picks the formation, starting XI, bench order and captain.
- **Transfer advice:** checks whether a transfer is worth making, including whether a −4 hit pays off.
- **Chip strategy:** suggests when to play the Wildcard, Free Hit, Triple Captain and Bench Boost.
- **Risk:** runs Monte Carlo simulations to give a range of likely scores, not just one number.

**How it works**

1. Collects historical data and live data from the FPL API.
2. Builds features such as rolling form, per-90 rates and team strength ratings.
3. Predicts expected points with interchangeable models (MLP, GRU, LightGBM and a component-based ensemble).
4. Optimises the squad with integer linear programming (PuLP).
5. Simulates thousands of gameweeks to measure risk.

Forecasts, results and past performance are published at [amparaj.github.io/xpfpl](https://amparaj.github.io/xpfpl/). The code is at [github.com/amparaj/xpfpl](https://github.com/amparaj/xpfpl).

## More about F1 Stratbox

F1 Stratbox is my Formula 1 strategy desk. It turns live timing and historical data into race analysis and forecasts, so I can see why a race played out the way it did and what's likely to happen next.

**What it does**

- **Standings and title odds:** tracks Grand Prix and Sprint points separately, and simulates 10,000 seasons to estimate each driver's title chances.
- **Race analysis:** breaks down results lap by lap, including pit stop strategies, tyre degradation and where the "tyre cliff" hits.
- **Qualifying:** compares sessions sector by sector.
- **Forecasts:** gives pole, podium and win probabilities for the next race.
- **History:** covers every F1 season since 1950.

**How it works**

1. Collects lap timing, pit stops, race control and weather data from the OpenF1 API, plus calendar and historical data from FastF1 and Jolpica.
2. Adds weather forecasts from Open-Meteo.
3. Refreshes the data with GitHub Actions every 10 minutes across race weekends.
4. Publishes the results on a React + Vite website, with a local Streamlit dashboard for post-race reviews and a strategy sandbox to test pit stop timing and tyre choices.

Race results, analysis and forecasts are published at [amparaj.github.io/f1-stratbox](https://amparaj.github.io/f1-stratbox/). The code is at [github.com/amparaj/f1-stratbox](https://github.com/amparaj/f1-stratbox).
