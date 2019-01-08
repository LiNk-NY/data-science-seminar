
4.4: Linear Discriminant Analysis
========================================================
author: Karin Lassnig
date: 05.12.2018
autosize: true

Table of contents 
========================================================



- Using Bayes' Theorem for Classification

- Linear Discriminant Analysis for p = 1

- Linear Discriminant Analysis for p >1

- Quadratic Discriminant Analysis

- Exercises


Using Bayes' Theorem for Classification
========================================================

Bayes Theorem:

$Pr(Y = k| X =x) = \dfrac{\pi_k*f_k}{\sum_{i=1}^K \pi_i*f_i(x)}$

where

K ..... number of classes, >= 2 

$\pi_k$ .... prior probability that a randomly chosen observation comes from the kth class


Using Bayes' Theorem for Classification
========================================================

$f_k(x) := Pr(X = x| Y = k)$

$p_k(x) := Pr(Y = k| X =x)$


Now we can use estimates of $\pi_k$ and $f_k(x)$ to compute $p_k(x)$

Linear Discriminant Analysis for p = 1
========================================================

Assumption: $f_k(x)$ is normal or Gaussian:

$f_k(x) = \dfrac{1}{\sqrt{2\pi\sigma_k}}exp(-\dfrac{2}{2\sigma_k^2}(x-\mu_k)^2)$ 

$p_k(x) = \dfrac{\pi_k \dfrac{1}{\sqrt{2\pi\sigma_k}}exp(-\dfrac{2}{2\sigma_k^2}(x-\mu_k)^2)}{\sum_{i=1}^K \pi_i \dfrac{1}{\sqrt{2\pi\sigma_k}}exp(-\dfrac{2}{2\sigma_k^2}(x-\mu_k)^2)}$

Linear Discriminant Analysis for p = 1
========================================================
The linear discriminant analysis (LDA) method approximates the Bayes classifier by using the following estimates: 

$\hat{\mu_k} = \dfrac{1}{n_k} \sum_{(j:Y_j=k)}^{}x_j$

$\hat{\sigma}^2 = \dfrac{1}{n-K}\sum_{k=1}^K\sum_{(j:y_j=k)}^{}(x_j-\hat{\mu_k})^2$ 

$\hat{\pi_k} = \dfrac{n_k}{n}$

Linear Discriminant Analysis for p = 1
========================================================
An observation X = x is assigned to the class for which

$\hat{\delta_k}(x) = x*\frac{\hat{\mu_k}}{\hat{\sigma}^2}-\frac{\hat{\mu_k}^2}{2\hat{\sigma}^2}+log(\hat{\pi_k})$

is largest. 

Linear Discriminant Analysis for p = 1
========================================================
Example


<img src="figure/Bild1-1.png" title="plot of chunk unnamed-chunk-1" alt="plot of chunk unnamed-chunk-1" width="100%" />

Linear Discriminant Analysis for p > 1
========================================================

Assumption: $X = (X_1,...,X_p)$ is drawn from a multivariate Gaussian (or multivariate normal)distribution, $N(\mu_k,\Sigma)$ with a class-specific mean vector and a common covariance matrix.

Bayes classifier assigns an observation X = x
to the class for which

$\delta_k(x) = X^T\Sigma^{-1}\mu_k-\dfrac{1}{2}\mu_k^T\Sigma^{-1}\mu_k+log\pi_k$

is largest.

Linear Discriminant Analysis for p > 1
========================================================

Example: Performance of LDA on the default data set, using a threshold of 50%

<img src="figure/Bild2-1.png" title="plot of chunk unnamed-chunk-2" alt="plot of chunk unnamed-chunk-2" width="100%" />

Linear Discriminant Analysis for p > 1
========================================================

Example: Performance of LDA on the default data set, using a threshold of 20%

<img src="figure/Bild3-1.png" title="plot of chunk unnamed-chunk-3" alt="plot of chunk unnamed-chunk-3" width="100%" />


Quadratic Discriminant Analysis
========================================================

Assumption: Observations are drawn from a normal distribution where each class has its own covariance matrix. 

$X \sim N(\mu_k,\Sigma_k)$

The Bayes classifier assigns an observation X = x to the class for which

$\delta_k(x) = -\dfrac{1}{2}x^T\Sigma_k^{-1}x+x^T\Sigma_k^{-1}\mu_k-\dfrac{1}{2}\mu_k^T\Sigma_k^{-1}\mu_k+log\pi_k$

is largest


Quadratic Discriminant Analysis
========================================================

<img src="figure/Bild4-1.png" title="plot of chunk unnamed-chunk-4" alt="plot of chunk unnamed-chunk-4" width="100%" />


Exercises
========================================================

<u>Exercise 5 (Page 169):</u>

We now examine the differences between LDA and QDA:

a) If the Bayes decision boundary is linear, do we expect LDA or QDA to perform better on the training set? On the test set?

b) If the Bayes decision boundary is non-linear, do we expect LDA or QDA to perform better on the training set? On the test set?

c) In general, as the sample size n increases, do we expect the test prediction accuracy of QDA relative to LDA to improve, decline,or be unchanged? Why?

Exercises
========================================================


d) True or False: Even if the Bayes decision boundary for a given problem is linear, we will probably achieve a superior test error rate using QDA rather than LDA because QDA is flexible enough to model a linear decision boundary. Justify your answer.

<u>Exercise 10 (Page 171):</u>
Continuing from the last session:

(e) Repeat (d) using LDA

(f) Repeat (d) using QDA


=======================================================

Thank you for your attention

