---
layout: post
title: "Exploring human vs machine learning (one blogpost at a time)"
date: '2019-07-15 11:16 +0100'
author: Piotr Migdał
tags:
  - deep-learning
  - cognition
description: >-
  To err is human... and machine, alike. Overfitting, adversarial examples, optical illusions, hallucinations, Freudian slips, etc.
image: /imgs/2019-07-15-human-machine-learning-motivation/pigeon_classifier_excelnet.jpg
---

The field of Artificial Intelligence started with inspiration, and ambition, to imitate our human cognition. We create things in our image and, well, they make similar mistakes:

> The biggest lie of every parent, pet owner and deep learning engineer:  
> “I’ve never shown it that, it must have learned it by itself!”  
> — a friend, Jan Rzymkowski, on FB; translation mine

While each particular machine learning algorithm comes with its own artifacts and limitations, some issues are much broader. In fact, there are limitations of any learning process, machine or human alike.
I think that it’s worth investigating these, as there is a lot of room for cross-pollination between machine learning and cognitive science.

> Speaking as a psychologist, I’m flabbergasted by claims that the decisions of algorithms are opaque while the decisions of people are transparent. I’ve spent half my life at it and I still have limited success understanding human decisions. - [Jean-François Bonnefon's tweet](https://twitter.com/JFBonnefon/status/1131889460927500288)

In this blog post, I will explain why I consider it an important, and fruitful, problem. My main point is to share my motivation for my other blog posts (existing and planned) exploring concrete aspects of human vs machine cognition.

![](/imgs/2019-07-15-human-machine-learning-motivation/artifact_data_science_martaczc.jpg)

> [Artifact in game vs in (data scientist)](https://www.deviantart.com/martaczc/art/Artifact-in-game-vs-in-data-scientist-life-609525369) life by MartaCzC (posted with permission)

## Motivation

We can explore learning patterns, [cognitive biases](https://en.wikipedia.org/wiki/List_of_cognitive_biases), and [logical fallacies](https://en.wikipedia.org/wiki/List_of_fallacies) through the prism of machine learning.
Moreover, biological systems keep inspiring progress of ML (evolutionary algorithm, artificial neural networks, attention). Or sometimes it turns out that deviating from biological inspirations does better (e.g. ReLU instead of sigmoid activations in deep learning).

Some of these issues are theoretical, good for neuroscientists and machine learning researchers. Others are crucial also for any practitioner — to make sure that we reduce (rather than amplify) social biases, improve safety, etc.

Except for scientific & philosophical curiosity, and ethical & safety concerns, I have also a more down-to-earth  motivation — I make my living teaching machine learning.

![](/imgs/2019-07-15-human-machine-learning-motivation/teach_people_to_teach_machines.png)

> “I teach people to teach machines” — [my LinkedIn post](https://www.linkedin.com/feed/update/urn:li:activity:6503583595418914816)

It’s handy to have useful analogies and metaphors, showing that machine learning is “reasoning on steroids”, rather than some kind of sorcery.

## Machine learning

If you need a general introduction, I wrote [Data science intro for math/phys background](https://p.migdal.pl/2016/03/15/data-science-intro-for-math-phys-background.html) in 2016. To my surprise, it is still up-to-date and useful to people coming from other backgrounds as well.

### Each computer model is different

Contrary to public reception,  “AI” is not a single method. Each machine learning model is different, with pros and cons, and there is not even hope for creating “the best one” for all data (so-called [no free lunch theorem](https://en.wikipedia.org/wiki/No_free_lunch_theorem)).
Computer cognition is different than our own. And varies from algorithm to algorithm. Querying a relational database with SQL is different than asking Alexa.

In my opinion, it is useful to compare various approaches, no matter if there are deterministic scripts, statistical models, “shallow” machine learning, or deep learning. All in all, people used the word “AI” for many things (“AI” for opponents in computer games is usually deterministic scripts).

Even when we look at classic machine learning classifiers, they differ both with their predictions and the way they arrive at such. Let's see [Scikit-learn classifier comparison](https://scikit-learn.org/stable/auto_examples/classification/plot_classifier_comparison.html): nearest neighbors, linear support vector machine (SVM), radial-basis function SVM, Gaussian process, a decision tree, Random Forest, etc.

![](/imgs/2019-07-15-human-machine-learning-motivation/sklearn_classifier_comparison.png)

So:

* Which algorithm is the best?
* Which algorithm creates predictions matching your own judgement?


There is a work-in-progress [Which Machine Learning algorithm are you?](https://github.com/stared/which-ml-are-you) by Katarzyna Kańska and me. For a longer list of interactive tools, see [Interactive Machine Learning, Deep Learning and Statistics websites](https://p.migdal.pl/interactive-machine-learning-list/). And if you like to draw your own classifiers, see [this livelossplot Jupyter Notebook](https://github.com/stared/livelossplot/blob/master/examples/2d_prediction_maps.ipynb).

### Even deep learning is simple

If you don’t know deep learning yet, it is a bunch of simple mathematics operations (addition, multiplication, maximal value).
Learning about deep learning made me think that it is not deep learning doing magic… it’s our cognition that is based on heuristics, that are just good enough.

![](/imgs/2019-07-15-human-machine-learning-motivation/pigeon_classifier_excelnet.jpg)

> From flesh to machines: pigeon learn to detect cancer tissue from images ([video](https://www.youtube.com/watch?v=flzGjnJLyS0), [paper summary](https://www.sciencemag.org/news/2015/11/pigeons-spot-cancer-well-human-experts)) or [MNIST recognition using spreadsheets](http://www.deepexcel.net/), without any macros.

Don’t take me wrong: mastering deep learning is hard and takes time (as of any specialized activity). But if you want to start playing with that, and you know Python, you can write your first network today, vide:

* [Learning Deep Learning with Keras](https://p.migdal.pl/2017/04/30/teaching-deep-learning.html) (2017)
* [Keras or PyTorch as your first deep learning framework](https://deepsense.ai/keras-or-pytorch/) (2018)
* [Thinking in Tensors, writing in PyTorch](https://github.com/stared/thinking-in-tensors-writing-in-pytorch/) (work in progress)

If you think that “oh, recognizing images can be done by machines, but feelings, sentience, spirituality, and deep motivations are inherently human”, I recommend reading [Consciousness Explained](https://en.wikipedia.org/wiki/Consciousness_Explained) by Daniel Dennett (and in general the philosophy of mind camp). It does the job at de-enchanting consciousness itself.


## Let’s learn from mistakes

> To err is human... and machine, alike.

If we get the correct answer to our question, we are happy… but that’s it.

> Everyone knows that dragons don’t exist. But while this simplistic formulation may satisfy the layman, it does not suffice for the scientific mind. […] The brilliant Cerebron, attacking the problem analytically, discovered three distinct kinds of dragon: the mythical, the chimerical, and the purely hypothetical. They were all, one might say, nonexistent, but each non-existed in an entirely different way. — [Stanisław Lem, The Cyberiad](https://www.goodreads.com/quotes/1132401-everyone-knows-that-dragons-don-t-exist-but-while-this-simplistic)

Usually, we can be right in one way but mistaken in infinitely many ways. And each of these reveals something about the cognitive process. Think about: Freudian slips — “when you say one thing, but mean your mother”. In a similar vein, word vectors can carry connotations, including undesirable ones (vide [How to make a racist AI without really trying](http://blog.conceptnet.io/posts/2017/how-to-make-a-racist-ai-without-really-trying/)). I recommend taking the [Implicit Bias Test](https://implicit.harvard.edu/implicit/takeatest.html) to see what are your unconscious biases for/against people of a given gender, age or ethnicity.

People learn a lot about human neuroscience from brain regions being damages, as in the famous book [The Man Who Mistook His Wife for a Hat](https://en.wikipedia.org/wiki/The_Man_Who_Mistook_His_Wife_for_a_Hat) by Oliver Sacks. With machine learning models, so far there is no ethics commission forbidding random experiments on them. Thanks to that I run [Deep Frankenstein: dissecting and sewing artificial neural networks](https://brainhackwarsaw.github.io/index.html#project4), at Brainhack (no pun intended!).

## Posts

So, without further ado, let’s jump to the content:

### Current

* [king — man + woman is queen; but why?](https://p.migdal.pl/2017/01/06/king-man-woman-queen-why.html) — touch the subject of analogies and cognitive metaphors with word embeddings such as word2vec or GloVe
* [Does AI have a dirty mind, too?](https://medium.com/@marekkcichy/does-ai-have-a-dirty-mind-too-6948430e4b2b) with [Marek K. Cichy](https://medium.com/u/5bf0995463b) — racy adversarial examples, or: seemingly NSFW illusions fooling nude picture detectors
* [Dreams, Drugs and ConvNets](https://medium.com/@pmigdal/dreams-drugs-convnets-ae7ed6ad50a5) — seeing patterns, in vivo & in silica; or: artifacts generated by artificial neural networks and by psychedelics


### Intend to write

But there are more coming!

* Overfitting — rote learning, superstitions, nipples and conspiracy theories
* Scalar fallacy — binary is bad, scalars are not enough
* AI is not an Abrahamic God — image classification is a reality, AGI and transhumanism are still sci-fi
* Trypophobia — the fear of holes (based on this), based on [a project with Grzegorz Uriasz and Artur Puzio](https://github.com/cytadela8/trypophobia) and [a subsequent one with Piotr Woźnicki and Michał Kuźba](https://github.com/kmichael08/trypophobia-detection)
* YOLO?! Object (mis)classification and safety

![PEGI](/imgs/2019-07-15-human-machine-learning-motivation/pegi.png)

All in all, [Pan European Game Information](https://pegi.info/) is a checklist. We will cover most of the points.

## Thanks

I am grateful to [Rafał Jakubanis](https://github.com/rafajak) and [Katarzyna Kańska](http://github.com/kkanska) for numerous remarks on the draft.
