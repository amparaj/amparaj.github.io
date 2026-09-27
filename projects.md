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
