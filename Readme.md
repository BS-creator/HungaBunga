


## HungaBunga: A Package to brute force all sklearn models with all of sklearn parameters!
### Ahhh Hunga Bunga!

![hungabunga](https://github.com/ypeleg/HungaBunga/blob/master/HungaBunga.png?raw=true)



#### What?
Yes.

#### No! Really! What?
Many believe that

> most of the work of supervised (non-deep) Machine Learning lies in feature engineering, whereas the model-selection process is just running through all the models or just take xgboost.

So here is an automation for that.

# HOW IT WORKS
Runs through all `sklearn` models (both classification and regression), with **all possible hyperparameters**, and rank using cross-validation.

# MODELS
Runs **all the model** available on `sklearn` for supervised learning [here](http://scikit-learn.org/stable/supervised_learning.html). The categories are:

* Generalized Linear Models
* Kernel Ridge
* Support Vector Machines
* Nearest Neighbors
* Gaussian Processes
* Naive Bayes
* Trees
* Neural Networks
* Ensemble methods

Note: Some models were dropped out (nearly none of them..) and some crash or cause exceptions from time to time. It takes REALLY long to test this out so clearing exceptions took me a while.

# USAGE

### How to run

#### Option I: brain = True

from hunga_bunga import HungaBungaClassifier, HungaBungaRegressor

clf = HungaBungaClassifier()
clf.fit(x, y)
clf.predict(x)


#### Option II: brain = True

from hunga_bunga import HungaBungaClassifier, HungaBungaRegressor
clf = HungaBungaClassifier(brain=True)
clf.fit(x, y)


The output looks this:

| Model                       |  accuracy     |  Time/clf (s)|
|---------------------------- |:-------------:|:-------------:|
|SGDClassifier                |     0.967     |      0.001   |
|LogisticRegression           |     0.940      |      0.001   |
|Perceptron                   |     0.900       |      0.001   |
|PassiveAggressiveClassifier  |     0.967     |      0.001   |
|MLPClassifier                |     0.827     |      0.018   |
|KMeans                       |     0.580      |      0.010    |
|KNeighborsClassifier         |     0.960      |      0.000       |
|NearestCentroid              |     0.933     |      0.000       |
|RadiusNeighborsClassifier    |     0.927     |      0.000       |
|SVC                          |     0.960      |      0.000       |
|NuSVC                        |     0.980      |      0.001   |
|LinearSVC                    |     0.940      |      0.005   |
|RandomForestClassifier       |     0.980      |      0.015   |
|DecisionTreeClassifier       |     0.960      |      0.000       |
|ExtraTreesClassifier         |     0.993     |      0.002   |

*The winner is: ExtraTreesClassifier with score 0.993.*

