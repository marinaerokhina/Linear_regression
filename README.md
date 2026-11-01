# Seoul Bike Sharing — Linear Regression

[Русская версия](README_RUS.md)

**Python · pandas · scikit-learn · Data cleaning · Regression**

University machine-learning lab exploring how weather and calendar information relates to hourly bicycle rentals in Seoul. The project includes an executed Jupyter notebook, the input dataset with intentionally introduced data-quality issues, the cleaned dataset, and a comparison of three linear-regression models.

## What was done

1. Inspected data types, distributions, missing values and relationships between columns.
2. Cleaned the input table, encoded categorical values and prepared numeric features.
3. Compared three linear regression models on a **70/30 random train/test split** (random state 8).
4. Evaluated predictions using MAE, RMSE and R²; plotted regression diagnostics.

| Model | Selected features | RMSE | R² |
| --- | --- | ---: | ---: |
| M1 | Air temperature | 529.195 | 0.2910 |
| M2 | Weather measurements | 493.450 | 0.3836 |
| M3 | Weather and calendar features | **430.192** | **0.5315** |

**Result:** M3 performed best in this experiment. Metrics are measured in the original target scale (hourly rented-bicycle count).

## Files

- [linear_regression.ipynb](linear_regression.ipynb) — complete notebook with saved outputs, figures and explanations.
- [SeoulBikeData_nan24_SIIiMO.csv](SeoulBikeData_nan24_SIIiMO.csv) — supplied teaching dataset containing intentionally introduced missing/incorrect data.
- [SeoulBikeData_prepared.csv](SeoulBikeData_prepared.csv) — result of the notebook's cleaning workflow.
- [README_RUS.md](README_RUS.md) — Russian documentation.

## Run

Install the packages in [requirements.txt](requirements.txt), then open `linear_regression.ipynb` with Jupyter. Run from the repository directory so that relative CSV paths resolve.

## Limitations

This is a **coursework experiment**, not a deployed prediction service. A random split may overestimate performance on genuinely future observations in a time series. The input is a modified teaching copy, not the untouched UCI original.

## Dataset and attribution

Based on [Seoul Bike Sharing Demand (UCI)](https://archive.ics.uci.edu/dataset/560/seoul+bike+sharing+demand), associated with V. E. Sathishkumar, *Seoul Bike Sharing Demand Prediction*, [Mendeley Data, V2 (2020)](https://doi.org/10.17632/zbdtzxcxvg.2). The course-provided input contains intentional data-quality modifications.
