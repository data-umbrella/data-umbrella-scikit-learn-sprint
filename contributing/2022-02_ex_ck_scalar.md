## Example: Check Scalar Function

### Blog
https://blog.dataumbrella.org/example-of-check-scalar-function-contribution-in-scikit-learn

### Getting Started
Usual:  
1. conda activate sklearndev
2. sync repo
3. work from feature branch
4. Rebuild from source, if needed: `pip install -e . --no-build-isolation -v`

### References
- Reshama's pull requests:  https://github.com/scikit-learn/scikit-learn/pulls?q=is%3Apr+author%3Areshamas+is%3Aclosed

### Issue: Use the function check_scalar for parameters validation
- [Issue #21927](https://github.com/scikit-learn/scikit-learn/issues/21927)
Go into this file: https://github.com/scikit-learn/scikit-learn/blob/main/sklearn/linear_model/_glm/glm.py

### Files I am working on
- I added the valid scalar parameter intervals in this pull request: "DOC adding valid intervals for SGDClassifier class parameters" [#22115](https://github.com/scikit-learn/scikit-learn/pull/22115)
- File with the class: [`sklearn/linear_model/_stochastic_gradient.py`](https://github.com/scikit-learn/scikit-learn/blob/main/sklearn/linear_model/_stochastic_gradient.py)
- There are 4 classes in this file. 
- I will work on, line 77:  `class BaseSGD(SparseCoefMixin, BaseEstimator, metaclass=ABCMeta):`
- `def fit` is on line 126
- Find associated test file for this class: [sklearn/linear_model/tests/test_sgd.py](https://github.com/scikit-learn/scikit-learn/blob/main/sklearn/linear_model/tests/test_sgd.py)

### These are the scalar parameters:  
1. `alpha`
2. `l1_ratio`
3. `max_iter`
4. `tol`
5. `verbose`
6. `epsilon`
7. `random_state`
8. `eta0`
9. `power_t`
10. `validation_fraction`
11. `n_iter_no_change`
12. `average`

### Test file
I see this on line 227
```python
@pytest.mark.parametrize("fit_method", ["fit", "partial_fit"])
@pytest.mark.parametrize(
    "params, err_msg",
    [
        ({"alpha": -0.1}, "alpha must be >= 0"),
        ({"penalty": "foobar", "l1_ratio": 0.85}, "Penalty foobar is not supported"),
        ({"loss": "foobar"}, "The loss foobar is not supported"),
        ({"l1_ratio": 1.1}, r"l1_ratio must be in \[0, 1\]"),
        ({"learning_rate": "<unknown>"}, "learning rate <unknown> is not supported"),
        ({"nu": -0.5}, r"nu must be in \(0, 1]"),
        ({"nu": 2}, r"nu must be in \(0, 1]"),
        ({"alpha": 0, "learning_rate": "optimal"}, "alpha must be > 0"),
        ({"eta0": 0, "learning_rate": "constant"}, "eta0 must be > 0"),
        ({"max_iter": -1}, "max_iter must be > zero"),
        ({"shuffle": "false"}, "shuffle must be either True or False"),
        ({"early_stopping": "false"}, "early_stopping must be either True or False"),
        (
            {"validation_fraction": -0.1},
            r"validation_fraction must be in range \(0, 1\)",
        ),
        ({"n_iter_no_change": 0}, "n_iter_no_change must be >= 1"),
    ],
 ```
 
 #### alpha
 ```python
 Values must be in the range `[0.0, inf)`.
 ```
 


I did find a test for `max_iter` argument  
```python
@pytest.mark.parametrize("max_iter", ["not a number", 0, -1, 5.5, [1]])def test_glm_max_iter_argument(max_iter): """Test GLM for invalid max_iter argument.""" y = np.array([1, 2]) X = np.array([[1], [2]]) glm = GeneralizedLinearRegressor(max_iter=max_iter) with pytest.raises(ValueError, match="must be a positive integer"): glm.fit(X, y)Next, I am going to run the test for this: Example:  pytest sklearn/cluster/tests/test_affinity_propagation.py::test_affinity_propagation_params_validation
```

For me:  `pytest sklearn/linear_model/_glm/tests/test_glm.py::test_glm_max_iter_argument`  

Note:  there are errors, but they are related to another function:  

```bash
E   ModuleNotFoundError: No module named 'sklearn._loss._loss'If there are errors, rebuild source code (`pip install -e . --no-build-isolation -v`)
```

For the particular test of interest, `max_iter` does check a variety of values:  `("max_iter", ["not a number", 0, -1, 5.5, [1]])`

In this case, I ran the tests and all 5 passed.
Next, I go back to python file with class of interest:https://github.com/scikit-learn/scikit-learn/blob/main/sklearn/linear_model/_glm/glm.py

Validation should be within the `def fit` function.

```python
import library at top:from ...utils import check_scalar
```

For now, comment out the "if not isinstance..." 
part I:
- a) I checked the tests first, and it did exist (checking both min and max vals)
- b) did the import, commented out old code, added in the `check_scalar` functionc) I now have 5 failed tests and not sure what to do next.  I do see that the existing test checks for `[1]` which is a list, and the error is:   
 
```bash        if not isinstance(x, target_type):>           raise TypeError(f"{name} must be an instance of {target_type}, not {type(x)}.")E           TypeError: max_iter must be an instance of <class 'numbers.Integral'>, not <class 'list'>.
sklearn/utils/validation.py:1409: TypeError
```

