---
layout: post
title: "Learning Deep Learning with Keras"
date: '2017-04-18 19:30 +0100'
author: Piotr Migdał
tags:
  - machine-learning
  - deep-learning
  - tutorial
mathjax: true
description: >-
  Don't be afraid of artificial neural networks - it is easy to start! Here's overview and links to didactic materials.
image: /imgs/2017-04-17-learning-deep-learning/deep_learning_meme_keras.png
---

I teach deep learning both for living (as the main [deepsense.io instructor](http://workshops.deepsense.io/), in a Kaggle-winning team[^deepsense]) and as part of my volunteering to [Polish Children's Fund](http://crastina.se/gifted-children-in-poland-by-piotr-migdal/) with workshops for gifted high-school students[^trypophobia]. I want to share a few things I've learnt about teaching (and learning) deep learning.

Whether you want to start learning deep learning for you career, have a nice adventure (e.g. with [detecting huggable objects](https://www.reddit.com/r/MachineLearning/comments/4casci/can_i_hug_that_i_trained_a_classifier_to_tell_you/)) or get insight into machines before they take over[^webcomics], this post is for you! Its goal is not to teach neural networks, but to provide an overview and point to didactically useful resources.

![Deep Learning Meme - What I actually do (Keras version)](/imgs/2017-04-17-learning-deep-learning/deep_learning_meme_keras.png)

Don't be afraid of artificial neural networks - it is easy to start! In fact, my biggest regret is delaying learning it, because of their perceived difficulty. To start all what you need is really basic programming and very simple mathematics.

I suggest starting image recognition tasks with [Keras](https://keras.io/), a high-level neural network library in Python. If you are new to this language, you need to pick its basics - see [section on Python](http://p.migdal.pl/2016/03/15/data-science-intro-for-math-phys-background.html#python) in my [introduction to data science](http://p.migdal.pl/2016/03/15/data-science-intro-for-math-phys-background.html).
If you like to use neural networks with less code than Keras, the only option is to [use pigeons](https://www.youtube.com/watch?v=flzGjnJLyS0). Yes, seriously: [Pigeons spot cancer as well as human experts](http://www.sciencemag.org/news/2015/11/pigeons-spot-cancer-well-human-experts)!


## Before we start, let's talk... and play

**Deep learning** is a name for **machine learning** techniques using many-layered artificial **neural networks**. Occasionally people use **artificial intelligence**, but unless you want to sound sci-fi, it is reserved for problems that are considered "too hard for machines" - a frontier that keeps moving rapidly.

This is a field that exploded in the [last few years](https://devblogs.nvidia.com/parallelforall/mocha-jl-deep-learning-julia/), reaching human-level accuracy in visual recognition tasks. It's not a surprise, that [companies like Google or Facebook are taking lead over academia](http://www.economist.com/news/business/21695908-silicon-valley-fights-talent-universities-struggle-hold-their).
Though, while ocassion


Moreover, each few months I am being mind-blown but something exceeding my expectations, e.g.:

XXX

* unreasonable
* style transfer (and movies)
* face reenactment
* drawing cats
* colorizing
* GANs
* pix2pix

You need to have basic notion of machine learning - classification and validation. You can see my [machine learning section](http://p.migdal.pl/2016/03/15/data-science-intro-for-math-phys-background.html#statistics-and-machine-learning), or at least start with this beautiful tree-based [visual introduction to machine learning](http://www.r2d3.us/visual-intro-to-machine-learning-part-1/).
If you are curios what are the neural networks, take a loot at this series of videos with a smooth introduction:

* [Neural Networks Demystified](http://lumiverse.io/series/neural-networks-demystified)
* [A Visual and Interactive Guide to the Basics of Neural Networks](http://jalammar.github.io/visual-interactive-guide-basics-neural-networks/) by J Alammar

These techniques are data-hungry. See a plot of [AUC score](https://stats.stackexchange.com/questions/132777/what-does-auc-stand-for-and-what-is-it) for [logistic regression, random forest and deep learning on Higgs dataset](https://github.com/szilard/benchm-ml/tree/master/x1-data-higgs) (datapoints are in millions):

![Logistic Regression vs Random Forest vs Deep Learning on Higgs dataset ](/imgs/2017-04-17-learning-deep-learning/linear_random_forest_deep_learning_higgs_szilard.png)

In general there is no guarantee that even with a lot of data deep learning does better than other techniques, for example tree-based such as random forest or [boosted trees](https://xgboost.readthedocs.io/en/latest/model.html).

Do I need some [Skynet](https://en.wikipedia.org/wiki/Skynet_%28Terminator%29) to run it? Actually not - it's a piece of software, as any other. And you can play with in even in your browser:

* [TensorFlow Playground](http://playground.tensorflow.org/) for point separation, with a visual interface
* [ConvNetJS](http://cs.stanford.edu/people/karpathy/convnetjs/) for digit and image recognition
* [Keras.js Demo](https://transcranial.github.io/keras-js/) - to visualize and use real networks in your browser (e.g. ResNet-50)


## Mathematics

Deep learning (that is - neural networks with many layers) use very simple mathematical operations - just many of them. Here there are a few, which you can find in almost any network (read the below, but don't get intimidated):

* vectors, matrices, multi-dimensional arrays,
* addition, multiplication,
* [convolutions](http://setosa.io/ev/image-kernels/) to extract and process local patterns,
* activation functions: [sigmoid](https://en.wikipedia.org/wiki/Sigmoid_function), [tanh](https://www.wolframalpha.com/input/?i=tanh[x]) or [ReLU](https://en.wikipedia.org/wiki/Rectifier_%28neural_networks%29) to add non-linearity,
* [softmax](https://en.wikipedia.org/wiki/Softmax_function) to convert vectors into probabilities,
* [log-loss (cross-entropy)](http://datascience.stackexchange.com/questions/9302/the-cross-entropy-error-function-in-neural-networks) to penalize wrong guesses in a smart way,
* gradients and chain-rule ([backpropagation](http://cs231n.github.io/optimization-2/)) for optimizing network parameters,
* stochastic gradient descent and its variants (e.g. [momentum](http://distill.pub/2017/momentum/)).

If your background is in physics[^quantum], mathematics, statistics or signal processing - most likely you already know more than enough to start!

If you last contact with mathematics was in high-school, don't worry. This mathematics is simple to a point that a convolutional neural network for digit recognition can be implemented in a spreadsheet (with no macros), see: [Deep Spreadsheets with ExcelNet](http://www.deepexcel.net/).
It is only a proof-of-principle solution - not only inefficient, but also lacking the most crucial part - ability to train new networks.

Basics of vector calculus is crucial not only for deep learning, but also many other machine learning techniques (e.g. in [word2vec I wrote about](p.migdal.pl/2017/01/06/king-man-woman-queen-why.html)).
To learn it I recommend starting from one of the following:

* J. Ström, K. Åström, and T. Akenine-Möller, [Immersive Linear Algebra](http://immersivemath.com/ila/index.html) - a linear algebra book with fully interactive figures
*  Applied Math and Machine Learning Basics: [Linear Algebra](http://www.deeplearningbook.org/contents/linear_algebra.html) from the [Deep Learning](http://www.deeplearningbook.org/) book
* [Linear algebra cheat sheet for deep learning](https://medium.com/towards-data-science/linear-algebra-cheat-sheet-for-deep-learning-cd67aba4526c) by Brendan Fortuner

Since there are many references to [NumPy](https://docs.scipy.org/doc/numpy-dev/user/quickstart.html), it may be useful to learn its basics:

* [From Python to Numpy](http://www.labri.fr/perso/nrougier/from-python-to-numpy/) by Nicolas P. Rougier
* [SciPy lecutres: The NumPy array object](http://www.scipy-lectures.org/intro/numpy/array_object.html)

 At the same time - bear: look back at the meme, at its *What mathematicians think I do* part. It's totally fine to start from a magically working code.


## Frameworks

There is a handful of popular deep learning libraries, including [TensorFlow](https://www.tensorflow.org/), [Theano](http://deeplearning.net/software/theano/), [Torch](http://torch.ch/) and [Caffe](http://caffe.berkeleyvision.org/). All of them have Python interface (now also for Torch: [PyTorch](http://pytorch.org/)).

So, which to choose? First, as always, screw all subtle performance benchmarks, as *[premature optimization is the root of all evil](https://en.wikiquote.org/wiki/Donald_Knuth)*.
What is crucial, is to start with one which easy to write (and read!), one with many online resources, and one that you can actually install on your computer without too much of pain.

Bear in mind that core frameworks are multidimensional array expression compilers with GPU support. Current neural networks can be expressed as such. However, if you want just to work with neural networks, by [rule of least power](https://en.wikipedia.org/wiki/Rule_of_least_power), I recommend starting with a framework just for neural networks. For example...


### Keras

If you like philosophy of Python (brevity, readability, one preferred way to do things), [Keras](https://keras.io/) is for you. It is a high-level library living on top of TensorFlow or Theano.
Also, if you want to have a propaganda picture, there a possibly biased (or overfitted?) popularity ranking:

* [The state of deep learning frameworks (from GitHub metrics), April 2017. - François Chollet (Keras creator)](https://twitter.com/fchollet/status/852194634470223873)

![](/imgs/2017-04-17-learning-deep-learning/deep_learning_framework_popularity_apr2017_fchollet.png)

If you want to consult a different source, based on [arXiv](https://arxiv.org/) paper rather than GitHub activity, see [A Peek at Trends in Machine Learning](https://medium.com/@karpathy/a-peek-at-trends-in-machine-learning-ab8a1085a106) by Andrej Karpathy.
Popularity is important - it means that if you want to search for a network architecture, googling for it (e.g. `UNet Keras`) is likely to return an example.
Where to start learning it? Documentation on Keras is nice, and [its blog](https://blog.keras.io/) is a valuable resource. For a complete, interactive introduction to deep learning with Keras in [Jupyter Notebook](http://jupyter.org/), I really recommend:

* [Deep Learning with Keras and TensorFlow](https://github.com/leriomaggio/deep-learning-keras-tensorflow) by Valerio Maggio

For shorter ones, try one of these:

* [Visualizing parts of Convolutional Neural Networks using Keras and Cats](https://hackernoon.com/visualizing-parts-of-convolutional-neural-networks-using-keras-and-cats-5cc01b214e59) by Erik Reppel
* [Deep learning for complete beginners: convolutional neural networks with Keras](https://cambridgespark.com/content/tutorials/convolutional-neural-networks-with-keras/index.html) by Petar Veličković
* [Handwritten Digit Recognition using Convolutional Neural Networks in Python with Keras](http://machinelearningmastery.com/handwritten-digit-recognition-using-convolutional-neural-networks-python-keras/) by Jason Brownlee (Theano tensor order)


* XXX mine to Keras
  * with ASCII plots
  * loading notMNIST

There are a few add-on to Keras, especially useful for learning it. I created [ASCII summary for sequential models](https://github.com/stared/keras-sequential-ascii) to show data flow inside networks, along with the number of parameters at each layer:

XXX (some more realistic example)


```
           OPERATION           DATA DIMENSIONS   WEIGHTS(N)   WEIGHTS(%)

               Input   #####      3   32   32
  BatchNormalization    μ|σ  -------------------        64     0.1%
                       #####      3   32   32
       Convolution2D    \|/  -------------------       448     0.8%
                relu   #####     16   30   30
       Convolution2D    \|/  -------------------      2320     4.3%
                relu   #####     16   28   28
        MaxPooling2D   Y max -------------------         0     0.0%
                       #####     16   14   14
       Convolution2D    \|/  -------------------       272     0.5%
                tanh   #####     16   14   14
             Flatten   ||||| -------------------         0     0.0%
                       #####        3136
               Dense   XXXXX -------------------     50192    94.1%
                       #####          16
             Dropout    | || -------------------         0     0.0%
                       #####          16
               Dense   XXXXX -------------------        51     0.1%
             softmax   #####           3
```

You might be also interested in nicer progress bars with [keras-tqdm](https://github.com/bstriner/keras-tqdm), exploration of activations at each layer with [quiver](https://github.com/jakebian/quiver) or converting Keras models to JavaScript, runnable in a browser.


### TensorFlow

If not Keras, then I recommend starting with TensorFlow.
It is a bit more low-level and verbose, but makes it straightforward to optimize various multidimensional array (or, well, tensor) operations. A few good resources:

* the official [TensorFlow Tutorials](https://www.tensorflow.org/versions/master/tutorials/index.html) is very good
* [TensorFlow Tutorial and Examples for beginners](https://github.com/aymericdamien/TensorFlow-Examples/) by Aymeric Damien (with Python 2.7)
* [Simple tutorials using Google's TensorFlow Framework](https://github.com/nlintz/TensorFlow-Tutorials) by Nathan Lintz

In any case, [TensorBoard](https://www.tensorflow.org/get_started/summaries_and_tensorboard) makes it easy to keep track of the training process. It can be [also used with Keras, via callbacks](http://stackoverflow.com/questions/42112260/how-do-i-use-the-tensorboard-callback-of-keras).


### Other

Theano is similar to TensorFlow, but a bit older and harder to start.
For example, you need to manually write updates of variables. Typical neural network layers are not included, so one often uses libraries such as [Lasagne](https://lasagne.readthedocs.io/). If you look at a place to start, I like this introduction:

* [Theano Tutorial](http://www.marekrei.com/blog/theano-tutorial/) by Marek Rei

At the same time, if you see some nice code in Torch or PyTorch, don't be afraid to install and run it! Remember, frameworks are only tools.


## Datasets

Every machine learning problem needs data. You cannot just tell it *"detect if there is a cat in this picture"* and expect computer to tell you the answer. You need to *show* many instances of cats, and pictures not containing cats, and (hopefully) it will learn to generalize it other cases.
So, you need some data to start. And it is not a drawback of machine learning or just deep learning - it is a fundamental property of any learning!

Before you dive into some unknown waters, it is good to take a look at some [popular datasets](https://www.kaggle.com/benhamner/d/benhamner/nips-papers/popular-datasets-over-time/code). The key part about them is that they are... popular. It means, you can find a lot of examples what works.

### MNIST

> Many good ideas will not work well on MNIST (e.g. batch norm). Inversely many bad ideas may work on MNIST and no transfer to real [computer vision]. - [François Chollet's tweet](https://twitter.com/fchollet/status/852594987527045120)

Still, I recommend starting with [MNIST digit recognition dataset](http://yann.lecun.com/exdb/mnist/) (60k grayscale 28x28 images), included in [keras.datasets](https://keras.io/datasets/). Not necessary to master it, but just to get sense that it works at all (or to test installation and basics of Keras API).

### notMNIST

> Indeed, I once even proposed that the toughest challenge facing AI workers is to answer the question: "What are the letters 'A' and 'I'? - [Douglas R. Hofstadter](https://web.stanford.edu/group/SHR/4-2/text/hofstadter.html) (1995)

A more interesting dataset, and harder for classical machine learning algorithms, is [notMNIST](http://yaroslavvb.blogspot.com/2011/09/notmnist-dataset.html) (letters A-J from strange fonts). If you want to start with in, here is my [gist for notMNIST loading and logistic regression in Keras](https://gist.github.com/stared/70daf8e0334abf6e7527259e7221f568).

### CIFAR

A more advanced once, still suitable for CPU is [CIFAR-10 dataset](https://www.cs.toronto.edu/~kriz/cifar.html), a dataset of 32x32 photos (also in [keras.datasets](https://keras.io/datasets/)). It is

See also:

* [Which paper provides the best results on standard dataset X?](http://rodrigob.github.io/are_we_there_yet/build/) - a ranking of methods for MNIST, CIFAR and a few other datasets

### More

Deep learning requires a lot of data. If you want to train your network from scratch, it may require as many as ~10k images even if low-resolution (32x32).
Especially if data is scarce, there is no guarantee that a network will learn anything. So, what are the ways to go?

* use really low res (if your eye can see it, no need to use higher resolution)
* get a lot of data (for images like 256x256 it may be: millions of instances)
* re-train a network that already saw a lot
* generate much more data (with rotations, shifts, distortions)

Often, it's a combination of everything mentioned here.


## Standing at the shoulders of giants

Creating a new neural network has a lot in common with cooking - there are typical ingredients (layers) and recipes (popular network architectures). The lasagne metaphor is unavoidable, as we already saw.
The most important cooking contest is [ImageNet](www.image-net.org), with recognition of 1000 classes from (networks typically use 224x224).

[Neural Network Architectures](https://culurciello.github.io/tech/2016/06/04/nets.html) by Eugenio Culurciello

![Deep Learning Architectures - a scatter plot of network sizes, performances and ops per run](/imgs/2017-04-17-learning-deep-learning/deep_learning_architectures_culurciello.png)

from ; it didn't mention [SqueezeNet](https://gab41.lab41.org/lab41-reading-group-squeezenet-9b9d1d754c75) an architecture vastly reducing the number of parameters (e.g. 510x for AlexNet).

A few key networks can be readily loaded from [keras.applications](https://keras.io/applications/) module: Xception, VGG16, VGG19, ResNet50, InceptionV3. Some other are not as plug&play, but still easy to find online.
These networks serve two purposes:

* give insight into useful building blocks and architectures
* are great candidates for retraining (so called [transfer learning](http://cs231n.github.io/transfer-learning/)), when using architecture along with pre-trained weights).

XXX other implementations

* [U-Net: Convolutional Networks for Biomedical Image Segmentation](https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/)
  * [Retina blood vessel segmentation with a convolution neural network](https://github.com/orobix/retina-unet) - Keras implementation
  * [Deep Learning Tutorial for Kaggle Ultrasound Nerve Segmentation competition, using Keras](https://github.com/jocicmarko/ultrasound-nerve-segmentation)
* [A Neural Algorithm of Artistic Style](https://arxiv.org/abs/1508.06576)
  * [Neural Style Transfer & Neural Doodles implemented in Keras](https://github.com/titu1994/Neural-Style-Transfer) by Somshubra Majumdar


Another set of insights:

* [The Neural Network Zoo](http://www.asimovinstitute.org/neural-network-zoo/) by Fjodor van Veen
* [How to train your Deep Neural Network](http://rishy.github.io/ml/2017/01/05/how-to-train-your-dnn/) - how many layers, parameters, etc


## Infrastructure

For very small problems (e.g. MNIST, notMNIST), you can use your personal computer - even if it is a laptop and computations are on CPU.

For small problems (e.g. CIFAR, the unreasonable RNN), you might be still able to use PC, but it requires much more patience and trade-offs.

For medium and larger problems, essentially the only way to go is to use a machine with a strong graphic card (GPU). For example, it took us 2 days to train a model for satellite image processing for a Kaggle competition, see our [Deep learning for satellite imagery via image segmentation](https://deepsense.io/deep-learning-for-satellite-imagery-via-image-segmentation/) by Arkadiusz Nowaczyński. On a strong CPU it would had taken weeks, see:

* [Benchmarks for popular convolutional neural network models](https://github.com/jcjohnson/cnn-benchmarks) by Justin Johnson

The easiest, and the cheapest, way to use a strong GPU is to rent a remote machine on a per-hour basis. You can use Amazon (it is not only a bookstore!), here are some guides:

* [Keras with GPU on Amazon EC2 – a step-by-step instruction](https://medium.com/@mateuszsieniawski/keras-with-gpu-on-amazon-ec2-a-step-by-step-instruction-4f90364e49ac) by Mateusz Sieniawski, my mentee
* [Running Jupyter notebooks on GPU on AWS: a starter guide](https://blog.keras.io/running-jupyter-notebooks-on-gpu-on-aws-a-starter-guide.html) by Francois Chollet


## Further reading



* Courses
  * [CS231n: Convolutional Neural Networks for Visual Recognition by Andrej Karpathy](http://cs231n.github.io/) and [its videos](https://www.youtube.com/playlist?list=PLLvH2FwAQhnpj1WEB-jHmPuUeQ8mX-XXG)
* Books
  * [Ian Goodfellow and Yoshua Bengio and Aaron Courville, Deep Learning, An MIT Press book](http://www.deeplearningbook.org/) - XXX GREAT, GREAT!
  * [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com/) by Micheal Nielsen (yes, author of the Green Book)
* List of resources
  * [How to Start Learning Deep Learning](http://ofir.io/How-to-Start-Learning-Deep-Learning/) by Ofir Press
  * [A Guide to Deep Learning by YN^2](http://yerevann.com/a-guide-to-deep-learning/)
* General
  * [The Unreasonable Effectiveness of Recurrent Neural Networks](http://karpathy.github.io/2015/05/21/rnn-effectiveness/) by Andrej Karpathy
  * [How convolutional neural networks see the world - Keras Blog](https://blog.keras.io/how-convolutional-neural-networks-see-the-world.html)
  * [What convolutional neural networks look at when they see nudity – Clarifai Blog](http://blog.clarifai.com/what-convolutional-neural-networks-see-at-when-they-see-nudity/) (NSFW)
  * [Convolutional neural networks for artistic style transfer](https://harishnarayanan.org/writing/artistic-style-transfer/) by Harish Nrayanan
  * [Dreams, Drugs and ConvNets](https://speakerdeck.com/pmigdal/dreams-drugs-and-convnets) - my slides (NSFW)
* Technical
  * [Yes you should understand backprop](https://medium.com/@karpathy/yes-you-should-understand-backprop-e2f06eab496b) by Andrej Karpathy
  * [Generative Adversarial Networks (GANs) in 50 lines of code (PyTorch)](https://medium.com/@devnag/generative-adversarial-networks-gans-in-50-lines-of-code-pytorch-e81b79659e3f)
  * [Minimal and Clean Reinforcement Learning Examples](https://github.com/rlcode/reinforcement-learning)
  * [An overview of gradient descent optimization algorithms](http://sebastianruder.com/optimizing-gradient-descent/) by Sebastian Ruder
  * [Picking an optimizer for Style Transfer](https://medium.com/slavv/picking-an-optimizer-for-style-transfer-86e7b8cba84b) by Slav Ivanov
  * [Building Autoencoders in Keras](https://blog.keras.io/building-autoencoders-in-keras.html) by Francois Chollet
* Staying up-to-data:
  * [r/MachineLearning](https://www.reddit.com/r/MachineLearning/) for news
  * [distill.pub](http://distill.pub/) - an interactive, visual, open-access journal for machine learning research, with expository articles
  * my links at [https://pinboard.in/u:pmigdal/t:deep-learning](pinboard.in/u:pmigdal/t:deep-learning)
  * [twitter.com/fastml_extra](https://twitter.com/fastml_extra)
  * [GitXiv](http://www.gitxiv.com/) - arXiv + Github + Links + Discussion
  * don't be afraid to read academic papers; some are well-written and insightful (if you own Kindle or another e-reader, I recommend [Dontprint](http://dontprint.net/))
* Data
  * Kaggle
  * [iNaturalist 2017 Competition](https://github.com/visipedia/inat_comp) (675k images with 5k species)



Inspiration:

* mushrooms
* https://www.reddit.com/r/MachineLearning/comments/665flm/p_selfdriving_car_course_with_python_tensorflow/


## Thanks

I would like to thank... (you know, feedback is not only welcomed, but even might be appreciated here)

[Deep learning meme](http://knowyourmeme.com/memes/what-people-think-i-do-what-i-really-do) is not mine - I've just I rewrote from Theano to Keras (with TensorFlow backend).


## Trash

* [Building a simple neural-network with Keras](https://github.com/wxs/keras-mnist-tutorial/blob/master/MNIST%20in%20Keras.ipynb) by Xavier Snelgrove (Theano backend, old Keras 1 API)
* [Keras Tutorial: The Ultimate Beginner’s Guide to Deep Learning in Python](https://elitedatascience.com/keras-tutorial-deep-learning-in-python) with (Python 2.7 and Theano, old Keras 1 API)

* plotify, or discard:
  * https://devblogs.nvidia.com/parallelforall/mocha-jl-deep-learning-julia/ -> newer?
  * https://github.com/mrgloom/kaggle-dogs-vs-cats-solution


[^deepsense]: [NOAA Right Whale Recognition, Winners' Interview](http://blog.kaggle.com/2016/01/29/noaa-right-whale-recognition-winners-interview-1st-place-deepsense-io/) (1st place, Jan 2016), and a fresh one: [Deep learning for satellite imagery via image segmentation](https://deepsense.io/deep-learning-for-satellite-imagery-via-image-segmentation/) (4th place, Apr 2017)
[^webcomics]: It made a few episodes of webcomics obsolete: [xkcd: Tasks](https://xkcd.com/1425/) (totally, by [Park or Bird?](https://laughingsquid.com/park-or-bird-a-national-park-and-bird-identifying-app-inspired-by-an-xkcd-comic/)), [xkcd: Game AI)](https://xkcd.com/1002/) (partially, by [AlphaGo](https://deepmind.com/research/alphago/)), [PHD Comics: If TV Science was more like REAL Science](http://phdcomics.com/comics.php?n=1156) (not exactly, but still it's cool, by [LapSRN](http://vllab1.ucmerced.edu/~wlai24/LapSRN/))
[^trypophobia]: This January during a 5-day workshop 6 high-school students participated in a rather NSFL project - constructing a neural network for detecting trypophobia triggers, see e.g. [grzegorz225/trypophobia-detector](https://github.com/grzegorz225/trypophobia-detector) and [cytadela8/trypophobia_detector](https://github.com/cytadela8/trypophobia_detector/).
[^quantum]: If your background is in quantum information, the only thing you need to change is ℂ to ℝ. And expect less tensor structure, and more - convolutions.
