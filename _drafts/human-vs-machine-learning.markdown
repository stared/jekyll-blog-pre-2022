---
layout: post
title: "Human overfitting: exams, nipples and conspiracy theories"
date: 2018-06-16 15:58 +0100
author: Piotr Migdał
tags: [data-science, machine-learning, cognition, ml-vs-hl]
mathjax: false
description: 'Human vs machine learning: overfitting. Exams, nipples, racism, superstitions and other examples.'
image: /imgs/XXX_put_sth_there.jpg
---

While each particular machine learning algorithm comes with its own artifacts and limitations, some issues are much broader.

If fact, there are limitations of any learning process, machine or human alike. I think that it's worth investigating these, as there is a lot of room for cross-pollination between machine learning and cognitive science.

We may be able to see some of learning patterns, cognitive biases and logical fallacies through the prism of machine learning. Moreover, biological systems inspire (artificial neural networks)

XXX physics optics paper

On a more down-to-earth
I make my living teaching machine learning. It's


## What is overfitting?

When I give an introduction to machine learning, I often start with the [classic Iris dataset](https://en.wikipedia.org/wiki/Iris_flower_data_set), printed on paper, and ask participants to draw division lines. Some people draw straight lines, while others get more creative.

XXX picture!

So, the one on the right is better as it captures all points? Well, not.

Overfitting is a problem when a machine learning model performs well on the training dataset at the cost of its predictive power (working on yet unseen data).





http://scikit-learn.org/stable/auto_examples/model_selection/plot_underfitting_overfitting.html

* [Machine Learning Crash Course: Part 4 - The Bias-Variance Dilemma](https://ml.berkeley.edu/blog/2017/07/13/tutorial-4/) by Daniel Geng and Shannon Shih

For pathological examples of overfitting (which passed though per review of questionable quality):

* [Will women outrun men in ultra-marathon road races from 50 km to 1,000 km?](https://springerplus.springeropen.com/articles/10.1186/2193-1801-3-97) by (censored out of mercy)

And it short - I know that polynomial fittings are everywhere, but think twice before using anything of higher order than 3.

So,

* too complex model,
* too high weights,
* too much memorization,
* extrapolation from too sparse data.

I will discussed both "active" cases, and ones frozen in the culture.

## Examples of overfitting

To much memorization.


### Exams

You are a student learning for a difficult exam. Would you rather:

* revise note, re-read text,
* study exam questions.

In the worst case, if you memorize answers (question 1-A, 2-C, 3-A, 4-D, ...) it will works extremely well for the same exam set, but your accuracy will drop to guess-by chance level for a different question set (or even: a different order of answers).

In a typical case, students memorize answers from previous exams and learn exam patters.
(Typically exam questions are a small, and not representative, subset of any discipline.)

This problems seems to be profound in medicine.


> To a point that I made a bet with a friend, on the lethal dose of potassium ions (a single does, orally). Her guess was closer to a recommended daily intake.

**Solution**

If oyu make sure memorization isn't the mai



### Memorization


We would have saved him

I medical

To a point that I made a bet with a friend, on the lethal dose of potassium ions (a single does, orally). Her guess was closer to a recommended daily intake.  


* wetland biology camp
* potassium lethal does bet ()
* medicine in general



### Gender discrimination

One of hallmarks of overfitting are too high weights given to a certain trait. To fight it, we use regularization. Depending on your statistical philosophy, it is a penalty, or a Bayesian prior.



* [Are women paid less than men for the same work?](https://www.economist.com/blogs/graphicdetail/2017/08/daily-chart) - The Economist

### Racism

Another facet of the same problem. Ethnicity is often coupled with other factors such as economic status, social capital, immigration status.


* [How to make a racist AI without really trying](https://blog.conceptnet.io/2017/07/13/how-to-make-a-racist-ai-without-really-trying/) by Rob Speer

While it is tempting


### Nipples

In Western culture nudity is associated with sexuality.

What is more interesting from machine learning perspective is what do we consider nudity.
A woman exposing only a slightly part of her nipple is considered nude, while one showing her breasts (except for nipples) is considered dressed.



Sure, it may me benef

* [Genderless Nipples exposes Instagram’s double standard on nudity](http://www.theverge.com/2016/12/6/13852900/genderless-nipples-instagram-censorship-policy)
* [Brestfeeding cartoon](http://beta.latimes.com/opinion/topoftheticket/la-na-tt-breastfeeding-moms-20120705-story.html) by David Horsey

Interestingly enough, AI is

**Solution**:


### Interviews and applications

One very often overfitting-like problem is academic and job recruitment process.




## Too complex models

### Superstitions

Most cultures and religions believe in some superstitions.

When we bake a cake, there are many steps involved. It may contain steps

Don't

For example, don't take


[Monday’s medical myth: you can’t mix antibiotics with alcohol](https://theconversation.com/mondays-medical-myth-you-cant-mix-antibiotics-with-alcohol-4407)
[Can I drink alcohol while taking antibiotics?](https://www.nhs.uk/chq/pages/871.aspx) - NHS



### Conspiracy theories

We have tendency to look for patterns.
In many cases

Sometimes there

https://xkcd.com/1725/



Usually they don't take account for coincidences (i.e. noise) - every single event has some meaning and need to be fitted into the narrative.


Cherry-picking models. [Spurious correlations](http://www.tylervigen.com/spurious-correlations)


If you are smart enough to read about machine learning and cognition, you know what is the weakest spot of many conspiracy theories - the assumption that there is some plan and an individual (or group) is able to

## Some other commnets

Fitting to a single metric

Equally good managers.



## When it is not a problem

### When overfitting is acceptable

Overfitting can be good, or acceptable, in certain instances.

The prime example is compression - when we don't need our results to generalize.

[Mnemonic](https://en.wikipedia.org/wiki/Mnemonic), or memory techniques, can help learning languages, formuleae, phone numbers, etc.
They can work by compressing, creating redundancy, or transforming problems into ones that are easier to memorize.

### When

### Tricks and hacks



### Physics



### When underfitting is desirable

* insuarrances

##



## Ending



See also:

* [What's a real-world example of “overfitting”?](https://stats.stackexchange.com/questions/128616/whats-a-real-world-example-of-overfitting) - Cross Validated

Can you think of other examples of overfitting?

Ideas for next posts:

* Dreams, drugs and ConvNets
* Scalar fallacy


# TODO, etc

### To mention

* Occam's razor
* porn in general, sweets, etc
* logical fallacies
* CVs, schools, interviews!
* [king - man + woman is queen; but why?](http://p.migdal.pl/2017/01/06/king-man-woman-queen-why.html)
* [Dating for nerds (part 2): gender differences](http://p.migdal.pl/2017/09/30/dating-for-nerds-gender-differences.html)
* https://www.reddit.com/r/MachineLearning/comments/4xr6bn/overfitting_and_human_brain/
* adversarial examples, https://blog.kjamistan.com/adversarial-learning-for-good-my-talk-at-34c3-on-deep-learning-blindspots/
* https://xkcd.com/1725/
* metaphors we live be
* maybe also: whales, mammals
* [Two heads are better than one. How about more?](https://egtheory.wordpress.com/2014/01/30/two-heads-are-better-than-one-how-about-more/)
* Knowledge, experience, overfitting
  * https://twitter.com/essiryy/status/634741367864954880
  * https://imgur.com/gallery/a6feg5X (with many)
  * http://www.myconfinedspace.com/2015/10/05/information-vs-knowledge-vs-conspiracy-theory/
* maybe to read https://www.reddit.com/r/MachineLearning/comments/7nt2sw/d_null_space_of_a_statistical_classifier/
* https://arxiv.org/pdf/1801.00631.pdf - on why does
* bias-variance and discrimination
* https://datascience.stackexchange.com/questions/61/why-is-overfitting-bad-in-machine-learning/ including xkcd strip
* https://lukeoakdenrayner.wordpress.com/2018/06/05/explain-yourself-machine-producing-simple-text-descriptions-for-ai-interpretability/ - interpretability

## other sources

* https://www.analyticsvidhya.com/blog/2014/10/introduction-k-neighbours-algorithm-clustering/ (maybe)
* http://christopherroach.com/articles/statistics-for-hackers/ (maybe)
* http://bl.ocks.org/jonahwilliams/810d8d84278539952369 ?
* create kNN in D3.js?


## neuroinspirations

* https://deepmind.com/blog/understanding-deep-learning-through-neuron-deletion/
* http://yosinski.com/deepvis
* https://datascience.stackexchange.com/questions/12851/how-do-you-visualize-neural-network-architectures
* https://github.com/mlajtos/moniel and discussions there: https://github.com/mlajtos/moniel/issues/13
* http://www.sciencemag.org/news/2018/04/could-artificial-intelligence-get-depressed-and-have-hallucinations?utm_source=sciencemagazine&utm_medium=facebook-text&utm_campaign=aidepression-18840
* https://www.reddit.com/r/MachineLearning/comments/8moils/d_does_or_can_machine_learning_produce_mental/
* http://togelius.blogspot.com/2018/05/empiricism-and-limits-of-gradient.html and philosophy

Confusion matrix:
* https://ml4a.github.io/demos/confusion_cifar_convnet/

Also to write about:

* Drugs, dreams and ConvNets

### Binary fallacy

Good vs evil, utilitarism and softmax

* Differentiability!
* Always some uncertainty
* Centrism as a starting point
* "Vector fallacy"
