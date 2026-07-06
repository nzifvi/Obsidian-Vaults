[[1,2 - sklearn Mixin classes]] $\leftarrow$

#sklearn #sklearn-models

---
# what is `sklearn.base.BaseEstimator`
`BaseEstimator` is the base class of all `sklearn` models.

Creating a child class which inherits from `BaseEstimator` allows for an `sklearn` compatible model to be created.
- Would allow for a custom model to be used with ALL sklearn sub-libraries (evaluation, hyperparameter tuning, etc.)

If inheriting from `BaseEstimator` class, there are function members which MUST be implemented in order for all `sklearn` features to work.
1) \_\_init\_\_()
2) get_params()
3) set_params()
4) \_\_repr\_\_()
5) \_\_sklearn_clone\_\_()

