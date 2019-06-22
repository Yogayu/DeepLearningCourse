---
title: 'Home'
prev_page:
  url: 
  title: ''
next_page:
  url: https://sites.google.com/case.edu/techne-public-site/home
  title: 'Techne Public Site'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---
# Deep Learning course for humanists

![](./images/logo.png)

This is my [Google Summer of Code 2019](https://summerofcode.withgoogle.com/projects/#6543412331806720) Project with [Red Hen Lab](http://www.redhenlab.org/).

The Project goal is to design and develops an online course, to teach deep learning for students in the humanities and social sciences. The course will contain basic deep learning theory and labs case studies from multimodal communication. 

Project Mentors: [Francis Steen](http://cogweb.ucla.edu/steen/), [Mark Turner](http://markturner.org) and Rajesh Kasturirangan.

## Course Outline

### Background Knowledge

Programming

- [Python Basic](https://sites.google.com/case.edu/techne-public-site/python?authuser=0)

Math

- basic matrix, calculus, and statistics.

### Chapter 1 Introduction

1. What is deep learning?
2. Relationship: AI-> machine learning -> deep learning
3. What can deep learning do?
4. [Environment Setup](https://yogayu.github.io/DeepLearningCourse/part0/environment.html#environment-setup)
   Setup the environment we need in this course, including Anaconda, TensorFlow and Jupyter Lab.

### Chapter 2 Perceptron

1. How do we learn?
2. How can machine learn?
3. Perceptron: a single layer neural network

### Chapter 3 Multilayer Perceptron

A multi-layer perceptron is called Neural Networks

#### Section 1

##### 1. Neuron

- Biological neuron model
  - Artificial neural

##### 2. Activation function

- Why need this? None-linearities
  - Some common activation functions

##### 3. Two layer Neural Network

The architecture:

- Nodes
- Input/Output
- Layer
  - Input Layer
  - Output Layer
  - Hidden Layer: Why we call it hidden layer
- Connection
  - Fully connected
- Weights

#### Section 2

##### 1. Propagation

- Forward Propagation
- Backward Propagation
- Math: Matrix Multiplication

Make animation videos.

##### 2. Learning: Training Neural Networks

- Example
- Error loss
  The empirical loss measures the total loss over the dataset
- Loss Optimization
  - Loss function is a function of the Weight
  - Gradient Descent
    - Greedy algorithm
    - Like Hiking Down a Mountain
      Make an animation video
    - Local minimum
- Optimization

#### Physical Experiment

- Every student acted as a Neuron
- Mock Forward Propagation
- Mock Backward Propagation

### Chapter 4 Make your own neural network to classify handwritten digitals

In this chapter, the student will learn how to teach the computer to classify handwritten digits by using MNIST dataset in Python.

**DataSet:** The dataset I choose for this part is MNIST(Modified National Institute of Standards and Technology)  dataset, which has a training set of 60,000 examples, and a test set of 10,000 examples. It is a subset of a larger set available from NIST(National Institute of Standards and Technology) which gives data set of over 800,000 images of handwritten digits from 3,600 writers. The digits have been size-normalized and centered in a fixed-size image.

TBD

## Other Projects

TBD

### Classify Hand Gesture Pose in Art

In this part, the student will learn how to classify Hand Gesture Pose in Art using Tensorflow.

**Dataset:**  we will use Rijksmuseum dataset, the [Fototeca Zeri data](<http://data.fondazionezeri.unibo.it/query/>) or the [Bibliotheca Hertziana dataset]([http://foto.biblhertz.it](http://foto.biblhertz.it/)).

### Audio Recognition of Simple words

In this part, the student will learn how to build a basic speech recognition network that recognizes ten different words:  "yes", "no", "up", "down", "left", "right", "on", "off", "stop", or "go". Real speech and audio recognition systems is much more complex than classify handwritten digits. 

**Dataset**: we will use the [Speech Commands dataset](https://storage.cloud.google.com/download.tensorflow.org/data/speech_commands_v0.02.tar.gz), which consists of over 105,000 WAVE audio files of people saying thirty different words. This data was collected by Google and released under a CC-BY license.

### Exploring Sentiment in Literature

In this part, the student will learn how to build use Convolutional Neural Network and Recurrent Neural Network to train a [models](https://github.com/awjuliani/DNN-Sentiment), which will let us exploring Sentiment in Literature.

**Dataset**: we will choose three books (one positive book, one negative book, and one normal book) form [**Project Gutenberg**](http://www.gutenberg.org). Project Gutenberg offers over 58,000 free eBooks. 



## About Me

- **Name**: Xinyu You
- **Email**: yxydiscovery@gmail.com
- **Github**: [yogayu](http://github.com/yogayu)
- **Website**: [data2art](http://data2art.com)
- **Resume**: [youxinyu.me](http://youxinyu.me)

If there are any problems, please feel free to contact me.