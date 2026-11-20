# Methodology notes

## Logistic regression in brief
Logistic regression predicts the probability that an observation belongs to class 1 by passing a linear combination of predictors through the sigmoid function:

    p = 1 / (1 + e^-(b0 + b1*x1 + ... + bn*xn))

Predict class 1 when p is above a chosen threshold (0.5 by default).

| Type | Target | Example |
|---|---|---|
| Binomial | 2 categories | Fraud / not fraud |
| Multinomial | 3+ unordered | cat / dog / sheep |
| Ordinal | 3+ ordered | low / medium / high |

## Assumptions
1. Independent observations
2. Binary dependent variable
3. Linearity between predictors and the log-odds
4. No extreme outliers
5. Adequate sample size (rule of thumb: at least 10 events per predictor)

## Reading coefficients
- **Coefficient (β):** change in log-odds per one-unit increase in the predictor.
- **Odds ratio (e^β):** multiplicative change in the odds. 1 means no association; above 1 raises the odds; below 1 lowers them.
- Small coefficients on wide-ranging variables (glucose, in mg/dL) can still imply large effects, so judge importance over a realistic range and with p-values.

## The Wald test
Tests whether one or more coefficients are jointly equal to zero.

- H0: the tested coefficients are all zero
- p ≥ 0.05: fail to reject, the variables can be dropped together
- p < 0.05: at least one should stay

A joint test matters when predictors are correlated, because individual t-tests can each look insignificant while the group is not.

## Metrics used
- **Accuracy:** share correct. Misleading on imbalanced data.
- **Recall / sensitivity:** share of real positives caught.
- **Precision:** share of positive predictions that are right.
- **ROC-AUC:** how well the model ranks positives above negatives, across all thresholds.
- **Precision-recall curve:** more informative than ROC when positives are rare.
- **McFadden pseudo-R²:** fit measure for logit models; 0.2–0.4 is considered a good fit. Not comparable to OLS R².
