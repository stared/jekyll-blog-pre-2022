---
layout: "post"
title: "Small Data & Shallow Learning"
date:  2016-01-22 18:25:00 +0100
tags: [data-science, big-data, deep-learning]
description: 'Embrace small datasets and simple data analysis. Most of things happen there.'
image: /imgs/some_picture.png
---

You may get an impression that unless you do Deep Learning with Big Data you are not a Real Data Scientist™[^1]. In fact, often I am being asked:

> * someone: So, I guess you work with big data and deep learning?
> * me: Actually, I do shallow learning on small data!

Most of data scientists I know use Python or R on their local machines. And it is small data (as it can be stored and processed on a local machine) and not-deep learning (without GPU, usually in the cloud, it's hard to go beyond toy examples). Out of my friends, only *Type-B Data Scientists* (according to the [Doing Data Science at Twitter](https://medium.com/@rchang/my-two-year-journey-as-a-data-scientist-at-twitter-f0c13298aee6) taxonomy) work daily with Big Data.

It is true that a lot of frontiers are in "big OR deep" (I like to visualize it as universe and ocean abbys). And tracking its progress is beneficial even if I don't use particular methodology (to see what it possible). However, don't get misled that most of data science work happens to be in this area!

## Small

You may think that "since people at Google, Facebook and Twitter say that Big Data is the only data they deal with, so should I". Well, unless you work at Google, you won't get Google-sized data.
Small companies rarely get big data. And even the whole text content of the current English Wikipedia is around 50GB. Unpacked. For classical academic research, were

Some startups are desperately trying to use overengineered solutions - because of catching hype, lack of data expertise, or - because, hey, their 10MB dataset is going to grow to petabytes in no time!

> If you want to work with a few screws, screw-driver is the right tool - not assembling a production-class machine.

Usually I deal with amounts from a few hundreds of kBs to a few GBs. It is an artifact of being a freelancer - if they deal with big data, then they have dedicated full-time data scientists or don't want to give their data to a third part, But still - there is a lot of work at this scale.
Advanced models

## Shallow

Most of problems are simple. Sometimes they don't involve any machine learning at all - just some aggregative statistics. However, even if they are simple they aren't necessarily trivial: communicating with people who created it, assembling it from various sources, cleaning it[^2], aggregating them in a meaningful way, thinking how the results can be interpreted (and how - cannot). Very often they need more curiosity, diligence and skepticism rather than brand new machine learning techniques[^3].

> If you are to a foreign country and use their language, typically it's about saying "Hi!" and buying food, rather than translating 18th-century poetry.

Moreover, as shocking it sounds, performance is not always the key - life is not a [Kaggle](https://www.kaggle.com/) competition![^4] It does not matter how well you can predict a thing, if the thing is meaningless (or worse: misleading). Also, sometimes a few percents more are not worth time you could spend on a different project.

Quite a few times I used linear regression in some end models - the client wanted an *interpretable result* and (after scaling variables) it was almost as performant as random forest.
For the same reason often I use `ctree` from [R partykit](http://partykit.r-forge.r-project.org/partykit/) to get shallow decision trees, with a few splits, only when it is statistically significant. From the machine learning perspective, it is a serious underfitting. But for human interpretation - a great thing!

Deep learning is by no means a

## What matters

Sure, there are problems when either you have to use big data or using it is a game-changer.
There are problems when nothing comes close to deep learning (think: progress image recognition in the last few year).

But, let me repeat myself:

> Most problems are simple.

And, in the end, we need to pass it to human in a digestible (small end simple) form like "if we go with email A, conversion rate is 7%, but if we go with email B: 13%" or even "this is a cat".

To be fair, I know some Spark and I've just started learning deep learning.

[^1]: If you think that I am not a *real data scientist*, I am fine that. If anything, I would prefer to be a *complex data scientist*. As a side note, I am not a *real programmer*. Proof? Usually I use Atom (the shiny and easy editor), not vim or emacs, vide [xkcd.com/378](https://xkcd.com/378/).
[^2]: Cleaning data sounds like cleaning a room, but sometimes is closer to finding treasure in a maze. One of the most "wow" tasks I had involved fuzzy matching of two databases.
[^3]: Sometimes I am shocked that some tasks, that 3 years ago took me a month now would take only slightly less. In data retrieval and cleaning they may be not as many shortcuts (e.g. manually reverse-engineering some text format).
[^4]: Unless you work on a Kaggle competition, as my [co-workers from deepsense.io, who won the right whale recognition](http://deepsense.io/deep-learning-right-whale-recognition-kaggle/).
