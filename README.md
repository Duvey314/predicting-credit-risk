# Predicting Credit Risk

![credit risk](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4f/Credit-cards.jpg/330px-Credit-cards.jpg)


## Table of contents
* [Overview](#overview)
* [Logistic Regression Summary](#logistic-regression-summary)
* [Ensemble Classifier Summary](#ensemble-classifier-summary)
* [Challenges](#challenges)
* [Technology](#technology)

### Overview
Credit risk is an inherently unbalanced classification problem, as the number of good loans easily outnumber the number of risky loans. Therefore, you’ll need to employ different techniques to train and evaluate models with unbalanced classes. Jill asks you to use imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling. Your final task is to evaluate the performance of these models and make a recommendation on whether they should be used to predict credit risk.

The goals of this challenge are for you to:
* Implement machine learning models.
* Use resampling to attempt to address class imbalance.
* Evaluate the performance of machine learning models.


### Logistic Regression Summary

Random Oversampler - Using the Naive Random Oversampling method we started model with 51,366 low risk and high risk target values. This value is two orders of magnitude larger than our original value of high risk targets of 347. This resampled dataset resulted in a balanced accuracy score of 0.65, an average precision of 0.99, and an average recall of 0.57.

SMOTE - Using the SMOTE Oversampling method we started model with 246 low risk and high risk target values. This resampled dataset resulted in a balanced accuracy score of 0.55, an average precision of 0.99, and an average recall of 0.41.

Undersample - Using the SMOTEENN algorithm we started model with 51,366 low risk and high risk target values. This resampled dataset resulted in a balanced accuracy score of 0.65, an average precision of 0.99, and an average recall of 0.57.

SMOTEENN - Using the SMOTEENN algorithm we started model with 68,460 low risk and 62,011 high risk target values. This resampled dataset resulted in a balanced accuracy score of 0.65, an average precision of 0.99, and an average recall of 0.58.


Each method of resampling the data has a use case but not every method works for every case. The method of evaluation depends on the situation. Since we a trying to find high risk customers, the most important predictor is the recall score of the model. In this the naive random oversampler method is the best choice. It has an average recall score of 0.57 but a recall value of 0.73 for the high risk customers. The other methods had values of 0.63(SMOTE), 0.68(Undersampling), and 0.72(SMOTEENN). This value along with the accuracy score of 0.65 make it the best candidate for this situation.


### Ensemble Classifier Summary

Balanced Random Forest Classifier - The balanced random forest randomly under-samples each boostrap sample to balance it. This algorithm resulted in a balanced accuracy score of 0.79, an average precision of 0.99, and an average recall of 0.87. The most important features according to the model were the principal received to date (total_rec_prncp), payments received to date for total amount funded (total_pymnt), and the payments received to date for portion of total amount funded by investors (total_pymnt_inv).

Easy Ensemble AdaBoost Classifier - The AdaBoost classifier is a meta-estimator that begins by fitting a classifier on the original dataset and then fits additional copies of the classifier on the same dataset but where the weights of incorrectly classified instances are adjusted such that subsequent classifiers focus more on difficult cases. This algorithm resulted in a balanced accuracy score of 0.93, an average precision of 0.99, and an average recall of 0.94.

The better classifier in this case is certainly the AdaBoost classifier. The recall score of 0.92 for the high risk cases means that it is performs very strong at finding high risk loans. The accuracy score of 0.93 is also the highest of any of the other classifiers or resampling used.



### Challenges




### Technology



### Resources
*[Lending Club Data Dictionary](https://resources.lendingclub.com/LCDataDictionary.xlsx)
