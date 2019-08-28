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
# An online deep learning course for humanists

![log](media/logo.png)

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

  - [Read Online](#read-online)
  - [Project Description](#project-description)
  - [Slides](#slides)
    - [Lesson1-Introduction](#lesson1-introduction)
      - [Keynote](#keynote)
      - [Keynote Content](#keynote-content)
    - [Lesson2-perceptron & Multilayer perceptron](#lesson2-perceptron--multilayer-perceptron)
      - [Keynote](#keynote-1)
      - [Keynote Content](#keynote-content-1)
    - [Lesson3-Training Neural Networks](#lesson3-training-neural-networks)
      - [Keynote](#keynote-2)
      - [Content](#content)
    - [Lesson4-Backpropagation](#lesson4-backpropagation)
      - [Keynote](#keynote-3)
      - [Content](#content-1)
    - [Lesson5-CNNs](#lesson5-cnns)
      - [Keynote](#keynote-4)
      - [Content](#content-2)
    - [Lesson6-RNNs](#lesson6-rnns)
      - [keynote](#keynote)
      - [content](#content)
    - [Lesson7-Neural Network Zoo](#lesson7-neural-network-zoo)
      - [keynote](#keynote-1)
- [Course Outline](#course-outline)
  - [Chapter 0 Background Knowledge](#chapter-0-background-knowledge)
  - [Chapter 1 Introduction](#chapter-1-introduction)
  - [Chapter 2 Perceptron](#chapter-2-perceptron)
    - [Perceptron: foundation block of Neural Network](#perceptron-foundation-block-of-neural-network)
    - [Iris Classification Example](#iris-classification-example)
  - [Chapter 3 Multilayer Perceptron (deep feedforward networks)](#chapter-3-multilayer-perceptron-deep-feedforward-networks)
    - [The architecture of Multilayer perceptron](#the-architecture-of-multilayer-perceptron)
    - [Activation function](#activation-function)
    - [Design Output Layer](#design-output-layer)
  - [Chapter 4 Forward Propagation](#chapter-4-forward-propagation)
    - [Forward Process](#forward-process)
    - [Matrixs](#matrixs)
    - [Apply Matrix to Neural Network computation](#apply-matrix-to-neural-network-computation)
    - [Design the Output Layer](#design-the-output-layer)
    - [Why we use None-linearities activation function?](#why-we-use-none-linearities-activation-function)
  - [Chapter 5 Learning: Training Neural Networks](#chapter-5-learning-training-neural-networks)
    - [Loss function](#loss-function)
    - [Learning to minimize error: Gradient Descent method](#learning-to-minimize-error-gradient-descent-method)
    - [Back Propagation](#back-propagation)
  - [Physical Experiment](#physical-experiment)
  - [Chapter 6 Make your own neural network to classify handwritten digitals](#chapter-6-make-your-own-neural-network-to-classify-handwritten-digitals)
  - [Reference](#reference)
    - [Dataset and Content](#dataset-and-content)
    - [Broader Discussion](#broader-discussion)
  - [About Me](#about-me)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


## Read Online

This book is powered by Jekyll Book. So you can read it online: 
- [Github Jekyll Book](https://yogayu.github.io/DeepLearningCourse/)
- [Red Hen Lab's Techne Public Site](https://sites.google.com/case.edu/techne-public-site/home)

## Project Description

This is my [Google Summer of Code 2019](https://summerofcode.withgoogle.com/projects/#6543412331806720) Project with [Red Hen Lab](http://www.redhenlab.org/).

The Project goal is to design and develops an online course, to teach deep learning for students in the humanities and social sciences. The course will contain basic deep learning theory and labs case studies from multimodal communication. 

Project Mentors: [Francis Steen](http://cogweb.ucla.edu/steen/), [Mark Turner](http://markturner.org) and Rajesh Kasturirangan.


## Slides
All the course slide can be found at this [directory](https://github.com/Yogayu/DeepLearningCourse/tree/master/Slides).

### Lesson1-Introduction

#### Keynote

- [Introduction Keynote](https://github.com/Yogayu/DeepLearningCourse/blob/master/Slides/Lesson1-Introduction.key)
- [Introduction PDF](https://github.com/Yogayu/DeepLearningCourse/blob/master/Slides/Lesson1-Introduction.pdf)

#### Keynote Content

- Application of deep learning
- What is Artificial Intelligence?
- What is Machine Learning?
- What is Deep Learning?
- Limitation of deep learning

### Lesson2-perceptron & Multilayer perceptron

#### Keynote

- [Perceptron & Multilayer perceptron Keynote](https://github.com/Yogayu/DeepLearningCourse/blob/master/Slides/Lesson2-PerceptronAndStructure.key)
- [Perceptron & Multilayer perceptron PDF](https://github.com/Yogayu/DeepLearningCourse/blob/master/Slides/Lesson2-PerceptronAndStructure.pdf)

#### Keynote Content

- Logic-gate neurons
- Neuron-like perceptron
- Neurons are more powerful
- Color Factory
- Multilayer perceptron
  - Why is the middle layer called a hidden layer?
  - Activation functions
  - Commonly used activation functions
  - Why must the activation functions be non-linear?
- Forward Propagation
- Example: Handwritten Digits Recognition

### Lesson3-Training Neural Networks
#### Keynote

- [Training Neural Networks Keynote](https://github.com/Yogayu/DeepLearningCourse/blob/master/Slides/Lesson3-TrainingAndGradientDescent.key)
- [Training Neural Networks PDF](https://github.com/Yogayu/DeepLearningCourse/blob/master/Slides/Lesson3-TrainingAndGradientDescent.pdf)

#### Content
- Loss function
- Gradient Descent
  - What is Gradient Descent?
  - Simple Example
  - Avoid Overshooting
  - Challenges: Local Minima

### Lesson4-Backpropagation
#### Keynote

- [Backpropagation Keynote](https://github.com/Yogayu/DeepLearningCourse/blob/master/Slides/Lesson4-Backpropagation.key)
- [Backpropagation PDF](https://github.com/Yogayu/DeepLearningCourse/blob/master/Slides/Lesson4-Backpropagation.pdf)

#### Content
- Compute Graph
  - Example
  - Local Compute
  - Compute Graph Advantage
- The Chain Rule
- Compute graph & Chain Rule
- Back propagation
  - Back propagation of addition nodes
  - Back propagation of multiplication nodes
  - Back propagation of ReLU
  - Back propagation of Sigmoid
- Application
  - Exercise 1
  - Exercise 2
- Summary

### Lesson5-CNNs

#### Keynote

- [CNNs Keynote](https://github.com/Yogayu/DeepLearningCourse/blob/master/Slides/Lesson5-CNNs.key)
- [CNNs PDF](https://github.com/Yogayu/DeepLearningCourse/blob/master/Slides/Lesson5-CNNs.pdf)

#### Content

- A Brief History of CNNs 
- Why we need CNNs? 
- The Structure of CNNs
- Convolution operation
- Padding Stride
- Convolution
- Pooling
- Some typical CNNs 
- Example: Dog or Cat?

### Lesson6-RNNs
#### keynote

- [RNNs Keynote](https://github.com/Yogayu/DeepLearningCourse/blob/master/Slides/Lesson6-RNNs.key)
- [RNNs PDF](https://github.com/Yogayu/DeepLearningCourse/blob/master/Slides/Lesson6-RNNs.pdf)

#### content

- Sequence modeling
- Deep forward neural networks vs Recurrent neural networks
- Recurrent neural networks
- The Problems Of RNNs
- LSTM networks
- Application of RNNs

### Lesson7-Neural Network Zoo
#### keynote

- [RNNs Keynote](https://github.com/Yogayu/DeepLearningCourse/blob/master/Slides/Lesson7-Neural%20Network%20Zoo.key)
- [RNNs PDF](https://github.com/Yogayu/DeepLearningCourse/blob/master/Slides/Lesson7-Neural%20Network%20Zoo.pdf)

# Course Outline
## Chapter 0 Background Knowledge

Programming

- [Python Basic](https://sites.google.com/case.edu/techne-public-site/python?authuser=0)

Math

- basic matrix, calculus, and statistics.

## Chapter 1 Introduction

- [x] What is artificial intelligence, machine learning, deep learning and their relationship?
- [x] Environment Setup
      Anaconda, TensorFlow and Jupyter Lab.

## Chapter 2 Perceptron

### Perceptron: foundation block of Neural Network

- [x] How do we learn? (Biological neuron model)
- [x] How can machine learn? (Artificial neural->Perceptron)

### Iris Classification Example

- [x] Question and Dataset
- [x] Linear Classifier
- [x] Implement a perceptron

## Chapter 3 Multilayer Perceptron (deep feedforward networks)

### The architecture of Multilayer perceptron

- Nodes
- Input/Output
- Layer
    - Input Layer
    - Output Layer
    - Hidden Layer: Why we call it hidden layer
- Connection
    - Fully connected
- Weights

### Activation function

- [x] What is Activation function?
- [x] The common active function

### Design Output Layer

- [x] Regression and classification

## Chapter 4 Forward Propagation

### Forward Process

### Matrixs
  - [x] What is Matrix
  - [x] Multiplying Matrixs

### Apply Matrix to Neural Network computation

- [x] Apply Matrix to Neural Network computation

### Design the Output Layer

- [x] Design the Output Layer

### Why we use None-linearities activation function?


## Chapter 5 Learning: Training Neural Networks

### Loss function

- [x] How well does the neural network predict: Loss Function
  - [x] Example
  - [x] Loss function: Mean Squared Error
  - [x] Why we use squared error instead of raw error?

    The empirical loss measures the total loss over the dataset. Loss function is a function of the Weight.

### Learning to minimize error: Gradient Descent method

- [x] Gradient Descent
  - [x] Minimize error
  - [x] What is Gradient Descent?
    - [x] Greedy algorithm
    - [x] Like Hiking Down a Mountain
    - [x] Simple Example
    - [x] Local minimum

### Back Propagation
- [x] Compute Graph
- [x] Chain Rule
- [x] Back Propagation

The error is propagated backwards to the other layers.


## Physical Experiment

- Each student acted as a Neuron
- Mock Forward Propagation
- Mock Backward Propagation

## Chapter 6 Make your own neural network to classify handwritten digitals

In this chapter, the student will learn how to teach the computer to classify handwritten digits by using MNIST dataset in Python.

**DataSet:** The dataset I choose for this part is MNIST(Modified National Institute of Standards and Technology)  dataset, which has a training set of 60,000 examples, and a test set of 10,000 examples. It is a subset of a larger set available from NIST(National Institute of Standards and Technology) which gives data set of over 800,000 images of handwritten digits from 3,600 writers. The digits have been size-normalized and centered in a fixed-size image.

## Reference

### Dataset and Content

- [Kaggle -- MNIST sign language](https://www.kaggle.com/datamunge/sign-language-mnist)
- [OpenML](https://www.openml.org/home) -- datasets, tasks, flows, results
- [Speed Dating](https://www.openml.org/d/40536) -- [Covertype satellite images](https://www.openml.org/d/150)
- [Awesome Public Datasets on GitHub](https://github.com/awesomedata/awesome-public-datasets)
- [Wikipedia's list of datasets for machine-learning research](https://en.wikipedia.org/wiki/List_of_datasets_for_machine-learning_research)
- [Medium's 50 best public datasets for machine learning](https://medium.com/towards-artificial-intelligence/the-50-best-public-datasets-for-machine-learning-d80e9f030279)
- [25 Open Datasets for Deep Learning](https://www.analyticsvidhya.com/blog/2018/03/comprehensive-collection-deep-learning-datasets/)
- [UC Irvine Machine Learning Repository](https://archive.ics.uci.edu/ml/index.php)
- [1996 English Broadcast News Speech](https://catalog.ldc.upenn.edu/LDC97S44)
- [Skymind open datasets](https://skymind.ai/wiki/open-datasets)

- Grokking Deep Learning Andrew W. Trask
- [*Make Your Own Neural Network* ](https://www.amazon.com/Make-Your-Own-Neural-Network-ebook/dp/B01EER4Z4G/)*by* [Tariq Rashid](https://www.amazon.com/Tariq-Rashid/e/B01N1YH9L9/ref=dp_byline_cont_ebooks_1)
- [*Introduction to Deep Learning*](https://www.youtube.com/watch?v=aircAruvnKk&list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi&index=1) animation videos created by [3Blue1Brown](https://www.youtube.com/watch?v=aircAruvnKk&list=PLZHQObOWTQDNU)
- [http://introtodeeplearning.com](http://introtodeeplearning.com/)
- http://deeplearning.net/tutorial/
- [https://nndl.github.io](https://nndl.github.io/) 
- http://zh.gluon.ai/index.html 

### Broader Discussion

- [Critique of Pure Learning](https://www.nature.com/articles/s41467-019-11786-6) (2019)
- Geoffrey Hinton on capsule networks: https://www.youtube.com/watch?v=rTawFwUvnLE
  - [Hinton, Dynamic Routing Between Capsules](https://arxiv.org/abs/1710.09829)
  - For the MNIST dataset, see [A Tensorflow implementation of CapsNet based on Geoffrey Hinton's paper Dynamic Routing Between Capsules](https://github.com/naturomics/CapsNet-Tensorflow)
- [Yann LeCun on the limits of deep learning](https://www.quora.com/What-are-the-limits-of-deep-learning-2) (2016, Quora)
- [Artificial Intelligence Pioneer Says We Need to Start Over](https://cacm.acm.org/news/221108-artificial-intelligence-pioneer-says-we-need-to-start-over/fulltext) (2017)
- [Why is Geoffrey Hinton suspicious of backpropagation and wants AI to start over?](https://www.quora.com/Why-is-Geoffrey-Hinton-suspicious-of-backpropagation-and-wants-AI-to-start-over)
- [Geoffrey Hinton talk "What is wrong with convolutional neural nets?"](https://www.youtube.com/watch?v=rTawFwUvnLE)


## About Me

- **Name**: Xinyu You
- **Email**: yxydiscovery@gmail.com
- **Github**: [yogayu](http://github.com/yogayu)
- **Website**: [data2art](http://data2art.com)
- **Resume**: [youxinyu.me](http://youxinyu.me)

If there are any problems, please feel free to contact me.
