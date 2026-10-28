# Common AI recommendation audit

**Reject.** Choosing the forest setting and threshold with 2026 results, then reporting that same 2026 score, makes it a selection score, not an independent test: the data were already used to decide. Training ending in 2021 does not fix this; independence depends on whether the scored data influenced any choice.
Evidence: threshold is chosen on dev by `choose_threshold` (`pitwindow_student_v2.py:55`), called in `evaluate_scores` (`lab03_support_v3.py:112`); `outputs/run_manifest_v3.json` records `"threshold_selection": "dev only; reused unchanged on train"`, so our dev numbers are selection results too.
`load_learning` (`lab03_support_v3.py:53-54`) only admits 2018–2021 and 2022 rounds ≤ 11; no 2026 data were obtained or run.

## Truthful use / no-use record

Tool and use, or “No AI used for this lab”:

If used, one actual suggestion (quote or faithful summary):
What we accepted/rejected:
Exact check performed and repository evidence:
One limitation relevant to this work:

Do not invent an error or interaction. No minimum number of prompts is required.

## Contributions

- Contributor 1, concrete action and related file/cell:
- Contributor 2, concrete action and related file/cell:
