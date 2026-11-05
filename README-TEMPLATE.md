# README-TEMPLATE — the dictionary "Join the proofreading" section

_Created: 05-11-2026 · Last updated: 05-11-2026_

Drop-in boilerplate for any sanskrit-lexicon dictionary repository README: an
enthusiast on-ramp that funnels Sanskrit readers into digitisation verification.
Copy everything between the two COPY markers into your README, fill the slots,
and vendor the three visuals once (see [Vendoring the visuals](#vendoring-the-visuals)).
Pilot: [MWS](https://github.com/sanskrit-lexicon/MWS) — copy freely from its README.

## Dictionary-specific slots

| Slot | Fill with | MW example |
|---|---|---|
| `{{DICT_NAME}}` | Dictionary title and author | *A Sanskrit-English Dictionary*, Monier-Williams 1899 |
| `{{DICT_CODE}}` | Lower-case dict code used by the observatory | `mw` |
| `{{REPO}}` | Repository name | `MWS` |
| `{{Cologne_DISPLAY}}` | The dictionary's Cologne web display URL | `https://www.sanskrit-lexicon.uni-koeln.de/scans/MWScan/2020/web/webtc/indexcaller.php` |
| `{{READING_GUIDE}}` | The dictionary's reading guide on csl-guides | `https://sanskrit-lexicon.github.io/csl-guides/users/reading-monier-williams` |

Progress numbers stay out of this template on purpose: the progress card SVG
carries its own snapshot citation, and every other number belongs to the repo's
own dated sections (readme-truth-pass).

<!-- ==================== COPY FROM HERE ==================== -->

## Join the proofreading

{{DICT_NAME}} was digitised by hand from the printed book, and the text is
checked against the page scans one entry at a time. You can help at any level —
no git, no setup, no Sanskrit-degree required to start.

> [!TIP]
> **The three-step ladder.** ① [Spot an error](#-spot-an-error--no-git-needed)
> → ② [Verify an entry against the scan](#-verify-an-entry-against-the-scan)
> → ③ [Prepare the change file](#-prepare-the-change-file). Start at ①; stop
> whenever you like — every rung is a real contribution.

### ① Spot an error — no git needed

Reading the dictionary and comparing it with the printed page **is** the work.
When the digital text and the scan disagree, open one correction issue:

**[Report a correction](https://github.com/sanskrit-lexicon/{{REPO}}/issues/new?template=data-correction.yml)**

The form asks only for the headword, the reading you see, the reading you
expect, and your evidence. What to collect before you click:
[Report a Typo](https://sanskrit-lexicon.github.io/csl-guides/contributing/report-a-typo).

### ② Verify an entry against the scan

Turn a reported error into a verified one: find the source line, compare it
with the printed scan, and decide whether it is a digital typo, a print
correction, a markup problem, or a question. The walkthrough holds your hand
through one full case (a real `mw` entry, start to finish):
[Process One Correction](https://sanskrit-lexicon.github.io/csl-guides/contributing/process-one-correction).

### ③ Prepare the change file

Corrections are never typed into the dictionary directly — they travel as small
change files with an audit trail, reviewed and applied in monthly batches:
[the correction workflow](https://github.com/sanskrit-lexicon/csl-corrections/blob/main/docs/correction-workflow.md).

### How a correction travels

![From printed page to correction and back](docs/assets/pipeline.svg)

![Dictionary progress](docs/assets/progress-{{DICT_CODE}}.svg)

![One real correction, before and after](docs/assets/correction-example.svg)

### Use the dictionary

Browse {{DICT_NAME}} online at the [Cologne display]({{Cologne_DISPLAY}}), or
learn to read entries the way lexicographers built them:
[the reading guide]({{READING_GUIDE}}).

<!-- ==================== COPY TO HERE ==================== -->

## Vendoring the visuals

All three images are committed static SVG — no external badge services, no
client-side rendering. `docs/assets/` is relative to your README.

1. **Pipeline diagram** (`pipeline.svg`) and **before/after panel**
   (`correction-example.svg`) are dictionary-independent: copy them from the
   pilot repo [MWS `docs/assets/`](https://github.com/sanskrit-lexicon/MWS/tree/master/docs/assets).
2. **Progress card** (`progress-{{DICT_CODE}}.svg`) is generated from the
   committed OBS-T snapshot — regenerate, do not hand-edit:

   ```bash
   python ../csl-observatory/tools/render_readme_visuals.py --dict {{DICT_CODE}} --out docs/assets/progress-{{DICT_CODE}}.svg
   ```

   The card carries its own snapshot citation; refresh it monthly, riding the
   [correction-batch PR](https://github.com/sanskrit-lexicon/csl-corrections/blob/main/docs/BATCH_RUNBOOK.md).

_Dr. Mārcis Gasūns_
