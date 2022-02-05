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

### Issue: Ensure that functions's docstrings pass numpydoc validation
- [Issue #21350](https://github.com/scikit-learn/scikit-learn/issues/21350)
Go into this file: https://github.com/scikit-learn/scikit-learn/blob/main/sklearn/linear_model/_glm/glm.py

There are 4 classes in this file. 
I will work on this one:  class GeneralizedLinearRegressor(RegressorMixin, BaseEstimator):  
Find associated test file for this class: In this case, it is this file: https://github.com/scikit-learn/scikit-learn/blob/main/sklearn/linear_model/_glm/tests/test_glm.py

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

