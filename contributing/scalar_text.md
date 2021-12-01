## Issue Title
Use the function `check_scalar` for parameters validation. 

## Prerequisites
This is an **intermediate-level** issue for second time contributors. This requires the following experience:
- You have already set up your working virtual environment.
- You have submitted at least one other pull request to this library.
- Experience using [`pytest`](https://docs.pytest.org/en/6.2.x/).
- It is helpful to be familiar with the acceptable range of values (minimum and maximum) for the estimator you are working on. If you are not familiar with an estimator, you can reference other sources outside of scikit-learn documentation to get that information. 

## Background / Objective

References [#20724](https://github.com/scikit-learn/scikit-learn/issues/20724)

A helper function exists in scikit-learn which validates a scalar value, [documentation](https://scikit-learn.org/stable/modules/generated/sklearn.utils.check_scalar.html)
It is used to validate parameters of classes (? and functions). Most of the current classes in scikit-learn do not use this helper function.  We want to refactor the code so that it does use this standard helper function. Utilizing this helper function will help to get consistent error types and messages.

If there is a scalar argument that isn't being checked, we want to check it, or validate it using the `check_scalar` function.  In some cases it is currently being checked, but it is not using the `check_scalar` function.  For that change, we refactor the code.  (Refactoring means making changes to the code that result in the same output as before.)

The function `check_scalar` is defined in [`scikit-learn/sklearn/utils/validation.py`](https://github.com/scikit-learn/scikit-learn/blob/6077d52b706d118c0d9fb1e69c254bc67e15b078/sklearn/utils/validation.py)


## Steps
- [ ] Find a class with constuctors that have scalar numeric as parameters. There are some listed below in the "Classes to Update" section. 
- [ ] Make sure you have created a separate branch from `main` before editing files for your new contribution. Refer to our [contributing guidelines](https://scikit-learn.org/dev/developers/contributing.html#how-to-contribute) for more information.
- [ ] Work on one estimator at a time and submit each in a separate pull request. 
- [ ] The pull request can be named:  "MNT Use check_scalar in: [EstimatorName]"
- [ ] Check scalar parameters with helper function
- [ ] Add tests

 
Some instructions on adding scalar validation with `check_scalar` on classes
 
1. **Look for classes with constructors having scalar numeric as parameters (e.g `int`, `float`) used to set attributes**, for instance [`dampling`, `max_iter`, and `convergence_iter` in `AffinityPropagation` are scalar parameters]( https://github.com/scikit-learn/scikit-learn/pull/20723/files#diff-62083de22888eadb572404f8f7255a19a74370eeaf2a893858b066d90ada979eL273-L285)  used [to set eponymous attributes in `AffinityPropagation`](https://github.com/scikit-learn/scikit-learn/pull/20723/files#diff-62083de22888eadb572404f8f7255a19a74370eeaf2a893858b066d90ada979eR404-R406)
1. **Inspect if any of the associated class attributes aren't checked with `check_scalar`**, you can search in the file text for the attributes. For instance [associated attributes of `dampling`, `max_iter`, and `convergence_iter` in `AffinityPropagation` were not validated](https://github.com/scikit-learn/scikit-learn/pull/20723/files#diff-62083de22888eadb572404f8f7255a19a74370eeaf2a893858b066d90ada979eL458).
1. **Add tests on the class interfaces to assert behavior when wrong values are provided**, those test _must_ fail before adding validation. For instance [@glemaitre added a parametrised test for those parameters](https://github.com/scikit-learn/scikit-learn/pull/20723/files#diff-35c6902baaa6b79819df8746c45a68f5d9057003fcd4189ac1d44213ac1eced2R76-R95).
1. **Add `check_scalar` calls where needed**. Generally, this is not done in the constructor but rather just before calling the core of the method. For instance, in the case of #20723, [@glemaitre added `check_scalar` calls just before the call to `affinity_propagation` which is the core of the method.](https://github.com/scikit-learn/scikit-learn/pull/20723/files#diff-62083de22888eadb572404f8f7255a19a74370eeaf2a893858b066d90ada979eR460-R475)

## Examples for Reference
- [x] `sklearn/cluster/_affinity_propagation.py`  [#20723](https://github.com/scikit-learn/scikit-learn/pull/20723) (@glemaitre)
- [ ] `sklearn/linear_model/_ridge.py`  [#21341](https://github.com/scikit-learn/scikit-learn/pull/21341) (@ArturoAmorQ)

## Classes Updated
- [x] `sklearn/neighbors/_nca.py`
- [x] `sklearn/decomposition/_pca.py`
- [x] `sklearn/feature_extraction/text.py`    [#20752](https://github.com/scikit-learn/scikit-learn/pull/20752) (@AlekLefebvre)
- [x] `sklearn/preprocessing/_discretization.py`
- [x] `sklearn/cluster/_affinity_propagation.py`  [#20723](https://github.com/scikit-learn/scikit-learn/pull/20723) (@glemaitre)
- [x] `sklearn/cluster/_birch.py`  [#20816](https://github.com/scikit-learn/scikit-learn/pull/20816) (@SanjayMarreddi)
- [x] `sklearn/cluster/_dbscan.py`  [#20816](https://github.com/scikit-learn/scikit-learn/pull/20816) (@SanjayMarreddi)
- [x] `sklearn/ensemble/_weight_boosting.py` (AdaBoostClassifier)  [#21442](https://github.com/scikit-learn/scikit-learn/pull/21442) (@genvalen)


## Classes to Update
- [ ] `sklearn/ensemble/_weight_boosting.py` (AdaBoostRegressor)  [#21605](https://github.com/scikit-learn/scikit-learn/pull/21605) (@genvalen)
- [ ] `sklearn/ensemble/_gb.py` (BaseGradientBoosting)  [#21632](https://github.com/scikit-learn/scikit-learn/pull/21632) (@genvalen)
- [ ] `sklearn/cluster/_bicluster.py` (SpectralBiClustering)  [#20817](https://github.com/scikit-learn/scikit-learn/pull/20817) (@creatornadiran)
- [ ] `sklearn/cluster/_bicluster.py` (SpectralCoClustering)  [#20817](https://github.com/scikit-learn/scikit-learn/pull/20817) (@creatornadiran)
- [ ] `sklearn/linear_model/_ridge.py`  (Ridge) [#21341](https://github.com/scikit-learn/scikit-learn/pull/21341) (@ArturoAmorQ)
- [ ] `sklearn/linear_model/_ridge.py`  (RidgeCV)      (@ArturoAmorQ)
- [ ] `sklearn/linear_model/_coordinate_descent.py` (Lasso) (@ArturoAmorQ)
- [ ] `sklearn/linear_model/_coordinate_descent.py` (LassoCV) (@ArturoAmorQ)
- [ ] `linear_model/_glm/glm.py` (GeneralizedLinearRegressor) (@reshamas)
- [ ] `linear_model/_glm/glm.py` (PoissonRegressor)  (@reshamas)
- [ ] `linear_model/_glm/glm.py` (GammaRegressor)  (@reshamas)
- [ ] `linear_model/_glm/glm.py` (TweedieRegressor)  (@reshamas)

