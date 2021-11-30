## Issue Title
Use the function `check_scalar` for parameters validation. 

## Issue Type
This is an **intermediate-level** issue for second time contributors.

## Background / Objective

References [#20724](https://github.com/scikit-learn/scikit-learn/issues/20724)

A helper function exists in scikit-learn which validates a scalar value:  
https://scikit-learn.org/stable/modules/generated/sklearn.utils.check_scalar.html

Currently,.... inconsistent error messages, 

The function `check_scalar` is defined in [`scikit-learn/sklearn/utils/validation.py`](https://github.com/scikit-learn/scikit-learn/blob/6077d52b706d118c0d9fb1e69c254bc67e15b078/sklearn/utils/validation.py)


Utilizing this helper function will help to get consistent error types and messages.

## Steps

Some instructions on adding scalar validation with `check_scalar` on classes
 
1. **Look for classes with constructors having scalar numeric as parameters (e.g `int`, `float`) used to set attributes**, for instance [`dampling`, `max_iter`, and `convergence_iter` in `AffinityPropagation` are scalar parameters]( https://github.com/scikit-learn/scikit-learn/pull/20723/files#diff-62083de22888eadb572404f8f7255a19a74370eeaf2a893858b066d90ada979eL273-L285)  used [to set eponymous attributes in `AffinityPropagation`](https://github.com/scikit-learn/scikit-learn/pull/20723/files#diff-62083de22888eadb572404f8f7255a19a74370eeaf2a893858b066d90ada979eR404-R406)
1. **Inspect if any of the associated class attributes aren't checked with `check_scalar`**, you can search in the file text for the attributes. For instance [associated attributes of `dampling`, `max_iter`, and `convergence_iter` in `AffinityPropagation` were not validated](https://github.com/scikit-learn/scikit-learn/pull/20723/files#diff-62083de22888eadb572404f8f7255a19a74370eeaf2a893858b066d90ada979eL458).
1. **Add tests on the class interfaces to assert behavior when wrong values are provided**, those test _must_ fail before adding validation. For instance [@glemaitre added a parametrised test for those parameters](https://github.com/scikit-learn/scikit-learn/pull/20723/files#diff-35c6902baaa6b79819df8746c45a68f5d9057003fcd4189ac1d44213ac1eced2R76-R95).
1. **Add `check_scalar` calls where needed**. Generally, this is not done in the constructor but rather just before calling the core of the method. For instance, in the case of #20723, [@glemaitre added `check_scalar` calls just before the call to `affinity_propagation` which is the core of the method.](https://github.com/scikit-learn/scikit-learn/pull/20723/files#diff-62083de22888eadb572404f8f7255a19a74370eeaf2a893858b066d90ada979eR460-R475)
1. **Repeat this process for each new class**, you can have a look at @ArturoAmorQ's PR linked just above: #21341

Feel free to ping us if you need help.

## Functions Updated
- [x] `sklearn/ensemble/_weight_boosting.py`
- [x] `sklearn/neighbors/_nca.py`
- [x] `sklearn/decomposition/_pca.py`
- [x] `sklearn/feature_extraction/text.py`
- [x] `sklearn/preprocessing/_discretization.py`
- [x] `AffinityPropagation` [#20723](https://github.com/scikit-learn/scikit-learn/pull/20723) Example by @glemaitre
- [x] `sklearn/cluster/_birch.py` [#20816](https://github.com/scikit-learn/scikit-learn/pull/20816)
- [x] `sklearn/cluster/_dbscan.py` [#20816](https://github.com/scikit-learn/scikit-learn/pull/20816)

## Functions to Update
- [ ] `AdaBoostRegressor` [#21605](https://github.com/scikit-learn/scikit-learn/pull/21605)
- [ ] `BaseGradientBoosting` [#21632](https://github.com/scikit-learn/scikit-learn/pull/21632)
- [ ] `SpectralBiClustering`, `SpectralCoClustering` [#20817](https://github.com/scikit-learn/scikit-learn/pull/20817)
- [ ] `linear_model.Ridge`[#21341](https://github.com/scikit-learn/scikit-learn/pull/21341)



