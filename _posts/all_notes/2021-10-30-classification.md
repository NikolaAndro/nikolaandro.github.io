---
layout: post
title:  "Classification - ML"
date:   2021-10-30 09:29:20 +0700
categories: post
---

# Which one is it?

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
Given features of an example, our model assigns a probability to each possible class. Returning to our animal classification example where the classes are  {cat,dog} , a classifier might see an image and output the probability that the image is a cat as 0.9. We can interpret this number by saying that the classifier is 90% sure that the image depicts a cat. The magnitude of the probability for the predicted class conveys one notion of uncertainty. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
When we have more than two possible classes, we call the problem ***multiclass classification***. Common examples include hand-written character recognition  {0,1,2,...9,a,b,c,...} . While we attacked regression problems by trying to minimize the squared error loss function, ***the common loss function for classification problems is called cross-entropy***.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Now, assume that you built a classifier and trained it to predict if a mushroom is poisonous based on a photograph. Say our poison-detection classifier outputs that the probability that mushroom you found contains a death cap is 0.2. In other words, the classifier is 80% sure that our mushroom is not a death cap. Still, you would have to be a fool to eat it. That is because the certain benefit of a delicious dinner is not worth a 20% risk of dying from it. In other words, the effect of the uncertain risk outweighs the benefit by far. Thus, we need to compute the expected risk that we incur as the loss function, i.e., we need to multiply the probability of the outcome with the benefit (or harm) associated with it. In this case, the loss incurred by eating the mushroom can be  0.2 × ∞ + 0.8 × 0 = ∞ , whereas the loss of discarding it is  0.2 × 0 + 0.8 × 1 = 0.8 . Our caution was justified: as any mycologist would tell us, the mushroom actually is a death cap.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Nikola Andric
