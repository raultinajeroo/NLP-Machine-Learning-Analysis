# :robot: NLP-Machine-Learning-Analysis
This repository contains a thorough analysis of different Machine Learning models and their capabilities in predicting wether a tweet is disaster related or not.

## **Table of Contents**
1. Introduction
2. Preparation
   - Libraries
   - Visualization
   - Data Preprocessing
3. Models
   - Logistic Regression
   - Random Forest
   - Suppor Vector Machines
   - Naïve Bayes
   - Convolutional Neural Network (One-Hot Encoded Location and Keyword Features)
   - Convolutional Neural-Network (Weighted Location and Keyword Features)
4.   Final Results
5.   Conclusion

## **Pre-requisites and Installation**
This project requires Python and the following Python libraries installed:

 NumPy
 Pandas
 Matplotlib
 scikit-learn
 Tensorflow
 Keras
 Seaborn
 NLTK
 Contractions
 
## **Data Overview**:
**Files**: train.csv and test.csv

**Features**:

      id - a unique identifier for each tweet
      text - the text of the tweet
      location - the location the tweet was sent from (may be blank)
      keyword - a particular keyword from the tweet (may be blank)
      target - in train.csv only, this denotes whether a tweet is about a real disaster (1) or not (0)
     
## **Final Results**

| Model       | Version | Train Accuracy | Val Accuracy | Test F1 Score |
| :-:         | :-      | :-:            | :-:          | :-:           |
| Log. Reg.   | 1.0     |      0.8549    |      0.7638  |       0.7821  |
|             | 2.0     |      0.8556    |    0.7607    |               |
|             | 3.0     |        0.8548  |       0.7680 |               |
|             | Fix     |       0.8734   |      0.7771  |               |
| Rand. F.    | 1.0     |        0.9840  |        0.7433|      0.77505  |
|             | 2.0     |          0.9841|       0.7593 |               |
| SVC         | LK      |    0.9049      |    0.7577    |    0.78976    |
|             | RBF     |      0.9531    |    0.7587    |               |
| Naïve Bayes | Multi   |      0.8633    |     0.7429   |     0.79098   |
|             | Bern    |      0.8693    |     0.7529   |               |
|             | Comp    |      0.8671    |     0.7469   |               |
| CNN         | (1-Hot) |     0.8512     |      0.7169  |       0.79098 |
|             |(W. Loss)|       0.8801   |       0.7465 |        0.80171|

## **Conclusion**
* Models used: Logistic Regression, Random Forest, Support Vector Machines, Naive Bayes, and two Convolutional Neural Networks (CNNs)
  - CNNs used text, keyword, and location features with different encoding techniques (1-Hot encoding and weighted representations)
  - CNN with weighted location and keyword representations achieved highest accuracy (>80% f1 score)
* Weighted representations captured more meaningful features
* 'text' feature has the highest correlation with accuracy
* SVC showed incredibly promising results, with a little more work it could possibly out do CNN's results
