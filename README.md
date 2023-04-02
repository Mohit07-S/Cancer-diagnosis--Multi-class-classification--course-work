# Cancer-diagnosis-Classification
Multi-class classification problem


Problem statement:
● Classify the given genetic variations/mutations based on evidence from text-based
clinical literature. (Classify given data into one of 9 classes)
Objective:
● Predict the probability of each data-point belonging to each of the nine classes.
Constraints:
● Errors can be very costly.
● Probability of a data-point belonging to each class is needed. (need answers in
probabilities)
● Interpretability is important.
● No low-latency requirement.
EDA:
● 2 files and both have one common column (id), merge both tables:
training_variants (ID , Gene, Variations, Class), training_text (ID, Text)
ML prob:
● Multi-class classification
Metrics:
● we need prob., good with imbalanced, and good with ML models.
● Multi log-loss (for probability answers), Confusion matrix, Precision, Recall (for
interpretability)
● Calculating mis-qualified points.
Imbalanced dataset (through output class)
Gene, variation are categorical data (used one hot encoding, response coding to convert
into numerical(vector))
Text is text data: pre-processing, encoding, use no. of occurrence, Normalizing each row
Gene & variation:
used no. of occurrence of each categories of gene & variation, apply LR with only
gene feature to know whether gene is useful variable or not
(compare with random model performance) & same applied for variation feature as
well.
What I have done:
● Maintaining the same distribution of output variable, even after splitting data into
train, test and cv.
● Apply a random model to check the worst performance (minimum required value).
Will use it to compare with other models.

Modeling:
works well with high dimensions:
1) LR with balancing, without balancing along with one hot encoding and sgd classifier(good
with large dataset).
2) Linear svm with balancing, one hot encoding, and sgd.
Not works well with high dimensions:
3) Random forest with one hot (powerful model, so tried it out)
Tried stacking as well:
4) LR + Linear svm + Naive bayes with one hot.
Conclusion:
Out of all models, LR with balancing along with one hot gives the best result in terms of:
log loss, no. of misqualified points(mostly), interpretability.

Conclusion:
Out of all models, LR with balancing along with one hot gives the best result in terms of:
log loss, no. of misqualified points(mostly), interpretability.
