# Expected analysis checkpoints

These values come from the executed study workflow and are included so reviewers can verify a rerun.

## Cohort construction

| Stage | Expected rows |
|---|---:|
| Broad ADRD candidate retrieval | 1,126,036 |
| After historical exact/fuzzy/skip keyword rules | 422,011 |
| After historical political/noise exclusion | 388,104 |
| Matching original 20-keyword revision definition | 25,767 |
| Matching refined 17-keyword definition | 19,830 |
| Final cohort after additional noise exclusion | 19,303 |

## Frozen manuscript-facing cohort counts

- unique authors/users: 11,164
- interaction posts: 13,065
- non-interaction posts: 6,238
- reply instances: 6,359
- repost instances: 6,590
- quote instances: 1,316
- interaction touchpoints: 14,265
- total likes: 681,664

## Social network

- full interaction network: 10,651 nodes, 12,640 edges
- largest connected component: 6,789 nodes, 9,914 edges
- CNM communities: 71
- modularity: 0.8380

## Semantic network at cosine threshold 0.70

- retained semantic nodes: 3,405 (45.1%)
- edges: 19,763
- communities: 188
- modularity: 0.7014
- top-5 share: 61.7%

## Human validation

- 200 post pairs, 50 per prespecified stratum
- percent agreement: 83.5%
- Cohen's kappa: 0.636
