---
layout: post
title:  "Why do word2vec analogies work?"
date:   2016-08-28 13:24:00 +0100
author: Piotr Migdał
tags:
  - machine-learning
mathjax: true
description: 'Some desc'
image: /imgs/word2vec_julia.jpg
---

## Counts, coincidences and meaning

Sometimes a seemingly naive technique gives powerful results. Perhaps you've heard about changing words into vectors, so that `king - man + woman = queen`. I will try to explain why it works!
Consider this sentence:

> a small, fluffly roosety climbed a tree

What's a `roosety`? I would say that something like a squirrel, since two words can be easily interchanged. What's funny, we don't even need to know grammar to be able to tell if one word can be replaced by another - all we need is to know probabilities that certain word co-occur within a short distance (let say: 3).

How we can write


Let $$P(w_a, w_b)$$ be the probability that words $$w_a$$ and $$w_b$$ co-occur within short distance.

Two words are similar if

$$ P(w|w_a) = P(w|w_b) $$

for every word *w*. If we divide both sides $$P(w)$$ and apply logarithm we get

$$ PMI(w, w_a) = PMI(w, w_b) $$

[pointwise mutual information](https://en.wikipedia.org/wiki/Pointwise_mutual_information), a quantity I am in love with (see [TagOverflow](https://github.com/stared/tagoverflow#tagoverflow) and other co-occurrence graphs).


## Compression

> (Cultures of Machine Learning) The Compressors: View cognition as compression.

from https://news.ycombinator.com/item?id=10954508

Even with a small dictionary of 100 000 words, keeping track of all pairs would require 8 gigabytes of space.

$$ PMI(w_a, w_b) = \vec{v}_a \cdot \vec{v}_b, $$

were $$\vec{v}_i$$ are vectors, typically of 50-300 dimensions.

As we see, the condition

$$ PMI(w, w_a) = PMI(w, w_b) $$

$$ \vec{v} \cdot \vec{v}_a = \vec{v} \cdot \vec{v}_b $$

$$ \vec{v} \cdot \left( \vec{v}_a - \vec{v}_b \right) = 0 $$

Test: ♂ 

## Analogies



Sometimes we can get


See:

* GloVe
* country - capital from
* coming soon: ...


## Difference


## Technicalities


Typically there are two sets of vectors - left and right.

Word and context.

PPMI - positive pointwise mutual information.

Weighting.

Different algorithms.


## Things that do not make sense

* word1 + word2 (though, (word1 + word2)/2 does)
* word1 - word2 (at least, not as a word)

## Play with it!

[link to notebook]

Stay tuned -

## Outline

* text was
* words, pairs
* different algorithms
* https://hackpad.com/word2links-961ICHP0Lkl


## References

* http://nlp.stanford.edu/projects/glove/
* Jeffrey Pennington, Richard Socher, Christopher D. Manning, [GloVe: Global Vectors for Word Representation](http://nlp.stanford.edu/pubs/glove.pdf) (2014)
* [Chapter 19: Vector Semantics](https://web.stanford.edu/~jurafsky/slp3/19.pdf) from Daniel Jurafsky, James H. Martin, [Speech and Language Processing](https://web.stanford.edu/~jurafsky/slp3/) (2015)

![](/imgs/word2vec_julia.jpg)
