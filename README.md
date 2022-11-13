# MultiOutputClassification_NLP
Using statistical inferences &amp; NLP for multioutput classification problem


This time another interesting challenge raised in Kaggle about essay evaluation of Students as "Feedback Prize - English Language Learning".
The goal of this competition is to assess the language proficiency of 8th-12th grade English Language Learners (ELLs). Utilizing a dataset of essays written by ELLs will help to develop proficiency models that better supports all students.
This assessment includes 6 different categories such as 'cohesion', 'syntax', 'vocabulary','phraseology', 'grammar', 'conventions'.
Some of the classes can be calculated based on the statistical inferences from text and some are semantic. So, better to extract semantic features by semantic models.
My approach for semantic inferences was BERT model. Then, adding othere statistial inferences to classify all essays into 6 classes.

For finding the proper machine learning algorithm to apply on last features, I used Grid Search. List of suitable algorithms with related hyper parameters are defined. At the end, the proper algorithm with best hyper parameters was chosen which results in better performance.


