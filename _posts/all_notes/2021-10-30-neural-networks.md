---
layout: post
title:  "Neural Networks"
date:   2021-10-30 09:29:20 +0700
categories: post
---

# Key Components

    1. The data that we can learn from.
    2. A model of how to transform the data.
    3. An objective function that quantifies how well (or badly) the model is doing.
    4. An algorithm to adjust the model’s parameters to optimize the objective function.

# Data

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 When every example is characterized by the same number of numerical values, we say that 
 the data consist of fixed-length vectors and we describe the constant length of the vectors as the ***dimensionality of the data***. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 However, not all data can easily be represented as fixed-length vectors. While we might expect microscope images to come from standard 
 equipment, we cannot expect images mined from the Internet to all show up with the same resolution or shape. For images, we might consider 
 cropping them all to a standard size, but that strategy only gets us so far. We risk losing information in the cropped out portions.
 One major advantage of deep learning over traditional methods is the comparative grace with which modern models can handle ***varying-length data***.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Generally, the more data we have, the easier our job becomes. When we have more data, we can train more powerful models and
 rely less heavily on pre-conceived assumptions.
  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Finally, it is not enough to have lots of data and to process it cleverly. We need the right data. If the data are full of mistakes, 
 or if the chosen features are not predictive of the target quantity of interest, learning is going to fail. 
 The situation is captured well by the ***cliché: garbage in, garbage out. ***

# Models

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Most machine learning involves transforming the data in some sense. We might want to build a system that ingests photos and predicts smiley-ness. 
 Alternatively, we might want to ingest a set of sensor readings and predict how normal vs. anomalous the readings are. By model, we denote the 
 computational machinery for ingesting data of one type, and spitting out predictions of a possibly different type. In particular, we are 
 interested in statistical models that can be estimated from data. 

# Objective Functions

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  In order to develop a formal mathematical system of learning machines, we need to have formal measures of how good (or bad) our models are. 
  In machine learning, and optimization more generally, we call these objective functions. By convention, we usually define objective functions 
  so that lower is better. This is merely a convention. You can take any function for which higher is better, and turn it into a new function 
  that is qualitatively identical but for which lower is better by flipping the sign. Because lower is better, these functions are sometimes 
  called **loss functions.**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  When trying to predict numerical values, the most common loss function is ***squared error***, i.e., the square of the difference between 
  the prediction and the ground-truth. For classification, the most common objective is to minimize error rate, i.e., the fraction of
  examples/data instances on which our predictions disagree with the ground truth. Some objectives (e.g., squared error) are easy to optimize. 
  Others (e.g., error rate) are difficult to optimize directly, owing to non-differentiability or other complications. In these cases,
  it is common to optimize a **surrogate objective.**
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Typically, the loss function is defined with respect to the model’s parameters and depends upon the dataset. We learn the best 
 values of our model’s parameters by minimizing the loss incurred on a set consisting of some number of examples collected for training.
 However, doing well on the training data does not guarantee that we will do well on unseen data. So we will typically want to split the 
 available data into two partitions: the training dataset (or training set, for fitting model parameters) and the test dataset 
 (or test set, which is held out for evaluation), reporting how the model performs on both of them. You could think of training 
 performance as being like a student’s scores on practice exams used to prepare for some real final exam. Even if the results are 
 encouraging, that does not guarantee success on the final exam. In other words, the test performance can deviate significantly from 
 the training performance. When a model performs well on the training set but fails to generalize to unseen data, we say that it is ***overfitting.***
 In real-life terms, this is like flunking the real exam despite doing well on practice exams.
  
# Optimization Algorithms

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Once we have got some data source and representation, a model, and a well-defined objective function, we need an algorithm capable of searching for the best possible parameters for minimizing the loss function. Popular optimization algorithms for deep learning are based on an approach called gradient descent. In short, at each step, this method checks to see, for each parameter, which way the training set loss would move if you perturbed that parameter just a small amount. It then updates the parameter in the direction that may reduce the loss.


