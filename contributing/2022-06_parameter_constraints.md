## Notes for `_parameter_constraints`

- List of `ck_scalar` classes:  https://github.com/scikit-learn/scikit-learn/issues/21927
- Prior ck_scalar PR by Reshama: MAINT Common parameter validation 
   - [21946: MAINT Use check_scalar to validate scalar in: GeneralizedLinearRegressor](https://github.com/scikit-learn/scikit-learn/pull/21946) 
- Jeremie's PR: [22722 MAINT Common parameter validation](https://github.com/scikit-learn/scikit-learn/pull/22722)
- (1/192 tasks complete) Open Issue [#23462](https://github.com/scikit-learn/scikit-learn/issues/23462)

### Examples
- `k_means.py`:  https://github.com/scikit-learn/scikit-learn/blob/ec5d2ed9e5bfb6b0baff57ff1f994310e9a31ad9/sklearn/cluster/_kmeans.py#L1312
- Example PR that has been merged in: [MNT LinearRegression uses _validate_parameters](https://github.com/scikit-learn/scikit-learn/pull/23491)

Goal:  
- a common method for the validation of the parameters of an estimator

### `_parameter_constraints`
- https://github.com/scikit-learn/scikit-learn/search?q=_parameter_constraints

## Steps
1. xxx
1. xxx
1. Finally, remove the estimator from the list of skipped estimators for the common param validation test:  [scikit-learn/sklearn/tests/test_common.py](https://github.com/scikit-learn/scikit-learn/blob/ec5d2ed9e5bfb6b0baff57ff1f994310e9a31ad9/sklearn/tests/test_common.py#L448)
1. Make sure the test passes:  `pytest -vl sklearn/tests/test_common.py -k check_param_validation`
1. See below for Pull Request description.

PR title2:  
- MAINT LinearRegression uses _validate_parameters
- [WIP] MNT Use _validate_params in NMF and MiniBatchNMF 

Pull Request Description:  
```
### References
Towards #23462

### Description
LinearRegression uses `_validate_parameters`

```

### Import statement
```python
from ..utils._param_validation import validate_params
```


### `_parameter_constraints` statement

Put `_parameter_constraints` after `class` docstring and before `def init`.

#### Example 1

[sklearn/cluster/_kmeans.py](https://github.com/scikit-learn/scikit-learn/blob/5bd39c2b672dae8c9742d43866b81c3afde23c2c/sklearn/cluster/_kmeans.py)

Put `_parameter_constraints` after `class` docstring and before `def init`.

```
class MiniBatchKMeans(_BaseKMeans):
```

```python
    _parameter_constraints = {
        **_BaseKMeans._parameter_constraints,
        "init": [StrOptions({"k-means++", "random"}), callable],
        "copy_x": [bool],
        "algorithm": [StrOptions({"lloyd", "elkan"})],
        "bisecting_strategy": [StrOptions({"biggest_inertia", "largest_cluster"})],
    }
```

#### Example 2
[sklearn/cluster/_kmeans.py](https://github.com/scikit-learn/scikit-learn/blob/5bd39c2b672dae8c9742d43866b81c3afde23c2c/sklearn/cluster/_kmeans.py)

Put `_parameter_constraints` after `class` docstring and before `def init`.

```
class _BaseKMeans(
```

```python
    _parameter_constraints = {
        "n_clusters": [Interval(Integral, 1, None, closed="left")],
        "init": [StrOptions({"k-means++", "random"}), callable, "array-like"],
        "n_init": [
            StrOptions({"auto", "warn"}, internal={"warn"}),
            Interval(Integral, 1, None, closed="left"),
        ],
        "max_iter": [Interval(Integral, 1, None, closed="left")],
        "tol": [Interval(Real, 0, None, closed="left")],
        "verbose": [Interval(Integral, 0, None, closed="left"), bool],
        "random_state": ["random_state"],
    }
```

In `def fit`, add in:
```python
self._validate_params()
```


#### Example 3
[sklearn/linear_model/_base.py](https://github.com/scikit-learn/scikit-learn/blob/79c176de3f8a6972fe9e087f612f77bbd2b40ad6/sklearn/linear_model/_base.py)

Put `_parameter_constraints` after `class` docstring and before `def init`.

```python
class LinearRegression(MultiOutputMixin, RegressorMixin, LinearModel):
```

```python
    _parameter_constraints = {
        "fit_intercept": [bool],
        "normalize": [StrOptions({"deprecated"}, internal={"deprecated"}), bool],
        "copy_X": [bool],
        "n_jobs": [None, Integral],
        "positive": [bool],
    }
```

In `def fit`, add in:
```python
self._validate_params()
```

---

## Reshama's Notes
- scikit-learn build is in this directory:  `/Users/reshamashaikh/software-build/scikit-learn`
- Activate virtual environment:  `conda activate sklearndev`
- Go to feature branch:  `git checkout validate_params_glr`
- *Then*, open up VS Code
- Ref:  [MAINT Use check_scalar to validate scalar in: GeneralizedLinearRegressor #21946](https://github.com/scikit-learn/scikit-learn/pull/21946)
- Base class for `glm` is here:  `sklearn/linear_model/_glm/glm.py`   [glm.py](https://github.com/scikit-learn/scikit-learn/blob/main/sklearn/linear_model/_glm/glm.py)
- 

