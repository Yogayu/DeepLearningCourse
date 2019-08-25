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
# An online deep learning course for humanists (WIP)

![log](media/logo.png)

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

  - [Read Online](#read-online)
  - [Project Description](#project-description)
- [An online deep learning course for humanists (WIP)](#an-online-deep-learning-course-for-humanists-wip)
  - [Read Online](#read-online)
  - [Project Description](#project-description)
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
    - [Optimization](#optimization)
  - [Physical Experiment](#physical-experiment)
  - [Chapter 6 Make your own neural network to classify handwritten digitals](#chapter-6-make-your-own-neural-network-to-classify-handwritten-digitals)
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


## Slides
All the course slide can be found at this [directory](https://github.com/Yogayu/DeepLearningCourse/tree/master/Slides).

- Lesson1-Introduction
- Lesson2-PerceptronAndStructure
- Lesson3-TrainingAndGradientDescent
- Lesson4-Backpropagation
- Lesson5-CNNs
- Lesson6-RNNs
- Lesson7-Neural Network Zoo

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

[x] Apply Matrix to Neural Network computation

### Design the Output Layer

[x] Design the Output Layer

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