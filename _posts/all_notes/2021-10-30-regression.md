---
layout: post
title:  "Regressiong - ML"
date:   2021-10-30 09:29:20 +0700
categories: post
---

# How much? How many?

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
We might construct a table, where each row corresponds to a different house, and each column corresponds to some relevant attribute,
such as the square footage of a house, the number of bedrooms, the number of bathrooms, and the number of minutes (walking) 
to the center of town. In this dataset, each example would be a specific house, and the corresponding feature vector would be 
one row in the table. If you live in New York or San Francisco, and you are not the CEO of Amazon, Google, Microsoft, or Facebook,
the (sq. footage, no. of bedrooms, no. of bathrooms, walking distance) feature vector for your home might look something like:  [600,1,1,60]. 
However, if you live in Pittsburgh, it might look more like  [3000,4,3,10] . Feature vectors like this are essential for most 
classic machine learning algorithms.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
What makes a problem a regression is actually the output. Say that you are in the market for a new home. You might want to estimate 
the fair market value of a house, given some features like above. The label, the price of sale, is a numerical value. When labels
take on arbitrary numerical values, we call this a regression problem. Our goal is to produce a model whose predictions closely
approximate the actual label values.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Lots of practical problems are well-described regression problems. Predicting the rating that a user will assign to a movie can 
be thought of as a regression problem and if you designed a great algorithm to accomplish this feat in 2009, you might have won 
the 1-million-dollar Netflix prize. Predicting the length of stay for patients in the hospital is also a regression problem. 
**A good rule of thumb is that any how much? or how many? problem should suggest regression**, such as:

- How many hours will this surgery take?
- How much rainfall will this town have in the next six hours?

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Even if you have never worked with machine learning before, you have probably worked through a regression problem informally. 
Imagine, for example, that you had your drains repaired and that your contractor spent 3 hours removing gunk from your sewage pipes.
Then he sent you a bill of 350 dollars. Now imagine that your friend hired the same contractor for 2 hours and that he 
received a bill of 250 dollars. If someone then asked you how much to expect on their upcoming gunk-removal invoice you might make 
some reasonable assumptions, such as more hours worked costs more dollars. You might also assume that there is some base charge and 
that the contractor then charges per hour. If these assumptions held true, then given these two data examples, you could already 
identify the contractor’s pricing structure: 100 dollars per hour plus 50 dollars to show up at your house. If you followed that
much then you already understand the high-level idea behind linear regression.


 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Nikola Andrić
 
