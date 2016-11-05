---
layout: post
title:  "Why do word2vec analogies work?"
date:   2016-11-04 13:24:00 +0100
author: Piotr Migdał
tags:
  - machine-learning
mathjax: true
description: 'Some desc'
image: /imgs/word2vec_julia.jpg
---

Words, vectors, analogies

## Intro

word2vec transforms words into vectors, so that words with similar meaning end up laying close to each other. Moreover, it allows us to use vector arithmetics to work with analogies, for example the famous `king - man + woman = queen`.

I will try to explain how it works, with the special emphasis on the meaning of a vector difference, at the same time omitting as many technicalities as possible.

## Counts, coincidences and meaning

Sometimes a seemingly naive technique gives powerful results. It turns that merely looking at word coincidences, while ignoring all grammar and context, can provide us insight into the word meaning.
Consider this sentence:

> a small, fluffy roosety climbed a tree

What's a `roosety`? I would say that something like a squirrel, since two words can be easily interchanged. Such reasoning is called the [distributional hypothesis](https://en.wikipedia.org/wiki/Distributional_semantics) and summarized as:

> a word is characterized by the company it keeps (John Rupert Firth)

If we want to teach it to a computer, the simplest approach is making it look only at word pairs.
Let *P(a|b)* be conditional probability that given a word *b* there is word *a* within a short distance (let's say - being spaced by no more that 2 words).
Then we claim that two words *a* and *b* are similar if

$$ P(w|a) = P(w|b) $$

for every word *w*.
In other words, if we have this equality, no matter if there is word *a* or *b*, all other words occur with the same frequency.


## Pointwise mutual information and compression

In principle, we can compute *P(a|b)* for every word pair.
But even with a small dictionary of 100 000 words (bear in mind we need to keep all declinations, proper names and things which are not in official dictionaries, yet are in use) keeping track of all pairs would require 8 gigabytes of space.

Often instead of working with conditional probabilities, we use the [pointwise mutual information](https://en.wikipedia.org/wiki/Pointwise_mutual_information), defined as:

$$ PMI(a, b) = \log \left[ \frac{P(a,b)}{P(a)P(b)} \right] = \log \left[ \frac{P(a|b)}{P(a)} \right].$$

Its direct interpretation is how much more likely we get a pair than if it were at random.
Logarithm makes it easier to work with [words appearing at frequencies](https://en.wiktionary.org/wiki/Wiktionary:Frequency_lists/) of different orders of magnitude.
I am in love with (see [TagOverflow](https://github.com/stared/tagoverflow#tagoverflow) and other co-occurrence graphs).

(Digression: [Heavy Metal and Natural Language Processing - Part 1](http://www.degeneratestate.org/posts/2016/Apr/20/heavy-metal-and-natural-language-processing-part-1/))

Regardless if we see [cognition as compression](https://news.ycombinator.com/item?id=10954508), or consider it only a numerical trick, we can approximate *PMI* as a vector scalar product:

$$ PMI(a, b) = \vec{v}_a \cdot \vec{v}_b, $$

where $$\vec{v}_i$$ are vectors, typically of 50-300 dimensions.

XXX Or maybe actually showing with left and right vectors, as it make some stuff simpler, and more fair, and with easier limit for dim=dictionary_size XXX

At the first glance it may be strange that all words can be compressed to a space of much smaller dimensionality. But there are words that can be trivially interchanged (e.g. *John* to *Peter*) and there is a lot of structure in general (we will see a bit of it in the **Analogies** section).

## Similarity

The condition that *P(w|a)=P(w|b)* is equivalent to

$$ PMI(w, a) = PMI(w, b), $$

which (after expressing it with vectors) is

$$ \vec{v}_w \cdot \vec{v}_a = \vec{v} \cdot \vec{v}_b $$

$$ \vec{v}_w \cdot \left( \vec{v}_a - \vec{v}_b \right) = 0 $$

If it needs to work for every $$ \vec{v}_w \cdot $$, then

$$ \vec{v}_a = \vec{v}_b. $$

Of course, in every practical case we won't get an exact equality, just words being close to each other. But thanks to looking at the vectors, we can look for synonyms (or often: antonyms).

## Analogies

What I find much more interesting is that words form a linear space. In particular, a zero vector represent a totally uncharacteristic word, occurring with every other word at the random chance level.




Sometimes we can get


See:

* GloVe
* country - capital from
* coming soon: ...

Analogies can be of various form - including cities and their zip codes. (XXX link XXX)


## Difference

Test: ♂

## Things that do not make sense

* word1 + word2 (though, (word1 + word2)/2 does)
* word1 - word2 (at least, not as a word)

## Technicalities

* const * word

Typically there are two sets of vectors - left and right.

Word and context.

PPMI - positive pointwise mutual information.

Weighting.

Different algorithms.




## Play with it!

[link to notebook]

Stay tuned -

## Outline

* text was
* words, pairs
* different algorithms
* https://hackpad.com/word2links-961ICHP0Lkl


## Why this entry

2 week summer internship for Julia Bazińska,

See also my blog posts:

* [Helping exceptionally gifted children in Poland](http://crastina.se/gifted-children-in-poland-by-piotr-migdal/) (on the Polish Children's Fund)
* [D3.js workshop at ICM for KFnrD](http://p.migdal.pl/2016/02/09/d3js-icm-kfnrd.html)

## References

* [GloVe: Global Vectors for Word Representation](http://nlp.stanford.edu/projects/glove/)
  * Jeffrey Pennington, Richard Socher, Christopher D. Manning, [GloVe: Global Vectors for Word Representation](http://nlp.stanford.edu/pubs/glove.pdf) (2014)
* Daniel Jurafsky, James H. Martin, [Speech and Language Processing](https://web.stanford.edu/~jurafsky/slp3/) (2015)
  * [Chapter 15: Vector Semantics](https://web.stanford.edu/~jurafsky/slp3/15.pdf) (and [slides](https://web.stanford.edu/~jurafsky/slp3/slides/vector1.pdf))
  * [Chapter 16: Semantics with Dense Vectors](https://web.stanford.edu/~jurafsky/slp3/16.pdf) (and [slides](https://web.stanford.edu/~jurafsky/slp3/slides/vector2.pdf))
* [Five crazy abstractions my Deep Learning word2vec model just did](http://byterot.blogspot.com/2015/06/five-crazy-abstractions-my-deep-learning-word2doc-model-just-did-NLP-gensim.html)
* George Lakoff, Mark Johnson, [Metaphors We Live By](https://www.amazon.com/Metaphors-We-Live-George-Lakoff/dp/0226468011)
* [Conceptual Metaphor Home Page by George Lakoff ](http://web.archive.org/web/20121015142744/http://cogsci.berkeley.edu/lakoff) (1994, webarchive)
* [Language necessarily contains human biases, and so will machines trained on language corpora](https://freedom-to-tinker.com/2016/08/24/language-necessarily-contains-human-biases-and-so-will-machines-trained-on-language-corpora/)
* [Improving Distributional Similarity with Lessons Learned from Word Embeddings](https://levyomer.wordpress.com/2015/03/30/improving-distributional-similarity-with-lessons-learned-from-word-embeddings/)
* [Skipgram isn’t Matrix Factorisation](http://building-babylon.net/2016/05/12/skipgram-isnt-matrix-factorisation/)
* [Sense2vec with spaCy and Gensim](https://explosion.ai/blog/sense2vec-with-spacy)
* [How does word2vec work? by Omer Levy](https://www.quora.com/How-does-word2vec-work)
* [A Word is Worth a Thousand Vectors](http://multithreaded.stitchfix.com/blog/2015/03/11/word-is-worth-a-thousand-vectors/) by Chris Moody
* [Making sense of word2vec](https://rare-technologies.com/making-sense-of-word2vec) by Radim Rehurek
* [Vector Representations of Words - TensorFlow Tutorial](https://www.tensorflow.org/versions/r0.11/tutorials/word2vec/index.html)
  * [Jupyter Notebook from Udacity Course](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/examples/udacity/5_word2vec.ipynb)
* [Distributional approaches to word meanings - Ling 236/Psych 236c, Stanford (Potts)](http://web.stanford.edu/class/linguist236/materials/ling236-handout-05-09-vsm.pdf)

![](/imgs/word2vec_julia.jpg)
