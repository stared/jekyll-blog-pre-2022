---
layout: "post"
title: "What is log-loss?"
date: "2017-01-27 17:27"
---

In machine learning when we predict classes, usually we use log-loss as the cost function. That is, for each instance we calculate:

$$ - p_1^{true} \log(p_1) - p_2^{true} \log(p_2) $$

Or, in a common place in which ground truth consist of sure answers, then

$$ - \log (p_{predicted}) $$

More straightforward error measures like accuracy (i.e. percent of correct answers), [precision and recall](https://en.wikipedia.org/wiki/Precision_and_recall) are not enough.
We need to accommodate for uncertainty (and also: provide a continuous, differentiable quantity).

So, why not just predicting mean square error on probabilities, i.e. $(p-p^{true})^2$? There are practical and fundamental reasons. A practical if we predicted

## Never say never

One corollary is that we never want to
Ridiculously low probabilities are not a problem.

In deep learning soft-max


## Log-likelihood

A more fundamental approach to log-loss







## Mean squared error

https://en.wikipedia.org/wiki/Mean_squared_error


## And further

* [Ian Goodfellow et al., Deep Learning](http://www.deeplearningbook.org/), MIT Press
  * [3.13 Information Theory](http://www.deeplearningbook.org/contents/prob.html)
  * [5.5 Maximum Likelihood Estimation](http://www.deeplearningbook.org/contents/ml.html)
