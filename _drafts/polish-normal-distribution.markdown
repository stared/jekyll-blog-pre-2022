---
layout: "post"
title: "Polish normal distribution"
date: "2016-05-15 12:47"
mathjax: true
---

> some student: But why 4.5? If I got another question I might get 5.
> Iwo Białynicki-Birula: Every grade has a stochastic component.


[Matura](https://en.wikipedia.org/wiki/Matura) (from *maturity exam*) is a Polish nationwide end-of-high-school exam. One of its side-effect is this curious distribution of total scores obtained by examinees:

PIC

It is not hard to guess that the `30%` is the passing mark. And you may (motivation to appeal for people being 1-2 points below the threshold is not balanced with )


But this one is picturesque - a neat Gaussian distribution with clear excitation pattern. You may have already seen it:

* [Another Case of Teacher Cheating, or Is It Just Altruism?](http://freakonomics.com/2011/07/07/another-case-of-teacher-cheating-or-is-it-just-altruism/) (2011) - Freakonomics
* [Distribution of results of the Matura (high school exit exam) in Poland in 2013. The minimum score to pass is 30%.](https://www.reddit.com/r/dataisbeautiful/comments/27dx4q/distribution_of_results_of_the_matura_high_school/) (2013) - reddit.com/r/dataisbeautiful
* http://imgur.com/ZR4jdWt
* [Henry Garner, Clojure for Data Science [p 36]](http://www.slideshare.net/PacktPub/clojure-for-data-science-sample-chapter)


I think it deserves its own name. An easy task, since it is the motherlode of puns: *central exam theorem*, *passing limit theorem*, *matural distribution*, or the one I used in the title: *Polish-normal distribution*[^1].

The distributions for other years look similar[^2]:

PICS 2010-2014 (or even 2015)




But it does not look the same for other exams, see:

PICS

Even if there is a


You can explore more histograms here:
* https://matury.shinyapps.io/histogramy/


# Misconceptions

Before going further, let's clear some misconceptions.

## It is cheating

Not necessary. The official marking guideline says that in case of doubt.
Since there are a few extremely subjective criteria related to essay - almost always there are a few points to take or (in this case) give.

## We need to fix it ASAP

The score of `30%`, while a passing score, is still very low - not enough to get to any decent university.

## Scores should be normally distributed

**No!** Sum over correlated variables (and with different distributions) does not need to be Gaussian. In fact, here the baseline is Gaussian, because items are poorly correlated[^lowcorr].

*But, but... there are 300k people.* The number for people does not change the shape of this curve - it means that we probe extremely well - equating counts with the underlying distribution.

In fact, other subjects have non-Gaussian distribution.

## Are there geniuses?

You may notice a small peak at `100%`, separate from the main Gaussian. So - does it mean that there is a separate group of people, who are not merely very talented and well-prepared?

The winners of the Polish Olympiad don't need to write it and automatically get `100%`.


# Interference



# 2d Plot

# Gaussian model

Another simple approach is to compare. 
Link to code

Notes:

* R packege [zozlak/ZPD](https://github.com/zozlak/ZPD) - for accessing schools and anonymized exam data
* R package [mirt](https://cran.r-project.org/web/packages/mirt/index.html) - multidimensional item response theory ([tutorials](https://github.com/philchalmers/mirt/wiki))
* Piotr Migdał, Marta Czarnocka-Cieciura, [Analiza i wizualizacja danych maturalnych](https://github.com/stared/delab-matury), [DELab UW](http://delab.uw.edu.pl/) (in Polish)


* [A Fishy-Looking Test Score Distribution - Pricenomics](http://priceonomics.com/a-fishy-looking-test-score-distribution/)

* [What Good Marathons and Bad Investments Have in Common - NYTimes](http://www.nytimes.com/2014/04/23/upshot/what-good-marathons-and-bad-investments-have-in-common.html)


# Use also, maybe

* https://en.wikipedia.org/wiki/Bell%27s_theorem
* crazy probability distributions

[^moremames]: I am sure you can come with other names. Mail them to me! :)
[^y2016]: Sadly, I don't posses data for this year.
[^lowcor]: Item within *Polish - basic level* are less correlated.
