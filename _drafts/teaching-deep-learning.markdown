---
layout: "post"
title: "Teaching Deep Learning"
date: "2017-03-04 15:00"
---

I teach deep learning both for living (as a [deepsense.io instructor](http://workshops.deepsense.io/)) and for fun/mission [Polish Children's Fund](http://crastina.se/gifted-children-in-poland-by-piotr-migdal/) (this Jan we had a NSFL project).

In this post I don't intent to teach neural networks, but to point to useful resources.

To start your you need basics of Python syntax and very simple mathematics.
I suggest starting with [Keras](https://keras.io/), a high-level neural network library in Python.

* [Neural Networks Demystified](http://lumiverse.io/series/neural-networks-demystified) - smooth introduction


## Examples

Before you start learning, let's play in your browser:

* [TensorFlow Playground](http://playground.tensorflow.org/) for point separation
* [ConvNetJS](http://cs.stanford.edu/people/karpathy/convnetjs/) for digit and image recognition
*

## Mathematics

Deep learning (that is - neural networks with many layers) use very simple

* vectors, matrices, multi-dimensional arrays
* addition, multiplication,
* [convolutions](http://setosa.io/ev/image-kernels/) to extract and process local patterns,
* activation functions: [sigmoid](https://en.wikipedia.org/wiki/Sigmoid_function), [tanh](https://www.wolframalpha.com/input/?i=tanh[x]), [ReLU](https://en.wikipedia.org/wiki/Rectifier_%28neural_networks%29) to add non-linearity,
* [softmax](https://en.wikipedia.org/wiki/Softmax_function) to convert vectors into probabilities,
* [log-loss (cross-entropy)](http://datascience.stackexchange.com/questions/9302/the-cross-entropy-error-function-in-neural-networks) to penalize wrong guesses in a smart way.

If your background is in physics, mathematics, statistics or signal processing - most likely you already know more than enough.

If you last contact with mathematics was in high-school, don't worry. This mathematics is simple to a point that a convolutional neural network for digit recognition can be implemented in a spreadsheet (with no macros):

* [Deep Spreadsheets with ExcelNet](http://www.deepexcel.net/)


## Frameworks

The most popular deep learning frameworks use, or at least - support, Python.
Some of [TensorFlow](https://www.tensorflow.org/), [Theano](http://deeplearning.net/software/theano/), [Torch](http://torch.ch/).

Unlike

If you like philosophy of Python (brevity, readability, one preferred way to do things), Keras is for you.


Neural networks happen to be


* [Deep Learning with Keras - Tutorial @ EuroScipy 2016](https://github.com/leriomaggio/deep-learning-keras-tensorflow)
* [TensorFlow Tutorials](https://www.tensorflow.org/versions/master/tutorials/index.html)

https://gist.github.com/stared/70daf8e0334abf6e7527259e7221f568
and in a week were able to




## Dataset

I recommend starting with [MNIST digit recognition dataset](http://yann.lecun.com/exdb/mnist/) (60k grayscale 28x28 images).

A more interesting dataset, and harder for classical machine learning algorithms, is [notMNIST](http://yaroslavvb.blogspot.com/2011/09/notmnist-dataset.html) (letters A-J from strange fonts). If you want to start with in, here is my [gist for notMNIST loading and logistic regression in Keras](https://gist.github.com/stared/70daf8e0334abf6e7527259e7221f568).


## Standing at the shoulders of giants


Creating a new neural network has a lot in common with cooking -


If tou

* [How to train your Deep Neural Network](http://rishy.github.io/ml/2017/01/05/how-to-train-your-dnn/) - how many layers, parameters, etc

## Machine Learning context




## Infrastructure

For small problems, you can use your personal computer - even if it is a laptop and computations are on CPU.

For medium problems, you might be still able to use PC, but

* [Keras with GPU on Amazon EC2 – a step-by-step instruction](https://medium.com/@mateuszsieniawski/keras-with-gpu-on-amazon-ec2-a-step-by-step-instruction-4f90364e49ac) by Mateusz Sieniawski, my mentee

## Links



* [Image Kernels - Explained Visually](http://setosa.io/ev/image-kernels/) - on 2d convolutions
* [Building a simple neural-network with Keras](https://github.com/wxs/keras-mnist-tutorial/blob/master/MNIST%20in%20Keras.ipynb)



* [Ian Goodfellow and Yoshua Bengio and Aaron Courville, Deep Learning, An MIT Press book](http://www.deeplearningbook.org/) ([and just PDF](https://github.com/HFTrader/DeepLearningBook))

* [CS231n: Convolutional Neural Networks for Visual Recognition by Andrej Karpathy](http://cs231n.github.io/) and [its videos](https://www.youtube.com/playlist?list=PLLvH2FwAQhnpj1WEB-jHmPuUeQ8mX-XXG)




* [A Guide to Deep Learning by YN^2](http://yerevann.com/a-guide-to-deep-learning/)

* [Handwritten Digit Recognition using Convolutional Neural Networks in Python with Keras](http://machinelearningmastery.com/handwritten-digit-recognition-using-convolutional-neural-networks-python-keras/)
* https://elitedatascience.com/keras-tutorial-deep-learning-in-python ?

https://pinboard.in/search/u:pmigdal?query=deep-learning



### Examples

* [Colorful Image Colorization](http://richzhang.github.io/colorization/)

### Keras add-ons

* [keras-tqdm](https://github.com/bstriner/keras-tqdm) - nicer progress bars
* [keras.js](https://transcranial.github.io/keras-js/) - convert Keras models to JavaScript, runnable in a browser (simplest GPU support ever!)
* [quiver](https://github.com/jakebian/quiver) - interactive ConvNet features visualization for Keras
* [ASCII summary for sequential models](https://github.com/stared/keras-sequential-ascii) - I started developing :)

## Further reading


* [The Unreasonable Effectiveness of Recurrent Neural Networks](http://karpathy.github.io/2015/05/21/rnn-effectiveness/) by Andrej Karpathy
* [How convolutional neural networks see the world - Keras Blog](https://blog.keras.io/how-convolutional-neural-networks-see-the-world.html)

* [Generative Adversarial Networks (GANs) in 50 lines of code (PyTorch)](https://medium.com/@devnag/generative-adversarial-networks-gans-in-50-lines-of-code-pytorch-e81b79659e3f#.oa2ljanet)

[r/MachineLearning](https://www.reddit.com/r/MachineLearning/) for news
