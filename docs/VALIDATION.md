# Portfolio validation notes

The portfolio renderer reads archived `code/modeling/Final_model_comparison/model_results.csv`. Means and standard deviations come from the original five-fold CV results. The portfolio work does not constitute an independent rerun of the full research pipeline.

## Reconciled definitions

- Actual quantile-label code uses `quantile(0.2)` and `quantile(0.8)`. The old README's “tercile” was incorrect and has been corrected.
- The source universe and modeled samples are different stages. Model comparison has 158 finance-only observations and 154 text/combined observations; do not call this a 400-observation classification evaluation.
- The result CSV uses 8 finance features, 19 modeled text features and 27 combined features. Intermediate text tables contain additional IDs and columns.
- Standard deviation across five folds is not a confidence interval or a significance test between models.

## Interpretation limits

One historical event, small extreme-quantile samples, multiple model comparisons, different sample coverage and possible upstream feature-fitting leakage limit inference. Verify PCA, topic modeling, feature selection and scaling are fitted inside training folds before treating these scores as unbiased out-of-sample estimates. A strong CV score does not establish a causal mechanism or a deployable trading strategy.

## Data access

Existing research data includes earnings-call material sourced through WRDS / Capital IQ. The portfolio update adds no raw transcript copies. Repository availability is not a data redistribution license; users must follow original provider terms. This update retains prior research history and authorship.
