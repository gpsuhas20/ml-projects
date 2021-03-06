cseas/ml-projects
==============

Machine Learning projects using traditional algorithms.
- [Naive Bayes Mini Project](#naive-bayes-mini-project)
- [Support Vector Machines Mini Project](#support-vector-machines-mini-project)
- [Custom K Nearest Neighbors Classifier](#custom-k-nearest-neighbors-classifier)
- [Custom Decision Tree Classifier](#custom-decision-tree-classifier)
- [Deep Neural Network Classifier](#deep-neural-network-classifier)
- [Iris Flower Data Set](#iris-flower-data-set)
- [MNIST Data Set](#mnist-data-set)

## Naive Bayes Mini Project

[Code](https://github.com/cseas/ml-projects/tree/master/naive_bayes)

A couple of years ago, J.K. Rowling (of Harry Potter fame) tried something interesting. She wrote a book, “The Cuckoo’s Calling,” under the name Robert Galbraith. The book received some good reviews, but no one paid much attention to it--until an anonymous tipster on Twitter said it was J.K. Rowling. The London Sunday Times enlisted two experts to compare the linguistic patterns of “Cuckoo” to Rowling’s “The Casual Vacancy,” as well as to books by several other authors. After the [results of their analysis](http://languagelog.ldc.upenn.edu/nll/?p=5315) pointed strongly toward Rowling as the author, the Times directly asked the publisher if they were the same person, and the publisher confirmed. The book exploded in popularity overnight.

I've done something very similar in this project. We have a set of emails, half of which were written by one person and the other half by another person at the same company. Our objective is to classify the emails as written by one person or the other based only on the text of the email. I start with Naive Bayes in this mini-project, and then expand in later projects to other algorithms.

I start by getting a list of strings. Each string is the text of an email, which has undergone some basic preprocessing; I then use the code to split the dataset into training and testing sets.

One particular feature of Naive Bayes is that it’s a good algorithm for working with text classification. When dealing with text, it’s very common to treat each unique word as a feature, and since the typical person’s vocabulary is many thousands of words, this makes for a large number of features. The relative simplicity of the algorithm and the independent features assumption of Naive Bayes make it a strong performer for classifying texts. In this mini-project, I used Naive Bayes classifier from scikit-learn to classify emails by author.

## Support Vector Machines Mini Project

[Code](https://github.com/cseas/ml-projects/tree/master/svm)

In this mini-project, I tackle the exact same email author ID problem as the Naive Bayes mini-project, but now with an SVM. I clarify some of the practical differences between the two algorithms. I've also tuned parameters a lot more than in Naive Bayes. I compared the training and prediction times to Naive Bayes.

I concluded that Naive Bayes is great for text -- it’s faster and generally gives better performance than an SVM for this particular problem. Of course, there are plenty of other problems where an SVM might work better. Knowing which one to try when you’re tackling a problem for the first time is part of the art and science of machine learning. In addition to picking your algorithm, depending on which one you try, there are parameter tunes to worry about as well, and the possibility of overfitting (especially if you don’t have lots of training data).

## Custom K Nearest Neighbors Classifier

[Code](https://github.com/cseas/ml-projects/tree/master/custom_knn)

In this project, I wrote a simple implementation of the K Nearest Neighbors classifier, one of the simplest classifiers around. I've written my own version of the "fit" and "predict" functions for the KNeighborsClassifier class, replacing it by implementing a custom class, keeping the rest of the pipeline the same as scikit-learn. I implemented the KNN classifier with K as 1 and by finding the euclidian distances of the nearest points for predictions.

The pros of this method are that it is relatively easy to understand and works reasonably well for some problems. The basic con is that it is computationally intensive. It has to iterate over every training point to make a prediction. Also, it is hard to represent relationships between features in K Nearest Neighbors. A decision tree might be a better choice if we want the algorithm to understand the complex relationships between features and the label we're trying to predict. A neural network might be even better. However, if your features are linearly separable, then there's no need to use a neural network, although, it will still do the job.

## Custom Decision Tree Classifier
[Code](https://github.com/cseas/ml-projects/tree/master/custom_dt)

I've written a Decision Tree Classifier from scratch in pure Python. For this project, I've written a toy dataset that includes both numeric and categorical attributes.

Our goal is to predict the type or fruit, like an apple or a grape, based on features like colour and size.

Each row in the dataset is an example. The first two columns provide features or attributes that describe the data. The last column gives the label, or class we want to predict. We can modify the dataset by adding additional features or more examples, and the program will work in exactly the same way.

The dataset is written so that it's not perfectly separable. For example, there's no way to tell apart the second and fifth examples. They have the same features, but different labels. This is so we can see how our tree handles this case. The testing data is in the same format.

To build the tree, we use the Decision Tree Learning algorithm called CART (Classification And Regression Trees).

All nodes in the tree receive a list of rows as input. And the root will receive the entire training set. Each node will ask a true/false question about one of the features. The goal of the question is to unmix the labels as we proceed down the tree.

## Deep Neural Network Classifier

[Code](https://github.com/cseas/ml-projects/tree/master/dnn)

In this project, I've solved the Iris dataset using a Deep Neural Network Classifier in TensorFlow. Achieved a similar accuracy as with my earlier implementation of a [Custom K Nearest Neighbors Classifier](https://github.com/cseas/ml-projects/tree/master/custom_knn) with a relatively higher training time. I concluded that a neural network, although solved the problem, may not always be needed for problems of small scale.

## Iris Flower Data Set

[Code](https://github.com/cseas/ml-projects/tree/master/iris)

[Iris](https://en.wikipedia.org/wiki/Iris_flower_data_set) is a classic machine learning problem. In it, you want to identify what type of flower you have, based on different measurements like the length and width of the petal. The dataset includes three different types of flowers. They're all species of Iris - Setosa, Versicolor, and Virginica. We're given 50 examples of each type, so 150 examples in total. There are four features that are used to describe each example. These are the length and width of the sepal and petal.

I separated some testing data from the dataset and used the rest of the training data to train a Decision Tree classifier and predict values of the testing data. I also visualised a block diagram representation of the decision tree in pdf format. I concluded that every question the decision tree asks must be about one of your features. That means the better your features are, the better a tree you can build.

## MNIST Data Set

[Code](https://github.com/cseas/ml-projects/tree/master/mnist)

In this project, I've written an image classifier using TensorFlow. The problem is to classify handwritten digits from the MNIST Data Set. Writing a simple classifier for these is often considered the Hello World of Computer Vision.

MNIST is a multi-class classification problem. Given an image of a digit, our job is to predict which one it is.

I've used `matplotlib` to display images and `tensorflow` to train the classifier. The dataset contains thousands of labeled images of handwritten digits. It's pre-divided into train, which is 55,000 and test, which is 10,000.

The images are low resolution, just 28x28 pixels in grayscale. Each image contains exactly one digit.

When we're working with images, we use the raw pixels as features. A 28x28 image has 784 pixels, so we have 784 features. And here we're using the flattened representation of the image. To flatten an image means to convert it from a 2D array to a 1D array by unstacking the rows and lining them up.

The inputs and outputs are fully connected, and each of these edges has a weight. The weights are adjusted by gradient descent.

I trained and evaluated the model to get above 92% accuracy. We can easily get 99% with Deep Learning. I then visualized the weights the classifier learned, with the positive weights drawn in red, and negative weights drawn in blue.