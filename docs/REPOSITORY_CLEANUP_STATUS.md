# Repository cleanup status

| Component | Status | Notes |
|---|---|---|
| `00_data_filtering_reproducibility.ipynb` | CLEANED | Repository-relative paths; historical rules preserved |
| `01_main_revision_pipeline.ipynb` | CLEANED | Final 17-keyword cohort and frozen analysis pipeline |
| `02_downstream_analysis.ipynb` | CLEANED | Bipartite/cross-network downstream analysis |
| `03_reviewer_validation_sampling.ipynb` | CLEANED | Blinded semantic-pair sampling + post-length audit |
| `03_1_human_validation_analysis.ipynb` | CLEANED | Independent reviewer ratings; no consensus step |
| `04_export_nodexl_figures.ipynb` | CLEANED | Export utility; does not rerun community detection |
| `05_table2_keyword_extraction.ipynb` | CLEANED | Candidate extraction; manual interpretation step documented |
| `06_manuscript_number_audit.ipynb` | CLEANED | Frozen manuscript cohort-number audit |
| `config/keyword_rules_reviewed.xlsx` | RESTORED | Original reviewed workbook; 174 observed keyword rows |
| Raw Bluesky data | NOT INCLUDED | Correct: public source dataset is linked, not redistributed |
| Heavy pipeline re-execution after cleanup | NOT PERFORMED | Intentional; public packaging did not rerun the full source archive |
