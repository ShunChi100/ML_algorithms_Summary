
$n$ observations, $d$ features, multiple classes

||Train Efficiency|Prediction Efficiency|Interpretability|Accuracy|No. of Features|Data Preprocessing|Method|
|:------|:--------|:---------|:---------|:------------|:-----------|:------------|:-----------|
|KNN|$O(1)$|$O(n^2)$|Good: Definition of Distances|Good if distance is well defined|small (curse of dimension)|balanced scaling|Measure distance|
|Decision Tree|$m$: depth of the tree. Continuous: $O(mdn\log(n))$. Categorical: $O(nd)$|$O(m)$|Good: Comparisons at nodes|Good|Can be large|litte if the data is clean|Divide according to features|
|AdaBoost|$T$: No. of weak learners. $f$: Training time for each learner. $O(T*f)$|$p$: predicting time for each learner. $O(T*p)$|Bad|Better|Can be large|little if use Decision tree as base learner|Learn from errors and average|
|Bagging|$T$: No. of Bootstrapping. $f$: Training time for each learner. $O(T*f)$|$p$: predicting time for each learner. $O(T*p)$|Bad|Better|Can be large|little if use decision tree as base learner|Average over Bootstrapping learners that use randomly select observations with replacement|
|Random Forest|$T$: No. of estimators. $f$: Training time for each estimator. $O(T*f)$ (can be parallelized)|$p$: predicting time for each learner. $O(T*p)$|Bad|Better|Can be large|little since decision tree is the base estimator|Average over different decision trees that 1. use randomly selected observations with replacement. 2. use randomly selected features|
|SVM|between $O(dn^2)$ and $O(dn^3)$|$O(d)$|Good (linear) or Bad (rbf)|Better|Can be large (even for $d > n$)|Need to convert to numeric, maybe balanced scaling too? |Construct a maximum margin between classes (with kernel trick in higher dimensional space)|
|Naive Bayes|$c$: No. of classes. $O(nd + cd)$|$O(cd)$|Good|Poor|Can be large (even for $d > n$)|Categorical data (text)|Construct "probability" of a class happening based Bayes rule, but assume features are conditionally independent.|
