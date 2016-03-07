---
layout: "post"
title: "Data science intro for math/phys background"
date: "2016-03-02 21:03"
author: Piotr Migdał
tags:   [data-science,python,r]
mathjax: false
description: "Learn Python (or R), machine learning and other stuff."  
---

After posting [What I do or: science to data science]({site.url}/2015/12/14/sci-to-data-sci.html) I got a lot of emails on how to make this transition.

In this post I try to summarize my advice. I don't intend to write a complete "walkthough", but to provide a starting point, with links to further materials. I target it at people with quantitive background (e.g. physics, mathematics, statistics), regardless if they are undergraduate students, PhDs or after a few postdocs. Some points may be valid for other backgrounds (but then - use it at your own risk).

## My background

In short:

* I had a lot of background in physics, signal analysis and academic programming and none in practical programming
* I started learning Python (for web scraping and plotting)
* then (~6 months later) I participated in a 1-month data science school (Big Dive in Turin)
* then (~6 month later) I went to a summer internship in data science in San Francisco (for 4 months)
* after this, I started part-time freelancing (as I was finishing my PhD).

Most data science things are simple and at the point that you are able to use R or Python you can start, gradually increasing your knowledge and experience. All projects required me to learn something new; many required me to reed academic papers.


## What is data science?

> Data scientist is a person who is better at statistics than any programmer and better at programming than any statistician.

