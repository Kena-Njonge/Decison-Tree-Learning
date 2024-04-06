# Decision Tree Learning

<img src=".\Decision_Tree.png">

When it comes to the problem of weak AI i.e. agents that act intelligent but are not conscious, there are many approaches to acheiving the goal of intellligence depending on the task. Some tasks such as (some) games "only" need clever algorithms at run-time as to acheive this. The algorithms may be very rudimentary in some cases. For example in tic-tac-toe, we wouldn't even have to use clever algorithms like minimax or alpha-beta search; one could easily hard code the best move for each state. Search algorithms are paricularly efficient for a wide range of applications,given good heuristic functions. Nevertheless, some cases call for another tool entirely, such as planning or learning. Today, we will take a look at the latter.


Learning is the process of an agent improving its future performance by adapting its output based on a given percept sequence and knowledge about the world. Learning is an important tool as the perfect behavior for an agent may not be programmable. This can be due to a dynamic environment that prevents a programmer from implementing every possible action, e.g., the environment of a humanoid robot or the Mars exploration rovers, which can take steps of varying lengths. Or it may be due to a dynamic environment in which not every outcome is predictable, e.g., the stock market. Three forms of learning are common in artificial intelligence: supervised learning, unsupervised learning, and reinforcement learning. These types of learning differ in the form of feedback available for the agent. In supervised learning, both the input and output are available to the agent; reinforcement learning does not provide the output to the agent but provides feedback in the form of a reward or a punishment, and unsupervised learning does not provide any feedback. Decision Tree Learning is an inductive (supervised) form of learning where the agent learns a function based on given input-output pairs.

## Motivation

I was introduced to decision tree learning as part of the "Intro to AI" course in the previous semester and had seen and executed the basic algorithm by hand. I was interested in learning how it was implemented in popular modules such as scikit-learn and gaining insight into some higher-level concepts for decision trees that I hadn't been introduced to yet.

I completed a course on [Kaggle](https://www.kaggle.com/), "Intro to Machine Learning," in which I was introduced to the DecisionTreeRegressor class and learned some basics of model evaluation based on data from the Iowa housing market. My main goal for this project was to improve my proficiency in pandas, matplotlib, scikit-learn, and practice using the core functions. I wanted to do some plotting and modeling and gain insight from it.

As I continue learning, I may update this project or add other notebooks to this repository.


## Dependencies

This notebook uses the following dependencies. Please ensure you have Python installed. I used VS Code when writing down the execution instructions, so if you are not familiar with venvs, kindly download it; it provides a straightforward way to create them without having to use the command line. I will not rehash how to create a venv here. If you need a guide on that, please check the subsections "Setting up a venv", "What is a venv", and "Creating a venv" [here](https://github.com/Kena-Njonge/Grade_Analysis)

The dependencies will be installed when you create the venv.

- [Python](https://www.python.org/) (version 3.12.2 or later)
- [Pandas](https://pandas.pydata.org/) (version 2.2.1 or later)
- [Matplotlib](https://matplotlib.org/) (version 3.8.0 or later)
- [scikit-learn](https://scikit-learn.org/stable/) (version 1.3.0 or later)
- [Ipython Kernel](https://ipython.org/) (version 6.29.3 or later)
- [Numpy](https://numpy.org/) (version 1.26.4 or later)




## Decion Trees.

Decision Trees are a simple model, one of their main advantages is their explainability, as a user can clearly understand what steps were taken and what considerations there were in the generation of a certain output. They are also the basic building blocks for some more complicated models in data science, e.g., random forests. Decision Trees' main weakness is they are prone to overfitting; deep decision trees will capture noise and memorize data.


There are two types of decision trees: classifiers and regression-based decision trees. The differentiator between the two is if the value that we want to predict, our target, and our features are all discrete or if some are continuous. If the values are discrete, we can use classification; otherwise, we use regression. Apart from this, the methods for creating a model are pretty similar. The model is trained by splitting the training data based on some attribute. We choose the attribute that either maximizes or minimizes a target value, depending on the context. This selection could be based on criteria such as the Gini coefficient, Information Gain, or Mean Squared Error. Despite their limitations, decision trees have shown themselves to be very useful in the industry.

## The Dataset

The dataset that I will use in this notebook was provided by Anaconda as part of their "Data Analysis with Excel and Python course," which I completed. The course itself was mostly focused on showing that core Excel functionality such as pivot tables can just as easily be implemented in Python. For this, we used Pandas.

The dataset consists of 392 entries with 8 attributes. Each entry consists of data about a car, e.g., its name, how many miles per gallon it achieves, the year it was built, and its origin. The dataset was provided with no NaN rows or other peculiarities, so there was no preprocessing needed.
