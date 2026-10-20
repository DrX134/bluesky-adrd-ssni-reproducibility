# Configuration files

This directory contains the cohort-construction specifications used by the public reproducibility notebooks.

## Historical broad retrieval

- `broad_keywords_minimized.txt`: 197 broad candidate terms used for the initial substring retrieval from English-language Bluesky posts.
- `keyword_rules_reviewed.xlsx`: the original manually reviewed keyword-frequency workbook supplied from the historical workflow.
- `keyword_rules_reviewed.csv`: browser-readable copy of the same three columns (`keyword`, `frequency`, `exact`).

The reviewed workbook contains 174 observed broad terms. The remaining 23 terms from the 197-term broad list had zero observed matches in the frequency table and therefore were absent from the review workbook.

Historical rule coding:

- `exact = 1`: word-boundary exact match (11 terms)
- `exact = 0`: exclude/skip the candidate term (5 terms)
- blank/NA: substring match (158 terms)

Notebook 00 applies these rules to the broad candidate set and reproduces the intended handoff logic:

`1,126,036 -> 422,011 -> 388,104` rows.

## Final revision cohort

- `original_20_revision_keywords.txt`: the 20-keyword revision definition before removing nonspecific brain-fog terms.
- `removed_nonspecific_keywords.txt`: `brain fog`, `foggy brain`, and `cognitive fog`.
- `final_17_keywords.txt`: final 17 inclusion terms used in the revised manuscript.
- `final_exact_match_keywords.txt`: terms treated with word-boundary exact matching in Notebook 01 (`ADRD`, `apoe`).
- `stage00_political_exclusion_terms.txt`: historical broad political/noise exclusions used before the Notebook 01 handoff.
- `stage01_additional_noise_exclusion_terms.txt`: additional final noise exclusions (`mcconnell`, `reagan`, `ebony`).

The public notebooks preserve the original analytical rules. The repository cleanup changes file organization and path portability only; it does not intentionally alter cohort definitions.
