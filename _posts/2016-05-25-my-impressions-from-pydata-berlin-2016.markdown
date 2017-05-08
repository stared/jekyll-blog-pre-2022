---
layout: "post"
title: "My impressions from PyData Berlin 2016"
date: 2016-05-25 14:42 +0100
author: Piotr Migdał
tags:
  - data-science
  - python
  - ephemeral
mathjax: false
description: "Was it worth it? (Yes.) Links to the best talks."
---


Last week I attended [PyData Berlin 2016](http://pydata.org/berlin2016/schedule/). It was my first non-academic conference. I was not sure if it was going to be interesting or going beyond things I can see on the Internet anyway. But since I've never been to Berlin, had an open invitation by a friend of mine[^skander], and it's 6.5h by train[^trains] from Warsaw, I decided to go.

td;dr: It was worth my time and I really enjoyed the event.


# Talks

Talks I have found the most interesting:

* Katharina Rasch, [What every Data Scientist should know about data anonymization](https://github.com/krasch/presentations/blob/master/pydata_Berlin_2016.pdf)
  * anonymization by merging unique rows; sensitive information is culture-dependent
* Łukasz Czarnecki, [Brand recognition in real-life photos using deep learning](http://www.slideshare.net/ukaszCzarnecki/brand-recognition-in-reallife-photos-using-deep-learning-lukasz-czarnecki-pydata-berlin-2016/)
  * if you use pre-trained convolutional neural network (like VGG_S), not that many samples are needed (~300 per class)
* Maciej Gryka, Removing Soft Shadows with Hard Data ([research paper](http://www0.cs.ucl.ac.uk/staff/M.Gryka/download/learning-to-remove-soft-shadows.pdf))
  * custom Random Forest can do wonders, even for problems typically suitable for CNNs (vide [image colorization](http://richzhang.github.io/colorization/))
* Julia Evans, [How to trick a neural network](http://jvns.ca/blog/2016/05/21/a-few-notes-from-my-pydata-berlin-keynote/)
  * a periodical reminder that learning by playing (and breaking) is the best way of learning
* Matthew Honnibal, Designing spaCy: A high-performance natural language processing (NLP) library written in Cython
  * after reading [Sense2vec with spaCy and Gensim](https://spacy.io/blog/sense2vec-with-spacy) it was insightful to hear about the package design philosophy

Also, these were good:

* Daniel Kirsch, [Functional Programming in Python](https://github.com/kirel/functional-python)
* David Higgins, [Introduction to Julia for Python programmers](https://github.com/daveh19/pydataberlin2016)
* Katharine Jarmul, [Holy D@t*! How to Deal with Imperfect, Unclean Datasets](https://docs.google.com/presentation/d/1G-lgHKTdrqeeJhcvVmd7C9gOIfTRe429zhBN6lmKKzA/)
* Ian Ozsvald, [Statistically Solving Sneezes and Sniffles (a work in progress)](http://ianozsvald.com/2016/05/07/statistically-solving-sneezes-and-sniffles-a-work-in-progress-report-at-pydatalondon-2016/)
* Olivier Grisel, [Evolution of the pydata ecosystem](http://ogrisel.github.io/decks/2016_pydata_berlin/)
* Delia Rusu, [Estimating stock price correlations using Wikipedia](https://speakerdeck.com/deliarusu/estimating-stock-price-correlations-using-wikipedia)

And talks I missed, but I am sure were great:

* Wes McKinney, [Python Data Ecosystem: Thoughts on Building for the Future](http://www.slideshare.net/wesm/python-data-ecosystem-thoughts-on-building-for-the-future)
* Lev Konstantinovskiy, [Practical Word2vec in Gensim](https://github.com/RaRe-Technologies/movie-plots-by-genre) (workshop)
* Maciej Jaskowski, [Let's play Space Invaders!](http://maciejjaskowski.github.io/2016/03/09/space-invaders.html)

If your beloved talk is not there, don't cry - most likely it was in a parallel session. (Also, in general topic selection and quality of presentation was good.)

I had a lightning talk: [Teaching Machine Learning](https://speakerdeck.com/pmigdal/teaching-machine-learning). I should write a blog post on it one day (especially on the [5-day data analysis summer school for sociology students and researchers](https://github.com/DELabUW/szkola-letnia-2015), as now materials are in Polish). As for now, it is implicitly covered in [Data science intro for math/phys background](http://p.migdal.pl/2016/03/15/data-science-intro-for-math-phys-background.html).


# Other take-home lessons

* There are so many ex-physicists. I even heard *Hey, I saw you... on ICPS*[^icps].
* Many methods are new, so it's crucial to learn them (and how can they be tailored to your tasks); sometimes being an expert with 10-year experience is physically impossible.
* The number of participants was optimal (200? I hate huge conferences).
* If other PyData events are of similar quality, it's not my last time there! :)


# Links

* [PyData Berlin 2016 Materials](https://github.com/deeplook/pydata_berlin2016_materials) (mainly slides)
* [Notes from my PyData Berlin keynote by Julia Evans](http://jvns.ca/blog/2016/05/21/a-few-notes-from-my-pydata-berlin-keynote/)
* If your have your own blog post or photo gallery from this event - mail me! :)
* UPDATE: [There are videos from the talks](https://www.youtube.com/playlist?list=PLGVZCDnMOq0ogEIvRHZyXMNJwkEPHi6Bl)!

Thanks to the organizers!


[^skander]: Thanks Skander!
[^trains]: I love traveling by train. And I spend my time in trains more productively than in the office. I work, read or sleep... efficiently. I guess it's mainly because of slow Internet connection, fixed time, and less opportunities for distraction.
[^icps]: [International Conference of Physics Students](https://en.wikipedia.org/wiki/International_Conference_of_Physics_Students), not [International Carnivorous Plant Society](http://www.carnivorousplants.org/). Since ICPS is a very student event (a crazy conference party each night), I got scared. Fortunately, [Martina Pugliese](https://twitter.com/m_letitbe) remembered me from giving [A mathematical model of the Mafia game](https://arxiv.org/abs/1009.1031) talk. It was in 2010 in Graz; for a moment of nostalgia, here [are my photos](http://migdal.zenfolio.com/2010/icps2010graz).
