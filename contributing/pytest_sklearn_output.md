### `pytest sklearn`

```bash

(sklearndev) % pytest sklearn                                     
============================================================ test session starts ============================================================
platform darwin -- Python 3.7.1, pytest-4.0.0, py-1.7.0, pluggy-0.8.0
rootdir: /Users/reshamashaikh/scikit-learn, inifile: setup.cfg
collected 10627 items                                                                                                                       

sklearn/_config.py .                                                                                                                  [  0%]
sklearn/discriminant_analysis.py ..                                                                                                   [  0%]
sklearn/exceptions.py ..                                                                                                              [  0%]
sklearn/impute.py ..                                                                                                                  [  0%]
sklearn/kernel_approximation.py ....                                                                                                  [  0%]
sklearn/kernel_ridge.py .                                                                                                             [  0%]
sklearn/naive_bayes.py ....                                                                                                           [  0%]
sklearn/pipeline.py ....                                                                                                              [  0%]
sklearn/random_projection.py ...                                                                                                      [  0%]
sklearn/cluster/affinity_propagation_.py .                                                                                            [  0%]
sklearn/cluster/bicluster.py ..                                                                                                       [  0%]
sklearn/cluster/birch.py .                                                                                                            [  0%]
sklearn/cluster/dbscan_.py .                                                                                                          [  0%]
sklearn/cluster/hierarchical.py ..                                                                                                    [  0%]
sklearn/cluster/k_means_.py ..                                                                                                        [  0%]
sklearn/cluster/mean_shift_.py .                                                                                                      [  0%]
sklearn/cluster/spectral.py .                                                                                                         [  0%]
sklearn/cluster/tests/test_affinity_propagation.py .......                                                                            [  0%]
sklearn/cluster/tests/test_bicluster.py ........s.                                                                                    [  0%]
sklearn/cluster/tests/test_birch.py .......                                                                                           [  0%]
sklearn/cluster/tests/test_dbscan.py .......................                                                                          [  0%]
sklearn/cluster/tests/test_feature_agglomeration.py .                                                                                 [  0%]
sklearn/cluster/tests/test_hierarchical.py .....................                                                                      [  0%]
sklearn/cluster/tests/test_k_means.py ...........s................................................................................... [  1%]
..........................                                                                                                            [  2%]
sklearn/cluster/tests/test_mean_shift.py ..........                                                                                   [  2%]
sklearn/cluster/tests/test_optics.py ..........................                                                                       [  2%]
sklearn/cluster/tests/test_spectral.py .............                                                                                  [  2%]
sklearn/compose/_column_transformer.py ..                                                                                             [  2%]
sklearn/compose/_target.py .                                                                                                          [  2%]
sklearn/compose/tests/test_column_transformer.py .ss.s........s................sssssssss...........s                                  [  3%]
sklearn/compose/tests/test_target.py ...........                                                                                      [  3%]
sklearn/covariance/empirical_covariance_.py .                                                                                         [  3%]
sklearn/covariance/robust_covariance.py .                                                                                             [  3%]
sklearn/covariance/shrunk_covariance_.py ..                                                                                           [  3%]
sklearn/covariance/tests/test_covariance.py ......                                                                                    [  3%]
sklearn/covariance/tests/test_elliptic_envelope.py ....                                                                               [  3%]
sklearn/covariance/tests/test_graph_lasso.py ....                                                                                     [  3%]
sklearn/covariance/tests/test_graphical_lasso.py ....                                                                                 [  3%]
sklearn/covariance/tests/test_robust_covariance.py .......                                                                            [  3%]
sklearn/cross_decomposition/cca_.py .                                                                                                 [  3%]
sklearn/cross_decomposition/pls_.py ...                                                                                               [  3%]
sklearn/cross_decomposition/tests/test_pls.py ........                                                                                [  3%]
sklearn/datasets/base.py .......                                                                                                      [  3%]
sklearn/datasets/samples_generator.py .                                                                                               [  3%]
sklearn/datasets/tests/test_20news.py sss                                                                                             [  3%]
sklearn/datasets/tests/test_base.py ...................                                                                               [  3%]
sklearn/datasets/tests/test_california_housing.py .                                                                                   [  3%]
sklearn/datasets/tests/test_covtype.py s                                                                                              [  3%]
sklearn/datasets/tests/test_kddcup99.py ss                                                                                            [  3%]
sklearn/datasets/tests/test_lfw.py sssss                                                                                              [  3%]
sklearn/datasets/tests/test_mldata.py ....                                                                                            [  3%]
sklearn/datasets/tests/test_openml.py .....................................................                                           [  4%]
sklearn/datasets/tests/test_rcv1.py s                                                                                                 [  4%]
sklearn/datasets/tests/test_samples_generator.py ............................                                                         [  4%]
sklearn/datasets/tests/test_svmlight_format.py ......................................................                                 [  5%]
sklearn/decomposition/base.py .                                                                                                       [  5%]
sklearn/decomposition/factor_analysis.py .                                                                                            [  5%]
sklearn/decomposition/fastica_.py .                                                                                                   [  5%]
sklearn/decomposition/incremental_pca.py .                                                                                            [  5%]
sklearn/decomposition/kernel_pca.py .                                                                                                 [  5%]
sklearn/decomposition/nmf.py ..                                                                                                       [  5%]
sklearn/decomposition/online_lda.py .                                                                                                 [  5%]
sklearn/decomposition/pca.py .                                                                                                        [  5%]
sklearn/decomposition/sparse_pca.py ..                                                                                                [  5%]
sklearn/decomposition/truncated_svd.py .                                                                                              [  5%]
sklearn/decomposition/tests/test_dict_learning.py .........................................................                           [  5%]
sklearn/decomposition/tests/test_factor_analysis.py .                                                                                 [  5%]
sklearn/decomposition/tests/test_fastica.py ........                                                                                  [  5%]
sklearn/decomposition/tests/test_incremental_pca.py .................                                                                 [  6%]
sklearn/decomposition/tests/test_kernel_pca.py ............                                                                           [  6%]
sklearn/decomposition/tests/test_nmf.py ........................                                                                      [  6%]
sklearn/decomposition/tests/test_online_lda.py .............sss...............                                                        [  6%]
sklearn/decomposition/tests/test_pca.py .........................................                                                     [  7%]
sklearn/decomposition/tests/test_sparse_pca.py ....ss........ss....                                                                   [  7%]
sklearn/decomposition/tests/test_truncated_svd.py ...............                                                                     [  7%]
sklearn/ensemble/forest.py ..                                                                                                         [  7%]
sklearn/ensemble/partial_dependence.py ..                                                                                             [  7%]
sklearn/ensemble/voting_classifier.py .                                                                                               [  7%]
sklearn/ensemble/tests/test_bagging.py ...............................                                                                [  7%]
sklearn/ensemble/tests/test_base.py ....                                                                                              [  7%]
sklearn/ensemble/tests/test_forest.py ............................................................................................... [  8%]
.....................................................................                                                                 [  9%]
sklearn/ensemble/tests/test_gradient_boosting.py .................................................................................... [ 10%]
.................................                                                                                                     [ 10%]
sklearn/ensemble/tests/test_gradient_boosting_loss_functions.py .........                                                             [ 10%]
sklearn/ensemble/tests/test_iforest.py ..............                                                                                 [ 10%]
sklearn/ensemble/tests/test_partial_dependence.py .......                                                                             [ 10%]
sklearn/ensemble/tests/test_voting_classifier.py .................                                                                    [ 10%]
sklearn/ensemble/tests/test_weight_boosting.py ................                                                                       [ 11%]
sklearn/feature_extraction/dict_vectorizer.py ..                                                                                      [ 11%]
sklearn/feature_extraction/hashing.py .                                                                                               [ 11%]
sklearn/feature_extraction/image.py .                                                                                                 [ 11%]
sklearn/feature_extraction/text.py ...                                                                                                [ 11%]
sklearn/feature_extraction/tests/test_dict_vectorizer.py ............................                                                 [ 11%]
sklearn/feature_extraction/tests/test_feature_hasher.py ...........                                                                   [ 11%]
sklearn/feature_extraction/tests/test_image.py ....................                                                                   [ 11%]
sklearn/feature_extraction/tests/test_text.py ............................................................x......                     [ 12%]
sklearn/feature_selection/rfe.py ..                                                                                                   [ 12%]
sklearn/feature_selection/univariate_selection.py ......                                                                              [ 12%]
sklearn/feature_selection/variance_threshold.py .                                                                                     [ 12%]
sklearn/feature_selection/tests/test_base.py .....                                                                                    [ 12%]
sklearn/feature_selection/tests/test_chi2.py .....                                                                                    [ 12%]
sklearn/feature_selection/tests/test_feature_select.py .................................                                              [ 12%]
sklearn/feature_selection/tests/test_from_model.py .....................                                                              [ 13%]
sklearn/feature_selection/tests/test_mutual_info.py ........                                                                          [ 13%]
sklearn/feature_selection/tests/test_rfe.py ............                                                                              [ 13%]
sklearn/feature_selection/tests/test_variance_threshold.py ..                                                                         [ 13%]
sklearn/gaussian_process/gpc.py .                                                                                                     [ 13%]
sklearn/gaussian_process/gpr.py .                                                                                                     [ 13%]
sklearn/gaussian_process/tests/test_gpc.py ..............................                                                             [ 13%]
sklearn/gaussian_process/tests/test_gpr.py ................................................................................           [ 14%]
sklearn/gaussian_process/tests/test_kernels.py ...................................................................................... [ 15%]
..................................................................................................................................... [ 16%]
.................................                                                                                                     [ 16%]
sklearn/linear_model/base.py .                                                                                                        [ 16%]
sklearn/linear_model/bayes.py ..                                                                                                      [ 16%]
sklearn/linear_model/coordinate_descent.py .........                                                                                  [ 16%]
sklearn/linear_model/huber.py .                                                                                                       [ 16%]
sklearn/linear_model/least_angle.py .....                                                                                             [ 16%]
sklearn/linear_model/logistic.py ..                                                                                                   [ 16%]
sklearn/linear_model/omp.py ..                                                                                                        [ 16%]
sklearn/linear_model/passive_aggressive.py ..                                                                                         [ 16%]
sklearn/linear_model/perceptron.py .                                                                                                  [ 16%]
sklearn/linear_model/ransac.py .                                                                                                      [ 16%]
sklearn/linear_model/ridge.py ....                                                                                                    [ 16%]
sklearn/linear_model/sag.py .                                                                                                         [ 16%]
sklearn/linear_model/stochastic_gradient.py ..                                                                                        [ 16%]
sklearn/linear_model/theil_sen.py .                                                                                                   [ 16%]
sklearn/linear_model/tests/test_base.py ..................                                                                            [ 17%]
sklearn/linear_model/tests/test_bayes.py s........                                                                                    [ 17%]
sklearn/linear_model/tests/test_coordinate_descent.py .........................................                                       [ 17%]
sklearn/linear_model/tests/test_huber.py .........                                                                                    [ 17%]
sklearn/linear_model/tests/test_least_angle.py ..............................                                                         [ 18%]
sklearn/linear_model/tests/test_logistic.py ......................................................................................... [ 18%]
.....................................................................xx......                                                         [ 19%]
sklearn/linear_model/tests/test_omp.py ..................                                                                             [ 19%]
sklearn/linear_model/tests/test_passive_aggressive.py ................                                                                [ 19%]
sklearn/linear_model/tests/test_perceptron.py ...                                                                                     [ 19%]
sklearn/linear_model/tests/test_ransac.py .......................                                                                     [ 20%]
sklearn/linear_model/tests/test_ridge.py ............................................                                                 [ 20%]
sklearn/linear_model/tests/test_sag.py ................                                                                               [ 20%]
sklearn/linear_model/tests/test_sgd.py .............................................................................................. [ 21%]
......................................................................................................................                [ 22%]
sklearn/linear_model/tests/test_sparse_coordinate_descent.py ...........                                                              [ 22%]
sklearn/linear_model/tests/test_theil_sen.py .................                                                                        [ 22%]
sklearn/manifold/isomap.py .                                                                                                          [ 22%]
sklearn/manifold/locally_linear.py .                                                                                                  [ 22%]
sklearn/manifold/mds.py .                                                                                                             [ 22%]
sklearn/manifold/spectral_embedding_.py .                                                                                             [ 22%]
sklearn/manifold/t_sne.py .                                                                                                           [ 22%]
sklearn/manifold/tests/test_isomap.py ......                                                                                          [ 23%]
sklearn/manifold/tests/test_locally_linear.py .......                                                                                 [ 23%]
sklearn/manifold/tests/test_mds.py ...                                                                                                [ 23%]
sklearn/manifold/tests/test_spectral_embedding.py ....s.......                                                                        [ 23%]
sklearn/manifold/tests/test_t_sne.py ................................................                                                 [ 23%]
sklearn/metrics/classification.py .................                                                                                   [ 23%]
sklearn/metrics/pairwise.py ....                                                                                                      [ 23%]
sklearn/metrics/ranking.py ......                                                                                                     [ 23%]
sklearn/metrics/regression.py .......                                                                                                 [ 24%]
sklearn/metrics/scorer.py .                                                                                                           [ 24%]
sklearn/metrics/cluster/supervised.py .......                                                                                         [ 24%]
sklearn/metrics/cluster/tests/test_bicluster.py ...                                                                                   [ 24%]
sklearn/metrics/cluster/tests/test_common.py ........................................                                                 [ 24%]
sklearn/metrics/cluster/tests/test_supervised.py ...................                                                                  [ 24%]
sklearn/metrics/cluster/tests/test_unsupervised.py .........                                                                          [ 24%]
sklearn/metrics/tests/test_classification.py ...........................................................................              [ 25%]
sklearn/metrics/tests/test_common.py ................................................................................................ [ 26%]
..................................................................................................................................... [ 27%]
..................................................................................................................................... [ 28%]
..........................................................................................                                            [ 29%]
sklearn/metrics/tests/test_pairwise.py ..................................................................................             [ 30%]
sklearn/metrics/tests/test_ranking.py ..................................................                                              [ 30%]
sklearn/metrics/tests/test_regression.py .......                                                                                      [ 31%]
sklearn/metrics/tests/test_score_objects.py ................................................                                          [ 31%]
sklearn/mixture/tests/test_bayesian_mixture.py ..................                                                                     [ 31%]
sklearn/mixture/tests/test_gaussian_mixture.py ....................................                                                   [ 32%]
sklearn/mixture/tests/test_mixture.py ..                                                                                              [ 32%]
sklearn/model_selection/_search.py ...                                                                                                [ 32%]
sklearn/model_selection/_split.py ...............                                                                                     [ 32%]
sklearn/model_selection/_validation.py s...                                                                                           [ 32%]
sklearn/model_selection/tests/test_search.py .....................................................                                    [ 32%]
sklearn/model_selection/tests/test_split.py ...............................................                                           [ 33%]
sklearn/model_selection/tests/test_validation.py ....................................................                                 [ 33%]
sklearn/neighbors/base.py ....                                                                                                        [ 33%]
sklearn/neighbors/classification.py ..                                                                                                [ 33%]
sklearn/neighbors/graph.py ..                                                                                                         [ 33%]
sklearn/neighbors/nearest_centroid.py .                                                                                               [ 33%]
sklearn/neighbors/regression.py ..                                                                                                    [ 33%]
sklearn/neighbors/unsupervised.py .                                                                                                   [ 33%]
sklearn/neighbors/tests/test_ball_tree.py ........................................................................................... [ 34%]
..................................................................................................................................... [ 35%]
........................                                                                                                              [ 36%]
sklearn/neighbors/tests/test_dist_metrics.py ..........................................................                               [ 36%]
sklearn/neighbors/tests/test_kd_tree.py .............................................................................                 [ 37%]
sklearn/neighbors/tests/test_kde.py .......................................                                                           [ 37%]
sklearn/neighbors/tests/test_lof.py ............                                                                                      [ 37%]
sklearn/neighbors/tests/test_nearest_centroid.py .........                                                                            [ 37%]
sklearn/neighbors/tests/test_neighbors.py ..........................................................................                  [ 38%]
sklearn/neighbors/tests/test_quad_tree.py ...........                                                                                 [ 38%]
sklearn/neural_network/rbm.py .                                                                                                       [ 38%]
sklearn/neural_network/tests/test_mlp.py .........................                                                                    [ 38%]
sklearn/neural_network/tests/test_rbm.py ............                                                                                 [ 39%]
sklearn/neural_network/tests/test_stochastic_optimizers.py ......                                                                     [ 39%]
sklearn/preprocessing/_discretization.py .                                                                                            [ 39%]
sklearn/preprocessing/_encoders.py ..                                                                                                 [ 39%]
sklearn/preprocessing/data.py .............                                                                                           [ 39%]
sklearn/preprocessing/label.py ....                                                                                                   [ 39%]
sklearn/preprocessing/tests/test_base.py ...................                                                                          [ 39%]
sklearn/preprocessing/tests/test_common.py .........                                                                                  [ 39%]
sklearn/preprocessing/tests/test_data.py ...................................................................s.s.s.s...........s.s.... [ 40%]
....................................................................................................                                  [ 41%]
sklearn/preprocessing/tests/test_discretization.py ..................................                                                 [ 41%]
sklearn/preprocessing/tests/test_encoders.py ..................sss..............s................s.                                   [ 42%]
sklearn/preprocessing/tests/test_function_transformer.py ..........s                                                                  [ 42%]
sklearn/preprocessing/tests/test_imputation.py ........                                                                               [ 42%]
sklearn/preprocessing/tests/test_label.py .................................                                                           [ 42%]
sklearn/semi_supervised/label_propagation.py ...                                                                                      [ 42%]
sklearn/semi_supervised/tests/test_label_propagation.py .........                                                                     [ 42%]
sklearn/svm/classes.py ......                                                                                                         [ 42%]
sklearn/svm/tests/test_bounds.py ...................                                                                                  [ 43%]
sklearn/svm/tests/test_sparse.py ...............................                                                                      [ 43%]
sklearn/svm/tests/test_svm.py ...............................................                                                         [ 43%]
sklearn/tests/test_base.py .......................                                                                                    [ 44%]
sklearn/tests/test_calibration.py .........                                                                                           [ 44%]
sklearn/tests/test_check_build.py .                                                                                                   [ 44%]
sklearn/tests/test_common.py ........................................................................................................ [ 45%]
...................................................................................................s................................. [ 46%]
...s........................................................................................................................s........ [ 47%]
............................s...........................................................s..................................s......... [ 48%]
.............................................s.....................................................................................s. [ 50%]
......................s....................................s...................................s.............................s....... [ 51%]
.............................s....................................................................................................... [ 52%]
......................................................................................s....................................s......... [ 53%]
.........................s.....................................s..................................................................... [ 55%]
.............................................................................................................s....................... [ 56%]
..................................................................................................................................... [ 57%]
...........s....................................s.................................................................................... [ 58%]
..................................................s.................................................................................. [ 60%]
...........s........................................................................................s................................ [ 61%]
........................................................................................................s............................ [ 62%]
.........................s........................................................................................................... [ 63%]
..................................................................................................................................... [ 65%]
..................................................................................................................................... [ 66%]
...........................................................................s..................................s...................... [ 67%]
................s.........................................................................................s.......................... [ 68%]
............s........................................................................................................................ [ 70%]
..................................................................................................................................... [ 71%]
.........................s....................................................s...................................................... [ 72%]
..............................................................................................................................s...... [ 73%]
..................................................................................................................................... [ 75%]
..............s.....................s...............s................................................................................ [ 76%]
.......................................s............................................................................................. [ 77%]
.................................................s.....................................s............................................. [ 78%]
..................................................................................s.................................................. [ 80%]
...................................................................................s................................................. [ 81%]
.......................................................................................s.....................................s....... [ 82%]
...........................s..................................s..................................s................................... [ 83%]
..s..................................................................s......................................s........................ [ 85%]
...........s.........................s...........s................................................................................... [ 86%]
..................................................................................................................................... [ 87%]
......................................................................s.............................................................. [ 88%]
..........................................................................................................................s.......... [ 90%]
..................................................................................................................................... [ 91%]
.............................................................................                                                         [ 92%]
sklearn/tests/test_config.py ...                                                                                                      [ 92%]
sklearn/tests/test_discriminant_analysis.py ...............                                                                           [ 92%]
sklearn/tests/test_docstring_parameters.py s.                                                                                         [ 92%]
sklearn/tests/test_dummy.py ................................................                                                          [ 92%]
sklearn/tests/test_impute.py ...............................ss..........ss........................................................... [ 93%]
........                                                                                                                              [ 93%]
sklearn/tests/test_init.py .                                                                                                          [ 93%]
sklearn/tests/test_isotonic.py ..............................                                                                         [ 94%]
sklearn/tests/test_kernel_approximation.py .........                                                                                  [ 94%]
sklearn/tests/test_kernel_ridge.py ........                                                                                           [ 94%]
sklearn/tests/test_metaestimators.py .                                                                                                [ 94%]
sklearn/tests/test_multiclass.py .......................................                                                              [ 94%]
sklearn/tests/test_multioutput.py .......................                                                                             [ 94%]
sklearn/tests/test_naive_bayes.py ...........................................                                                         [ 95%]
sklearn/tests/test_pipeline.py .......................................                                                                [ 95%]
sklearn/tests/test_random_projection.py ................                                                                              [ 95%]
sklearn/tests/test_site_joblib.py ..                                                                                                  [ 95%]
sklearn/tree/export.py ..                                                                                                             [ 95%]
sklearn/tree/tree.py ..                                                                                                               [ 95%]
sklearn/tree/tests/test_export.py .....                                                                                               [ 95%]
sklearn/tree/tests/test_reingold_tilford.py ..                                                                                        [ 95%]
sklearn/tree/tests/test_tree.py ..................................................................................................... [ 96%]
........................................................................                                                              [ 97%]
sklearn/utils/__init__.py .......                                                                                                     [ 97%]
sklearn/utils/deprecation.py .                                                                                                        [ 97%]
sklearn/utils/extmath.py ..                                                                                                           [ 97%]
sklearn/utils/graph.py .                                                                                                              [ 97%]
sklearn/utils/multiclass.py ...                                                                                                       [ 97%]
sklearn/utils/testing.py .                                                                                                            [ 97%]
sklearn/utils/validation.py ..                                                                                                        [ 97%]
sklearn/utils/tests/test_bench.py .                                                                                                   [ 97%]
sklearn/utils/tests/test_class_weight.py ...........                                                                                  [ 97%]
sklearn/utils/tests/test_deprecation.py ...                                                                                           [ 97%]
sklearn/utils/tests/test_estimator_checks.py .......                                                                                  [ 97%]
sklearn/utils/tests/test_extmath.py ..........................                                                                        [ 98%]
sklearn/utils/tests/test_fast_dict.py ..                                                                                              [ 98%]
sklearn/utils/tests/test_fixes.py .............                                                                                       [ 98%]
sklearn/utils/tests/test_linear_assignment.py .                                                                                       [ 98%]
sklearn/utils/tests/test_metaestimators.py ..                                                                                         [ 98%]
sklearn/utils/tests/test_multiclass.py .....s..                                                                                       [ 98%]
sklearn/utils/tests/test_murmurhash.py ......                                                                                         [ 98%]
sklearn/utils/tests/test_optimize.py .                                                                                                [ 98%]
sklearn/utils/tests/test_random.py ....                                                                                               [ 98%]
sklearn/utils/tests/test_seq_dataset.py ..                                                                                            [ 98%]
sklearn/utils/tests/test_shortest_path.py ....                                                                                        [ 98%]
sklearn/utils/tests/test_show_versions.py ...                                                                                         [ 98%]
sklearn/utils/tests/test_sparsefuncs.py .........................................                                                     [ 98%]
sklearn/utils/tests/test_testing.py ...........s..                                                                                    [ 99%]
sklearn/utils/tests/test_utils.py ......s........................                                                                     [ 99%]
sklearn/utils/tests/test_validation.py ...............................................s.ss.............                               [100%]
========================================================== short test summary info ==========================================================
SKIP [1] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: This test is failing on the buildbot, but cannot reproduce. Temporarily disabling it until it can be reproduced and  fixed.
SKIP [1] sklearn/cluster/tests/test_k_means.py:238: Possible multi-process bug with some BLAS
SKIP [1] /Users/reshamashaikh/scikit-learn/sklearn/compose/tests/test_column_transformer.py:133: could not import 'pandas'
SKIP [2] /Users/reshamashaikh/scikit-learn/sklearn/compose/tests/test_column_transformer.py:264: could not import 'pandas'
SKIP [1] /Users/reshamashaikh/scikit-learn/sklearn/compose/tests/test_column_transformer.py:471: could not import 'pandas'
SKIP [9] /Users/reshamashaikh/scikit-learn/sklearn/compose/tests/test_column_transformer.py:806: could not import 'pandas'
SKIP [1] /Users/reshamashaikh/scikit-learn/sklearn/compose/tests/test_column_transformer.py:996: could not import 'pandas'
SKIP [3] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: Download 20 newsgroups to run this test
SKIP [1] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: Covertype dataset can not be loaded.
SKIP [2] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: kddcup99 dataset can not be loaded.
SKIP [5] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: PIL not installed.
SKIP [1] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: Download RCV1 dataset to run this test.
SKIP [2] sklearn/decomposition/tests/test_online_lda.py:207: Possible multi-process bug with some BLAS
SKIP [1] sklearn/decomposition/tests/test_online_lda.py:224: Possible multi-process bug with some BLAS
SKIP [2] sklearn/decomposition/tests/test_sparse_pca.py:79: Possible multi-process bug with some BLAS
SKIP [2] sklearn/decomposition/tests/test_sparse_pca.py:159: skipping mini_batch_fit_transform.
SKIP [1] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: test_bayesian_on_diabetes is broken
SKIP [1] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: pyamg not available.
SKIP [1] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/doctest.py:347: all tests skipped by +SKIP option
SKIP [4] /Users/reshamashaikh/scikit-learn/sklearn/preprocessing/tests/test_data.py:869: 'with_mean=True' cannot be used with sparse matrix.
SKIP [2] /Users/reshamashaikh/scikit-learn/sklearn/preprocessing/tests/test_data.py:1076: RobustScaler cannot center sparse matrix
SKIP [3] /Users/reshamashaikh/scikit-learn/sklearn/preprocessing/tests/test_encoders.py:311: could not import 'pandas'
SKIP [1] /Users/reshamashaikh/scikit-learn/sklearn/preprocessing/tests/test_encoders.py:492: could not import 'pandas'
SKIP [1] /Users/reshamashaikh/scikit-learn/sklearn/preprocessing/tests/test_encoders.py:660: could not import 'pandas'
SKIP [1] /Users/reshamashaikh/scikit-learn/sklearn/preprocessing/tests/test_function_transformer.py:203: could not import 'pandas'
SKIP [46] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: pandas is not installed: not testing for input of type pandas.Series to class weight.
SKIP [1] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: score_samples of BernoulliRBM is not invariant when applied to a subset.
SKIP [3] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: Skipping check_estimators_data_not_an_array for cross decomposition module as estimators are not deterministic.
SKIP [1] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: transform of MiniBatchSparsePCA is not invariant when applied to a subset.
SKIP [1] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: Not testing NuSVC class weight as it is ignored.
SKIP [1] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: decision_function of SVC is not invariant when applied to a subset.
SKIP [1] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: transform of SparsePCA is not invariant when applied to a subset.
SKIP [1] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: numpydoc is required to test the docstrings, as well as python version >= 3.5
SKIP [2] /Users/reshamashaikh/scikit-learn/sklearn/tests/test_impute.py:300: could not import 'pandas'
SKIP [2] /Users/reshamashaikh/scikit-learn/sklearn/tests/test_impute.py:413: could not import 'pandas'
SKIP [3] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: Pandas not found
SKIP [1] /Users/reshamashaikh/anaconda3/envs/sklearndev/lib/python3.7/site-packages/_pytest/nose.py:27: numpydoc is required to test the docstrings
SKIP [1] /Users/reshamashaikh/scikit-learn/sklearn/utils/tests/test_validation.py:700: could not import 'pandas'
SKIP [1] /Users/reshamashaikh/scikit-learn/sklearn/utils/tests/test_validation.py:709: could not import 'pandas'

================================== 10509 passed, 115 skipped, 3 xfailed, 14228 warnings in 387.01 seconds ===================================
 This problem is unconstrained.
RUNNING THE L-BFGS-B CODE

           * * *

Machine precision = 2.220D-16
 N =            3     M =           10

At X0         0 variables are exactly at the bounds

At iterate    0    f=  1.38629D+02    |proj g|=  6.27865D+01

           * * *

Tit   = total number of iterations
Tnf   = total number of function evaluations
Tnint = total number of segments explored during Cauchy searches
Skip  = number of BFGS updates skipped
Nact  = number of active bounds at final generalized Cauchy point
Projg = norm of the final projected gradient
F     = final function value

           * * *

   N    Tit     Tnf  Tnint  Skip  Nact     Projg        F
    3      1      2      1     0     0   2.422D+01   9.713D+01
  F =   97.133816163368238     

STOP: TOTAL NO. of ITERATIONS REACHED LIMIT                 

 Cauchy                time 0.000E+00 seconds.
 Subspace minimization time 0.000E+00 seconds.
 Line search           time 0.000E+00 seconds.

 Total User time 0.000E+00 seconds.

(sklearndev) %
```
