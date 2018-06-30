---
layout: post
title: Learning Deep Learning with Keras
date: '2017-04-30 23:59 +0100'
author: Piotr Migdał
tags:
  - machine-learning
  - deep-learning
  - overview
description: >-
  Don't be afraid of artificial neural networks - it is easy to start! An
  overview of deep learning with links to didactic materials.
image: /imgs/2017-04-30-learning-deep-learning/deep_learning_meme_keras.png
extras:
  - text: "tweet by François Chollet (the creator of Keras) with over 140 retweets"
    href: https://twitter.com/fchollet/status/858840192261644292
  - text: "Facebook post by Kaggle with over 200 shares"
    href: "https://www.facebook.com/kaggle/photos/a.10150387148668464.377856.135534208463/10155346265978464/?type=3&theater"
  - text: Hacker News front page
    href: https://news.ycombinator.com/item?id=15999578
external:
  title: "First Steps of Learning Deep Learning: Image Classification in Keras"
  href: http://www.kdnuggets.com/2017/08/first-steps-learning-deep-learning-image-classification-keras.html
  status: reprinted to KDnuggets
  date: 2017-08-16 09:30 +0800
---

I teach deep learning both for a living (as the main [deepsense.ai instructor](http://deepsense.ai/), in a Kaggle-winning team[^deepsense]) and as a part of my volunteering with the [Polish Children's Fund](http://crastina.se/gifted-children-in-poland-by-piotr-migdal/) giving workshops to gifted high-school students[^trypophobia]. I want to share a few things I've learnt about teaching (and learning) deep learning.

Whether you want to start learning deep learning for you career, to have a nice adventure (e.g. with [detecting huggable objects](https://www.reddit.com/r/MachineLearning/comments/4casci/can_i_hug_that_i_trained_a_classifier_to_tell_you/)) or to get insight into machines before they take over[^webcomics], this post is for you! Its goal is not to teach neural networks by itself, but to provide an overview and to point to didactically useful resources.

![Deep Learning Meme - What I actually do (Keras version)](/imgs/2017-04-30-learning-deep-learning/deep_learning_meme_keras.png)

Don't be afraid of artificial neural networks - it is easy to start! In fact, my biggest regret is delaying learning it, because of the perceived difficulty.
To start, all you need is really basic programming, very simple mathematics and knowledge of a few machine learning concepts.
I will explain where to start with these requirements.

In my opinion, the best way to start is from a high-level interactive approach (see also: [Quantum mechanics for high-school students](http://p.migdal.pl/2016/08/15/quantum-mechanics-for-high-school-students.html) and my [Quantum Game with Photons](http://quantumgame.io/)).
For that reason, I suggest starting with image recognition tasks in [Keras](https://keras.io/), a popular neural network library in Python.
If you like to train neural networks with less code than in Keras, the only viable option is to [use pigeons](https://www.youtube.com/watch?v=flzGjnJLyS0). Yes, seriously: [pigeons spot cancer as well as human experts](http://www.sciencemag.org/news/2015/11/pigeons-spot-cancer-well-human-experts)!


## What is deep learning and why is it cool?

**Deep learning** is a name for **machine learning** techniques using many-layered artificial **neural networks**. Occasionally people use the term **artificial intelligence**, but unless you want to sound sci-fi, it is reserved for problems that are currently considered *"too hard for machines"* - a frontier that keeps moving rapidly.
This is a field that exploded in the last few years, reaching human-level accuracy in visual recognition tasks (among many other tasks), see:

* [Measuring the Progress of AI Research](https://www.eff.org/ai/metrics) by Electronic Frontier Foundation (2017)

Unlike quantum computing, or fusion power - it is a technology that is being applied right now, not some possibility for the future.
There is a rule of thumb:

> Pretty much anything that a normal person can do in <1 sec, we can now automate with AI. - [Andrew Ng's tweet](https://twitter.com/andrewyng/status/788548053745569792)

Some people go even further, [extrapolating that statement to experts](https://lukeoakdenrayner.wordpress.com/2017/04/24/the-end-of-human-doctors-understanding-medicine/).
It's not a surprise that [companies like Google and Facebook at the cutting-edge of progress](http://www.economist.com/news/business/21695908-silicon-valley-fights-talent-universities-struggle-hold-their).
In fact, every few months I am blown away by something exceeding my expectations, e.g.:

* [The Unreasonable Effectiveness of Recurrent Neural Networks](http://karpathy.github.io/2015/05/21/rnn-effectiveness/)[^unreasonable] for generating fake Shakespeare, Wikipedia entries and LaTeX articles
* [A Neural Algorithm of Artistic Style](https://arxiv.org/abs/1508.06576) style transfer ([and for videos](https://www.youtube.com/watch?v=Khuj4ASldmU)!)
* [Real-time Face Capture and Reenactment](https://www.youtube.com/watch?v=ohmajJTcpNk)
* [Colorful Image Colorization](http://richzhang.github.io/colorization/)
* [Plug & Play Generative Networks](http://www.evolvingai.org/ppgn) for photorealistic image generation
* [Dermatologist-level classification of skin cancer](http://cs.stanford.edu/people/esteva/nature/) along with other medical diagnostic tools
* [Image-to-Image Translation (pix2pix)](https://phillipi.github.io/pix2pix/) - sketch to photo
* [Teaching Machines to Draw](https://research.googleblog.com/2017/04/teaching-machines-to-draw.html) sketches of cats, dogs etc

It looks like some sorcery.
If you are curious what neural networks are, take a look at this series of videos for a smooth introduction:

* [Neural Networks Demystified](https://www.youtube.com/watch?v=bxe2T-V8XRs) by Stephen Welch  - video series
* [A Visual and Interactive Guide to the Basics of Neural Networks](http://jalammar.github.io/visual-interactive-guide-basics-neural-networks/) by J Alammar

These techniques are data-hungry. See a plot of [AUC score](https://stats.stackexchange.com/questions/132777/what-does-auc-stand-for-and-what-is-it) for [logistic regression, random forest and deep learning on Higgs dataset](https://github.com/szilard/benchm-ml/tree/master/x1-data-higgs) (data points are in millions):

![Logistic Regression vs Random Forest vs Deep Learning on Higgs dataset ](/imgs/2017-04-30-learning-deep-learning/linear_random_forest_deep_learning_higgs_szilard.png)

In general there is no guarantee that, even with a lot of data, deep learning does better than other techniques, for example tree-based such as random forest or [boosted trees](https://xgboost.readthedocs.io/en/latest/model.html).


## Let's play!

Do I need some [Skynet](https://en.wikipedia.org/wiki/Skynet_%28Terminator%29) to run it? Actually not - it's a piece of software, like any other. And you can even play with it in your browser:

* [TensorFlow Playground](http://playground.tensorflow.org/) for point separation, with a visual interface
* [ConvNetJS](http://cs.stanford.edu/people/karpathy/convnetjs/) for digit and image recognition
* [Keras.js Demo](https://transcranial.github.io/keras-js/) - to visualize and use real networks in your browser (e.g. ResNet-50)

Or... if you want to use Keras in Python, see [this minimal example](https://github.com/stared/keras-mini-examples/blob/master/mnist_simple.ipynb) - just to get convinced you can use it on your own computer.


## Python and machine learning

I mentioned basics Python and machine learning as a requirement.
They are already covered in [my introduction to data science](http://p.migdal.pl/2016/03/15/data-science-intro-for-math-phys-background.html) in [Python](http://p.migdal.pl/2016/03/15/data-science-intro-for-math-phys-background.html#python) and [statistics and machine learning](http://p.migdal.pl/2016/03/15/data-science-intro-for-math-phys-background.html#statistics-and-machine-learning) sections, respectively.

For Python, if you already have [Anaconda distribution](https://www.continuum.io/downloads) (covering most data science packages), the only thing you need is to install [TensorFlow](https://www.tensorflow.org/install/) and [Keras](https://keras.io/#installation).

When it comes to machine learning, you don't need to learn many techniques before jumping into deep learning. Though, later it would be a good practice to see if a given problem can be solved with much simpler methods. For example, [random forest](http://blog.yhat.com/posts/random-forests-in-python.html) is often a lockpick, working out-of-the-box for many problems. You need to understand why we need to train and then test a classifier (to validate its predictive power). To get the gist of it, start with this beautiful tree-based animation:

* [Visual introduction to machine learning](http://www.r2d3.us/visual-intro-to-machine-learning-part-1/) by Stephanie Yee and Tony Chu

Also, it is good to understand [logistic regression](https://en.wikipedia.org/wiki/Logistic_regression), which is a building block of almost any neural network for classification.


## Mathematics

Deep learning (that is - neural networks with many layers) uses mostly very simple mathematical operations - just many of them. Here there are a few, which you can find in almost any network (look at this list, but don't get intimidated):

* vectors, matrices, multi-dimensional arrays,
* addition, multiplication,
* [convolutions](http://setosa.io/ev/image-kernels/) to extract and process local patterns,
* activation functions: [sigmoid](https://en.wikipedia.org/wiki/Sigmoid_function), [tanh](https://www.wolframalpha.com/input/?i=tanh[x]) or [ReLU](https://en.wikipedia.org/wiki/Rectifier_%28neural_networks%29) to add non-linearity,
* [softmax](https://en.wikipedia.org/wiki/Softmax_function) to convert vectors into probabilities,
* [log-loss (cross-entropy)](http://datascience.stackexchange.com/questions/9302/the-cross-entropy-error-function-in-neural-networks) to penalize wrong guesses in a smart way (see also [Kullback-Leibler Divergence Explained](https://www.countbayesie.com/blog/2017/5/9/kullback-leibler-divergence-explained)),
* gradients and chain-rule ([backpropagation](http://cs231n.github.io/optimization-2/)) for optimizing network parameters,
* stochastic gradient descent and its variants (e.g. [momentum](http://distill.pub/2017/momentum/)).

If your background is in mathematics, statistics, physics[^quantum] or signal processing - most likely you already know more than enough to start!

If your last contact with mathematics was in high-school, don't worry. Its mathematics is simple to the point that a convolutional neural network for digit recognition can be implemented in a spreadsheet (with no macros), see: [Deep Spreadsheets with ExcelNet](http://www.deepexcel.net/).
It is only a proof-of-principle solution - not only inefficient, but also lacking the most crucial part - the ability to train new networks.

The basics of vector calculus are crucial not only for deep learning, but also for many other machine learning techniques (e.g. in [word2vec I wrote about](p.migdal.pl/2017/01/06/king-man-woman-queen-why.html)).
To learn it, I recommend starting from one of the following:

* [Getting started with linear algebra for deep learning](https://hadrienj.github.io/posts/Deep-Learning-Book-Series-Introduction/) by Hadrien Jean (an intro to [Linear Algebra](http://www.deeplearningbook.org/contents/linear_algebra.html) from the [Deep Learning](http://www.deeplearningbook.org/))
* J. Ström, K. Åström, and T. Akenine-Möller, [Immersive Linear Algebra](http://immersivemath.com/ila/index.html) - a linear algebra book with fully interactive figures
* [Linear algebra cheat sheet for deep learning](https://medium.com/towards-data-science/linear-algebra-cheat-sheet-for-deep-learning-cd67aba4526c) by Brendan Fortuner

Since there are many references to [NumPy](https://docs.scipy.org/doc/numpy-dev/user/quickstart.html), it may be useful to learn its basics:

* [From Python to Numpy](http://www.labri.fr/perso/nrougier/from-python-to-numpy/) by Nicolas P. Rougier
* [SciPy lectures: The NumPy array object](http://www.scipy-lectures.org/intro/numpy/array_object.html)

 At the same time - look back at the meme, at the *What mathematicians think I do* part. It's totally fine to start from a magically working code, treating neural network layers like LEGO blocks.


## Frameworks

There is a handful of popular deep learning libraries, including [TensorFlow](https://www.tensorflow.org/), [Theano](http://deeplearning.net/software/theano/), [Torch](http://torch.ch/) and [Caffe](http://caffe.berkeleyvision.org/). Each of them has Python interface (now also for Torch: [PyTorch](http://pytorch.org/)).

So, which to choose? First, as always, screw all subtle performance benchmarks, as *[premature optimization is the root of all evil](https://en.wikiquote.org/wiki/Donald_Knuth)*.
What is crucial is to start with one which is easy to write (and read!), one with many online resources, and one that you can actually install on your computer without too much pain.

Bear in mind that core frameworks are multidimensional array expression compilers with GPU support. Current neural networks can be expressed as such. However, if you just want to work with neural networks, by [rule of least power](https://en.wikipedia.org/wiki/Rule_of_least_power), I recommend starting with a framework just for neural networks. For example...


### Keras

If you like the [philosophy of Python](https://en.wikipedia.org/wiki/Zen_of_Python) (brevity, readability, one preferred way to do things), [Keras](https://keras.io/) is for you. It is a high-level library for neural networks, using TensorFlow or Theano as its backend.
Also, if you want to have a propaganda picture, there is a possibly biased (or [overfitted](https://en.wikipedia.org/wiki/Overfitting)?) popularity ranking:

* [The state of deep learning frameworks (from GitHub metrics), April 2017. - François Chollet (Keras creator)](https://twitter.com/fchollet/status/852194634470223873)

![](/imgs/2017-04-30-learning-deep-learning/deep_learning_framework_popularity_apr2017_fchollet.png)

If you want to consult a different source, based on arXiv papers rather than GitHub activity, see [A Peek at Trends in Machine Learning](https://medium.com/@karpathy/a-peek-at-trends-in-machine-learning-ab8a1085a106) by Andrej Karpathy.
Popularity is important - it means that if you want to search for a network architecture, googling for it (e.g. `UNet Keras`) is likely to return an example.
Where to start learning it? Documentation on Keras is nice, and [its blog](https://blog.keras.io/) is a valuable resource. For a complete, interactive introduction to deep learning with Keras in [Jupyter Notebook](http://jupyter.org/), I really recommend:

* [Deep Learning with Keras and TensorFlow](https://github.com/leriomaggio/deep-learning-keras-tensorflow) by Valerio Maggio

For shorter ones, try one of these:

* [Visualizing parts of Convolutional Neural Networks using Keras and Cats](https://hackernoon.com/visualizing-parts-of-convolutional-neural-networks-using-keras-and-cats-5cc01b214e59) by Erik Reppel
* [Deep learning for complete beginners: convolutional neural networks with Keras](https://cambridgespark.com/content/tutorials/convolutional-neural-networks-with-keras/index.html) by Petar Veličković
* [Handwritten Digit Recognition using Convolutional Neural Networks in Python with Keras](http://machinelearningmastery.com/handwritten-digit-recognition-using-convolutional-neural-networks-python-keras/) by Jason Brownlee (Theano tensor dimension order[^theano])

There are a few add-ons to Keras, which are especially useful for learning it. I created [ASCII summary for sequential models](https://github.com/stared/keras-sequential-ascii) to show data flow inside networks (in a nicer way than `model.summary()`).
It shows layers, dimensions of data `(x, y, channels)` and the number of free parameters (to be optimized). For example, for [a network for digit recognition](https://github.com/fchollet/keras/blob/master/examples/mnist_cnn.py) it might look like:

```
           OPERATION           DATA DIMENSIONS   WEIGHTS(N)   WEIGHTS(%)

               Input   #####     32   32    3
              Conv2D    \|/  -------------------       896     0.1%
                relu   #####     32   32   32
              Conv2D    \|/  -------------------      9248     0.7%
                relu   #####     30   30   32
        MaxPooling2D   Y max -------------------         0     0.0%
                       #####     15   15   32
             Dropout    | || -------------------         0     0.0%
                       #####     15   15   32
              Conv2D    \|/  -------------------     18496     1.5%
                relu   #####     15   15   64
              Conv2D    \|/  -------------------     36928     3.0%
                relu   #####     13   13   64
        MaxPooling2D   Y max -------------------         0     0.0%
                       #####      6    6   64
             Dropout    | || -------------------         0     0.0%
                       #####      6    6   64
             Flatten   ||||| -------------------         0     0.0%
                       #####        2304
               Dense   XXXXX -------------------   1180160    94.3%
                relu   #####         512
             Dropout    | || -------------------         0     0.0%
                       #####         512
               Dense   XXXXX -------------------      5130     0.4%
             softmax   #####          10
```

You might be also interested in nicer progress bars with [keras-tqdm](https://github.com/bstriner/keras-tqdm), exploration of activations at each layer with [quiver](https://github.com/keplr-io/quiver), checking attention maps with [keras-vis](https://github.com/raghakot/keras-vis) or converting Keras models to JavaScript, runnable in a browser with [Keras.js](https://transcranial.github.io/keras-js/).
Speaking of languages, there is also [R interface to Keras](https://rstudio.github.io/keras/).

**EDIT** (March 2018): Also, I wrote [livelossplot](https://github.com/stared/livelossplot/) - a live training loss plot in Jupyter Notebook (for Keras, PyTorch and other frameworks).


### TensorFlow

If not Keras, then I recommend starting with bare TensorFlow.
It is a bit more low-level and verbose, but makes it straightforward to optimize various multidimensional array (or, well, tensor) operations. A few good resources:

* the official [TensorFlow Tutorial](https://www.tensorflow.org/versions/master/tutorials/index.html) is very good
* [Learn TensorFlow and deep learning, without a Ph.D.](https://cloud.google.com/blog/big-data/2017/01/learn-tensorflow-and-deep-learning-without-a-phd) by Martin Görner
* [TensorFlow Tutorial and Examples for beginners](https://github.com/aymericdamien/TensorFlow-Examples/) by Aymeric Damien (with Python 2.7)
* [Simple tutorials using Google's TensorFlow Framework](https://github.com/nlintz/TensorFlow-Tutorials) by Nathan Lintz

In any case, [TensorBoard](https://www.tensorflow.org/get_started/summaries_and_tensorboard) makes it easy to keep track of the training process. It can also be [used with Keras, via callbacks](http://stackoverflow.com/questions/42112260/how-do-i-use-the-tensorboard-callback-of-keras).


### Other

[Theano](http://deeplearning.net/software/theano/) is similar to TensorFlow, but a bit older and harder to start.
For example, you need to manually write updates of variables. Typical neural network layers are not included, so one often uses libraries such as [Lasagne](https://lasagne.readthedocs.io/). If you're looking for a place to start, I like this introduction:

* [Theano Tutorial](http://www.marekrei.com/blog/theano-tutorial/) by Marek Rei

At the same time, if you see some nice code in Torch or PyTorch, don't be afraid to install and run it!

**EDIT** (July 2017): If you want a low-level framework, [PyTorch](http://pytorch.org/) may be the best way to start.
It combines relatively brief and readable code (almost like Keras) but at the same time gives low-level access to all features (actually, more than TensorFlow). Start here:

* [PyTorch - Tutorials](http://pytorch.org/tutorials/)
* [A repository showcasing examples of using PyTorch](https://github.com/pytorch/examples)

**EDIT** (June 2018): In [Keras or PyTorch as your first deep learning framework](https://deepsense.ai/keras-or-pytorch/) I discuss pros and cons of starting learning deep learning with each of them.
 

## Datasets

Every machine learning problem needs data. You cannot just tell it *"detect if there is a cat in this picture"* and expect the computer to tell you the answer. You need to *show* many instances of cats, and pictures not containing cats, and (hopefully) it will learn to generalize it to other cases.
So, you need some data to start. And it is not a drawback of machine learning or just deep learning - it is a fundamental property of any learning!

Before you dive into uncharted waters, it is good to take a look at some [popular datasets](https://www.kaggle.com/benhamner/d/benhamner/nips-papers/popular-datasets-over-time/code). The key part about them is that they are... popular. It means that you can find a lot of examples what works.
And have a guarantee that these problems can be solved with neural networks.

### MNIST

> Many good ideas will not work well on MNIST (e.g. batch norm). Inversely many bad ideas may work on MNIST and no[t] transfer to real [computer vision]. - [François Chollet's tweet](https://twitter.com/fchollet/status/852594987527045120)

Still, I recommend starting with the [MNIST digit recognition dataset](http://yann.lecun.com/exdb/mnist/) (60k grayscale 28x28 images), included in [keras.datasets](https://keras.io/datasets/). Not necessary to master it, but just to get a sense that it works at all (or to test the basics of Keras on your local machine).

### notMNIST

> Indeed, I once even proposed that the toughest challenge facing AI workers is to answer the question: "What are the letters 'A' and 'I'? - [Douglas R. Hofstadter](https://web.stanford.edu/group/SHR/4-2/text/hofstadter.html) (1995)

A more interesting dataset, and harder for classical machine learning algorithms, is [notMNIST](http://yaroslavvb.blogspot.com/2011/09/notmnist-dataset.html) (letters A-J from strange fonts). If you want to start with it, here is my [code for notMNIST loading and logistic regression in Keras](https://github.com/stared/keras-mini-examples/blob/master/notMNIST_starter.ipynb).

### CIFAR

If you want to play with image recognition, there is [CIFAR dataset](https://www.cs.toronto.edu/~kriz/cifar.html), a dataset of 32x32 photos (also in [keras.datasets](https://keras.io/datasets/)). It comes in two versions: 10 simple classes (including cats, dogs, frogs and airplanes ) and 100 harder and more nuanced classes (including beaver, dolphin, otter, seal and whale). I strongly suggest [starting with CIFAR-10](https://github.com/stared/keras-mini-examples/blob/master/cifar10_starter.ipynb), the simpler version.
Beware, [more complicated networks may take quite some time](https://github.com/stared/keras-mini-examples/blob/master/cifar10_official_example.ipynb) (~12h on CPU my 7 year old Macbook Pro).

**EDIT** (Nov 2017): If you are interested in practical exercises, I wrote [Starting deep learning hands-on: image classification on CIFAR-10](https://blog.deepsense.ai/deep-learning-hands-on-image-classification/).


### More

Deep learning requires a lot of data. If you want to train your network from scratch, it may require as many as ~10k images even if low-resolution (32x32).
Especially if data is scarce, there is no guarantee that a network will learn anything. So, what are the ways to go?

* use really low res (if your eye can see it, no need to use higher resolution)
* get a lot of data (for images like 256x256 it may be: millions of instances)
* re-train a network that already saw a lot
* generate much more data (with rotations, shifts, distortions)

Often, it's a combination of everything mentioned here.

**EDIT** (May 2018): Were to look for suitable datasets? [Kaggle Datasets](https://www.kaggle.com/datasets) is a place to start (along with some [Kaggle Competitions](https://www.kaggle.com/competitions)).

## Standing on the shoulders of giants

Creating a new neural network has a lot in common with cooking - there are typical ingredients (layers) and recipes (popular network architectures).
The most important cooking contest is [ImageNet Large Scale Visual Recognition Challenge](http://image-net.org/challenges/LSVRC/), with recognition of hundreds of classes from half a million dataset of photos.
Look at these [Neural Network Architectures](https://culurciello.github.io/tech/2016/06/04/nets.html), typically using 224x224x3 input (chart by Eugenio Culurciello):

![Deep Learning Architectures - a scatter plot of network sizes, performances and ops per run](/imgs/2017-04-30-learning-deep-learning/deep_learning_architectures_culurciello.png)

Circle size represents the number of parameters (a lot!). It doesn't mention [SqueezeNet](https://gab41.lab41.org/lab41-reading-group-squeezenet-9b9d1d754c75) though, an architecture vastly reducing the number of parameters (e.g. 50x fewer).

A few key networks for image classification can be readily loaded from the [keras.applications](https://keras.io/applications/) module: Xception, VGG16, VGG19, ResNet50, InceptionV3. Some others are not as plug & play, but still easy to find online - yes, there is [SqueezeNet in Keras](https://github.com/rcmalli/keras-squeezenet).
These networks serve two purposes:

* they give insight into useful building blocks and architectures
* they are great candidates for retraining (so-called [transfer learning](http://cs231n.github.io/transfer-learning/)), when using architecture along with pre-trained weights)

Some other important network architectures for images:

* [U-Net: Convolutional Networks for Biomedical Image Segmentation](https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/)
  * [Retina blood vessel segmentation with a convolution neural network](https://github.com/orobix/retina-unet) - Keras implementation
  * [Deep Learning Tutorial for Kaggle Ultrasound Nerve Segmentation competition, using Keras](https://github.com/jocicmarko/ultrasound-nerve-segmentation)
* [A Neural Algorithm of Artistic Style](https://arxiv.org/abs/1508.06576)
  * [Neural Style Transfer & Neural Doodles implemented in Keras](https://github.com/titu1994/Neural-Style-Transfer) by Somshubra Majumdar
* [A Brief History of CNNs in Image Segmentation: From R-CNN to Mask R-CNN](https://blog.athelas.com/a-brief-history-of-cnns-in-image-segmentation-from-r-cnn-to-mask-r-cnn-34ea83205de4) by Dhruv Parthasarathy

Another set of insights:

* [The Neural Network Zoo](http://www.asimovinstitute.org/neural-network-zoo/) by Fjodor van Veen
* [How to train your Deep Neural Network](http://rishy.github.io/ml/2017/01/05/how-to-train-your-dnn/) - how many layers, parameters, etc


## Infrastructure

For very small problems (e.g. MNIST, notMNIST), you can use your personal computer - even if it is a laptop and computations are on CPU.

For small problems (e.g. CIFAR, the unreasonable RNN), you might be still able to use a PC, but it requires much more patience and trade-offs.

For medium and larger problems, essentially the only way to go is to use a machine with a strong graphic card (GPU). For example, it took us 2 days to train a model for satellite image processing for a Kaggle competition, see our:

* [Deep learning for satellite imagery via image segmentation](https://blog.deepsense.ai/deep-learning-for-satellite-imagery-via-image-segmentation/) by Arkadiusz Nowaczyński

On a strong CPU it would have taken weeks, see:

* [Benchmarks for popular convolutional neural network models](https://github.com/jcjohnson/cnn-benchmarks) by Justin Johnson

The easiest, and the cheapest, way to use a strong GPU is to rent a remote machine on a per-hour basis. You can use Amazon (it is not only a bookstore!), here are some guides:

* [Keras with GPU on Amazon EC2 – a step-by-step instruction](https://medium.com/@mateuszsieniawski/keras-with-gpu-on-amazon-ec2-a-step-by-step-instruction-4f90364e49ac) by Mateusz Sieniawski, my mentee
* [Running Jupyter notebooks on GPU on AWS: a starter guide](https://blog.keras.io/running-jupyter-notebooks-on-gpu-on-aws-a-starter-guide.html) by Francois Chollet

**EDIT** (Dec 2017): For a hassle-free GPU support for deep learning I recommend [Neptune: Machine Learning Lab](https://neptune.ml/).


## Further learning

I encourage you to interact with code.
For example, notMNIST or CIFAR-10 can be great starting points.
Sometimes the best start is to start with someone's else code and run it, then see what happens when you modify parameters.

For learning how it works, this one is a masterpiece:

* [CS231n: Convolutional Neural Networks for Visual Recognition](http://cs231n.github.io/) by Andrej Karpathy and the [lecture videos](https://www.youtube.com/playlist?list=PLkt2uSq6rBVctENoVBg1TpCC7OQi31AlC)

When it comes to books, there is a wonderful one, starting from introduction to mathematics and machine learning learning context (it even covers [log-loss and entropy](http://www.deeplearningbook.org/contents/prob.html) in a way I like!):

* [Deep Learning, An MIT Press book](http://www.deeplearningbook.org/) by Ian Goodfellow, Yoshua Bengio and Aaron Courville

Alternatively, you can use (it may be good for an introduction with interactive materials, but I've found the style a bit long-winded):

* [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com/) by Michael Nielsen

**EDIT** (Dec 2017): For a very practical introduction to deep learning with Keras, I recommend [Deep Learning with Python](https://www.manning.com/books/deep-learning-with-python) by François Chollet.


### Other materials

There are many applications of deep learning (it's not only image recognition!).
I collected some introductory materials to cover its various aspects (beware: they are of various difficulty).
Don't try to read them all - I list them for *inspiration*, not *intimidation*!

* General
  * [The Unreasonable Effectiveness of Recurrent Neural Networks](http://karpathy.github.io/2015/05/21/rnn-effectiveness/) by Andrej Karpathy
  * [How convolutional neural networks see the world - Keras Blog](https://blog.keras.io/how-convolutional-neural-networks-see-the-world.html)
  * [What convolutional neural networks look at when they see nudity – Clarifai Blog](http://blog.clarifai.com/what-convolutional-neural-networks-see-at-when-they-see-nudity/) (NSFW)
  * [Convolutional neural networks for artistic style transfer](https://harishnarayanan.org/writing/artistic-style-transfer/) by Harish Nrayanan
  * [Dreams, Drugs and ConvNets](https://speakerdeck.com/pmigdal/dreams-drugs-and-convnets) - my slides (NSFW); I am considering turning it into a longer post on machine learning vs human learning, based on common mistakes
* Technical
  * [Yes you should understand backprop](https://medium.com/@karpathy/yes-you-should-understand-backprop-e2f06eab496b) by Andrej Karpathy
  * [Transfer Learning using Keras](https://medium.com/towards-data-science/transfer-learning-using-keras-d804b2e04ef8) by Prakash Vanapalli
  * [Generative Adversarial Networks (GANs) in 50 lines of code (PyTorch)](https://medium.com/@devnag/generative-adversarial-networks-gans-in-50-lines-of-code-pytorch-e81b79659e3f)
  * [Minimal and Clean Reinforcement Learning Examples](https://github.com/rlcode/reinforcement-learning)
  * [An overview of gradient descent optimization algorithms](http://sebastianruder.com/optimizing-gradient-descent/) by Sebastian Ruder
  * [Picking an optimizer for Style Transfer](https://medium.com/slavv/picking-an-optimizer-for-style-transfer-86e7b8cba84b) by Slav Ivanov
  * [Building Autoencoders in Keras](https://blog.keras.io/building-autoencoders-in-keras.html) by Francois Chollet
  * [Understanding LSTM Networks](http://colah.github.io/posts/2015-08-Understanding-LSTMs/) by Chris Olah
  * [Recurrent Neural Networks & LSTMs](https://ayearofai.com/rohan-lenny-3-recurrent-neural-networks-10300100899b) by Rohan Kapur
  * [Oxford Deep NLP 2017 course](https://github.com/oxford-cs-deepnlp-2017/lectures)
* List of resources
  * [How to Start Learning Deep Learning](http://ofir.io/How-to-Start-Learning-Deep-Learning/) by Ofir Press
  * [A Guide to Deep Learning by YN^2](http://yerevann.com/a-guide-to-deep-learning/)
* Staying up-to-date:
  * [r/MachineLearning](https://www.reddit.com/r/MachineLearning/) Reddit channel covering most of new stuff
  * [distill.pub](http://distill.pub/) - an interactive, visual, open-access journal for machine learning research, with expository articles
  * my links at [pinboard.in/u:pmigdal/t:deep-learning](https://pinboard.in/u:pmigdal/t:deep-learning) - though, just saving, not an automatic recommendation
  * [@fastml_extra](https://twitter.com/fastml_extra) Twitter channel
  * [GitXiv](http://www.gitxiv.com/) for papers with code
  * don't be afraid to read academic papers; some are well-written and insightful (if you own Kindle or another e-reader, I recommend [Dontprint](http://dontprint.net/))
* Data (usually from challenges)

## Thanks

I would like to thank [Kasia Kulma](https://kkulma.github.io/), [Martina Pugliese](https://martinapugliese.github.io/), Paweł Subko, [Monika Pawłowska](http://greenelephant.pl/shiny/rowery/) and [Łukasz Kidziński](http://kidzinski.com/) for helpful feedback on the content and to [Sarah Martin](http://goodsexlifestyle.com/) for polishing my English.

If you recommend a source that helped you with your adventure with deep learning - feel invited to contact me! ([@pmigdal](https://twitter.com/pmigdal) for short links, an email for longer remarks.)

The [deep learning meme](http://knowyourmeme.com/photos/1244486-what-people-think-i-do-what-i-really-do) is not mine - I just rewrote it from Theano to Keras (with TensorFlow backend).


[^deepsense]: [NOAA Right Whale Recognition, Winners' Interview](http://blog.kaggle.com/2016/01/29/noaa-right-whale-recognition-winners-interview-1st-place-deepsense-io/) (1st place, Jan 2016), and a fresh one: [Deep learning for satellite imagery via image segmentation](https://blog.deepsense.ai/deep-learning-for-satellite-imagery-via-image-segmentation/) (4th place, Apr 2017).
[^webcomics]: It made a few episodes of webcomics obsolete: [xkcd: Tasks](https://xkcd.com/1425/) (totally, by [Park or Bird?](https://laughingsquid.com/park-or-bird-a-national-park-and-bird-identifying-app-inspired-by-an-xkcd-comic/)), [xkcd: Game AI](https://xkcd.com/1002/) (partially, by [AlphaGo](https://deepmind.com/research/alphago/)), [PHD Comics: If TV Science was more like REAL Science](http://phdcomics.com/comics.php?n=1156) (not exactly, but still it's cool, by [LapSRN](http://vllab1.ucmerced.edu/~wlai24/LapSRN/)).
[^trypophobia]: This January during a 5-day workshop 6 high-school students participated in a rather NSFL project - constructing a neural network for detecting trypophobia triggers, see [Trypophobia Image Detector - Browser Plugin using Deep Learning](https://github.com/cytadela8/trypophobia) GitHub repository.
[^unreasonable]: The title alludes to [The Unreasonable Effectiveness of Mathematics in the Natural Sciences](http://www.dartmouth.edu/~matc/MathDrama/reading/Wigner.html) by Eugene Wigner (1960), one of my favourite texts in philosophy of science. Along with [More is Different](https://www.physics.ohio-state.edu/~jay/880/moreisdifferent.pdf) by PW Andreson (1972) and [Genesis and development of a scientific fact](https://www.amazon.com/Genesis-Development-Scientific-Ludwik-Fleck/dp/0226253252/) ([pdf here](http://www.evolocus.com/Textbooks/Fleck1979.pdf)) by Ludwik Fleck (1935).
[^quantum]: If your background is in quantum information, the only thing you need to change is ℂ to ℝ. Just expect less tensor structure, but more convolutions.
[^theano]: Is it only me, or does *Theano tensor dimension order* sound like some secret convent? Before you start searching how to join it: it is about the shape of multi-dimensional arrays: `(samples, channels, x, y)` rather than TensorFlow's `(samples, x, y, channels)`.
