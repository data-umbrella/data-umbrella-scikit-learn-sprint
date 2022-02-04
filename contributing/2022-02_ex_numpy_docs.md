## Example: Ensure that functions's docstrings pass numpydoc validation

### Blog

### Set up
- virtual environment set up
- dependencies installed
- Any installation questions, ask on Gitter:  https://gitter.im/scikit-learn/scikit-learn

### Getting Started
Usual:  
1. Go to directory where scikit-learn is. 
2. Activate virtual environment:  `conda activate sklearndev`
3. Sync repo
4. Work from feature branch; create feature branch from `main`
5. [ONLY IF NEEDED] Rebuild from source: `pip install -e . --no-build-isolation -v`

### Issue: Ensure that functions's docstrings pass numpydoc validation
- [Issue #21350](https://github.com/scikit-learn/scikit-learn/issues/21350)

### Working on issue
1. Pick a function: `sklearn.metrics.pairwise.paired_distances`  
https://github.com/scikit-learn/scikit-learn/pull/21440
1. Comment out function `#"sklearn.metrics.pairwise.paired_distances",` in this file here:  `scikit-learn/sklearn/tests/test_docstrings.py`
2. Run at the terminal:  `pytest sklearn/tests/test_docstrings.py -k sklearn.metrics.pairwise.paired_distances`
3. 

```bash
E           
E           # Errors
E           
E            - PR01: Parameters {'**kwds'} not documented

sklearn/tests/test_docstrings.py:364: ValueError
============================================= 1 failed, 2107 deselected in 1.03s =============================================
(sklearndev) 
```
