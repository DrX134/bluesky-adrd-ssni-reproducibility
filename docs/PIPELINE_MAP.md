# Pipeline map

1. `00_data_filtering_reproducibility.ipynb`
   - public Bluesky posts -> English-language posts -> broad ADRD candidate retrieval -> reviewed exact/fuzzy rules -> historical political/noise exclusion
   - handoff: `data/processed/matched_subset_exact_fuzzy_no_political_5_7_new.parquet`
2. `01_main_revision_pipeline.ipynb`
   - refined final 17-keyword cohort -> interaction expansion -> follower enrichment -> social network -> semantic embeddings -> similarity network -> threshold sensitivity -> corrected semantic mapping
3. `02_downstream_analysis.ipynb`
   - user-topic bipartite summaries, no-topic audit, cross-network tests, figures/tables
4. `03_reviewer_validation_sampling.ipynb`
   - prespecified blinded semantic-pair sample and post-length audit
5. `03_1_human_validation_analysis.ipynb`
   - independent reviewer agreement, Cohen's kappa, stratum/cutoff summaries
6. `04_export_nodexl_figures.ipynb`
   - NodeXL export only; no community detection is rerun
7. `05_table2_keyword_extraction.ipynb`
   - candidate term extraction and manual-review sheet for Table 2
8. `06_manuscript_number_audit.ipynb`
   - final cohort-number consistency checks
