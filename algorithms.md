# Federated Analysis Algorithms Descriptions

More information on the available federated analysis algorithms, although retrievable through the individual component list, can be directly found on [https://github.com/madgik/exareme/tree/24.3.0/Exareme-Docker/src/mip-algorithms](https://github.com/madgik/exareme/tree/24.3.0/Exareme-Docker/src/mip-algorithms)

This includes documentation on existing algorithm federation approach, unit tests, as well as information related to creating a new algorithm.


###  k-Means Clustering
The purpose of the k-means algorithm is to partition the data into k clusters. Here, all attributes should be numerical and we use the Eucledean distance as our metric.  

[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/KMEANS)

### ANOVA
Analysis of variance (ANOVA) is a collection of statistical models and their associated estimation procedures (such as the "variation" among and between groups) used to analyze the differences among group means in a sample.  [Wikipedia](https://en.wikipedia.org/wiki/Analysis_of_variance)

[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/ANOVA)

### CART
The purpose of the CART algorithm is to construct a binary decision tree for the given dataset. The training procedure is different for regression and classification trees.  
[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/CART)

### Calibration Belt
This is an original algorithm aiming to compute a confidence band for the calibration curve, in order to validate the predictive power of some model against independent samples.  

[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/CALIBRATION_BELT)

### ID3
The purpose of the ID3 algorithm is to construct a decision tree for the given dataset. In ID3 all the attributes should be categorical.  

[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/ID3)

### Kaplan-Meier Estimator
The Kaplan–Meier estimator, also known as the product limit estimator, is a non-parametric statistic used to estimate the survival function from lifetime data. In medical research, it is often used to measure the fraction of patients living for a certain amount of time after treatment.  [Wikipedia](https://en.wikipedia.org/wiki/Kaplan%E2%80%93Meier_estimator)
  
[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/KAPLAN_MEIER)

### Linear Regression
Linear regression is a linear approach to modeling the relationship between a dependent variable and one or more independent variables.

[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/LINEAR_REGRESSION)

### Logistic Regression
Logistic Regression training is done by Maximum Likelihood Estimation (MLE) by gradient descent using, for example, Newton's method. Applying Newton's method leads to the following algorithm, called Iteratively Reweighted Least Squares (IRLS). Here the dependent variable y has to be binary.  

[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/LOGISTIC_REGRESSION)

### Naive Bayes Training
In machine learning, naïve Bayes classifiers are a family of simple "probabilistic classifiers" based on applying Bayes' theorem with strong (naïve) independence assumptions between the features. [Wikipedia](https://en.wikipedia.org/wiki/Naive_Bayes_classifier)

[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/NAIVE_BAYES_TRAINING)

### Naive Bayes with Cross Validation
[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/NAIVE_BAYES_TRAINING_STANDALONE)

### Pearson Correlation
This algorithm computes the Pearson correlation coefficient between two vectors x and y using the eq.(1)  

[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/PEARSON_CORRELATION)

### Principal Components analysis
The are usually two approaches for computing the principal components. The first is by diagonalizing the covariance matrix, while the second is by SVD decomposition on the data matrix X. In most implementations the second approach is preferred due to its numerical stability. Here however, we took the first approach since it better fits with our privacy requirements. Additionally, as a first step, data is centered and standardized.  

[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/PCA)

### T-Test Independent
The Student’s Independent samples t-test (sometimes called a two-samples t-test) is used to test the null hypothesis that two groups have the same mean. A low p-value suggests that the null hypothesis is not true, and therefore the group means are different. In each local dataset, let x and y be the variables of interest.y is the grouping variable with two levels.  

[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/TTEST_INDEPENDENT)

### T-Test One-Sample 
The Student’s One-sample t-test is used to test the null hypothesis that the true mean is equal to a particular value (typically zero). A low p-value suggests that the null hypothesis is not true, and therefore the true mean (μ) must be different from the test value. In each local dataset, let xj be the variable of interest.  

[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/TTEST_ONESAMPLE)

### T-Test Paired
The Student’s paired samples t-test (sometimes called a dependent-samples t-test) is used to test the null hypothesis that the difference between pairs of measurements is equal to zero. A low p-value suggests that the null hypothesis is not true, and that the difference between the measurement pairs is not zero. In each local dataset, let xj1 and xj2 be the variables of interest.  

[Documentation](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms/TTEST_PAIRED)
