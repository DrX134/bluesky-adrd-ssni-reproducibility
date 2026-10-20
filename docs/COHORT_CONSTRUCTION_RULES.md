# Cohort construction rules and checkpoints

This document maps the two-stage cohort construction used in the revised analysis.

## Stage 00 — broad source reduction

1. Read the public Bluesky post archive.
2. Retain English-language posts.
3. Apply the 197-term broad substring list in `config/broad_keywords_minimized.txt`.
4. Historical checkpoint: **1,126,036** candidate rows.
5. Apply the reviewed exact/fuzzy/skip rules in `config/keyword_rules_reviewed.xlsx`.
   - exact terms: 11
   - skipped terms: 5
   - substring/fuzzy terms: 158
6. Historical checkpoint: **422,011** rows.
7. Remove posts containing the historical political/noise terms in `config/stage00_political_exclusion_terms.txt`.
8. Historical handoff checkpoint: **388,104** rows.
9. Save `data/processed/matched_subset_exact_fuzzy_no_political_5_7_new.parquet`.

The reviewed keyword-frequency workbook contains 174 observed terms. 23 terms in the original 197-term broad list had zero matches and therefore do not appear in the frequency workbook.

## Stage 01 — final manuscript cohort

Notebook 01 re-filters the 388,104-row handoff parquet using the revision-specific ADRD inclusion definition.

1. Original 20-keyword revision definition: **25,767** matching rows.
2. Remove `brain fog`, `foggy brain`, and `cognitive fog` as independent inclusion triggers.
3. Final 17-keyword definition: **19,830** matching rows.
4. Remove rows matching `mcconnell|reagan|ebony`.
5. Final revised cohort: **19,303** post records from **11,164** users.

The three removed nonspecific phrases do not act as automatic exclusion terms. A post containing one of them remains eligible if it also matches at least one of the retained 17 ADRD terms.

## Why both stages are retained

Stage 00 documents how the very large public source dataset was reduced to the historical candidate pool used by the study. Stage 01 documents the final revision-specific cohort definition used for every manuscript analysis. Both stages are included because the reviewer explicitly requested a reproducible path from the source dataset to the final ADRD analytic cohort.
