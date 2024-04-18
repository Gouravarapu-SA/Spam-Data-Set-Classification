# Classifiers Evaluation

This code evaluates the performance of three classification models: Logistic Regression, Support Vector Machine (SVM), and Random Forest, on a spam email classification task using the SpamBase dataset.

## Dataset

The dataset used is the `spambase.data` file, which contains email features and a binary label indicating whether the email is spam or not spam. You can fetch the dataset using the `ucimlrepo` package:

pip install ucimlrepo
from ucimlrepo import fetch_ucirepo

# fetch dataset
spambase = fetch_ucirepo(id=94)

# data (as pandas dataframes)
X = spambase.data.features
y = spambase.data.targets

# metadata
print(spambase.metadata)

# variable information
python print(spambase.variables) 

# Evaluation Metrics
The performance of the classifiers is evaluated using the following metrics:

- Accuracy
- F1-Score
- Training Time

# Methodology
The code performs a stratified 10-fold cross-validation on the dataset. For each fold, the following steps are performed:

1. Split the data into training and testing sets.
2. Train the three classifiers (Logistic Regression, SVM, and Random Forest) on the training set.
3. Evaluate the performance of the classifiers on the testing set using the above metrics.
4. Rank the classifiers based on their performance for each metric.

After all folds, the code calculates the average and standard deviation of each metric across the folds. It also calculates the overall ranking of the classifiers based on the average ranking across all metrics.

# Statistical Tests
The code applies the Friedman test and the Nemenyi post-hoc test to determine if there are significant differences between the classifiers for each metric (accuracy, F1-score, and time). The critical difference for the Nemenyi test is calculated and used to identify pairwise significant differences between classifiers.

# Output
The code outputs the following:

- Average and standard deviation of each metric for each classifier.
- Fold-wise performance data for each metric and classifier.
- Fold-wise ranking data for each metric and classifier.
- Overall ranking of classifiers based on the average ranking across all metrics.
- Results of the Friedman and Nemenyi tests for each metric.

# Usage
To run the code, make sure you have the following dependencies installed:

- NumPy
- Pandas
- scikit-learn
- tabulate
- ucimlrepo

Run the code, and the output will be printed to the console.


