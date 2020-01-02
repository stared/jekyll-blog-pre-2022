---
layout: post
title: "Simple diagrams of convoluted neural networks"
date: '2018-09-15 12:00 +0100'
author: Piotr Migdał
tags:
  - deep-learning
  - data-viz
description: >-
  A good diagram is worth a thousand equations - let's create more of these!``
image: https://cdn-images-1.medium.com/max/2032/1*Z7X3ypVDlNGlXeVcJqICbg.png
external:
  title: "Simple diagrams of convoluted neural networks"
  href: https://medium.com/inbrowserai/simple-diagrams-of-convoluted-neural-networks-39c097d2925b
  status: originally published on Medium
  date: 2018-09-15 12:00 +0100
---

> A good diagram is worth a thousand equations — let’s create more of these!

Neural networks are complicated, multidimensional, nonlinear array operations. How can we present a deep learning model architecture in a way that shows key features, while avoiding being too complex or repetitive? How can we present them in a way that is clear, didactic and insightful? (Bonus points if it is beautiful as well!). Right now, there is no standard for plots — neither for research nor didactic projects. Let me take you through an overview of tools and techniques for visualizing whole networks and particular blocks!

# The baseline

AlexNet was a breakthrough architecture, setting convolutional networks (CNNs) as the leading machine learning algorithm for large image classification. The paper introducing AlexNet presents an excellent diagram — but there is something missing…

