# Feature importance

It is quite common to use model-embedded approach to evaluate feature importance, for example, random forest-based feature importance evaluation. In Sklearn, it use the Gini information as the evaluation metric.

However, it quite common to met the problem with multi-collinearity in the input features. Sklearn provided an interesting solution by running hierachical clustering among input features, then randomly pick one feature from each cluster, then evaluate. With many permutations, we can also get a importance metric for each feature. (link to permutation importance with multicolinearity: https://scikit-learn.org/stable/auto_examples/inspection/plot_permutation_importance_multicollinear.html#sphx-glr-auto-examples-inspection-plot-permutation-importance-multicollinear-py)

In Udacity course, it introduced a new method named "SHAP" which represent for shapley additive explanation. This method will consider the marginal contribution of one variable in all potential combination. So the results are more robust. The challenge part is how to iterate all potential variable combination which will grow exponentially by the number of features.
