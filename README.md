# Credit Risk Modeling & Profit Optimization

## Overview

This project investigates how credit approval decisions can be optimized
for expected bank profit rather than model accuracy alone.

The analysis uses a Kaggle Credit Risk Dataset and evaluates:

- Data quality and missing-value bias
- Credit risk prediction
- Random Forest classification
- Decision threshold optimization
- Expected Monetary Profit (EMP)
- Cost-sensitive training
- Out-of-sample model evaluation

## Key Results

| Metric | Result |
|---|---:|
| Cleaned dataset | 32,576 |
| Default rate | 21.82% |
| Test AUC | 0.912 |
| Optimal threshold | 0.40 |
| Test profit | $1,449,533 |
| Gain vs. 0.50 threshold | +$323,413 |

## Data Quality

76% of interest-rate values were corrupted in the source data.

The corruption was not randomly distributed:

- Grade A: 98.2% corrupted
- Grade B: 98.0% corrupted

Simply removing corrupted rows would therefore have disproportionately
removed the safest customers.

Instead, missing interest rates were imputed using the median interest
rate within each loan grade.

## Modeling Approach

1. Data cleaning and validation
2. Train/validation/test split
3. Random Forest model
4. Probability prediction
5. Profit calculation using EMP
6. Threshold optimization on validation data
7. Final evaluation on untouched test data
8. Comparison with cost-sensitive training

## Main Finding

The profit-maximizing threshold was 0.40 rather than the standard 0.50.

The 0.40 threshold produced an honest out-of-sample test profit of
$1,449,533, representing a $323,413 improvement over the 0.50 cutoff.

## Cost-Sensitive Training

Cost-sensitive training was also tested.

It produced lower test profit than the standard model with threshold tuning:

- Moderate weighting: $1,257,010
- Full weighting: $1,220,395

This suggests that adding cost information during training did not improve
the final business outcome in this experiment.

## Deliverables

- Excel analysis
- Credit risk dashboard
- Executive summary

## Tools

- Python
- Excel
- Machine Learning
- Random Forest
- Statistical analysis
- Data cleaning
- Model evaluation
- Business decision analysis

## Dataset

Kaggle Credit Risk Dataset (laotse)

## Disclaimer

This project is an analytical portfolio project. Profit calculations
include illustrative assumptions and should not be used directly for
real-world lending decisions without further validation.