* [The State of Data Science - RJMetrics Report](https://rjmetrics.com/resources/reports/the-state-of-data-science/) - especially plots *top 20 skills of a data scientist* and *top 20 backgrounds of data scientists*; collorally:
* [Doing Data Science at Twitter - Robert Chang](https://medium.com/@rchang/my-two-year-journey-as-a-data-scientist-at-twitter-f0c13298aee6) - you want to be a Type A Data Scientist, according to its taxonomy
* [Advice and insights from 25 amazing data scientists](http://www.thedatasciencehandbook.com/) - interviews with practitioners holding various positions, having various backgrounds.

Contrary to its name, it's rarely "science". That is, in data science the emphasis is on practical results (like in engineering) - not proofs, mathematical purity or rigor characteristic to academic science. Things need to work, and there is little difference if it is based on an academic paper, usage of an existing library, your own code or an impromptu hack.


## On the transition


* [How to leave academia - Chris Stucchio](https://www.chrisstucchio.com/blog/2012/leaving_academia.html) - getting practical skills, interviews, salary negotiations
* [Academia to Industry: Data Science Myths and Truths - Emily Thompson](http://www.insightdatascience.com/blog/academia_to_industry_data_science_myths_and_truths.html) - so: no, you don't have to do adverts or finance

> While having a strong coding ability is important, data science isn’t all about software engineering (in fact, have a good familiarity with python and you’re good to go). Data scientists live at the intersection of coding, statistics, and critical thinking.

### Resume vs academic CV

In the software industry resume plays a different role than CV in academia. Rather than being a complete record or all positions, publication, etc, it is a short (typically 1 page) summary of the main skills and the most important positions/accomplishments. It is used screen candidates, not as the final judgement.
To see the difference, compare and contrast [my data science resume](https://github.com/stared/cv-resume/blob/master/piotr_migdal_cv_prog.pdf) with [my academic CV](https://github.com/stared/cv-resume/blob/master/piotr_migdal_cv_sci.pdf).

### Priorities

In academia, you are allowed to cherry-pick a problem and work on it for 2 years. The result needs to be novel, and you need to research previous and similar solutions.

In industry, you should solve a given problem end-to-end. It does not matter if you read the solution somewhere, you discovered it by yourself etc. And the cycles are typically much shorter.

Moreover, deadlines are more important that the quality. I.e. in academia it may be common that a problem instead of 1 month takes a year or more. In industry, if you need to solve something in one month, it’s common to come with a dirty solution, which bases of shady assumptions, etc. (So "perfect, but with delay" vs "good enough but on time". )

### Being employable

My regrets:

* not doing the transition earlier,
* Stockholm syndrome / being afraid outside of academia,
* having complexes on not being a true computer scientists.


The most important thing: you don't have to know everything (actually, it's impossible), but:

* have minimal skills so that you are useful starting from day 1 (e.g. you can get data and present summary statistics; they don’t want to start with learning you Python and Git),
* be able and eager to learn (in general, their technologies, be self-driven to discover and solve new problems even without being explicitly guided).

I was afraid that it is a problem that I lack 10+ years of experience with C++ and Java; so how can I compete with serious software engineers, who did their computer science major?

## Programming languages

For general data science, the usual starting tools are [Python](https://www.python.org/r) and [R](https://www.r-project.org/). If you already know some other languages it will help, still - learn one of the above.

> But... Python or R? There are some crazy fights, right?

* [Choosing R or Python for data analysis? An infographic](http://blog.datacamp.com/r-or-python-for-data-analysis/)
* [Should you teach Python or R for data science?](http://www.dataschool.io/python-or-r-for-data-science/) - a more detailed use-cases
* [Python, Machine Learning, and Language Wars - Sebastian Raschka](http://sebastianraschka.com/blog/2015/why-python.html) - also mention R, and why MATLAB is too old (and Julia - too young)

tl;dr: both are good choices. Pick one you prefer for any reason; two really good ones are:

* This thing is great! I want to apply it [some other data]. Oh, it is in [a language].
* Having a community of people from whom you can learn.

I mean, there are specific use cases when one is better than the other. But in majority of tasks both are fine. And well (some may disagree), but they are tools, not religions.

I won't point to a general tutorials (there many - just Google one you like).


### R

R is a tool for statistics turned into a language. The standard way of using it is via [RStudio](https://www.rstudio.com/).
Be sure to learn basics of [dplyr](https://cran.r-project.org/web/packages/dplyr/vignettes/introduction.html) and [ggplot2](http://ggplot2.org/) (I almost always load them by default; especially dplyr, which makes operations on dataframes much easier, faster and more readable). Then everything else depends on the problems you are solving.

If you go the R way, at very least:

* [Do your "data janitor work" like a boss with dplyr](http://www.r-bloggers.com/do-your-data-janitor-work-like-a-boss-with-dplyr/)
* [Data Wrangling with dplyr and tidyr Cheat Sheet](http://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf)
* [Quick Introduction to ggplot2b - Edwin Chen](http://blog.echen.me/2012/01/17/quick-introduction-to-ggplot2/)
* [Graphics, ggplot2](http://r4stats.com/examples/graphics-ggplot2/)
* [Getting Started with R: Kaggle's Titanic Competition](Getting Started with R: Kaggle's Titanic Competition)

Some R pearls:

* [R Markdown](http://rmarkdown.rstudio.com/) - dynamic documents, presentations, and reports from R
* [Shiny](http://shiny.rstudio.com/) - turn your analyses into interactive web applications


### Python

Python is a much better general-purpose language (with pros and cons on not being statistics-oriented).

For Python, I would suggest installing it (Python 3) through [Anaconda](https://www.continuum.io/downloads), and using [Jupyter Notebook](http://jupyter.org/). Main packages are [NumPy](http://www.numpy.org/), [SciPy](http://www.scipy.org/) (numerics), [Pandas](http://pandas.pydata.org/) (like R dataframes), [matplotlib](http://matplotlib.org/) (plots, but not as nice as ggplot2) and [scikit-learn](http://scikit-learn.org/) (for machine learning). Learn to be comfortable with Python (installing packages, loading, saving and transforming data, etc).

* [A modern guide to getting started with Data Science and Python](http://twiecki.github.io/blog/2014/11/18/python-for-data-science/)
* [Overview of Python Visualization Tools](http://pbpython.com/visualization-tools-1.html)
* [Web Scraping - It’s Your Civic Duty](http://pbpython.com/web-scraping-mn-budget.html)
* [Pandas Visualization](http://pandas.pydata.org/pandas-docs/stable/visualization.html)
* [Scipy Lecture Notes - One document to learn numerics, science, and data with Python](http://www.scipy-lectures.org/)
* [A gallery of interesting IPython Notebooks](https://github.com/ipython/ipython/wiki/A-gallery-of-interesting-IPython-Notebooks)
* links from [DELabUW/szkola-letnia-2015](https://github.com/DELabUW/szkola-letnia-2015)


## Statistics and Machine Learning

Before, you need some basic linear algebra (vectors, matrices, SVD, ...), calculus (exp, log, differentiation, integration, ...) probability (independence, conditional probability, ...), but if you are from natural science background, you already know that.

It does not mean that you you know all - it just means that right now you have mathematical skills sufficient to be an employable data scientists and you are able to read about other methods, algorithms, etc.

* [A Visual Introduction to Machine Learning](http://www.r2d3.us/visual-intro-to-machine-learning-part-1/)
* [Dive into Machine Learning with Jupyter notebook, Python, and scikit-learn](http://hangtwenty.github.io/dive-into-machine-learning/)
* [PyCon 2015 Scikit-learn Tutorial](https://github.com/jakevdp/sklearn_pycon2015)

For statistics, screw learning by heart various statistical distributions and tests - you can easily look them up later. What is crucial, is to understand the idea of tests, cross validation, bootstrapping and Bayesian inference. For the later I recommend:

* [David MacKay, Information Theory, Inference, and Learning Algorithms](http://www.inference.phy.cam.ac.uk/itila/book.html) - doing the Bayesian Interference and Machine Learning track).


* [Static and dynamic network visualization with R](http://kateto.net/network-visualization)


It's a fast changing field - and I read a lot of academic papers. Not just to stretch my intellectual muscles, but solve a particular problem.

## Other software skills

Often you will need to install something, collaborate with others and do other tasks. The crucial point so to know what is possible - especially not to reinvent the wheel.

* basics of bash/shell (`cd`, `ls`, `pwd`)
* CSV, [JSON](https://en.wikipedia.org/wiki/JSON)
* git for version control - see [Why use version control systems for writing a paper?](http://academia.stackexchange.com/a/5286/49)
  * [tryGit - Got 15 minutes and want to learn Git?](https://try.github.io/)
  * [Learn Git Branching](http://pcottle.github.io/learnGitBranching/)
  * [SourceTree](https://www.sourcetreeapp.com/) - graphical interface for git (Win, OSX)
* regex[p]
  * [Learn regular expressions in about 55 minutes - Sam Hughes](http://qntm.org/files/re/re.html)
  * [RegExr](http://regexr.com/)
  * [Regular Expressions Cheat Sheet - DaveChild](http://www.cheatography.com/davechild/cheat-sheets/regular-expressions/)
* basics of SQL
  * [SQL Cheet Sheet](http://www.sql-tutorial.net/sql-cheat-sheet.pdf)
  * [An Introductory SQL Tutorial: How to Write Simple Queries](http://blog.hubspot.com/marketing/sql-tutorial-introduction)
* HTML (and JavaScript may be a plus)
  * [Introduction to HTML - MDN ](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Introduction)
  * my post: [D3.js workshop at ICM for KFnrD]({site.url}/2016/02/09/d3js-icm-kfnrd.html)

## Practicing and building showcase

Some people recommend [Kaggle](https://www.kaggle.com/,) as a starting point but I wouldn't for the same reasons as in [5 Reasons Kaggle Projects Won't Help Your Data Science Resume](http://datascienceresume.com/advice/5-reasons-why-doing-kaggle-projects-won-t-help-you-create-a-stand-out-data-science-resume). That is, some nice tutorials and posts, but competitions are difficult and test only a subset of data science - tweaking performance of machine learning. Beware that industrial problems rarely look like that (e.g. in all mine data cleaning was a big thing, and in none 1% score improvement mattered). See also: [Machine learning isn't Kaggle competitions](http://jvns.ca/blog/2014/06/19/machine-learning-isnt-kaggle-competitions/).

For playing with machine learning [UCI Machine Learning Repository: Data Sets](http://archive.ics.uci.edu/ml/datasets.html) is a GREAT source for datasets you can play with.

Personally I enjoy the most working on data I care about or find genuinely interesting. Making results public is a great room for both feedback and building a showcase.
It can be an IPython Notebook, or a website, or even a just a plot (but then be sure to sign it - it it goes viral you want to get recognition!). E.g. some mine:

* [Polish Book Themes](http://p.migdal.pl/wizualizacja-wolnych-lektur/polish_books_themes.html)
* [TagOverflow](http://p.migdal.pl/tagoverflow/)
* [Analysis of 2010-2014 matura exams](https://github.com/stared/delab-matury) (in Polish)

Be sure to get a [GitHub](https://github.com) account! Mine looks like that: [github.com/stared](https://github.com/stared).
And don’t be afraid to put premature code: if it is not good yet then no-one will notice (or care) anyway.

Some people like writing about problems they have just learnt (e.g. [How gzip uses Huffman coding](http://jvns.ca/blog/2015/02/22/how-gzip-uses-huffman-coding/)). It may or may not be your thing.


## Data science boot camps

It’s totally fine to learn things on your own. But doing on a boot camp may be a huge boosts - motivational, with access to tutors/experts, with job opportunities.

* [BIG DIVE](http://www.bigdive.eu/) - *Development, Visualization and Data Science*
  * [BIG DIVE, czyli o dawaniu nura w dane](http://smarterpoland.pl/index.php/2013/05/big-dive-czyli-o-nurkowaniu-w-danych/) (in Polish) - I participated in the 1st edition!
  * [Big Dive review - alkamid](http://alkamid.com/big-dive-review-1/)
* [Insight Data Science Fellows Program](http://insightdatascience.com/) - *an intensive seven week post-doctoral training fellowship bridging the gap between academia and data science*
* [S2DS London](http://www.s2ds.org/)
* [Recurse Center (aka Hacker School)](https://www.recurse.com/) - *a free, self-directed, educational retreat for people who want to get better at programming, whether they've been coding for three decades or three months*
  * [its manual](https://www.recurse.com/manual) is a nice resource on good environment for learning


## Internships

If you are still a student - doing an internship may be a great way. I did mine during my PhD studies (in Europe it is not common to take a break, and a lot of people in academia dissuaded me, but ).

To search for offers try googling `data science/scientists intern/internship`, visit some job listings (e.g. [Indeed]( http://www.indeed.com/jobs?q=data+science+intern&l=)).
Some bigger companies (Facebook, Google, IMB, Microsoft) offer internships, see:

* [What companies have data science internships? - Quora](https://www.quora.com/What-companies-have-data-science-internships)

Sometimes it makes sense to mail a company even if they don't use words `intern` or `internship` - especially smaller ones may be flexible.



In the [San Francisco] Bay Area (i.e. north of Silicon Valley) there are plenty opportunities to learn data science - it should be your primary destination.
To work in US you need to get J-1 visa (of course, after they want you), but it's relatively easy (but takes ~2-3 months).

I think the easiest way is to look for various meeting. Especially via [Meetups](http://www.meetup.com/) - look for anything that may fit (data science, R communities, big data etc) and try to start visiting a lot of them (e.g. 3/week) and only afterward you will see which are the most useful. In the Bay Area it is an advantage to be "bold". Don't be afraid to asking about or for anything, starting talking to people etc - on the average it will be much better than taking a passive posture. See also:

* [A brief guide to tech internships](http://alexeymk.com/a-brief-guide-to-tech-internships/)
* [How to intern in Silicon Valley with a J1 visa](http://web.archive.org/web/20150413000314/http://blog.sendtoinc.com/2013/12/11/silicon-valley-internship-j1-visa/)
* [An Intern's Guide to a Summer in the Bay Area](http://alexeymk.com/an-interns-guide-to-a-summer-in-the-bay-area/) (from 2011, so now renting prices are higher)

## Feed

* [Hacker News](https://news.ycombinator.com/)
* [DataTau](http://www.datatau.com/)
* [Cross Validated - Stack Exchange](http://stats.stackexchange.com/)

## Advanced stuff

http://camdavidsonpilon.github.io/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers/
Deep learning may be within your reach (but it has steeper learning curve, is more data&computation intensive and more specific than "traditional" machine learning). Good places to start reading are Karpathy's blog and things around Deep Dreams.
http://karpathy.github.io/2015/05/21/rnn-effectiveness/ (my favourite reading in the last 2 years or so!)
https://github.com/google/deepdream/blob/master/dream.ipynb
It (neural networks in general) requires Lua + Torch or Python + Theano.Of couse, you have to put the Video links of Hugo Larochelle : https://www.youtube.com/watch?v=SGZ6BttHMPw

Or something in between, NLP:
http://www-nlp.stanford.edu/projects/glove/
https://radimrehurek.com/gensim/

## Am I employable?

I think that the best way to learn Data Science is by working!
Once you pass threshold of being employable, it’s much better to have access to the real Data Science, and getting salary, than just doing n+1 course (but don’t forget than in Data Science you must keep learning; just - you need to balance between working and learning).
An alternative (or maybe better: a side-activity) is to do projects you can share on GitHub or something.

When you have some academic title, no-one will question your intelligence. But they may question your practical skills. From my experience, you need to fulfill two requirements:

* have minimal skills so that you are useful starting from day 1 (e.g. you can get data and present summary statistics; they don’t want to start with learning you Python and Git),
* be able and eager to learn (in general, their technologies, be self-driven to discover and solve new problems even without being explicitly guided).

In any case - start soon.

Here and everywhere else: please DON’T take approach of “learn book[s] THEN play”; start with playing. You will never _learn_ machine learning - but you need to create and maintain a habit of continuously learning machine learning.

## What's next?

Thx to: Guillaume Carbajal

* Example for projects.
