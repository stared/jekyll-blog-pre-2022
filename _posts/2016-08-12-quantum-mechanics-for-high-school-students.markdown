---
layout: "post"
title: "Quantum mechanics for high-school students"
date: 2016-08-12 14:42 +0100
tags:
  - quantum
  - teaching
mathjax: true
description: "Outlines and materials related to my basics courses, with light polarization as the quantum information carrier."
image: /imgs/2016-08-12-quantum-whiteboard-julia.jpg
---

![No-cloning theorem with Júlia Amorós Binefa in 2012](/imgs/2016-08-12-quantum-whiteboard-julia.jpg)

A few times I gave introductions to quantum mechanics for talented high-school students, in Poland (2011, 2016) and in Spain[^catalonia] (2011, 2012).

I have already shared it a few times over the course of years. Now I have found some time[^finding_time] to clean it a bit, hoping that you may find it useful or inspiring for others.

I certainly keeps inspiring me. First two workshops convinced me that quantum mechanic isn't that hard or bizarre and can be thought to motivated high-school students[^who_can]. Moreover, one of its consequences is [Quantum Game with Photons](http://quantumgame.io) I am developing (but is playable at this stage! and certainly sufficient as a sandbox for interferometers - use `∞` mode).


## My approach

Before jumping into actual content, let me explain my approach. Some is my teaching credo (I don't want to argue with others, as it is a matter of taste, not - fact), some are lessons learnt (often the hard way).

### What

I use light polarization as the prototypical two-level quantum system, starting from vectors and 2x2 matrices (with straightforward calculations rather than abstraction), as it:

* is simple and can be visualized geometrically,
* can be explained classically, with a smooth transition into the quantum world,
* can be directly demonstrated (e.g. with polarizations sheets, polarization filters, LCD screen, reflections, sugar solutions, [naked eye](https://en.wikipedia.org/wiki/Haidinger%27s_brush)),
* passes the [Scott Aaronson's Minus-Sign Test](http://www.scottaaronson.com/blog/?p=613) in a simple way[^minus_sign] (crucial!),
* directly translates to applications like quantum cryptography.

A classical[^classical] quantum mechanics introductions starts from position (and momentum) of a single particle. Sure, it has valuable pieces like calculating energies and orbitals, and there is the Heisenberg uncertainty principle. However, IMHO starting with classical mechanics (continuous variables) is the worst approach, as it is:

* starts with infinitely dimensional Hilbert space,
* requires classical mechanics background,
* seeds some wrong intuitions due to classical mechanics as the background,
* it's easy to sink into technicalities of differentiating and integrating.

Working with electrons as the two-state system (spin up, spin down) has the benefit, however:

* the classical-quantum link is much more complicated,
* no way to show it directly,
* rotations can be tricky (try explaining that spin-up plus spin-down is spin-left).

### How

Moreover, when it comes to the mathematical tools, I try not treating them as a necessary evil or means to an end, as:

* complex numbers are interesting on their own,
* polarization of light is interesting on its own,
* linear algebra is useful on its own.

When it comes to delivery:

* rather involve and inspire than merely give lectures,
* use Python (previously Mathematica) to actually calculate and plot things,
* don't use more formalism/mathematics than it's necessary,
* flexibly change the program according to their skills and interests,
* more in my answer [How to improve myself as a lecturer - Academia Stack Exchange](http://academia.stackexchange.com/questions/5236/how-to-improve-myself-as-a-lecturer/5249#5249).

For experimental stuff, it's crucial to show first, explain later (otherwise you are killing suspension and awe):

> The researchers' conclusion was that, in the context of strange toys of unknown function, prior explanation does, indeed, inhibit exploration and discovery.

from [When should you teach children, and when should you let them explore? - The Economist](http://www.economist.com/node/18741484).

![LCD screen + plastic cup + polarizer](/imgs/2016-08-12-quantum-polarization.jpg)


## Materials

### Simple books

* Valerio Scarani, [Six Quantum Pieces: A First Course in Quantum Physics](http://www.amazon.com/Six-Quantum-Pieces-Course-Physics/dp/9814327549)
  * the first few chapters are great (it also starts with a single photon and polarization), then it quickly gets too abstracts (optimal cloning)
* Andrzej Dragan, [Niezwykle Szczególna Teoria Względności](http://www.fuw.edu.pl/~dragan/Fizyka/Nstw.pdf) (*Extraordinarily Special Relativity*), chapter 5. on Bell inequality (in Polish)
* Leonard Susskind, Art Friedman, [Quantum Mechanics: The Theoretical Minimum. What You Need to Know to Start Doing Physics.](http://www.amazon.com/Quantum-Mechanics-Theoretical-Leonard-Susskind/dp/0465062903)
  * two-level system, though with an electron which is conceptually harder  
  * also in Polish: [Mechanika kwantowa - teorytyczne minimum](http://www.proszynski.pl/Mechanika_kwantowa__Teoretyczne_minimum-p-33197-.html)
* Konrad Banaszek, Rafał Demkowicz-Dobrzański, [Quantum information 1/2](http://www.fuw.edu.pl/~demko/Teksty/ik05/2012/qi12.pdf)
  * lecture notes; it starts with two-level system of polarization of light; it is not incidental - Konrad Banaszek was my MSc advisor and I was raised in this quantum optical environment
  * also some exercises: http://www.fuw.edu.pl/~demko/students.html

### Online stuff

* [1-D Quantum Mechanics](http://www.falstad.com/qm1d/) (on http://www.falstad.com/mathphysics.html)
  * Play with it (it is nice also for older kids; at least I am in love with it); you can easily create coherent or squeezed states for the harmonic oscillator potential.
* From the same site, also [Ripple Tank](http://www.falstad.com/ripple/) is marvelous:
  * You can see the interference, the total internal reflection, the lensing, the Fresnel zone plates, the Doppler effect, the scattering and many, many other phenomena.
* my [Quantum Game with Photons](http://quantumgame.io)
* [Quantum Circuit Simulator: Quirk](http://algorithmicassertions.com/2016/05/22/quirk.html)
  * direct link: http://www.davyw.com/quantum/
* [Eigenvectors and Eigenvalues - Visually Explained](http://setosa.io/ev/eigenvectors-and-eigenvalues/)
* Python (in [Jupyter Notebook](http://jupyter.readthedocs.io)) for calculations and plots
  * see my blog entry: [Data science intro for math/phys background ](http://p.migdal.pl/2016/03/15/data-science-intro-for-math-phys-background.html) and the paragraph on Python
  * see [Qubism in QuTiP](http://nbviewer.jupyter.org/github/qutip/qutip-notebooks/blob/master/examples/example-qubism-and-schmidt-plots.ipynb)

### Websites

* [Jones calculus - Wikipedia](https://en.wikipedia.org/wiki/Jones_calculus)
* my entry [Quantum superposition - Azimuth blog](https://johncarlosbaez.wordpress.com/2015/03/13/quantum-superposition/) or why does an electron need to be in two places at once
* [Visualizing complex-valued functions with Matplotlib and Mayavi - Emilia Petrisor](http://nbviewer.jupyter.org/github/empet/Math/blob/master/DomainColoring.ipynb)
* [What is i^i? - SMBC so NSFW](http://www.smbc-comics.com/?id=2934)

### Textbooks

* Berthold-Georg Englert, [Lectures on Quantum Mechanics - Volume 1: Basic Matters](http://www.amazon.com/Lectures-Quantum-Mechanics-Basic-Matters/dp/9812569707)
  * a wonderful [course by Jacek Dobaczewski](http://www.fuw.edu.pl/~dobaczew/kwanty/kwanty.html) I had as an introduction to QM was based on that
  * [a poem, as a homework](http://www.fuw.edu.pl/~dobaczew/kwanty/wiersz.html) (in Polish)
* David Griffiths, [Introduction to Quantum Mechanics](https://archive.org/details/IntroductionToQuantumMechanics_718)
  * [an opinion on Quora](https://www.quora.com/Is-it-wise-to-read-Principles-of-Quantum-Mechanics-2nd-Edition-R-Shankar-as-an-introductory-textbook-in-quantum-mechanics)
* R. Shankar, [Principles of Quantum Mechanics](https://www.amazon.com/Principles-Quantum-Mechanics-2nd-Shankar/dp/0306447908)
* I **do not** recommend Leonard I. Schiff, [Quantum mechanics](https://archive.org/details/QuantumMechanics_500)
  * it is a common introduction, but one stuck in the worst classical rut
* [The Feynman Lectures on Physics, Volume III](http://www.feynmanlectures.caltech.edu/III_toc.html)
  *  I love the series, but in the case of Vol. III - please use it only as a supplement; there are some unique and insightful things like [chapter 7](http://www.feynmanlectures.caltech.edu/III_07.html) [chapter 10](http://www.feynmanlectures.caltech.edu/III_10.html)
* Michael A. Nielsen, Isaac L. Chuang, [Quantum Computation and Quantum Information](https://www.amazon.com/Quantum-Computation-Information-10th-Anniversary/dp/1107002176)
  * so called *the green book*
  * introduction from the non-physical perspective
* Carl D. Meyer, [Matrix Analysis and Applied Linear Algebra](http://www.matrixanalysis.com/)
  * a general intro/reference to linear algebra, very simply and didactically written (relevant chapters: 3, 4, 5)


## Course outlines

I did it four times:

* Jun-Jul 2011, Castelldefels, Spain, [ICFO](https://www.icfo.eu/) for [Jóvenes y Ciencia](http://www.fundaciocatalunya-lapedrera.com/es/content/j%C3%B3venes-y-ciencia)
* Aug 2011, Olsztyn, Poland, [7th Scientific Summer School](http://warsztatywww.wikidot.com/en:indie-camp-for-hs-geeks)
* Jun-Jul 2012, Castelldefels, Spain, [ICFO](https://www.icfo.eu/) for [Jóvenes y Ciencia](http://www.fundaciocatalunya-lapedrera.com/es/content/j%C3%B3venes-y-ciencia)
* May 2016, Serock, Poland, [Polish Children's Fund](crastina.se/gifted-children-in-poland-by-piotr-migdal/)


### Quantum optics, 7th Scientific Summer School (2011)

* whole camp during: 8-18 Aug 2011, Olsztyn, Poland
* [Optyka kwantowa - WWW 7](http://warsztatywww.wikidot.com/www7:optyka-kwantowa) (outline and problems, in Polish)
* around 6 participants
* 3h x 3 day workshop for talented high-schools students

![Quantum Zeno effect with polarization rotation by Krzysztof Lis](/imgs/2016-08-12-quantum-zeno-lis.jpg)

#### Outline

`0.` Linear algebra (in qualification tasks)

  Complex numbers (including radial representation), basics of linear algebra, quantum jargon (bras, kets and daggers).

`1.` Polarization of light

  What is that, how can we act on it (wave plates, polarizers, rotation by a solution of sugar, ...); also: the 3 polarizers "paradox".

`2.` Quants and measurement

  Single photons behave in the same as a classical wave, just they can't be measured partially, only 0/1. And then the quantum measurement is the most intuitive interpolation of the classical measurement.

`3.` Superposition vs mixture

  How to tell the difference using interference. Detection of the light-sensitive bomb.

`4.` Entanglement

  What is that? Why it is the most intuitive approach to more particles? Relation between interference, entanglement and looking at objects.

### Quantum cryptography, ICFO (2011)

* [Jóvenes y Ciencia](http://www.fundaciocatalunya-lapedrera.com/es/content/j%C3%B3venes-y-ciencia)
* [ICFO](https://www.icfo.eu/), Castelldefels (Barcelona)
* 15 Jun - 15 Jul 2011
* 6h twice a week
* 2 participants

#### Outline

`*` - an additional material that I used
`**` - an additional material that I didn't use

`1.` Classical cryptography

1.1. Naive letter/word relabeling

* give some interesting historical examples
* as an example use rot13
* `**` show that natural languages can be easily detected (with analysis of ngrams - i.e. frequencies of short strings of letters)

1.2. Perfect XOR

* show that is is perfect
* no difference between the message and the key
* practice on black&white images
* and on words (character -> 8 bits -> encoding -> sending -> decoding -> 8 bits -> character)
* but how to distribute the key?

1.3. `**` RSA

* modulo, factorability
* asymmetric codes, the actual RSA procedure
* it's hard to break but not impossible (give time estimations with _current_ technology)

`2.` Quantum cryptography

2.1. Measurement of the (classical) polarization of light

* `*` introduction to complex numbers
  * complex numbers are worth introducing on their own - not difficult, useful, and (geek) kids like it
* description of polarization with two numbers
* polarizer, measurement of intensity, cos^2(alpha)
* rotation of polarization (e.g. with half wave plates)
* 2x2 matrices, how one can describe rotations and measurements with them
* decomposition of a vector in different bases

2.2. Introduction to quantum mechanics (of two polarizations)

* but what if there are no 'intensities' but only counts of single photons?
* superposition vs mixture

2.3. BB84 protocol

* 2 bases, the actual protocol
* why Eve cannot simply eavesdrop without influencing noise
* how to estimate number of bits which can be in hands of Eve
* `*` 3 bases

2.4. `**` Quantum entanglement

* Bell pairs, how to deal with them mathematically
* classical correlations or more
* Bell inequality (including futile trails to break it)
* nonlocal boxes
* quantum teleportation

2.5 `**` Information theory

* Shannon entropy; when one can compress a file, how to play in "twenty questions" game
* how to quantize the sent information (quantum or classical), when there is noise in the channel
* how to check if information is altered and how to fix it (check sum, Hamming codes)


## And...?

If you want to use any materials - feel free! Though, I would be even happier if you tell me that.

If you have some other materials or references - just send them. Maybe it will inspire me how to do the next course.

I consider writing a simple introduction to quantum mechanics, with interactive simulations. If you consider it a great ideas, consider poking me. :)


> Before applying consult with your teacher or professor, as every misused didactic material may result in misunderstanding or discouragement.

[^catalonia]: Or rather: Catalonia!
[^finding_time]: Read: stolen time from other projects or was doing [white procrastination](http://paulgraham.com/procrastination.html).
[^who_can]: As a rule of thumb I can explain what is quantum mechanics in 3h, if the other person knows what are matrices.
[^minus_sign]: $$|\uparrow_z\rangle + |\downarrow_z\rangle \propto |\uparrow_x\rangle$$
[^classical]: Nomen omen!
