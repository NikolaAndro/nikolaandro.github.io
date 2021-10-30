---
layout: post
title:  "Classification - ML"
date:   2021-10-30 09:29:20 +0700
categories: post
---

# Which one?

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
For example, a bank wants to add check scanning to its mobile app. This would involve the customer snapping a 
photo of a check with their smart phone’s camera and the app would need to be able to automatically understand 
text seen in the image. Specifically, it would also need to understand handwritten text to be even more robust,
such as mapping a handwritten character to one of the known characters. This kind of which one? problem is
called classification.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
In **classification**, we want our model to look at features, e.g., the pixel values in an image, and then predict
which category (formally called class), among some discrete set of options, an example belongs. For handwritten
digits, we might have ten classes, corresponding to the digits 0 through 9. The simplest form of classification
is when there are only two classes, a problem which we call ***binary classification***. For example, our dataset 
could consist of images of animals and our labels might be the classes  {cat,dog} . While in regression, 
we sought a regressor to output a numerical value, in classification, we seek a classifier, whose output 
is the predicted class assignment.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
