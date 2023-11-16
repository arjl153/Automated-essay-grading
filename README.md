# Automated-essay-grading

## Introduction

Essays are a significant expression of academic achievement, but manual grading is expensive and time-consuming. Our project focuses on developing an automated essay grading system using machine learning techniques to provide fast, effective, and affordable solutions. The goal is to compare the efficacy and cost of automated scoring systems to human graders.

## Problem Statement

The project aims to build an automated essay assessment system by classifying textual entities into discrete categories, representing possible scores. Machine learning regression techniques, including Word2Vec and TF-IDF models, are employed. Performance is evaluated using Cohen’s Kappa coefficient and Mean Absolute Error (MAE). The implementation is done in Python.

## Approach

- <strong>Dataset:</strong> Essays are sourced from the Hewlett Foundation's automated essay scoring competition, divided into eight sets for variability.
  
- <strong>Data Cleaning:</strong> The cleaned dataset contains 21,633 rows and 7 columns, with an essay length between 150 and 550 words.
  
- <strong>Automated Essay Grading:</strong> Relevant features are extracted from essays using Word2Vec and TF-IDF models. The quadratic weighted Kappa score measures inter-rater agreement.

## Preprocessing

- <strong>Dataset Structure:</strong> Each essay includes an ID, essay set, and tagged score. Preprocessing involves minimal modification to preserve essay originality.
  
- <strong>Text Processing:</strong> Stop words are removed, and stemming is performed on essays to reduce dimensionality.
  
- <strong>Linguistic Models:</strong>
  - <strong>Word2Vec:</strong> Vectorizes words in a corpus, generating vectors of size 300.
  - <strong>TF-IDF:</strong> Reflects word importance, outputting a dense vector of size 300 after dimensionality reduction using TruncatedSVD.

- <strong>Machine Learning Models:</strong>
  - <strong>SVR (Support Vector Regression):</strong> Utilized for both Word2Vec and TF-IDF models.
  - <strong>LSTM (Long Short-Term Memory):</strong> Used for both Word2Vec and TF-IDF models, trained over 50 epochs with a batch size of 64.

## Results

| NLP Approach | ML Models | Kappa Score | Time Taken |
|--------------|-----------|-------------|------------|
| Word2Vec     | SVR       | 0.874       | 100.389 s  |
| Word2Vec     | LSTM      | 0.958       | 286.935 s  |
| TF-IDF       | SVR       | 0.937       | 95.410 s   |
| TF-IDF       | LSTM      | 0.959       | 271.194 s  |

## Conclusion

- TF-IDF outperforms Word2Vec across both SVR and LSTM models.
- LSTM exhibits better performance than SVR, indicated by higher Kappa scores.

<em>Note: The closer the Kappa score is to 1, the greater the inter-rater agreement.</em>

## References

- [The Hewlett Foundation: Automated Essay Scoring](https://hewlett.org/newsroom/hewlett-foundation-sponsors-prize-to-improve-automated-scoring-of-student-essays/)
- [Automated Essay Grading Using Machine Learning: Manvi Mahana, Mishel Johns, Ashwin Apte, Stanford University](http://cs229.stanford.edu/proj2012/MahanaJohnsApte-AutomatedEssayGradingUsingMachineLearning.pdf)
