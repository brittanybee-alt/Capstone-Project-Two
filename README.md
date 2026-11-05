# Where You Grow Up Matters: Predicting Adult Income for Low-Income Children in the DC Region

Springboard Data Science Career Track, Capstone Two.

## The question
Which neighborhood characteristics are most closely tied to adult income for children who grew up in low-income families, and can they help a foundation or community development agency decide where to focus first?

**Outcome:** `kfr_pooled_pooled_p25`, the mean household income rank (0 to 1) at ages 31 to 37 of children born 1978 to 1983 whose parents were at the 25th income percentile.
**Scope:** 735 census tracts in DC, Prince George's County (MD), and Arlington, Fairfax, and Alexandria (VA).
**Data:** Opportunity Atlas tract outcomes and Opportunity Insights tract covariates (opportunityatlas.org, opportunityinsights.org).

## Key results
| | |
|---|---|
| Final model | Linear regression (chosen by the one-standard-error rule) |
| Cross-validated R-squared | 0.745 (+/- 0.017), MAE 3.1 percentile points |
| Test R-squared (147 held-out tracts) | 0.833, MAE 2.8 percentile points |
| Baseline (guess the average) | MAE 7.1 percentile points |
| Strongest signals | share Black residents, household income (2000), share Asian residents, foreign-born share |

Average outcome by area: Virginia 0.51, Maryland 0.40, DC 0.37. Most of that gap is explained by neighborhood conditions, and the findings are associations, not causes.

## Repository guide
| Step | File |
|---|---|
| 1. Data wrangling | `DC_Capstone_Data_Wrangling.ipynb` |
| 2. Exploratory data analysis | `DC_Capstone_EDA.ipynb` |
| 3. Pre-processing and training data | `DC_Capstone_Preprocessing.ipynb` |
| 4. Modeling | `DC_Capstone_Modeling.ipynb` |
| 5. Final report (PDF) | `Capstone_Final_Report.pdf` |
| Model metrics | `model_metrics.txt` |

## How to run
Open the notebooks in Google Colab in order and upload the raw CSVs when prompted (the first notebook lists them). Each notebook saves its outputs to `data/processed/`, which the next one reads.

## Figures
Figures in the report: income rank by state, correlations with the outcome, predicted versus actual on the test set, and the final model's standardized weights.

## Limitations
Neighborhood-level associations only; 735 tracts; outcomes (born 1978 to 1983) predate the predictors (2000 to 2015); overlapping predictors make individual weights unstable.
