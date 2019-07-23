## Simple SPAM Detection using TF-IDF &amp; Logistic Regression

### Content
This repo contains:
- IPython script: `spam_classifier.ipynb`.
- List of the library need as prerequisites: `Requirements.txt`.
- Dataset: `Comment Spam.xls`.

### Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes:
- Clone this repo.
- Install the prerequisites.
- Run the ipython script.

### Prerequisites
- Install python
- Install `requirements.txt` using `pip`
```
pip install -r requirements.txt
```

### Data Pipeline
- Data Cleansing to remove special characters and transform the text to lowercase.
- Text preprocessing and tokenization using `CountVectorize` with stop_word='english' to filter the stopword. It builds a dictionary of features and transform texts to feature vectors. These steps to get the occurrences count of each word in the document/text.
- Data transforming using `TF-IDF`. Because of the difference in length of comments, longer comments will have higher average count values than shorter comments, even though they might talk about the same topics, TF-IDF was used to populate the number of occurrences of each word in a comment by the total number of words in the comment and also for weighting it in the whole comments that will be processed.
- Model Training using `LogisticRegression`. It used for predicting the 'Class' as it is most suitable for binary classification (after Data Transformation). Accuracy score of this model is `0.9138628213931487`.
- Classification Report

| | precision |  recall | f1-score | support |
|-| --------- | ------- | -------- | ------- |
| 0 | 0.94 | 0.95 | 0.95 | 139 |
| 1 | 0.94 | 0.93 | 0.94 | 121 |
| **avg / total** | **0.94** | **0.94** | **0.94** | **260** |

- Model Evaluation using `Cross Validation`.

| | Fold 1 | Fold 2 | Fold 3 | Fold 4 | Fold 5 |
|-| ------ | ------ | ------ | ------ | ------ |
| Score | 0.92 | 0.94 | 0.90 | 0.87 | 0.94 |

