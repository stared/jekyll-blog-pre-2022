---
layout: "post"
title: "Quantum mechanics for high-school students"
date: "2016-08-01 11:38"
---

> Before applying consult with your teacher or professor, as every misused didactic material may result in misunderstanding or discouragement.

A few times I gave introduction to quantum mechanics for talented high-school students. Here I share outlines and materials.

One of their consequences is [Quantum Game with Photons](http://quantumgame.io).


# Philosophy

(but with some experimental footing)

My general approach is to start with (classical) polarization of light, as it is a thing that:
- is simple and can be visualized geometrically,
- can be directly shown (e.g. with polarizations sheets, which I have).

And IMHO starting with classical mechanics (continuous variables) is the worst approach, as it is:
- difficult and
- seeds some wrong intuitions.

# Materials

* Valerio Scarani, [Six Quantum Pieces: A First Course in Quantum Physics](http://www.amazon.com/Six-Quantum-Pieces-Course-Physics/dp/9814327549)
* Simon Singh, The Code Book
  * a general intro to cryptography
* Carl D. Meyer, [Matrix Analysis and Applied Linear Algebra](http://www.matrixanalysis.com/DownloadChapters.html)
  * a general intro/reference to linear algebra, very simply and didactically written
* [1-D Quantum Mechanics](http://www.falstad.com/qm1d/) (on http://www.falstad.com/mathphysics.html)
  * Play with it (it is nice also for older kids; at least I am in love with it); you can easily create coherent or squeezed states for the harmonic oscillator potential.
* From the same site, also [Ripple Tank](http://www.falstad.com/ripple/) is marvelous:
  * You can see the interference, the total internal reflection, the lensing, the Fresnel zone plates, the Doppler effect, the scattering and many, many other phenomena.
* XXX speakerdeckize http://dl.dropbox.com/u/17968211/polarization-of-light.zip
  * (they work well with actually showing phenomena, I always bring my polarization sheets).
* XXX Quantum game XXX
* XXX Azimuth blog post XXX

# Course outlines

## Quantum optics, 7th WWW (2011)

* "Quantum optics" on "7th Scientific Summer School" (a camp that I co-organized)
  * XXX [Indie camp for high school geeks]() XXX
* 8-18 Aug 2011, Olsztyn, Poland
* http://warsztatywww.wikidot.com/www7:optyka-kwantowa
* 3h x 3 day workshop for talented high-schools students
* there were difficult qualification tasks both as a strong filter and to teach preliminary materials:
  * complex numbers (including radial representation),
  * basics of linear algebra,
  * quantum jargon (bras, kets and daggers).

### Outline

1. Polarization of light

  What is that, how can we act on it (wave plates, polarizers, rotation by a solution of sugar, ...); also: the 3 polarizers "paradox".

2. Quants and measurement

  Single photons behave in the same as a classical wave, just they can't be measured partially, only 0/1. And then the quantum measurement is the most intuitive interpolation of the classical measurement.

3. Superposition vs mixture

  How to tell the difference using interference. Detection of the light-sensitive bomb.

4. Entanglement

  What is that? Why it is the most intuitive approach to more particles? Relation between interference, entanglement and looking at objects.

### After

Notes by one of the participants:
http://dl.dropbox.com/u/17968211/www7quantum_notes_by_lis.zip
(beautiful font, nice drawings, ...)

It went really well (though I had a lot of luck to get so outstanding participants).
Also, it can be made a bit simpler, with less mathematics.

XXX Photo XXX

## Quantum cryptography, ICFO (2011)

* Programma Jonevs y Ciencia
* 15.06-15.07.2011, ICFO, Castelldefels (Barcelona)
* 6h twice a week
* 2 participants

General idea:
- Rather involve and inspire than merely give lectures.
- Use Python (or Mathematica) to actually test different cryptographic protocols (and sometimes - a coin), It's more convincing  for high-school students to see things actually working than proving things.
- Give simple homework exercises (given printed or in pdf, with lecture notes).
- Don't use more formalism/mathematics than it's necessary.
- Flexibly change the program according to their skills and interests.

### Outline

`*` - an additional material that I used
`**` - an additional material that I didn't use

#### 1. Classical cryptography

1.1. Naive letter/word relabeling
- give some interesting historical examples
- as an example use rot13
- `**` show that natural languages can be easily detected (with analysis of ngrams - i.e. frequencies of short strings of letters)

1.2. Perfect XOR
- show that is is perfect
- no difference between the message and the key
- practice on black&white images
- and on words (character -> 8 bits -> encoding -> sending -> decoding -> 8 bits -> character)
- but how to distribute the key?

1.3 `**` RSA
- modulo, factorability
- asymmetric codes, the actual RSA procedure
- it's hard to break but not impossible (give time estimations with _current_ technology)

#### 2. Quantum cryptography

2.1. Measurement of the (classical) polarization of light
- `*` introduction to complex numbers
  - complex numbers are worth introducing on their own - not difficult, useful, and (geek) kids like it
- description of polarization with two numbers
- polarizer, measurement of intensity, cos^2(alpha)
- rotation of polarization (e.g. with half wave plates)
- 2x2 matrices, how one can describe rotations and measurements with them
- decomposition of a vector in different bases

2.2. Introduction to quantum mechanics (of two polarizations)
- but what if there are no 'intensities' but only counts of single photons?
- superposition vs mixture

2.3. BB84 protocol
- 2 bases, the actual protocol
- why Eve cannot simply eavesdrop without influencing noise
- how to estimate number of bits which can be in hands of Eve
- `*` 3 bases

2.4. `**` Quantum entanglement
- Bell pairs, how to deal with them mathematically
- classical correlations or more
- Bell inequality (including futile trails to break it )
- nonlocal boxes
- quantum teleportation

2.5 `**` Information theory
- Shannon entropy; when one can compress a file, how to play in "twenty questions" game
- how to quantize the sent information (quantum or classical), when there is noise in the channel
- how to check if information is altered and how to fix it (check sum, Hamming codes)

### After

It went wonderful with one participant, but not the other.

## XXX This later at ICFO

## Serock 2016

https://hackpad.com/Optyka-kwantowa-Serock-2016-1xz8YYy9yBu
