# MultiOutputClassification_NLP
## Using statistical inferences &amp; NLP for multioutput classification problem


This time another interesting challenge raised in Kaggle about essay evaluation of Students as "Feedback Prize - English Language Learning".
The goal of this competition is to assess the language proficiency of 8th-12th grade English Language Learners (ELLs). Utilizing a dataset of essays written by ELLs will help to develop proficiency models that better supports all students.

Link to the competition : https://www.kaggle.com/competitions/feedback-prize-english-language-learning

This assessment includes 6 different categories such as **cohesion**, **syntax**, **vocabulary**,**phraseology**, **grammar**, **conventions**.
Some of the classes can be calculated based on the **statistical inferences** from text and some are semantic.
My approach for semantic inferences was **BERT model**. Then, adding othere statistial inferences such as 
* Counting the number of sentences
* Counting the number of unique words
* Counting number of unique phrases with two words
* Counting number of unique phrases with three words
* Counting the number of Part of Speech tags to evaluate complexity of text

By applying all of these approaches, there are 11 features which will be used to classify texts into 6 classes. (**Multiclass-multioutput classification**) 

Multiclass-multioutput classification (also known as multitask classification) is a classification task which labels each sample with a set of non-binary properties. Both the number of properties and the number of classes per property is greater than 2. A single estimator thus handles several joint classification tasks. This is both a generalization of the multilabel classification task, which only considers binary attributes, as well as a generalization of the multiclass classification task, where only one property is considered. For example, classification of the properties “type of fruit” and “colour” for a set of images of fruit. The property “type of fruit” has the possible classes: “apple”, “pear” and “orange”. The property “colour” has the possible classes: “green”, “red”, “yellow” and “orange”. Each sample is an image of a fruit, a label is output for both properties and each label is one of the possible classes of the corresponding property

For finding the proper machine learning algorithm to apply on last 11 features and classify the essays into 6 classes, I used Grid Search. I defined 7 different models with their related hyper parameters which are as follow:
* LinearRegression
* KNeighborsRegressor
* DecisionTreeRegressor
* RandomForestRegressor
* MultiOutputRegressor(LinearSVR())
* MultiOutputRegressor(GradientBoostingRegressor())
* MultiOutputRegressor(AdaBoostRegressor())

Please note than LinearSVR , GradientBoostingRegressor & AdaBoostRegressor can only be used for binary classification. So, I used MultiOutputRegressor over them to classify into multi classes.



