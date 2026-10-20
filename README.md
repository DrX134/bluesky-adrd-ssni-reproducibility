# Social-Semantic Network Integration of ADRD Discourse on Bluesky — Reproducibility Code

This repository contains the code and configuration used to construct the revised ADRD cohort and reproduce the social-network, semantic-network, user-topic, cross-network, and human-validation analyses reported in the manuscript.

## Source data

The source Bluesky dataset is publicly available from Failla and Rossetti's **Bluesky Social Dataset**, Zenodo DOI: `10.5281/zenodo.14669616
        
        `. The source data are not redistributed in this repository.

Place the required source files under `data/raw/` as described in `data/raw/README.md`.

## Run order

The primary notebook order is:

`00 -> 01 -> 02 -> 03 -> 03_1 -> 04 -> 05 -> 06`

See `docs/PIPELINE_MAP.md` for the role of each notebook and `docs/COHORT_CONSTRUCTION_RULES.md` for the complete source-to-cohort filtering logic.

### Core analysis

- `00_data_filtering_reproducibility.ipynb`: source-data filtering and historical 388,104-row handoff cohort
- `01_main_revision_pipeline.ipynb`: final 17-keyword cohort and core social/semantic analyses
- `02_downstream_analysis.ipynb`: bipartite, no-topic, community-topic, and cross-network analyses

### Reviewer validation and manuscript support

- `03_reviewer_validation_sampling.ipynb`: blinded semantic-pair validation sample and post-length audit
- `03_1_human_validation_analysis.ipynb`: independent-reviewer agreement and threshold summaries
- `04_export_nodexl_figures.ipynb`: NodeXL export utility for network figures
- `05_table2_keyword_extraction.ipynb`: candidate term extraction for Table 2, followed by documented human interpretation
- `06_manuscript_number_audit.ipynb`: final manuscript-facing cohort-number audit

## Cohort reproducibility

The public configuration now includes the original manually reviewed `keyword_frequency_4_23.xlsx` artifact as `config/keyword_rules_reviewed.xlsx`. It contains 174 observed terms from the 197-term broad list: 11 exact-match terms, 5 skipped terms, and 158 substring/fuzzy terms. The 23 broad terms not present in the workbook had zero observed matches in the generated frequency table.

Expected cohort checkpoints are:

`1,126,036 -> 422,011 -> 388,104 -> 25,767 -> 19,830 -> 19,303`

Details and interpretation are in `docs/COHORT_CONSTRUCTION_RULES.md` and `docs/EXPECTED_CHECKPOINTS.md`.

## Human validation

The repository includes `validation/threshold_pair_validation_ratings_only.csv`, which omits post text but retains the pair identifier, cosine similarity, prespecified stratum, and two independent blinded binary ratings. These fields reproduce the reported percent agreement, Cohen's kappa, and reviewer-specific stratum/cutoff summaries. No consensus adjudication was used in the final manuscript analysis.

## Environment

The executed core analysis used Python 3.12.7. Core package versions recorded during the final run are listed in `requirements.txt`.

## What is and is not included

Included: final analysis notebooks, keyword/exclusion configuration, small validation/summary outputs, and reproducibility documentation.

Not included: the full source Bluesky dataset, large intermediate parquet/embedding files, exploratory notebooks that did not contribute to the final manuscript, or raw human-validation post text.

## Repository packaging note

These public-facing notebooks were reorganized for path portability and removal of development-only cells. Analytical decisions, thresholds, seeds, cohort definitions, and frozen manuscript checkpoints were not intentionally changed. The computationally heavy source-data pipeline was not re-executed during repository packaging.

For audit details, see `docs/CODE_AUDIT.md`.
