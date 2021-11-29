## Issue Title
Use check_scalar for parameters validation

## Issue Type
This is an **intermediate-level** issue for second time contributors.


## Background / Objective

A helper function exists in scikit-learn which validates a scalar value:  
https://scikit-learn.org/stable/modules/generated/sklearn.utils.check_scalar.html

Since this helper could help to get consistent error types and messages, I was wondering if we could make a long-running issue to introduce this helper everywhere possible.

## Steps

## Example Pull Requests
- #20723

### Reference
[#20724](https://github.com/scikit-learn/scikit-learn/issues/20724)

## Functions to Update
- [x] `AdaBoostClassifer` #21442
- [ ]  `AdaBoostRegressor` #21605
- [ ]  
