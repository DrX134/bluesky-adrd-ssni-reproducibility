# Code audit and public-review readiness

The notebooks in `notebooks/` are organized as a public-facing reproduction pipeline rather than a record of every exploratory or failed analysis. Development-only cells, personal absolute paths, and stale duplicate logic were removed where possible while preserving the final analytical decisions.

| Notebook | Role | Public-review status | Main dependency |
|---|---|---|---|
| `00_data_filtering_reproducibility.ipynb` | Raw Bluesky posts to 388,104-row handoff cohort | Ready for code review | Public post archive + reviewed keyword rules |
| `01_main_revision_pipeline.ipynb` | Final 17-keyword cohort, social network, semantic network, threshold sensitivity | Ready for code review | Stage-00 handoff parquet + followers file |
| `02_downstream_analysis.ipynb` | Bipartite, no-topic, cross-network, effect-size and downstream figure analyses | Ready for code review | Notebook 01 outputs |
| `03_reviewer_validation_sampling.ipynb` | Blinded 200-pair sampling and post-length audit | Ready for code review | Frozen Notebook 01 outputs |
| `03_1_human_validation_analysis.ipynb` | Agreement, Cohen's kappa, stratum and cutoff summaries | Ready for code review | Completed independent reviewer ratings |
| `04_export_nodexl_figures.ipynb` | NodeXL-compatible exports for network figures | Ready for code review | Notebook 01 outputs |
| `05_table2_keyword_extraction.ipynb` | Candidate term extraction for Table 2 | Ready for code review; includes documented human interpretation step | Notebook 01 outputs |
| `06_manuscript_number_audit.ipynb` | Final manuscript-facing cohort-number audit | Ready for code review | Stage-00 handoff parquet |

## Static checks completed during repository packaging

- All public notebooks parse as valid Python code cells.
- Notebook outputs were cleared to avoid committing large or identifying rendered outputs.
- Personal Windows/OneDrive absolute paths were removed from executable code.
- Notebook 01 output filenames required by Notebooks 02, 03, 04, and 05 are explicitly referenced in the upstream notebook.
- The final manuscript checkpoints are listed in `EXPECTED_CHECKPOINTS.md`.
- The original reviewed `keyword_frequency_4_23.xlsx` artifact has been restored as `config/keyword_rules_reviewed.xlsx`.

## What was not done during packaging

The heavy pipeline was not rerun against the 235-million-post source archive during repository cleanup. The repository therefore distinguishes between (a) code cleanup/path portability and (b) re-execution of the computationally expensive source-data pipeline. Frozen manuscript counts are preserved as explicit checkpoints for any independent rerun.
