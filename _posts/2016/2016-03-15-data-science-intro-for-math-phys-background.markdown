---
layout: post
title: Data science intro for math/phys background
date: 2016-03-15 15:58 +0100
author: Piotr Migdał
tags:
  - data-science
  - python
  - r
mathjax: false
description: 'Academia to data science? Learn Python (or R), machine learning and other stuff.'
image: /imgs/2016-03-15-dark-side-of-science-meme.jpg
external:
  title: From Science to Data Science, a Comprehensive Guide for Transition
  href: http://www.kdnuggets.com/2016/04/data-science-comprehensive-guide-transition.html
  status: reprinted to KDnuggets
  date: 2016-04-12 11:03 +0800
---

![(meme) Welcome to dark side of science - data science](/imgs/2016-03-15-dark-side-of-science-meme.jpg)

After posting [What I do or: science to data science]({{site.url}}/2015/12/14/sci-to-data-sci.html) I got a lot of emails on how to make this transition.

In this post I try to summarize my advice. I don't intend to write a complete *walkthrough*, but to provide a starting point, with links to further materials. I target it at people with academic, quantitative background (e.g. physics, mathematics, statistics), regardless if they are undergraduate students, PhDs or after a few postdocs. Some points may be valid for other backgrounds[^1] (but then - use it at your own risk).

Here and everywhere else: please don't take approach of *learn book[s] then play* - start with playing!


## My story

In short:

* I had a strong background in physics and interest in complex system; I did a lot of academic programming and none of - practical.
* After the 1st year of my PhD studies I started learning Python (for web scraping and plotting) on my own time.
* 9 months later I participated in a 1-month data science school (Big Dive in Turin).
* 8 months later I went to a summer internship in data science in San Francisco (for 4 months).
* I started part-time freelancing (as I was finishing my PhD).
* After finishing PhD I made it my main activity.

All projects required me to learn something new - be it a library, a machine learning model or a software tool.


## What is data science?

