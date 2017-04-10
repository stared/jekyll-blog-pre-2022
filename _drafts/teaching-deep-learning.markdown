---
layout: "post"
title: "Teaching Deep Learning"
date: "2017-03-04 15:00"
---

I teach deep learning both for living (as the main [deepsense.io instructor](http://workshops.deepsense.io/), with [great co-workers](http://blog.kaggle.com/2016/01/29/noaa-right-whale-recognition-winners-interview-1st-place-deepsense-io/)) and as part of my volunteering to [Polish Children's Fund](http://crastina.se/gifted-children-in-poland-by-piotr-migdal/) - with a 5-day project[^trypophobia].

Whether you want to start learning deep learning for you career, or just want to have a nice adventure (and get insight into machines before they take over), this post is for you!
I don't intent to teach neural networks, but to provide an overview and point to didactically useful resources.

Don't be afraid of neural networks - it is easy to start. My biggest regret is delaying

To start your you need basics of Python syntax and very simple mathematics.
I suggest starting with [Keras](https://keras.io/), a high-level neural network library in Python. If you are new to Python, take a look at [my introduction to data science](http://p.migdal.pl/2016/03/15/data-science-intro-for-math-phys-background.html).


## Before we start



Also, it makes some webcomic strips obsolete:


* [A visual introduction to machine learning](http://www.r2d3.us/visual-intro-to-machine-learning-part-1/)
* [Neural Networks Demystified](http://lumiverse.io/series/neural-networks-demystified) - smooth introduction


## Examples

Do I need some SkyNet to run it? Actually not - it's a piece of software, as any other. And you can play with in even in your browser:

* [TensorFlow Playground](http://playground.tensorflow.org/) for point separation, with a visual interface
* [ConvNetJS](http://cs.stanford.edu/people/karpathy/convnetjs/) for digit and image recognition
* [Keras.js Demo](https://transcranial.github.io/keras-js/) - to visualize and use real networks in your browser (e.g. ResNet-50)


## Mathematics

Deep learning (that is - neural networks with many layers) use very simple

XXX this with number of weights

* vectors, matrices, multi-dimensional arrays,
* addition, multiplication,
* [convolutions](http://setosa.io/ev/image-kernels/) to extract and process local patterns,
* activation functions: [sigmoid](https://en.wikipedia.org/wiki/Sigmoid_function), [tanh](https://www.wolframalpha.com/input/?i=tanh[x]), [ReLU](https://en.wikipedia.org/wiki/Rectifier_%28neural_networks%29) to add non-linearity,
* [softmax](https://en.wikipedia.org/wiki/Softmax_function) to convert vectors into probabilities,
* [log-loss (cross-entropy)](http://datascience.stackexchange.com/questions/9302/the-cross-entropy-error-function-in-neural-networks) to penalize wrong guesses in a smart way,
* gradients and chain-rule ([backpropagation](http://cs231n.github.io/optimization-2/)) for minimizing error.

If your background is in physics, mathematics, statistics or signal processing - most likely you already know more than enough to start.

If you last contact with mathematics was in high-school, don't worry. This mathematics is simple to a point that a convolutional neural network for digit recognition can be implemented in a spreadsheet (with no macros):

* [Deep Spreadsheets with ExcelNet](http://www.deepexcel.net/)


* [Immersive Linear Algebra](http://immersivemath.com/ila/index.html) by J. Ström, K. Åström, and T. Akenine-Möller - a linear algebra book with fully interactive figures
*  Part I: Applied Math and Machine Learning Basics: 2 Linear Algebra from [Deep Learning](http://www.deeplearningbook.org/)

## Frameworks

The most popular deep learning frameworks use, or at least - support, Python.
Some of [TensorFlow](https://www.tensorflow.org/), [Theano](http://deeplearning.net/software/theano/), [Torch](http://torch.ch/).


Keras

If you like philosophy of Python (brevity, readability, one preferred way to do things), Keras is for you. Also, if you want to have a propaganda picture,


Neural networks happen to be


* [Deep Learning with Keras - Tutorial @ EuroScipy 2016](https://github.com/leriomaggio/deep-learning-keras-tensorflow)
* [TensorFlow Tutorials](https://www.tensorflow.org/versions/master/tutorials/index.html)

https://gist.github.com/stared/70daf8e0334abf6e7527259e7221f568
and in a week were able to




## Datasets

I recommend starting with [MNIST digit recognition dataset](http://yann.lecun.com/exdb/mnist/) (60k grayscale 28x28 images), included in [keras.datasets](https://keras.io/datasets/).

> Indeed, I once even proposed that the toughest challenge facing AI workers is to answer the question: "What are the letters 'A' and 'I'? - [Douglas R. Hofstadter](https://web.stanford.edu/group/SHR/4-2/text/hofstadter.html) (1995)

A more interesting dataset, and harder for classical machine learning algorithms, is [notMNIST](http://yaroslavvb.blogspot.com/2011/09/notmnist-dataset.html) (letters A-J from strange fonts). If you want to start with in, here is my [gist for notMNIST loading and logistic regression in Keras](https://gist.github.com/stared/70daf8e0334abf6e7527259e7221f568).

A more advanced once, still at verge of using CPU is [CIFAR-10 dataset](https://www.cs.toronto.edu/~kriz/cifar.html) (also in [keras.datasets](https://keras.io/datasets/)).


## Standing at the shoulders of giants

Creating a new neural network has a lot in common with cooking - there are typical ingredients and recipes.
The most important cooking contest is ImageNet.


For example, for image segmentation


If tou

* [keras.applications](https://keras.io/applications/): Xception, VGG16, VGG19, ResNet50, InceptionV3

> Keras Applications are deep learning models that are made available alongside pre-trained weights. These models can be used for prediction, feature extraction, and fine-tuning.

* [Which paper provides the best results on standard dataset X ?](http://rodrigob.github.io/are_we_there_yet/build/) - a ranking of methods for MNIST, CIFAR and a few other datasets

* [How to train your Deep Neural Network](http://rishy.github.io/ml/2017/01/05/how-to-train-your-dnn/) - how many layers, parameters, etc


## Infrastructure

For small problems, you can use your personal computer - even if it is a laptop and computations are on CPU.

For medium problems, you might be still able to use PC, but it requires much more patience and trade-offs.

* [Keras with GPU on Amazon EC2 – a step-by-step instruction](https://medium.com/@mateuszsieniawski/keras-with-gpu-on-amazon-ec2-a-step-by-step-instruction-4f90364e49ac) by Mateusz Sieniawski, my mentee


## Links

* [Linear algebra cheat sheet for deep learning](https://medium.com/towards-data-science/linear-algebra-cheat-sheet-for-deep-learning-cd67aba4526c) by Brendan Fortuner
* [Visualizing parts of Convolutional Neural Networks using Keras and Cats](https://hackernoon.com/visualizing-parts-of-convolutional-neural-networks-using-keras-and-cats-5cc01b214e59) by Erik Reppel
* [Benchmarks for popular convolutional neural network models](https://github.com/jcjohnson/cnn-benchmarks) by Justin Johnson
* [Image Kernels - Explained Visually](http://setosa.io/ev/image-kernels/) - on 2d convolutions
* [Building a simple neural-network with Keras](https://github.com/wxs/keras-mnist-tutorial/blob/master/MNIST%20in%20Keras.ipynb)
* [Learning curves of linear (logistic regression) vs non-linear models (random forest and deep learning)](https://github.com/szilard/benchm-ml/tree/master/x1-data-higgs) by Szilard Pafka
* https://devblogs.nvidia.com/parallelforall/mocha-jl-deep-learning-julia/ - progress ()
* size/performance:
  * https://github.com/mrgloom/kaggle-dogs-vs-cats-solution
  * [Neural Network Architectures](https://culurciello.github.io/tech/2016/06/04/nets.html) by
Eugenio Culurciello
* [Lab41 Reading Group: SqueezeNet](https://gab41.lab41.org/lab41-reading-group-squeezenet-9b9d1d754c75)
* Further applications
  * style transfer
  * segmentation
  * autoencoders
* https://xkcd.com/1425/
* http://www.economist.com/news/business/21695908-silicon-valley-fights-talent-universities-struggle-hold-their

* [Ian Goodfellow and Yoshua Bengio and Aaron Courville, Deep Learning, An MIT Press book](http://www.deeplearningbook.org/)

* [CS231n: Convolutional Neural Networks for Visual Recognition by Andrej Karpathy](http://cs231n.github.io/) and [its videos](https://www.youtube.com/playlist?list=PLLvH2FwAQhnpj1WEB-jHmPuUeQ8mX-XXG)




* [A Guide to Deep Learning by YN^2](http://yerevann.com/a-guide-to-deep-learning/)
* [How to Start Learning Deep Learning](http://ofir.io/How-to-Start-Learning-Deep-Learning/)

* [Handwritten Digit Recognition using Convolutional Neural Networks in Python with Keras](http://machinelearningmastery.com/handwritten-digit-recognition-using-convolutional-neural-networks-python-keras/)
* https://elitedatascience.com/keras-tutorial-deep-learning-in-python ?

https://pinboard.in/search/u:pmigdal?query=deep-learning




### Keras add-ons

* [keras-tqdm](https://github.com/bstriner/keras-tqdm) - nicer progress bars
* [keras.js](https://transcranial.github.io/keras-js/) - convert Keras models to JavaScript, runnable in a browser (simplest GPU support ever!)
* [quiver](https://github.com/jakebian/quiver) - interactive ConvNet features visualization for Keras
* [ASCII summary for sequential models](https://github.com/stared/keras-sequential-ascii) - I started developing :)


## Common misconceptions

### Better than other ML algorithms

### Kernels need to be set manually

### Why log-loss?

> If you're certain, you're certainly wrong, because nothing deserves certainty. — Bertrand Russell, Bertrand Russell Speaks His Mind (1960), p. 14.

### Is network going to solve tasks at super-human level?





## Further reading

* General
  * [The Unreasonable Effectiveness of Recurrent Neural Networks](http://karpathy.github.io/2015/05/21/rnn-effectiveness/) by Andrej Karpathy
  * [How convolutional neural networks see the world - Keras Blog](https://blog.keras.io/how-convolutional-neural-networks-see-the-world.html)
  * [What convolutional neural networks look at when they see nudity – Clarifai Blog](http://blog.clarifai.com/what-convolutional-neural-networks-see-at-when-they-see-nudity/) (NSFW)
  * [Convolutional neural networks for artistic style transfer](https://harishnarayanan.org/writing/artistic-style-transfer/) by Harish Nrayanan
  * [Dreams, Drugs and ConvNets](https://speakerdeck.com/pmigdal/dreams-drugs-and-convnets) - my slides (NSFW)
* Technical
  * [Yes you should understand backprop](https://medium.com/@karpathy/yes-you-should-understand-backprop-e2f06eab496b) by Andrej Karpathy
  * [Generative Adversarial Networks (GANs) in 50 lines of code (PyTorch)](https://medium.com/@devnag/generative-adversarial-networks-gans-in-50-lines-of-code-pytorch-e81b79659e3f#.oa2ljanet)
* Staying up-to-data:
  * [r/MachineLearning](https://www.reddit.com/r/MachineLearning/) for news
  * [distill.pub](http://distill.pub/) - an interactive, visual, open-access journal for machine learning research, with expository articles

[Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com/) by Micheal Nielsen (yes, author of the Green Book)


...or if you like to use neural networks with less code than Keras, the only option is [pigeons](https://www.youtube.com/watch?v=flzGjnJLyS0). Yes, seriously: [Pigeons spot cancer as well as human experts](http://www.sciencemag.org/news/2015/11/pigeons-spot-cancer-well-human-experts).

[^trypophobia]: This January during a 5-day workshop 6 high-school students participated in a rather NSFL project - constructing a neural network for detecting trypophobia triggers, see e.g. [grzegorz225/trypophobia-detector](https://github.com/grzegorz225/trypophobia-detector).  
