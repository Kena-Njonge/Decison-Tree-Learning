# Decision Tree Learning

<img src=".\Decision-Tree.png">

Learning is the process of an agent improving its future performance by adapting its output based on a given percept sequence and knowledge about the world. Learning is an important tool as the perfect behavior for an agent may not be programmable. This can be due to a dynamic environment that prevents a programmer from implementing every possible action e.g. the environment of a humanoid robot or the Mars exploration rovers, which can take a step of 30cm or 20 cm etc., or a dynamic environment in which not every outcome is predictable e.g. the stock market. Three forms of learning are common when it comes to artificial intelligence, supervised learning, unsupervised learning, and reinforcement learning. These types of learning differ in the form of feedback that is available for the agent. When it comes to supervised learning both the input and output are available to the agent, reinforcement learning does not provide the output to the agent but provides feedback in the form of a reward or a punishment, and unsupervised learning does not provide any feedback. Decision Tree Learning is an inductive (supervised) form of learning where the agent learns a function based on given input-output pairs. 

## Motivation

I got an introduction to decision tree learning as part of the "Intro to AI" course in the previous semester and had seen and executed the basic algorithm by hand, I was interested in learning how it was implemented in popular modules such as scikit-kearn and gaining insight into some higher level concepts for decision trees that I hadn't been introduced to yet. 

I completed a course on Kaggle "Intro to Machine Learning" in which I was introduced to the DecisionTreeRegressor class and learned some basics of model evaluation based on data from the Iowa housing market. As I learn more, I may update this project, or add other notebooks to this repository.  



## Dependencies

This notebook uses the following. Please ensure you have Python and Java installed. I used VS code when writing down the execution instructions, so if you are not familiar with venvs kindly download it, it provides a very easy way to create them without having to use the command line. I will not rehash how to create a venv here. If you need a guide on that, please check the subsections "Setting up a venv", "What is a venv" and "Creating a venv" [here](https://github.com/Kena-Njonge/Grade_Analysis)

The dependencies will be automatically installed when you create the venv.

- [Python](https://www.python.org/) (version 3.12.2 or later)
- [Pandas](https://pandas.pydata.org/) (version 2.2.1 or later)
- [Matplotlib](https://matplotlib.org/) (version 3.8.0 or later)
- [scikit-learn](https://scikit-learn.org/stable/) (version 1.3.0 or later)
- [Ipython Kernel](https://ipython.org/) (version 6.29.3 or later)
- [Numpy](https://numpy.org/) (version 1.26.4 or later)




## Decion Trees.

Decision Trees are a simple model, one of their main advantages is their explainability as a user can clearly understand what steps were taken and what considerations there were in the generation of a certain output. They are also the basic building blocks for some more complicated models in data science e.g. random forests. Decision Trees are prone to overfitting and deep decision trees will capture noise and memorize data. 


There are two types of decision trees, classifiers, and regression-based decision trees. The differentiator between the two is if the value that we want to predict, our target, and our features are all discrete or if some are continuous. Apart from this the methods for creating a model are pretty similar. The model is trained by splitting the training data based on some (discrete or continuous) attribute. We choose the attribute that maximizes respectively minimizes a target value, this could be the Gini coefficient, the Information Gain, or the Mean Squared Error. Once the training is complete, we can use our decision tree to predict future outcomes. Despite their limitations, decision trees have shown themselves to be very useful in industry. 
## The dataset

The dataset that I will use in this notebook was provided by Anaconda as part of their "Data Analysis with Excel and Python course" which I completed. The course itself was mostly focused on showing that core Excel functionality such as pivot tables, can just as easily be implemented in Python. For this we used Pandas. 