![Alex Krizhevsky, Ilya Sutskever, Geoffrey E Hinton, [ImageNet Classification with Deep Convolutional Neural Networks](http://www.cs.toronto.edu/~fritz/absps/imagenet.pdf) (2012), the original crop](https://cdn-images-1.medium.com/max/1964/1*nrNJXwfudc36wWw5Jbmfsg.png)

It does not require an eagle eye to spot it — the top part is accidentally cropped. And so it runs through all subsequent slide decks, references, etc. In my opinion, it is a symptom that, in deep learning research, visualization is a mere afterthought (with a few notable exceptions, including the [Distill journal](https://distill.pub/about/)).

One may argue that developing new algorithms and tuning hyperparameters are Real Science/Engineering™, while visual presentation is the domain of art and has no value. I couldn’t disagree more!

Sure, for computers running a program it does not matter if your code is without indentations and has obscurely named variables. But for people — it does. Academic papers are not a means of discovery — they are a means of communication.

Take another complex idea — quantum field theory. If you want to show the electron-positron annihilation process, creating a muon-antimuon pair, here’s the[ Feynman diagram](https://en.wikipedia.org/wiki/Feynman_diagram) (of the first-order term):

![Mark Thomson, [Particle Physics, Handout 4 : Electron-Positron Annihilation](https://www.hep.phy.cam.ac.uk/~thomson/partIIIparticles/handouts/Handout_4_2011.pdf)](https://cdn-images-1.medium.com/max/738/1*B_7b-pRXOarR4abf3_q4NQ.png)

Cute, isn’t it? But it is not an artistic impression. It is a graphical representation of the scattering amplitude, with each line being a propagator and each vertex — a point interaction.[ It directly translates to](https://www.southampton.ac.uk/~doug/ft1/ft115.pdf):

![](https://cdn-images-1.medium.com/max/1150/1*lxyoi02syfvOihIU1lJ-bQ.png)

I may be biased towards _“making things simpler”_ as I did with complex tensor operations in JavaScript, and visualized their results before it was cool (for[ Quantum Game with Photons](http://quantumgame.io/)). Yet, there is more to the Feynman diagrams analogy than using visual representations for formulae. In both quantum mechanics and deep learning, we do a lot of linear algebra with tensor structures. In fact, one may even use the[ Einstein summation convention in PyTorch](https://rockt.github.io/2018/04/30/einsum).

# Explaining neural network layers

Before we jump into network architectures, let’s focus on their building blocks — layers. For example, a[ Long Short-Term Memory](https://en.wikipedia.org/wiki/Long_short-term_memory) (LSTM) unit can be described with the following equation:

![](https://cdn-images-1.medium.com/max/1000/1*GFZ32jmyLR_QuBxNynqv2A.png)

Sure, it’s reasonably easy to parse these equations. At least — if you are already familiar with matrix multiplication conventions. But it is a very different thing to parse something, and to understand it. When I saw LSTM equations for the first time I could parse it, yet I had no idea what was going on.

By _“understanding”_ I don’t mean some spiritual sense of enlightenment — it may be as pleasing and intoxicating as misleading. Instead, I mean building a mental model we are able to work with (to explain, simplify, modify, predict what-if scenarios, etc). Often a graphical form may be cleaner than a verbal one:

![Chris Olah, [Understanding LSTM Networks](http://colah.github.io/posts/2015-08-Understanding-LSTMs/) (2015)](https://cdn-images-1.medium.com/max/1876/1*2BWMDwn_44nBLhTBTU1pZA.png)

[Understanding LSTM Networks](http://colah.github.io/posts/2015-08-Understanding-LSTMs/) is a wonderful blog post about LSTM cells that explains depicted operations in a step-by-step manner. It gave me a big _“Eureka!”_ moment, turning a seemingly random set of multiplications into a reasonable approach to writing (and reading!) data.

And here is an even more explicit diagram of LSTM below:

![Eli Benderski, [Minimal character-based LSTM implementation](https://eli.thegreenplace.net/2018/minimal-character-based-lstm-implementation/) (2018)](https://cdn-images-1.medium.com/max/1964/1*wGBtlv0xCJu9nBRgX4rcFw.png)

In my opinion:

> A good diagram is worth a thousand equations.

It works for almost any other blocks. We can visualize concepts such as dropout (i.e. switching-off neurons, and rendering their connections irrelevant):

![Srivastava, Hinton et al., [Dropout: A Simple Way to Prevent Neural Networks from Overfitting](http://www.cs.toronto.edu/~rsalakhu/papers/srivastava14a.pdf) (2014)](https://cdn-images-1.medium.com/max/1228/1*PghKZ1K2Lepg01EGfbtKoQ.jpeg)

While [I am not a big fan of drawing data flows upside-down](https://www.reddit.com/r/MachineLearning/comments/6j28t9/d_why_do_people_draw_neural_networks_upside_down/), this figure is very clear.

Graphical representations are useful for explaining compound blocks, composed of smaller ones (e.g. a few subsequent convolutions). Take a look at this Inception module diagram:

![Szegedy, Vanhoucke, Ioffe, Shlens, Wojna, [Rethinking the Inception Architecture for Computer Vision](https://arxiv.org/abs/1512.00567) (2015)](https://cdn-images-1.medium.com/max/870/1*VjlEF7Qe6ezY9oD-4h_deA.png)

Each visualization is different — not only in the terms of its style but what does it put an emphasis on, and what does it abstract away. What’s important? The number of layers, connections between them, convolution kernel size or activation function? Well, it depends. Abstraction means _“the process of considering something independently of its associations or attributes”_. The challenge is to decide what is important for a given communication, and what should be hidden.

For example, in this Batch Normalization diagram, the emphasis is on the backward pass:

![Frederik Kratzert, [Understanding the backward pass through Batch Normalization Layer](https://kratzert.github.io/2016/02/12/understanding-the-gradient-flow-through-the-batch-normalization-layer.html) (2016)](https://cdn-images-1.medium.com/max/2400/0*eHSZzD8H9WBuR9Ve.png)

# Data viz vs data art

You may get the impression that I argue for making deep learning papers more visually appealing. Well, it wouldn’t hurt to make charts nicer. When I work with data exploration, I often pick [nicer color schemes](http://bl.ocks.org/aaizemberg/78bd3dade9593896a59d) just to make a more pleasant experience. My main point is to turn visualizations into a more effective means of communication.

So, does nicer mean better? Not necessarily.[ The Line between Data Vis and Data Art](https://lisacharlotterost.github.io/2015/12/14/The-Line-between-Data-Vis-And-Data-Art/) by Lisa Charlotte Rost, which I found very insightful, explains the distinction.

![Lisa Charlotte Rost, [Meaning + Beauty in Data Vis and Data Art](https://lisacharlotterost.github.io/2015/12/19/Meaning-and-Beauty-in-Data-Vis/) (2015)](https://cdn-images-1.medium.com/max/1788/1*e1mu_o8ATwunBdOmtvj1IQ.png)

For example, look this stunning picture below:

![Matt Fyles (Graphcore), [Inside an AI ‘brain’ — What does machine learning look like?](https://www.graphcore.ai/posts/what-does-machine-learning-look-like) (2016)](https://cdn-images-1.medium.com/max/1700/1*eWzAOBnDsN3m1aaFMtcM9w.png)

Beautiful, isn’t it? To me, it looks alive — like a cell, with its organelle. …but hey — can we deduce anything from it? Would you even guess it’s the same AlexNet?

In another example, an animated multi-layer perceptron is focused on its aesthetic, rather than explanatory, value:

![Jesús Martínez-Blanco, [Sinapsis](http://chumo.github.io/Sinapsis/) (2016)](https://cdn-images-1.medium.com/max/1096/1*izgVEHysbzgvOIV8VR3c9A.gif)

To make it clear: data art has value on its own, as long as we don’t confuse artistic value with educational value. If you like going this route, I encourage you to use 3D animations of impulses such as[ these sparks](https://codepen.io/towc/embed/wGjXGY) or that[ colorful brain](https://codepen.io/lindell/embed/pePwzM) — for an actual ConvNet.

Sometimes the trade-off is less clear. This one, is it data viz or data art?

![GoogLeNet from Christian Szegedy et al., [Going Deeper with Convolutions](https://arxiv.org/abs/1409.4842) (2014)](https://cdn-images-1.medium.com/max/2012/1*MKtjMPlexFjSaiwJJ8ui3A.png)

I guess you said: _“data vis, obviously”_. In this case — we are in disagreement. While there is a nice color scheme, and the repetition of similar structures is visually pleasing, it is hard to implement this network solely based on this drawing. Sure, you get the gist of the architecture — i.e. the number of layers, and on the structure of blocks, but it’s not enough to reimplement the network (at least, not without a magnifying glass).

To make it clear — there is room for data art in publications. For example, in a network for detecting skin conditions, we see the diagram of Inception v3 feature-extracting layers. Here it is clear that the authors just use it, and represent it graphically, rather than explain its inner workings:

![Andrea Esteva et al., [Dermatologist-level classification of skin cancer with deep neural networks](https://cs.stanford.edu/people/esteva/nature/) (2017)](https://cdn-images-1.medium.com/max/2048/1*Sq8TC0ARvq3rs4z6xwg6rA.png)

And how would you classify this diagram, for exploring visual patterns that activate selected channels?

![Chris Olah et al., [Feature Visualization — Appendix](https://distill.pub/2017/feature-visualization/appendix/) (2017), distil.pub](https://cdn-images-1.medium.com/max/2032/1*Z7X3ypVDlNGlXeVcJqICbg.png)

I would classify the diagram below as a good example of data-viz. A trippy visualization does not make it a piece data-art. In this case, the focus is on network architecture abstraction and presenting relevant data (input images activating a given channel).

Some diagrams abstract a lot of information, giving only a very general idea of what is going on. See the [Neural Network Zoo](http://www.asimovinstitute.org/neural-network-zoo/) and [its prequel](https://www.asimovinstitute.org/neural-network-zoo-prequel-cells-layers/):

![Fjodor van Veen, [Neural Network Zoo](http://www.asimovinstitute.org/neural-network-zoo/) (2016), a fragment](https://cdn-images-1.medium.com/max/1222/1*dyuWUs3JfJihpbShcbHKzw.png)

# Explanatory architecture diagrams

We saw a few examples of layer diagrams, and pieces of data art related to neural network architectures.

Let’s go to (data) visualizations of neural network architectures. Here is the architecture of VGG16, a standard network for image classification.

![[https://blog.heuritech.com/2016/02/29/a-brief-report-of-the-heuritech-deep-learning-meetup-5/](https://blog.heuritech.com/2016/02/29/a-brief-report-of-the-heuritech-deep-learning-meetup-5/)](https://cdn-images-1.medium.com/max/1364/1*BncGa1UaQiYbYkSjLc39BA.png)

We see, step-by-step, tensor sizes and operations (marked as colors). It’s not abstract — box sizes are related to tensor shapes. Bear in mind that the thickness related to the number of channels is not to scale (well, we have 3 to 4096).

A similar approach is to show values for each channel, as in this DeepFace work:

![Yaniv Taigman, Ming Yang, Marc’Aurelio Ranzato, Lior Wolf, [DeepFace: Closing the Gap to Human-Level Performance in Face Verification](https://research.fb.com/publications/deepface-closing-the-gap-to-human-level-performance-in-face-verification/) (2014)](https://cdn-images-1.medium.com/max/2048/1*KHngh7OcKlkIQeuuUIZk7Q.png)

Such diagrams are not restricted to computer vision. Let’s see one for turning text into… colors:

![Chengwei Zhang, [How to train a Keras model to generate colors](https://heartbeat.fritz.ai/how-to-train-a-keras-model-to-generate-colors-3bc79e54971b) (2018)](https://cdn-images-1.medium.com/max/1506/1*kI5yEQPcf9X9d4j6JpwTpg.png)

Such diagrams might be useful if the goal is to show the network architecture and at the same time — give some hints on its inner workings. They seem to be especially useful for tutorials, e.g. the seminal [The Unreasonable Effectiveness of Recurrent Neural Networks](http://karpathy.github.io/2015/05/21/rnn-effectiveness/).

# Abstract architecture diagrams

However, for larger models, explanatory diagrams may be unnecessarily complex or too specific to show all possible layers within a single diagram style. So, the way to go is to use abstract diagrams. Typically, nodes denote operations, while arrows represent the tensor flow. For example, let’s look at this VGG-19 vs ResNet-34 comparison:

![Kaiming He, Xiangyu Zhang, Shaoqing Ren, Jian Sun, [Deep Residual Learning for Image Recognition](https://arxiv.org/abs/1512.03385) (2015), cropped](https://cdn-images-1.medium.com/max/1634/1*zOu3PXhdMBY6KZrDpCXdwQ.png)

We can see that there is some redundancy, as some units get reused or repeated. Since diagrams can be long (there is a reason why I cropped the one above!), it is beneficial to spot the patterns and consolidate them. Such hierarchy makes it simpler both to understand concepts and present them visually (unless we just want to create data-artsy diagrams of GoogLeNet).

For example, let’s look at this one, of Inception-ResNet-v1:

![Inception-ResNet-v1 as depicted in Szegedy et al., [Inception-v4, Inception-ResNet and the Impact of Residual Connections on Learning](https://arxiv.org/abs/1602.07261) (2016), combined two figures](https://cdn-images-1.medium.com/max/1844/1*l0h9YFYdyBUvk1E8LBZTQw.png)

I adore its composition — we see what’s going on, and which blocks are being repeated.

Another diagram that made a concept super clear to me was one for image segmentation, U-Net:

![Olaf Ronneberger, Philipp Fischer, Thomas Brox, [U-Net: Convolutional Networks for Biomedical Image Segmentation](https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/) (2015)](https://cdn-images-1.medium.com/max/2048/1*aBLf8WAEbEtJnJef3leQQQ.png)

Take note that this time nodes denote tensors, whereas arrows represent operations. I find this diagram very clear — we see tensor shapes, convolutions, and pooling operations. Since the original U-Net architecture is not too complex, we can do without looking at its hierarchical structure.

The task of creating clear diagrams get slightly more complicated when we want to use more complex building blocks. If we want to reproduce the network, we need to know its details:

- Number of channels
- Convolutions per MaxPool
- Number of MaxPools
- Batch normalization or dropout
- Activation functions (ReLU? before or after Batch Norm?)

As a great example of condensing this level of detail into a diagram, see the diagram below:

![Arkadiusz Nowaczyński, [Deep learning for satellite imagery via image segmentation](https://deepsense.ai/deep-learning-for-satellite-imagery-via-image-segmentation/) (2017)](https://cdn-images-1.medium.com/max/1896/1*gB_0B_-zeOoEqq_AOnWccw.png)

While the color choice could have been better, I adore its explicit form. There is a clear indication of the number of channels. Each complex layer is explicitly decomposed into its building blocks, maintaining all details (note 3-level hierarchy).

Another interesting approach to the neural network module hierarchy:

![AdaptNet architecture from Abhinav Velda et al., [DeepScene: Semantic Segmentation using Deep Upconvolutional Neural Networks](http://deepscene.cs.uni-freiburg.de/) (2016)](https://cdn-images-1.medium.com/max/1802/1*v7Im24aAolKx_RhxpxYWCA.jpeg)

# Automatic tools for neural network architecture visualization

You can draw your network manually. Use[ Inkscape](https://inkscape.org/en/) (as Chris Olah did),[ TikZ](http://www.texample.net/tikz/examples/) (if you are a fan of LaTeX) or any other tool. The other one is to generate them automatically.

I hope that you are aware that you already interact with one visual representation — code (yes, a text is a visual representation!). For some projects, the code might suffice, especially if you work with a concise framework (such as[ Keras or PyTorch](https://deepsense.ai/keras-or-pytorch/)). For more convoluted (pun totally intended) architectures, diagrams add a lot of explanatory value.

#### TensorBoard: Graph

[TensorBoard](https://www.tensorflow.org/guide/graph_viz) is arguably the most popular network visualization tool. A TensorFlow network graph looks like this:

![](https://cdn-images-1.medium.com/max/1168/1*7_ycMgp2YgcCLyMvzEDCNQ.png)

Does it provide a readable summary for a neural network?

In my opinion, it does not.

While this diagram shows the structure of computations, some things are long-winded (e.g. adding bias as a separate operation). Additionally, the most important parts are being masked: the core parameters of operations (e.g. convolution kernel size), and tensor sizes. Though, before going into criticising, I really encourage reading the accompanying paper:

- K. Wongsuphasawat, D. Smilkov et al,[ Visualizing dataflow graphs of deep learning models in TensorFlow](http://idl.cs.washington.edu/files/2018-TensorFlowGraph-VAST.pdf), 2018

This article provides insight into the many challenges of creating network diagrams bottom-up. Since we are allowed to use all TensorFlow operations, including auxiliary ones (such as initialization or logging), it is challenging to make a general, readable graph. If we don’t assume much about what is important to the reader(e.g. that convolution kernel size may vary, but all operations are expected to have a bias), it is hard to make a general tool for turning any TensorFlow computation diagram into a useful (think: publication-ready) diagram.

#### Keras

Keras is a high-level deep learning framework and therefore has huge potential for beautiful visualizations. (Side note: if you want to use an interactive train graph for Jupyter Notebook, I wrote one:[ livelossplot](https://github.com/stared/livelossplot).) Yet, in my opinion, its default visualizing option (using GraphViz) is not stellar:

![[https://keras.io/visualization/](https://keras.io/visualization/)](https://cdn-images-1.medium.com/max/1948/1*AUpvvhkmat7KBNIyPA2cYg.png)

I think it hides important details, while provides redundant data (duplicated tensor sizes). Aesthetically, I don’t love it nearly much as [Mike Bostock does](https://twitter.com/mbostock/status/1030198344423886848).

I tried to write another one(`pip install keras_sequential_ascii`), for trainings:

![Piotr Migdał, [Sequential model in Keras -> ASCII](https://github.com/stared/keras-sequential-ascii) (2017)](https://cdn-images-1.medium.com/max/1880/1*jLld9FGjaLHFhukZ0btIyw.png)

This structure works for small-sized sequential network architectures. I’ve found it useful for training and courses, such as[ Starting deep learning hands-on: image classification on CIFAR-10](https://deepsense.ai/deep-learning-hands-on-image-classification/). But not for anything more advanced (though, I was advised to use[ branching viz like from git log](https://stackoverflow.com/questions/1057564/pretty-git-branch-graphs)). And, apparently, I am not the only one who tried ASCII art for neural network viz:

![Brian Low, [Keras models as ASCII diagrams](https://github.com/brianlow/keras_diagram) (2016)](https://cdn-images-1.medium.com/max/1640/1*2O_B3FPZQHWLj1OJcBfP-Q.png)

Though, I would say that the most aesthetically pleasing is one found in[ Keras.js](https://github.com/transcranial/keras-js) (an ambitious project bringing neural networks to the browser, with GPU support):

![Leon Chen, [SeqeezeNet v.1.1 from Keras.js Demo](https://transcranial.github.io/keras-js/#/squeezenet-v1.1) (2018)](https://cdn-images-1.medium.com/max/1316/1*X2wPp_uPof7vMMyga3rwzQ.png)

This project is no longer in active development, in favor of [TensorFlow.js](https://js.tensorflow.org/). Yet, as it is open-source and modular (using [Vue.js](https://vuejs.org/) framework), it may work as a starting ground for creating a standalone-viz. Ideally, one working in Jupyter Notebook or separate browser window, much alike[ displaCy for sentence decomposition](https://spacy.io/usage/visualizers#section-jupyter).

#### Moniel

Instead of turning a functional neural network into a graph, we can define an abstract structure. In[ Moniel](https://github.com/mlajtos/moniel) by Milan Lajtoš the best part is that we can define a hierarchical structure:

![Milan Lajtoš, [Moniel — Interactive Notation for Computational Graphs](https://github.com/mlajtos/moniel) (2017)](https://cdn-images-1.medium.com/max/1638/1*u6uIQF4xTVe-ylJnAPoIDg.png)

I like this hierarchical-structure approach. Moniel was an ambitious idea to create a specific language (rather than, say, to use YAML). Sadly, [the project lies abandoned](https://github.com/mlajtos/moniel/issues/13).

#### Netscope

I got inspired by[ Netscope CNN Analyzer](https://dgschwend.github.io/netscope/quickstart.html) by[ dgschwend](https://github.com/dgschwend) (based on a project by[ ethereon](https://github.com/ethereon)). It is a project with many forks, so by now a different one may be more up-to-date:

![David Gschwend, Saumitro Dasgupta, [SqueezeNet v.1. from Netscope CNN Analyzer ](https://dgschwend.github.io/netscope/#/preset/squeezenet_v11)(2018)](https://cdn-images-1.medium.com/max/1546/1*yJl3F1gIPE2IK5y3yYa-lQ.png)

It is based on Caffe’s `.prototxt`format. I love its color theme, the display of channel sizes and mouseover tooltip for exact parameters. The main problem, though, is the lack of a hierarchical structure. Networks get (too) big very soon.

#### Netron

Another ambitious project: [Netron](https://github.com/lutzroeder/netron) by Lutz Roeder:

![Lutz Roeder, [Netrone — Visualizer for deep learning and machine learning models](https://github.com/lutzroeder/netron) (2018)](https://cdn-images-1.medium.com/max/2050/1*6nDySAw15yh2GHyevFYvnQ.png)

It is a web app, with standalone versions. Ambitiously, it reads various formats

> N*etron supports [ONNX](http://onnx.ai/) (`.onnx`, `.pb`), Keras (`.h5`, `.keras`), CoreML (`.mlmodel`) and TensorFlow Lite (`.tflite`). Netron has experimental support for Caffe (`.caffemodel`), Caffe2 (`predict_net.pb`), MXNet (`.model`, `-symbol.json`), TensorFlow.js (`model.json`, `.pb`) and TensorFlow (`.pb`, `.meta`).*

It sounds awesome! Though, it is a bit more verbose than NetScope (with activation functions) and, most fundamentally, it lacks the hierarchical structure. But for a general visualization, it may be the best starting point.

#### EDIT: Other tools

A few other tools that may be useful or inspiring:

- [NN-SVG: LeNet- and AlexNet-style diagrams](http://alexlenail.me/NN-SVG/LeNet.html)
- [Visualizing CNN architectures side by side with MXNet](http://josephpcohen.com/w/visualizing-cnn-architectures-side-by-side-with-mxnet/)
- [TensorSpace.js](https://tensorspace.org/) — an in-browser 3D visualizations of channels (stunning but hardly useful)
- [HiddenLayer](https://github.com/waleedka/hiddenlayer/) — diagrams with ONNX & Graphviz in Jupyter Notebook for TensorFlow, Keras and PyTorch
- [PlotNeuralNet](https://github.com/HarisIqbal88/PlotNeuralNet) — LaTeX code for drawing convolutional neural networks

And a few threads:

- [What tools are good for drawing neural network architecture diagrams? — Quora](https://www.quora.com/What-tools-are-good-for-drawing-neural-network-architecture-diagrams)
- [How do you visualize neural network architectures? — Data Science Stack Exchange](https://datascience.stackexchange.com/questions/12851/how-do-you-visualize-neural-network-architectures)

# Conclusion and call for action

We saw quite a few examples of neural network visualization, shedding light on the following trade-offs:

- **data viz **vs** data art** (useful vs beautiful)
- **explicit **vs** implicit** (should I show ReLU all the time? But what about tensor dimensions?)
- **shallow vs hierarchical**
- **static** (works well in publications) vs **interactive** (provides more information)
- **specific** vs **general** (does it work for a reasonably broad family of neural networks?)
- **data flow direction** (top to bottom, bottom to top, or left to right; hint: [please don’t draw bottom-to-top](https://www.reddit.com/r/MachineLearning/comments/6j28t9/d_why_do_people_draw_neural_networks_upside_down/))

Each of those topics is probably worth a Masters thesis, and all combined — a PhD (especially with a meticulous study of how people do visualize and what are the abstractions.)

I think there is a big opportunity in creating a standard neural network visualization tool, as common for neural network architectures as matplotlib is for charts. It remains a challenge at the intersection of deep learning and data visualization. The tool should be useful and general enough, to become a standard for:

- tutorials in neural networks
- academic publications
- showing network architecture to collaborators

If we want to make it interactive, JavaScript is a must. Be it D3.js, Vue.js, React or any other tech. That way, it is not only easy to make it interactive, but also system agnostic. Take [Bokeh](https://bokeh.pydata.org/) as an example — being useful within a Jupyter Notebook, but also — as a standalone website.

Would you like to start a brand new package? Or contribute to an existing one?

If you find any neural network particularly inspiring, or confusing, share it in the comments! :)

# Afterwords

This article is based on my talk “Simple diagrams of convoluted neural networks” ([abstract](https://pydata.org/berlin2018/schedule/presentation/30/),[ slides](https://www.dropbox.com/s/a7xako61ihuh82k/20180707_network_viz_pydata_berlin.pdf?dl=0)) from PyData Berlin 2018 (BTW: and I invite you to[ PyData Warsaw, 19–20 Nov 2018](https://pydata.org/warsaw2018/)). Typically I write on my blog[ p.migdal.pl](https://p.migdal.pl/). Now I give Medium a try, as it is easier to include images than with[ Jekyll](https://p.migdal.pl/2015/12/02/first-post.html).

I am grateful to [Ilja Sperling](https://medium.com/u/1631d8afa706) for fruitful conversations after the talk and to [Rafał Jakubanis](https://medium.com/u/72ff3f0101ef) and [Sarah Martin, CSC](https://medium.com/u/39462454f46a) for numerous remarks on the draft.