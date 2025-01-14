---
layout: post
title:  "Unsupervised and Self-Supervised Learning - ML"
date:   2021-10-30 09:29:20 +0700
categories: post
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
All the examples so far were related to supervised learning, i.e., situations where we feed the model a giant dataset containing both 
the features and corresponding label values. You could think of the supervised learner as having an extremely specialized job and an 
extremely banal boss. The boss stands over your shoulder and tells you exactly what to do in every situation until you learn to map 
from situations to actions. Working for such a boss sounds pretty lame. On the other hand, it is easy to please this boss. You just 
recognize the pattern as quickly as possible and imitate their actions.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
In a completely opposite way, it could be frustrating to work for a boss who has no idea what they want you to do. However, if you 
plan to be a data scientist, you had better get used to it. The boss might just hand you a giant dump of data and tell you to do some
data science with it! This sounds vague because it is. We call this class of problems unsupervised learning, and the type and number 
of questions we could ask is limited only by our creativity. We will address unsupervised learning techniques in later chapters. 
To whet your appetite for now, we describe a few of the following questions you might ask.

- Can we find a small number of prototypes that accurately summarize the data? Given a set of photos, can we group them into landscape 
photos, pictures of dogs, babies, cats, and mountain peaks? Likewise, given a collection of users’ browsing activities, can we group 
them into users with similar behavior? This problem is typically known as clustering.
- Can we find a small number of parameters that accurately capture the relevant properties of the data? The trajectories of a ball 
are quite well described by velocity, diameter, and mass of the ball. Tailors have developed a small number of parameters that
describe human body shape fairly accurately for the purpose of fitting clothes. These problems are referred to as subspace 
estimation. If the dependence is linear, it is called principal component analysis.
- Is there a representation of (arbitrarily structured) objects in Euclidean space such that symbolic properties can be well matched? 
This can be used to describe entities and their relations, such as “Rome”  −  “Italy”  +  “France”  =  “Paris”.
- Is there a description of the root causes of much of the data that we observe? For instance, if we have demographic data about 
house prices, pollution, crime, location, education, and salaries, can we discover how they are related simply based on 
empirical data? The fields concerned with causality and probabilistic graphical models address this problem.
- Another important and exciting recent development in unsupervised learning is the advent of generative adversarial networks.
These give us a procedural way to synthesize data, even complicated structured data like images and audio. The underlying statistical
mechanisms are tests to check whether real and fake data are the same.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
As a form of unsupervised learning, self-supervised learning leverages unlabeled data to provide supervision in training, 
such as by predicting some withheld part of the data using other parts. For text, we can train models to “fill in the blanks” 
by predicting randomly masked words using their surrounding words (contexts) 
in big corpora without any labeling effort! For images, we may train models to tell the relative 
position between two cropped regions of the same image [Doersch et al., 2015](https://www.cv-foundation.org/openaccess/content_iccv_2015/papers/Doersch_Unsupervised_Visual_Representation_ICCV_2015_paper.pdf).
In these two examples of self-supervised learning,
training models to predict possible words and relative positions are both classification tasks (from supervised learning).

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
The Squid
