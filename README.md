# Metro Pulse · نبض المترو

A prototype that estimates how crowded Cairo Metro stations are, by line, day and half hour, and suggests a quieter time to leave. Works in English and Arabic (full right-to-left layout).

**Live demo:** https://khaled223s.github.io/metro-pulse/ (Arabic: add `#ar` to the end)

## How the estimate works

There is no public live ridership feed for the Cairo Metro, so the estimate comes from a rule-based model:

```
crowd = time-of-day curve × station pull × rush direction × line factor
```

- **Time-of-day curve:** separate shapes for Sunday to Wednesday, Thursday night, Saturday, Friday (with the midday prayer dip) and Ramadan (busy before iftar, near empty during it).
- **Station pull:** interchanges like Sadat, Al-Shohadaa and Attaba draw the most riders.
- **Rush direction:** outer stations peak in the morning, downtown stations in the afternoon.
- **Campus effect:** university stations get busier at class start and finish on weekdays.
- **Line factor:** Line 1 is the most crowded, Line 3 the least.

Scores are modeled, not live counts. Next step: let riders send quick "how full is it?" check-ins and blend them into the curves.

## Built with

One HTML file with plain JavaScript and inline SVG charts. No frameworks, no build step.
