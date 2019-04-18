---
layout: post
title: "Powering AI to Play Doom"
author: Akansha Vashisth
categories: Image Processing
tags: [Python, Image Processing, CNN]
image: /img/doom_copy.jpg
site: /knit/doom.html
image_alt: Doom
---

As a kid, this is a game I really enjoyed playing though my mom used to go wild as all she saw was the constantly firing barrel on the computer screen. Here AI is used to train the model to beat the game!


# What is Overfitting? 
## Why should we care about it?

Suppose you have to buy a christmas present for your niece Goldilocks. It has been very long since you visited her and the only thing you remember about her is that she is very picky about sizes. You decide to buy a sweater for her and the only problem is that you don't know her size. There are three possibilities while picking the sweater:

- You buy any sweater and hope she likes it.
- You try to roughly estimate her size and buy a sweater/poncho which will probably fit her.
- You put some extra thought into what was her favourite colour when she was a kid and what kind of animals she liked back then. After all the extra thoughts, you buy a pink panther sweater for her which you are sure that she would love.

What do you think happened when she opened the present on christmas morning? 

Well, she is not five anymore and hates pink colour. This is exactly what **overfitting** is. When you try to put extra parameters in the training set to perfectly fit with the machine learning model, it fails to deal with new data. The solution may look perfect at that particular time, but it is not designed for futuristic data set which may differ in some values. For example, Goldilocks's choice of colour did change in future. Hence the parameter of "choice of colour" was of no use. It is important to choose such parameters which are relevant for the whole generalised solution and not just for that training data.

What would have happened if you would have stopped at the second point and just bought a basic well estimated sized sweater? It might have fit her and she might have liked it. This is called a **good/appropriate fit** in machine learning. When you try to approximate the solution and give valid parameters in the training data, the generalised solution fits on many data sets.

Case where you bought any sweater without giving any thought into the gift is called **underfitting**. In this case, the parameters taken into account were very less. Hence the performance of the model to predict is poor in training set as well as new data point.

Let's dive into some data now. Consider the following table with values of x and y:

 | X | Y |
 |:----:|:----:|
 | 1 | 7 |
 | 2 | 8 |
 | 3 | 7 |
 | 4 | 13|
 | 5 | 16|
 | 6 | 15|
 | 7 | 19|
 | 8 | 23|
 | 9 | 18|
 | 10| 21|
 

We create a model and use these values to train the model. When we plot the values on a graph, we get the following :

![](https://chunml.github.io/images/tutorials/underfit-overfit/poly_1.jpg)

[source](https://chunml.github.io/images/tutorials/underfit-overfit/poly_1.jpg)

We get a model which roughly represents the data but with less accuracy. This falls under the category of underfitting.

To improve the model, we can add extra parameters/features in our model to fit the data. To add these features, we increase the degree of the polynomial used in the model. Increasing the degree of polynomial means that if we were using X in the training data, now we will be using $X^2, X^3, X^4..$. When we plot the graph with increased polynomial degree of $X^2$, we get the following :

![](https://chunml.github.io/images/tutorials/underfit-overfit/poly_2.jpg)

[source](https://chunml.github.io/images/tutorials/underfit-overfit/poly_2.jpg)

As you can see, the curve is fitting our training data better than previous graph. 

Since we got better results by increasing the degree of polynomial, what if we try to increase the degree of polynomial more than 2 and find even more accurate results this time?
Let's increase the degree to 9 and plot the graph now,

![](https://chunml.github.io/images/tutorials/underfit-overfit/poly_9.jpg)

[source](https://chunml.github.io/images/tutorials/underfit-overfit/poly_9.jpg)

We get a curve which fits the training data perfectly. But this could be like the pink panther sweater, where seemingly best case turned out to be totally different. To test it with new values of data, we add 5 new values to the existing data and analyse how the model behaves for new data points:

![](https://chunml.github.io/images/tutorials/underfit-overfit/poly_9_overfit.jpg)

[source](https://chunml.github.io/images/tutorials/underfit-overfit/poly_9_overfit.jpg)

Did you see what happened? The model fails for the new data set. This is called overfitting in machine learning. The model fits the training data so accurately when a lot of features are involved. The model tends to memorize the training data rather than learning from it. Hence it fails when any new data set is used with the model. Overfitting leads poor machine learning models which fails to fit in new data. 

The whole idea of any meachine learning model is to provide a generic solution which could fit new data. This is the main reason we should be careful while adding new features in the model. The idea is find the sweet spot between underfitting and overfitting which will make our model an appropriate fit for the current data and any new data.

To solve the problem of overfitting, we should split the data set into two : training data and testing data. Once we utilise the training data to train the model, we could test the model on the testing data and check the accuracy of the model.


To summarize the concept of overfitting, I found a perfect picture which is quite straight forward:
![](https://cdn-images-1.medium.com/freeze/max/1000/1*0eNrNhMkfRBBC2kP_Wp3zQ.jpeg?q=20)

[source](https://cdn-images-1.medium.com/freeze/max/1000/1*0eNrNhMkfRBBC2kP_Wp3zQ.jpeg?q=20)





**Citations:**

Images and concepts: https://chunml.github.io/ChunML.github.io/tutorial/Underfit-Overfit/
Image : https://gerardnico.com/data_mining/overfitting
https://machinelearningmastery.com/overfitting-and-underfitting-with-machine-learning-algorithms/
