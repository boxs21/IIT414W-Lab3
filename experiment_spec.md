# Expectation for one additional candidate

The five base results are supplied. This expectation concerns YOUR additional run.

- Base model: `forest_sqrt` (random forest, 150 trees, `max_features='sqrt'`, `max_depth=6`, `class_weight='balanced_subsample'`, seed 414).
- Parameter and old → new value (one allowed tuple): `min_samples_leaf` 30 → 100.
- Conditions held fixed: same CSV and train (2018–2021) / dev (2022 rounds 1–11) split, seed 414, the nine permitted `FEATURES`, the same preprocessing fitted on train only, every other forest setting (`n_estimators=150`, `max_depth=6`, `max_features='sqrt'`, class weights), and the same dev threshold rule (≤10% of dev opportunities alerted, maximise distinct eligible entries caught, then precision, then threshold). The numeric threshold is reselected on dev by that rule, so it may differ from the parent's 0.608.
- Have you already run this additional candidate? No. This expectation was written before the first run of the candidate.
- Expected effect and mechanism, written before the first additional run if it has not happened: A leaf must now hold at least 100 training windows instead of 30, so trees cannot isolate small groups (for example rare circuit/compound/tyre-life combinations). Leaf scores become averages over larger groups, so scores should be smoother and with more ties. We expect train event recall to fall a little from 0.520 (less in-sample fitting), and the train/dev gap to shrink. On dev we expect a small change in event recall around the parent's 0.378 (140/370), most likely equal or slightly lower (roughly 0.34–0.38), because the parent is already restricted by `max_depth=6` and leaf size 30 is not very small relative to 63,165 training rows. More ties could make the selected dev alert count land a bit further below the 945-alert budget.
- Other trials already made, if any, and how the final candidate was chosen: None. We chose this tuple because it changes only regularisation of the best base dev system (`forest_sqrt`) and tests whether its dev advantage depends on small leaves. No other tuple was run.

Keep this record after running, even if wrong. Explain actual results in “4. Explain your additional result”.
Do not rewrite an expectation as if it predicted a result already seen.