Analyzing real, and often - dirty, data using a mixture of programming and statistics. Or, [as Josh Wills put it](https://www.quora.com/What-is-the-difference-between-a-data-scientist-and-a-statistician):

> Data scientist is a person who is better at statistics than any programmer and better at programming than any statistician.

From my perspective the whole process looks that way:

* ask question that is relevant to the project
* get data (CSV, SQL, plain text)
* process it (joining, cleaning, supplementing it)
* run analysis (statistical tests or machine learning)
* interpret and use results (being able to understand the above)
* present results (a report, plot, interactive data visualization)

And everything needs to be done in a reproducible way - so others can interact with your code, or even run it on a server. Depending on the job, there may be more emphasis on one part or the other.
Or even look at [this tweet](https://twitter.com/JennyBryan/status/688866722980364289) - while humorous[^6], it shows a balanced list of typical skills and activities of a data scientist:

![a data scientist should be able to (by Joel Grus)](/imgs/2016-03-15-a-data-scientist-should.png)

If you want to learn more about what is data science, look at the following links:

* [The State of Data Science and Machine Learning - Kaggle 2017 Survey](https://www.kaggle.com/surveys/2017)
* [Doing Data Science at Twitter - Robert Chang](https://medium.com/@rchang/my-two-year-journey-as-a-data-scientist-at-twitter-f0c13298aee6)
* [Advice and insights from 25 amazing data scientists](http://www.thedatasciencehandbook.com/) - interviews with practitioners holding various positions, having various backgrounds


## On the transition

When you have some academic title, no-one will question your intelligence. But they are justified to question your practical skills. From my experience, you need to fulfill two requirements:

* have minimal skills so that you are useful starting from day 1 (e.g. you can get data and present summary statistics; they don’t want to start with teaching you Python and Git),
* be able and eager to learn (in general, their technologies, be self-driven to discover and solve new problems even without being explicitly guided).

Most data science things are simple and at the point that you are able to use R or Python you can start working, gradually increasing your knowledge and experience. That is, after a few months you should be ready to start an entry-level job.

Initially, I was afraid that it is a problem that I lack 10+ years of experience with C++ and Java. So how could I compete with serious software engineers, who did their computer science major? But it turned out that most of my commercial projects are for IT companies - they have wonderful programmers but often no-one proficient at dealing with real data. So (from *Academia to Industry* linked below):

> While having a strong coding ability is important, data science isn’t all about software engineering (in fact, have a good familiarity with Python and you’re good to go). Data scientists live at the intersection of coding, statistics, and critical thinking.

See also:

* [How to leave academia - Chris Stucchio](https://www.chrisstucchio.com/blog/2012/leaving_academia.html) - getting practical skills, interviews, salary negotiations
* [Academia to Industry: Data Science Myths and Truths - Emily Thompson](http://www.insightdatascience.com/blog/academia_to_industry_data_science_myths_and_truths.html) - so: no, you don't have to do adverts or finance


### Priorities

In academia, you are allowed to cherry-pick an artificial problem and work on it for 2 years. The result needs to be novel, and you need to research previous and similar solutions. The solution needs to be perfect, even if not on time.

In industry, you should solve a given problem end-to-end. Things need to work, and there is little difference if it is based on an academic paper, usage of an existing library, your own code or an impromptu hack. The solution needs to be on time, even if just *good enough* and based on shady and poorly understood assumptions.

So, contrary to its name, it's rarely *science*[^2]. That is, in data science the emphasis is on practical results (like in engineering) - not proofs, mathematical purity or rigor characteristic to academic science.


### Resume vs academic CV

In the software industry resume plays a different role than CV in academia. Rather than being a complete record or all positions, awards and publication, it is a short (typically 1 page) summary of the main skills and the most important positions/accomplishments. It is used to screen candidates, not as the final judgement.
To see the difference, compare and contrast [my data science resume](https://github.com/stared/cv-resume/blob/master/piotr_migdal_resume_data_sci.pdf) with [my academic CV](https://github.com/stared/cv-resume/blob/master/piotr_migdal_cv_sci.pdf).


### Interviews

Applying for a job involves being asked technical questions - on the phone or Skype. For software engineering it involves both conceptual questions and whiteboard coding; for data science it may vary. In any case, take a look at:

* [Data Science Interviews - Trey Causey](http://treycausey.com/data_science_interviews.html)

If you need learn basic algorithms and data structures, I recommend:

* [Algorithms at Coursera by Wayne and Sedgewick](https://www.coursera.org/course/algs4partI) if you like MOOCs
* [T. Cormen, C. Leiserson, R. Rivest and C. Stein, Introduction to Algorithms](https://en.wikipedia.org/wiki/Introduction_to_Algorithms) - a classical, in-depth book

If you get no technical questions, it may be a red flag.
If you get only software engineering questions, it may be a sign that they want to hire a programmer, not - a data scientist (no matter what their job calling says);
and given you background you want to be a Type A Data scientist (i.e. more a statistician than a regular programmer), according to [this taxonomy](https://www.quora.com/What-is-a-data-scientist-3/answer/Michael-Hochster).

When they consider hiring you, this piece is crucial:

* [Ten Rules for Negotiating a Job Offer - Haseeb Qureshi](https://medium.freecodecamp.com/ten-rules-for-negotiating-a-job-offer-ee17cccbdab6#.rhwj57ckp)


## Programming languages

Most likely practical programming is the main skill you are missing.
For general data science, the standard tools are [Python](https://www.python.org/) and [R](https://www.r-project.org/). If you already know some other languages it will help, still - learn one of the above.

> But... Python or R? There are some crazy fights, right?

* [Choosing R or Python for data analysis? An infographic](http://blog.datacamp.com/r-or-python-for-data-analysis/)
* [Should you teach Python or R for data science?](http://www.dataschool.io/python-or-r-for-data-science/) - a more detailed use-cases
* [Python, Machine Learning, and Language Wars - Sebastian Raschka](http://sebastianraschka.com/blog/2015/why-python.html) - also mentions R, and why MATLAB is too old (and Julia - too young)

tl;dr: both are good choices. Pick one you prefer for any reason; two really good ones are:

* *This thing is great! I want to apply it to [some other data]. Oh, it is in [a language]!*
* Having a community of people from whom you can learn.

I mean, there are use cases when one is better than the other. But in the majority of tasks both are fine. And well (some may disagree), but they are tools, not religions (no need of fighting, not need of using exclusively one).

**EDIT** (Jun 2018):

* [Python eats away at R: Top Software for Analytics, Data Science, Machine Learning in 2018: Trends and Analysis](https://www.kdnuggets.com/2018/05/poll-tools-analytics-data-science-machine-learning-results.html)
* In *What language would you recommend new data scientists learn first?* from [2017 Kaggle survey](What language would you recommend new data scientists learn first?) - Python wins with R

I won't point to a general tutorials - there are tons of it and personal preferences vary (MOOCs, interactive courses, websites, textbooks, ...) and I tried to link only to things I recommend myself.
When I provide links - it is usually web materials rather than classical books. And it is for a reason:

* things change fast; a 2-year old book on a programming language may be well out-of-date,
* it is important how much you use in practice; dry-reading won't teach you a thing.


### R

R is a tool for statistics turned into a language. The standard way of using it is via [RStudio](https://www.rstudio.com/) (though, [you can use Jupyter](https://try.jupyter.org/)).
Be sure to learn basics of [dplyr](https://cran.r-project.org/web/packages/dplyr/vignettes/introduction.html) and [ggplot2](http://ggplot2.org/) (I almost always load them by default; especially dplyr, which makes operations on dataframes much easier, faster and more readable). Then everything else depends on the problems you are solving.

If you go the R way, at least:

* [Do your "data janitor work" like a boss with dplyr](http://www.r-bloggers.com/do-your-data-janitor-work-like-a-boss-with-dplyr/)
* [Data Wrangling with dplyr and tidyr Cheat Sheet](http://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf)
* [Quick Introduction to ggplot2 - Edwin Chen](http://blog.echen.me/2012/01/17/quick-introduction-to-ggplot2/)
* [Graphics, ggplot2](http://r4stats.com/examples/graphics-ggplot2/)
* [Getting Started with R: Kaggle's Titanic Competition](https://www.kaggle.com/c/titanic/details/new-getting-started-with-r)

Some R pearls:

* [R Markdown](http://rmarkdown.rstudio.com/) - dynamic documents, presentations, and reports from R
* [Shiny](http://shiny.rstudio.com/) - turn your analyses into interactive web applications


### Python

Python is a much better general-purpose language (with pros and cons on not being statistics-oriented).

For Python, I would suggest installing it (Python 3) through [Anaconda](https://www.continuum.io/downloads), and using [Jupyter Notebook](http://jupyter.org/). Main packages are [NumPy](http://www.numpy.org/), [SciPy](http://www.scipy.org/) (numerics), [Pandas](http://pandas.pydata.org/) (like R dataframes), [matplotlib](http://matplotlib.org/) (plots, but not as nice as ggplot2) and [scikit-learn](http://scikit-learn.org/) (for machine learning). Learn to be comfortable with Python (installing packages, loading, saving and transforming data, etc) - links below may help:

* [Hans Fangohr, Python for Computational Science and Engineering ](http://www.southampton.ac.uk/~fangohr/teaching/python/book.html)
* [Overview of Python Visualization Tools](http://pbpython.com/visualization-tools-1.html)
* [Pandas Visualization](http://pandas.pydata.org/pandas-docs/stable/visualization.html)
* [Web Scraping - It’s Your Civic Duty](http://pbpython.com/web-scraping-mn-budget.html)
* [Scipy Lecture Notes - One document to learn numerics, science, and data with Python](http://www.scipy-lectures.org/)
* [Matplotlib tutorial - Nicolas P. Rougier](http://www.labri.fr/perso/nrougier/teaching/matplotlib/)
* [A gallery of interesting IPython Notebooks](https://github.com/ipython/ipython/wiki/A-gallery-of-interesting-IPython-Notebooks)


## Statistics and Machine Learning

You need some basic linear algebra (vectors, matrices, SVD, ...), calculus (exp, log, differentiation, integration, ...) probability (independence, conditional probability, ...), but if you are from natural science background, you already know that.
It does not mean that you know all - it just means that right now you have mathematical skills sufficient to be an employable data scientists and you are able to read about other methods, algorithms, etc.

* [A Visual Introduction to Machine Learning](http://www.r2d3.us/visual-intro-to-machine-learning-part-1/)
* [Machine Learning at Coursera by Andrew Ng](https://www.coursera.org/learn/machine-learning)
* [Dive into Machine Learning with Jupyter notebook, Python, and scikit-learn](http://hangtwenty.github.io/dive-into-machine-learning/)
* [PyCon 2015 Scikit-learn Tutorial](https://github.com/jakevdp/sklearn_pycon2015)
* [G. James, D. Witten et al., An Introduction to Statistical Learning with Applications in R](http://www-bcf.usc.edu/~gareth/ISL/)

If you need to get a real dataset suitable for working with a given machine learning algorithm, there is a wonderful collection:

* [UCI Machine Learning Repository: Data Sets](http://archive.ics.uci.edu/ml/datasets.html)

For statistics, screw learning by heart various statistical distributions and tests - you can easily look them up later. What is crucial, is to understand the idea of tests, cross validation, bootstrapping and Bayesian inference. For the latter I recommend:

* [David MacKay, Information Theory, Inference, and Learning Algorithms](http://www.inference.phy.cam.ac.uk/itila/book.html) - doing the Bayesian Inference and Machine Learning track

It's a fast changing field - I am constantly tracking new libraries and updates to ones I am using. I read a lot of academic papers - not just to stretch my intellectual muscles, but solve a particular problem.


## Other software skills

Often you will need to install something, collaborate with others and do other tasks. The crucial point so to know what is possible - especially not to reinvent the wheel.

* basics of bash/shell (`cd`, `ls`, `pwd`, `head`, `wc`, `wget`)
  * [UNIX Tutorial for Beginners](http://www.ee.surrey.ac.uk/Teaching/Unix/)
  * [Basic Unix Shell Commands for the Data Scientist](http://practical-data-science.blogspot.com/2012/09/basic-unix-shell-commands-for-data.html)
* CSV, [JSON](https://en.wikipedia.org/wiki/JSON)
* git for version control - see [Why use version control systems for writing a paper?](http://academia.stackexchange.com/a/5286/49)
  * [tryGit - Got 15 minutes and want to learn Git?](https://try.github.io/)
  * [SourceTree](https://www.sourcetreeapp.com/) - graphical interface for git (Win, OSX)
  * [Learn Git Branching](http://pcottle.github.io/learnGitBranching/) - for bigger projects and collaborations
  * [GitHub](https://github.com/) - just create an account there
* regex[p]
  * [Learn regular expressions in about 55 minutes - Sam Hughes](http://qntm.org/files/re/re.html)
  * [RegExr](http://regexr.com/)
  * [Regular Expressions Cheat Sheet - DaveChild](http://www.cheatography.com/davechild/cheat-sheets/regular-expressions/)
* basics of SQL
  * [An Introductory SQL Tutorial: How to Write Simple Queries - Rachel Sprung](http://blog.hubspot.com/marketing/sql-tutorial-introduction)
  * [Learn SQL in stages - SQLZOO](http://sqlzoo.net/)
  * [Stack Exchange Data](https://data.stackexchange.com/) - see examples, write your own queries
  * [Sams Teach Yourself SQL in 10 Minutes](http://forta.com/books/0672336073/) - a book, in my spirit of teaching SQL (from `SELECT *`, not `CREATE`)
* working with REST APIs
  * e.g. [The Google Maps Geocoding API](https://developers.google.com/maps/documentation/geocoding/intro)
* HTML (and JavaScript may be a plus)
  * [Introduction to HTML - MDN ](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Introduction)
  * my post: [D3.js workshop at ICM for KFnrD]({{site.url}}/2016/02/09/d3js-icm-kfnrd.html)

Don't be afraid of learning new technologies (e.g. *this data is in [MongoDB](https://docs.mongodb.org/getting-started/python/introduction/), a NoSQL database; can you fetch it?*) - often you can get the basics in a day.
Most technologies, from the user's perspective, are easy (at least comparing to algebraic geometry or quantum field theory).


## Practicing and building a showcase

Some people recommend [Kaggle](https://www.kaggle.com) as a starting point but I would take it with a grain of salt.
Don't get me wrong - there are great resources, it provides feedback (otherwise it is hard to tell if your solution is good) and some people find it really engaging.
But if you start with a goal of winning - you will end up disappointed, with neither fame nor gold (prized competitions are not beginner-level).
Moreover, beware that industrial problems rarely look like that (e.g. in all mine data cleaning was a big thing, and in none 5% score improvement mattered). More on that:

* [5 Reasons Kaggle Projects Won't Help Your Data Science Resume](http://datascienceresume.com/advice/5-reasons-why-doing-kaggle-projects-won-t-help-you-create-a-stand-out-data-science-resume)
* [Machine learning isn't Kaggle competitions - Julia Evans](http://jvns.ca/blog/2014/06/19/machine-learning-isnt-kaggle-competitions/)


Personally, I enjoy the most working on data I care about and find genuinely interesting.
It drives my motivation much more than any competition could. Also, this way it is a complete data science - from asking questions and getting data to presenting the results in a meaningful form.

Making results public, including code, is a great room for both feedback and building a showcase.
It can be an IPython Notebook, or a website, or even a just a plot (but then be sure to sign it - if it goes viral you want to get due recognition!). E.g. some mine (see also [Projects]({{site.url}}/projects)):

* [Polish Book Themes](http://p.migdal.pl/wizualizacja-wolnych-lektur/polish_books_themes.html)
* [TagOverflow](http://p.migdal.pl/tagoverflow/) - graph of tags from Stack Exchange sites
* [Analysis of 2010-2014 matura exams](https://github.com/stared/delab-matury) (in Polish).

So, once again, be sure to get a [GitHub](https://github.com) account (for hosting code, [notebooks](https://github.com/blog/1995-github-jupyter-notebooks-3) and [websites](https://pages.github.com/)). Mine looks like that: [github.com/stared](https://github.com/stared).
And don’t be afraid to put premature code: if it is not good yet then no-one will notice (or care) anyway.
Also, some people like writing about problems they have just learnt (e.g. [How gzip uses Huffman coding - Julia Evans](http://jvns.ca/blog/2015/02/22/how-gzip-uses-huffman-coding/)). If it is your thing - just do it (see [my post on Jekyll]({{site.url}}/2015/12/02/first-post.html))!

EDIT (Feb 2018): If you want to play with data [Kaggle Datasets](http://kaggle.com/datasets) are a wonderful place to start.


## Data science boot camps

It’s totally fine to learn things on your own. But doing on a boot camp may be a huge boosts - motivational, with access to tutors/experts, with job opportunities. Here are some camps I am aware of:

* [BIG DIVE](http://www.bigdive.eu/) - *Development, Visualization and Data Science*
  * [BIG DIVE, czyli o dawaniu nura w dane](http://smarterpoland.pl/index.php/2013/05/big-dive-czyli-o-nurkowaniu-w-danych/) (in Polish) - I participated in the 1st edition!
  * [Big Dive review - alkamid](http://web.archive.org/web/20171004191246/http://alkamid.com/big-dive-review-1/)
* [Insight Data Science Fellows Program](http://insightdatascience.com/) - *an intensive seven week post-doctoral training fellowship bridging the gap between academia and data science*
* [S2DS London](http://www.s2ds.org/) - *Science to Data Science summer school*
* [Recurse Center (aka Hacker School)](https://www.recurse.com/) - *a free, self-directed, educational retreat for people who want to get better at programming, whether they've been coding for three decades or three months*
  * [its manual](https://www.recurse.com/manual) is a nice resource on good environment for learning


## Internships

If you are still a student - doing an internship may be a great way to get a lot of experience, feedback, confidence and contacts. I did mine during my PhD studies (in Europe it is not common to take a break, and a lot of people in academia dissuaded me, but I consider it a wonderful, life-changing experience)[^3].

To search for offers try googling `data science/scientist intern/internship` and visit some job listings (e.g. [Indeed]( http://www.indeed.com/jobs?q=data+science+intern&l=)).
Sometimes it makes sense to mail a company even if they don't use words `intern` or `internship` - especially smaller ones may be flexible.
Some bigger tech companies (Facebook, Google, IBM, Microsoft) offer internships[^4], see:

* [What companies have data science internships? - Quora](https://www.quora.com/What-companies-have-data-science-internships)

Aim at tech companies (to actually work in data science).
In the [San Francisco] Bay Area (i.e. north of Silicon Valley) there are plenty opportunities to learn data science - it should be your primary destination.
To work in US you need to get J-1 visa (of course, after they want you), but it's relatively easy (but takes ~2-3 months).

Once on-site, start look for various meeting and hackathons, especially via [Meetups](http://www.meetup.com/). Search for anything that may fit (data science, R communities, big data etc) and try to visit a lot of events. In the Bay Area it is an advantage to be "bold". So don't be afraid to asking about or for anything, starting talking to people etc - on the average it will be much better than taking a passive posture. See also:

* [A brief guide to tech internships](http://alexeymk.com/a-brief-guide-to-tech-internships/)
* [How to intern in Silicon Valley with a J1 visa](http://web.archive.org/web/20150413000314/http://blog.sendtoinc.com/2013/12/11/silicon-valley-internship-j1-visa/)
* [An Intern's Guide to a Summer in the Bay Area](http://alexeymk.com/an-interns-guide-to-a-summer-in-the-bay-area/) (from 2011, so now renting prices are ~30% higher)



## Feed

Never stop learning. Some feeds:

* [Hacker News](https://news.ycombinator.com/)[^5] - startups, tech; data science is one of its topics
* [DataTau](http://www.datatau.com/)
* [reddit.com/r/MachineLearning](https://www.reddit.com/r/MachineLearning/)
* [KDnuggets](http://www.kdnuggets.com/)

And if you have a question, a good place to ask (and search for answers) is:

* [Cross Validated - Stack Exchange](http://stats.stackexchange.com/)


## Advanced stuff

Since you are in maths, it may be possible for you to make a shortcut and get into advanced topics. Here is a random list of starting points I consider interesting:

* [Static and dynamic network visualization with R - Katya Ognyanova](http://kateto.net/network-visualization)
* [Probabilistic Programming & Bayesian Methods for Hackers - Cam Davidson-Pilon](http://camdavidsonpilon.github.io/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers/)
* [The Unreasonable Effectiveness of Recurrent Neural Networks - Andrej Karpathy](http://karpathy.github.io/2015/05/21/rnn-effectiveness/)

EDIT (Feb 2018) - some of my new introductions:

* [king - man + woman is queen; but why?](http://p.migdal.pl/2017/01/06/king-man-woman-queen-why.html)
* [Learning Deep Learning with Keras](http://p.migdal.pl/2017/04/30/teaching-deep-learning.html)
* [Starting deep learning hands-on: image classification on CIFAR-10](https://blog.deepsense.ai/deep-learning-hands-on-image-classification/)


## About

This blog post started as emails, and went through a stage of an extract of emails (shared on Google Docs). It took me way more time than I expected to present it in the current form.

There are many people who helped me with this post, at its various stages (starting from asking me questions!). But I would like to especially thank to: Adam Goliński, Sebastian Jaszczur, Kasia Kulma and Robert Bogucki for their remarks on the final version.

I would love to hear your feedback! Did you find it useful? Or maybe you would recommend another learning strategy? Or additional links?

Or maybe your company needs a data science training? I would be happy to provide it! See [http://deepsense.ai](http://deepsense.ai/) for the menu (and we are happy to make custom workshops) and fill the form or contact me directly!


[^1]: For instance, if you don't have a quantitative background, you need to focus on it (and it may be the hardest part). Since it was not my path, I can't help.
[^6]: In particular, *hacking p-value* is wrong. But you should be aware what is [p-value](https://en.wikipedia.org/wiki/P-value) and why it can be hacked (accidentally or purposefully).
[^2]: But if you come from a non-academic background (e.g. web dev), then from your perspective data science is science. Or to make it precise - it is engineering, but more like designing new engines, than building a house.
[^3]: Great thanks to Adam Zadrożny for showing me this possibility (he interned at Facebook while doing his PhD in gravity waves) and to [Jacek Migdał](http://jacek.migdal.pl/) for convincing me to apply to the Bay Area, rather than somewhere else.
[^4]: If you have background in computer science, it will be like playing on the easy level (it was not my case, though). It may be possible to apply as a software engineer expressing interest in data - and learn from that point.
[^5]: [Hacker News](http://news.ycombinator.com/) is my best general-purpose non-personal feed, complemented by [The Economist](http://www.economist.com/).
