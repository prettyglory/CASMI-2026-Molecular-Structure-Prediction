# CASMI 2026 — Version 14 Result

## Submission
- Kaggle notebook: **CASMI 2026 Submission**
- Version: **14**
- Status: **Succeeded**
- Method: **Fragment-Based Molecular Structure Ranking**
- Public score: **0.115**
- Previous Version 2 public score: **0.083**
- Absolute improvement: **+0.032**
- Relative improvement: **~38.6%**

## Method summary
The submission recomputes predictions from the competition `train.parquet`,
`test.parquet`, and `sample_submission.csv`.

The pipeline:
1. Builds a candidate structure library from the training data.
2. Estimates neutral precursor mass from supported adducts.
3. Filters candidate structures within 20 ppm.
4. Uses RDKit-based fragment matching on the strongest `[M+H]+` MS/MS peaks.
5. Ranks candidates by fragment-matching score, then precursor-mass error.
6. Uses mass-based ranking as a fallback.
7. Produces 25 unique SMILES predictions for every molecule.

## Offline Kaggle execution
The competition requires Internet access to be disabled. RDKit was therefore
installed from an attached offline wheel dataset before fragment scoring.

Offline wheel used:
`rdkit-2024.3.2-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl`

## Important note
The **0.115** value is the public leaderboard score. It is not necessarily the
final/private leaderboard result.
