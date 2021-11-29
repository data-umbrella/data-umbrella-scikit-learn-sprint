## Issue Title
Use check_scalar for parameters validation

## Issue Type
This is an **intermediate-level** issue for second time contributors.

## Background / Objective

A helper function exists in scikit-learn which validates a scalar value:  
https://scikit-learn.org/stable/modules/generated/sklearn.utils.check_scalar.html

Utilizing this helper function will help to get consistent error types and messages.

## Steps


### Reference
[#20724](https://github.com/scikit-learn/scikit-learn/issues/20724)

## Functions to Update
- [x] `AdaBoostClassifer` [#21442](https://github.com/scikit-learn/scikit-learn/pull/21422)
- [ ] `AdaBoostRegressor` [#21605](https://github.com/scikit-learn/scikit-learn/pull/21605)
- [x] `AffinityPropagation` [#20723](https://github.com/scikit-learn/scikit-learn/pull/20723)
- [ ] `BaseGradientBoosting` [#21632](https://github.com/scikit-learn/scikit-learn/pull/21632)
- [x] `birch`, `dbscan` [#20816](https://github.com/scikit-learn/scikit-learn/pull/20816)
- [x] `SpectralBiClustering`, `SpectralCoClustering` [#20817](https://github.com/scikit-learn/scikit-learn/pull/20817)
