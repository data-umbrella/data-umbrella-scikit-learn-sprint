### Notes for `_parameter_constraints`

- Prior ck_scalar PR by Reshama: MAINT Common parameter validation 
   - [21946: MAINT Use check_scalar to validate scalar in: GeneralizedLinearRegressor](https://github.com/scikit-learn/scikit-learn/pull/21946) 
- Jeremie's PR: [22722 MAINT Common parameter validation](https://github.com/scikit-learn/scikit-learn/pull/22722)
- (1/192 tasks complete) Open Issue [#23462](https://github.com/scikit-learn/scikit-learn/issues/23462)

#### Examples
- `k_means.py`:  https://github.com/scikit-learn/scikit-learn/blob/ec5d2ed9e5bfb6b0baff57ff1f994310e9a31ad9/sklearn/cluster/_kmeans.py#L1312
- Example PR that has been merged in: [MNT LinearRegression uses _validate_parameters](https://github.com/scikit-learn/scikit-learn/pull/23491)

Goal:  
- a common method for the validation of the parameters of an estimator



## Steps
1. xxx
1. xxx
1. Finally, remove the estimator from the list of skipped estimators for the common param validation test:  [scikit-learn/sklearn/tests/test_common.py](https://github.com/scikit-learn/scikit-learn/blob/ec5d2ed9e5bfb6b0baff57ff1f994310e9a31ad9/sklearn/tests/test_common.py#L448)
1. Make sure the test passes:  `pytest -vl sklearn/tests/test_common.py -k check_param_validation`
1. See below for Pull Request description.

PR title:  MAINT LinearRegression uses _validate_parameters

Pull Request Description:  
```
### References
Towards #23462

### Description
LinearRegression uses `_validate_parameters`

```
