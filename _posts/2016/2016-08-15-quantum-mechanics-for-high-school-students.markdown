---
layout: "post"
title: "Quantum mechanics for high-school students"
date: 2016-08-15 18:30 +0100
author: Piotr Migdał
tags:
  - quantum
  - teaching
mathjax: false
description: "Outlines and materials related to my basics courses, with light polarization as the quantum information carrier."
image: /imgs/2016-08-15-quantum-whiteboard-julia.jpg
extras:
  - text: "shared on r/Physics with over 300 upvotes"
    href: https://www.reddit.com/r/Physics/comments/5o3g7i/quantum_mechanics_for_highschool_students/
---

![No-cloning theorem with Júlia Amorós Binefa in 2012](/imgs/2016-08-15-quantum-whiteboard-julia.jpg)

*A participant, Julia Amorós Binefa, and the no-cloning theorem - ICFO, 2012.*

A few times I gave introductions to quantum mechanics for talented high-school students, in Poland (2011, 2016) and in Spain[^catalonia] (2011, 2012). I have been sharing the materials over the course of years. Now I have found some time[^finding_time] to clean it up a bit, hoping that you may find it useful or inspiring.

It certainly keeps inspiring me! First two workshops convinced me that quantum mechanics isn't that hard or bizarre and can be explained to motivated high-school students[^who_can]. Moreover, it resulted in the [Quantum Game with Photons](http://quantumgame.io). It's still in development, but already playable at this stage (and certainly sufficient as a sandbox for interferometers - use `∞` mode).


## My approach

