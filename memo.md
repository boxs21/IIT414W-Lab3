# Recommendation to the Head of Strategy: rival pit-entry alert

**Recommendation: further checking, not live use yet.** The adjusted forest model (table below) is the best option we tested and is worth checking further, but it is not ready to steer race decisions. It can be used, at most, as a secondary "watch list" next to the strategists' own judgement.

**Decision it could support.** At the end of each lap, the alert flags rivals who may enter the pits within their next three laps, so the pit wall knows whom to watch more closely (for example before choosing to cover an undercut). It predicts what a rival will do; it does not say what our car should do.

**How we tested it.** We trained on 2018–2021 races and compared systems on the first 11 races of 2022. Every system could raise an alert on at most 10% of rival-laps (945 of 9,451). We count how many of the 370 real pit entries received at least one alert in the three laps before them.

**What we found (11 races of 2022).**

| System | Alerts | Alerts that were right | Pit entries warned |
|---|---:|---:|---:|
| Never alert | 0 | – | 0 of 370 |
| Historical lookup table | 931 | 27% | 94 of 370 (25%) |
| Original forest model | 945 | 36% | 140 of 370 (38%) |
| **Adjusted forest model** | **938** | **40%** | **159 of 370 (43%)** |

The adjusted model (each rule must be supported by at least 100 past laps, instead of 30) warned of 19 more pit entries than the original with slightly fewer alerts. Still, about 6 of every 10 alerts (562 of 938) were for rivals who did not pit in that window, and 211 of 370 entries got no warning.

**Most relevant weakness.** The model is blind to early stops: all 49 entries made on tyres 5 laps old or less got no warning. These are often the surprising stops (damage, penalties, weather) where help is most needed. Also, at Miami, a circuit missing from the 2018–2021 history, one race received 19% of all alerts and three of four were false.

**Main limitation.** The same 11 races were used to set each alert level and to choose the winner, so 43% is likely optimistic. The data are a historical record: they do not show whether lap and tyre data would arrive on time during a live race. The alert score is a ranking, not a reliable percentage chance, and we have not measured any positions or seconds gained.

**Next check.** Freeze this model and its alert level, then test it once on the remaining 2022 races that were not used here, reporting alerts per race, how many alerts were right, and pit entries warned, with separate figures for new circuits and early stops.
