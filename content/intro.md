# Deep Learning course for humanists

![log](media/logo.png)

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

  - [Read Online](#read-online)
  - [Project Description](#project-description)
- [Course Outline](#course-outline)
  - [Chapter 0 Background Knowledge](#chapter-0-background-knowledge)
  - [Chapter 1 Introduction](#chapter-1-introduction)
  - [Chapter 2 Perceptron](#chapter-2-perceptron)
    - [Perceptron: a single layer neural network](#perceptron-a-single-layer-neural-network)
    - [Example: Iris Classification](#example-iris-classification)
  - [Chapter 3 Multilayer Perceptron (deep feedforward networks)](#chapter-3-multilayer-perceptron-deep-feedforward-networks)
    - [3.1 Multilayer perceptron](#31-multilayer-perceptron)
    - [3.2 Forward Propagation](#32-forward-propagation)
    - [3.3 Why we use None-linearities activation function?](#33-why-we-use-none-linearities-activation-function)
  - [Chapter 4 Learning: Training Neural Networks](#chapter-4-learning-training-neural-networks)
    - [4.1 Loss function](#41-loss-function)
    - [4.2 Loss Optimization](#42-loss-optimization)
    - [4.3 Back Propagation](#43-back-propagation)
    - [4.4 Optimization](#44-optimization)
  - [Physical Experiment](#physical-experiment)
  - [Chapter 5 Make your own neural network to classify handwritten digitals](#chapter-5-make-your-own-neural-network-to-classify-handwritten-digitals)
  - [Other Projects](#other-projects)
    - [Classify Hand Gesture Pose in Art](#classify-hand-gesture-pose-in-art)
    - [Audio Recognition of Simple words](#audio-recognition-of-simple-words)
    - [Exploring Sentiment in Literature](#exploring-sentiment-in-literature)
  - [About Me](#about-me)
  - [Reference](#reference)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


## Read Online

This book is powered by Jekyll Book. So you can read it online: 
- [Github Jekyll Book](https://yogayu.github.io/DeepLearningCourse/)
- [Red Hen Lab's Techne Public Site](https://sites.google.com/case.edu/techne-public-site/home)

## Project Description

This is my [Google Summer of Code 2019](https://summerofcode.withgoogle.com/projects/#6543412331806720) Project with [Red Hen Lab](http://www.redhenlab.org/).

The Project goal is to design and develops an online course, to teach deep learning for students in the humanities and social sciences. The course will contain basic deep learning theory and labs case studies from multimodal communication. 

Project Mentors: [Francis Steen](http://cogweb.ucla.edu/steen/), [Mark Turner](http://markturner.org) and Rajesh Kasturirangan.

# Course Outline
## Chapter 0 Background Knowledge

Programming

- [Python Basic](https://sites.google.com/case.edu/techne-public-site/python?authuser=0)

Math

- basic matrix, calculus, and statistics.

## Chapter 1 Introduction

- [x]  What is deep learning?
2. [x] Relationship: AI-> machine learning -> deep learning
3. [x] What can deep learning do?
4. [x] [Environment Setup](https://yogayu.github.io/DeepLearningCourse/part0/environment.html#environment-setup)
		Setup the environment we need in this course, including Anaconda, TensorFlow and Jupyter Lab.

## Chapter 2 Perceptron

### Perceptron: a single layer neural network

- [x] How do we learn? (Biological neuron model)
- [x] How can machine learn? (Artificial neural->Perceptron)

### Example: Iris Classification
- [x] Linear Classifier
- [x] Implement a perceptron

## Chapter 3 Multilayer Perceptron (deep feedforward networks)

### 3.1 Multilayer perceptron

- [x] The architecture
    - Nodes
    - Input/Output
    - Layer
        - Input Layer
        - Output Layer
        - Hidden Layer: Why we call it hidden layer
    - Connection
        - Fully connected
    - Weights
- [x] Activation function
    - What is Activation function
    - The common active function

### 3.2 Forward Propagation

- [x] Forward Process
- [x] Math: Multiplying Matrixs
- [x] Apply matrix to neural network computation
- [x] Design the output layer

Make animation videos(gifs).

### 3.3 Why we use None-linearities activation function?

## Chapter 4 Learning: Training Neural Networks

### 4.1 Loss function

- [x] Error loss function
    The empirical loss measures the total loss over the dataset. Loss function is a function of the Weight.

### 4.2 Loss Optimization

- [ ] Gradient Descent
  - Greedy algorithm
  - Like Hiking Down a Mountain
      Make an animation video
  - Local minimum

### 4.3 Back Propagation

- [ ] Back Propagation

### 4.4 Optimization
 
- [ ] Early stop

## Physical Experiment

- Every student acted as a Neuron
- Mock Forward Propagation
- Mock Backward Propagation

## Chapter 5 Make your own neural network to classify handwritten digitals

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

## Reference

- https://elitedatascience.com/machine-learning-projects-for-beginners
- https://github.com/gkchai/GestureRecognition
- https://www.tensorflow.org/tutorials/sequences/audio_recognition
- https://medium.com/@awjuliani/exploring-sentiment-in-literature-with-deep-learning-30366aff578e
- http://awjuliani.github.io/books/