Before jumping into the actual content, let me explain my approach. Some is my teaching credo (I don't want to argue with others, as it is a matter of taste, not - fact), some are lessons learnt (often the hard way).

### What

I use light polarization as the prototypical two-level quantum system, starting from vectors and 2x2 matrices (with straightforward calculations rather than abstraction), as it:

* is simple and can be visualized geometrically,
* can be explained classically, with a smooth transition into the quantum world,
* can be directly demonstrated (e.g. with polarizations sheets, polarization filters, LCD screen, reflections, sugar solutions, [naked eye](https://en.wikipedia.org/wiki/Haidinger%27s_brush)),
* passes the [Scott Aaronson's Minus-Sign Test](http://www.scottaaronson.com/blog/?p=613) in a simple and convincing way (crucial!),
* directly translates to applications like quantum cryptography.

A classical[^classical] quantum mechanics introduction starts from describing position (and momentum) of a single particle. Sure, it has valuable pieces like calculating energies and orbitals, and there is the Heisenberg uncertainty principle[^heisenberg]. However, IMHO starting with classical mechanics (continuous variables) is the worst approach, as it:

* starts with an infinite dimensional Hilbert space,
* deals with a particular system, giving little insight into general quantum mechanics,
* requires classical mechanics background,
* seeds some wrong intuitions due to classical mechanics as the background,
* is easy to sink into technicalities of differentiating and integrating.

Working with electrons as the two-state system (spin up, spin down) has some benefits (two-level system), however:

* the classical-quantum link is much more complicated,
* no way to show it directly,
* rotations can be tricky (try explaining that spin-up plus spin-down is spin-right).

### How

Moreover, when it comes to the mathematical tools, I try not treating them as a necessary evil or means to an end, as:

* complex numbers are interesting on their own (fractals, [polynomial roots](http://math.ucr.edu/home/baez/roots/)),
* polarization of light is interesting on its own (photography, electromagnetism),
* linear algebra is useful on its own (virtually all physics, deep learning).

When it comes to delivery, I try to:

* make it interactive rather than merely give lectures,
* use Python within Jupyter Notebook (previously Mathematica) to actually calculate and plot things,
* don't use more formalism or mathematics than it's necessary,
* flexibly change the program according to participants skills and interests,
* more in my answer to [How to improve myself as a lecturer - Academia Stack Exchange](http://academia.stackexchange.com/questions/5236/how-to-improve-myself-as-a-lecturer/5249#5249).

For experimental stuff, it's crucial to show first, explain later - if at all (otherwise you are killing the sense of suspension and awe):

> The researchers' conclusion was that, in the context of strange toys of unknown function, prior explanation does, indeed, inhibit exploration and discovery.

from [When should you teach children, and when should you let them explore? - The Economist](http://www.economist.com/node/18741484).

![LCD screen + plastic cup + polarizer](/imgs/2016-08-15-quantum-polarization.jpg)

*An LCD screen + a plastic cup + a camera with a polarizer.*

## Course outlines

I did it four times:

1. Jun-Jul 2011, Castelldefels, Spain, [ICFO](https://www.icfo.eu/) for [Jóvenes y Ciencia](http://www.fundaciocatalunya-lapedrera.com/es/content/j%C3%B3venes-y-ciencia)
2. Aug 2011, Olsztyn, Poland, [7th edition](http://warsztatywww.wikidot.com/www7-program) of [Wakacyjne Warsztaty Wielodyscyplinarne](http://warsztatywww.pl/)
  * more on the camp series: [An independent camp for high-school geeks](http://warsztatywww.wikidot.com/en:indie-camp-for-hs-geeks)
3. Jun-Jul 2012, Castelldefels, Spain, [ICFO](https://www.icfo.eu/) for [Jóvenes y Ciencia](http://www.fundaciocatalunya-lapedrera.com/es/content/j%C3%B3venes-y-ciencia)
  * co-taught with Jordi Tura, Julia Stasińska, Alejandro Zamora and John Lapeyre
4. May 2016, Serock, Poland, [Wielodyscyplinarny Obóz Naukowy](http://fundusz.org/program/warsztaty-i-obozy/321-oboz-w-serocku) of [Krajowy Fundusz na rzecz Dzieci](http://fundusz.org/english)
  * more on the program: [Helping exceptionally gifted children in Poland](http://crastina.se/gifted-children-in-poland-by-piotr-migdal/) at Scientia Crastina

Since there is a lot of redundancy, I will describe only 1. (3. was similar) and 2. (4. was similar), mentioning some modifications.


### Quantum optics, 7th Scientific Summer School (2011)

* whole camp during: 8-18 Aug 2011, Olsztyn, Poland
* [Optyka kwantowa - WWW 7](http://warsztatywww.wikidot.com/www7:optyka-kwantowa) (outline and problems, in Polish, but I guess you can read some math)
* qualification problems as a core part
  * so as to prepare the students wth simple problems which nevertheless require some effort
  * they served as a common starting level
  * unfortunately, in 2016 I couldn’t do that, which strongly impacted the course
* 5 participants
* 3h x 3 day workshop for talented high-schools students (in 2016: 2.5h x 3)

#### Outline

`0.` Linear algebra (in qualification problems)

  Complex numbers (including radial representation), basics of linear algebra, quantum jargon (bras, kets and daggers).

`1.` Polarization of light

  What is that, how can we act on it (wave plates, polarizers, rotation by a solution of sugar, ...); also: the 3 polarizers "paradox".

`2.` Quants and measurement

  Single photons behave in the same as a classical wave, just they can't be measured partially, only 0/1. And then the quantum measurement is the most intuitive interpolation of the classical measurement.

`3.` Superposition vs mixture

  How to tell the difference using interference. Detection of the light-sensitive bomb.

`4.` Entanglement

  What is that? Why it is the most intuitive approach to more particles? Relation between interference, entanglement and looking at objects.

I was positively surprised that all points were easy and enjoyable for the participants. There was a slight slowdown with the tensor product, but it wasn't a blocker.

In 2016, I covered only 0., 1. and 2., all on-site. Because of the lack of preparation (0.) and more interesting parts (3. and 4.) it didn't go as well as the one of 2011 (one of my best educational experiences ever!).

### Quantum cryptography and quantum information, ICFO (2011)

* 15 Jun - 15 Jul 2011, [ICFO](https://www.icfo.eu/), Castelldefels (Barcelona)
* 6h twice a week (in 2012 it was 2-3h daily, which was better)
* 2 participants

#### Outline

* `*` - an additional material that I used
* `**` - an additional material that I didn't use (some of it was in 2012, though)

`1.` Classical cryptography

1.1. Naive letter/word relabeling

* give some interesting historical examples
* as an example use rot13
* `**` show that natural languages can be easily detected (with analysis of ngrams - i.e. frequencies of short strings of letters)

1.2. Perfect XOR

* show that it is a perfect encryption
* no difference between the message and the key
* practice on black&white images
* and on words (character -> 8 bits -> encoding -> sending -> decoding -> 8 bits -> character)
* but how to distribute the key?

1.3. `**` RSA

* modulo, factorability
* asymmetric codes, the actual RSA procedure
* it's hard to break but not impossible (time estimates with current technology)

`2.` Quantum cryptography

2.1. Measurement of the (classical) polarization of light

* `*` introduction to complex numbers
* description of polarization with two numbers
* polarizer, measurement of intensity, projection
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
* Bell inequality (including futile trials to break it)
* nonlocal boxes (Popescu-Rohrlich)
* quantum teleportation

2.5 `**` Information theory

* Shannon entropy; when one can compress a file, how to play in "twenty questions" game
* how to quantize the sent information (quantum or classical), when there is noise in the channel
* how to check if information is altered and how to fix it (check sum, Hamming codes)


![Quantum Zeno effect with polarization rotation - notes by Krzysztof Lis](/imgs/2016-08-15-quantum-zeno-lis.jpg)

*The first historical drawing of "the light-twisting sugar solution as a mojito drink" - notes by Krzysztof Lis, Olsztyn, 2011.*


## Materials

### Simple books

* Valerio Scarani, [Six Quantum Pieces: A First Course in Quantum Physics](http://www.amazon.com/Six-Quantum-Pieces-Course-Physics/dp/9814327549)
  * the first few chapters are great (it also starts with a single photon and polarization), but then it quickly gets too abstracts (optimal cloning)
* Leonard Susskind, Art Friedman, [Quantum Mechanics: The Theoretical Minimum. What You Need to Know to Start Doing Physics.](http://www.amazon.com/Quantum-Mechanics-Theoretical-Leonard-Susskind/dp/0465062903)
  * two-level system, though with an electron which is conceptually harder  
  * also in Polish: [Mechanika kwantowa - teoretyczne minimum](http://www.proszynski.pl/Mechanika_kwantowa__Teoretyczne_minimum-p-33197-.html)
* Konrad Banaszek, Rafał Demkowicz-Dobrzański, [Quantum information 1/2](http://www.fuw.edu.pl/~demko/Teksty/ik05/2012/qi12.pdf)
  * lecture notes; it starts with two-level system of polarization of light; it is not incidental - Konrad Banaszek was my MSc advisor and I was raised in this quantum optical environment
  * also some exercises: [www.fuw.edu.pl/~demko/students.html](http://www.fuw.edu.pl/~demko/students.html)
* Andrzej Dragan, [Niezwykle Szczególna Teoria Względności](http://www.fuw.edu.pl/~dragan/Fizyka/Nstw.pdf) (en: *Extraordinarily Special Relativity*)
  * chapter 5. on Bell inequality
  * in general this text is so awesome it's pity it's only in Polish; [its author is also a photographer](http://andrzejdragan.com/)
* David Kaiser, [How the Hippies Saved Physics: Science, Counterculture, and the Quantum Revival](http://www.hippiessavedphysics.com/)
  * a general reading on the beginnings of quantum information (also, why quantum metaphysics is tempting but does not work); bear in mind it overvalues hippies - this field has also different, Soviet roots - vide [Holevo's theorem](https://en.wikipedia.org/wiki/Holevo%27s_theorem)

### Interactive stuff

* my [Quantum Game with Photons](http://quantumgame.io)
  * especially the `∞` mode, where you can freely simulate quantum mechanics of a single photon
* [Quantum Circuit Simulator: Quirk](http://algorithmicassertions.com/2016/05/22/quirk.html)
  * direct link: [algorithmicassertions.com/quirk](http://algorithmicassertions.com/quirk)
* [Eigenvectors and Eigenvalues - Visually Explained](http://setosa.io/ev/eigenvectors-and-eigenvalues)
* [Math and Physics Applets](http://www.falstad.com/mathphysics.html) by Paul Falstad (unfortunately in Java)
  * [1-D Quantum Mechanics](http://www.falstad.com/qm1d/) - once you are fine with basics of a harmonic oscillator and its eigenstates you can easily create coherent or squeezed states for the harmonic oscillator potential
  * [Ripple Tank](http://www.falstad.com/ripple/) for wave phenomena - interference, the total internal reflection, the lensing, the Fresnel zone plates, the Doppler effect, the scattering and many, many other phenomena
* Python (in [Jupyter Notebook](http://jupyter.readthedocs.io)) for calculations and plots
  * see my blog entry: [Data science intro for math/phys background ](http://p.migdal.pl/2016/03/15/data-science-intro-for-math-phys-background.html) and the paragraph on Python
  * see [Qubism in QuTiP](http://nbviewer.jupyter.org/github/qutip/qutip-notebooks/blob/master/examples/example-qubism-and-schmidt-plots.ipynb) and in general [QuTiP: Quantum Toolbox in Python](http://qutip.org/)
* EDIT: See also [Science-based games - a collaborative list](https://github.com/stared/science-based-games-list)

### Websites

* [Jones calculus - Wikipedia](https://en.wikipedia.org/wiki/Jones_calculus)
* my entry [Quantum superposition - Azimuth blog](https://johncarlosbaez.wordpress.com/2015/03/13/quantum-superposition/) or why does an electron need to be in two places at once
* [Visualizing complex-valued functions with Matplotlib and Mayavi - Emilia Petrisor](http://nbviewer.jupyter.org/github/empet/Math/blob/master/DomainColoring.ipynb)
* [What is i^i? - SMBC so NSFW](http://www.smbc-comics.com/?id=2934)
* [Third-Polarizing-Filter Experiment Demystified](http://alienryderflex.com/polarizer/) by Darel Rex Finley
* [Physics - Optics: Polarization (3 of 5) Three Polarizers](https://www.youtube.com/watch?v=r1sZY826Qys) YouTube video by Michel van Biezen

### Textbooks

* Berthold-Georg Englert, [Lectures on Quantum Mechanics - Volume 1: Basic Matters](http://www.amazon.com/Lectures-Quantum-Mechanics-Basic-Matters/dp/9812569707)
  * a wonderful [course by Jacek Dobaczewski](http://www.fuw.edu.pl/~dobaczew/kwanty/kwanty.html) I had as an introduction to QM was based on that; [a poem, as a homework](http://www.fuw.edu.pl/~dobaczew/kwanty/wiersz.html) (in Polish)
* David Griffiths, [Introduction to Quantum Mechanics](https://archive.org/details/IntroductionToQuantumMechanics_718)
  * [an opinion on Quora](https://www.quora.com/Is-it-wise-to-read-Principles-of-Quantum-Mechanics-2nd-Edition-R-Shankar-as-an-introductory-textbook-in-quantum-mechanics)
* R. Shankar, [Principles of Quantum Mechanics](https://www.amazon.com/Principles-Quantum-Mechanics-2nd-Shankar/dp/0306447908)
* I **do not** recommend Leonard I. Schiff, [Quantum mechanics](https://archive.org/details/QuantumMechanics_500)
  * it is a common introduction, but one stuck in the worst classical rut
* [The Feynman Lectures on Physics, Volume III](http://www.feynmanlectures.caltech.edu/III_toc.html)
  * I love the series, but in the case of Vol. III - please use it only as a supplement; there are some unique and insightful things like [chapter 7](http://www.feynmanlectures.caltech.edu/III_07.html) and [chapter 10](http://www.feynmanlectures.caltech.edu/III_10.html)
* Michael A. Nielsen, Isaac L. Chuang, [Quantum Computation and Quantum Information](https://www.amazon.com/Quantum-Computation-Information-10th-Anniversary/dp/1107002176)
  * so called *the green book*
  * introduction from the non-physical perspective
* Carl D. Meyer, [Matrix Analysis and Applied Linear Algebra](http://www.matrixanalysis.com/)
  * a general intro/reference to linear algebra, very simply and didactically written (relevant chapters: 3, 4, 5)


## And...?

If you want to use any materials - feel free! And I would be even happier to hear that.
If you have some other materials or references for an easy introduction you recommend - just send them.

I am considering writing a simple introduction to quantum mechanics, with interactive simulations (very likely with the Quantum Game engine). If you think it is a great idea, consider poking/teasing/tempting me. :)

I would like to thank [Michał Kotowski](http://www.math.toronto.edu/~michal/) for remarks on this blog post. And, of course, to everyone participating in my quantum mechanics workshops.

> Before applying consult with your teacher or professor, as every misused didactic material may result in misunderstanding or discouragement.

[^catalonia]: Or rather: Catalonia!
[^finding_time]: Read: stolen time from other projects or was doing [white procrastination](http://paulgraham.com/procrastination.html).
[^who_can]: As a rule of thumb I can explain what quantum mechanics is in 3h, if the other person knows what matrices are. I did it to biologists and they are fine.
[^classical]: Nomen omen!
[^heisenberg]: Though, I have a strong preference in showing it as a Fourier transform property, for which QM is only incidental. Again, it's just a wave phenomenon (as interference or tunneling).
