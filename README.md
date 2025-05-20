# 🍷 Classifier Evaluation on Spam Detection (SpamBase Dataset)

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Dataset](https://img.shields.io/badge/Dataset-UCI_SpamBase-orange.svg)

> This project compares the performance of three machine learning classifiers—**Logistic Regression**, **Support Vector Machine (SVM)**, and **Random Forest**—on the **SpamBase** dataset. The goal is to determine which algorithm performs best in detecting spam emails, using rigorous cross-validation and statistical testing.

---

## 📦 Dataset

The dataset used is the [SpamBase dataset](https://archive.ics.uci.edu/ml/datasets/spambase) from the UCI Machine Learning Repository.

### 🔄 How to Fetch

Install and use the `ucimlrepo` package:

```bash
pip install ucimlrepo
from ucimlrepo import fetch_ucirepo

# Fetch the dataset
spambase = fetch_ucirepo(id=94)

# Access features and targets
X = spambase.data.features
y = spambase.data.targets

# Dataset metadata
print(spambase.metadata)
print(spambase.variables)
```

---

# 📊 Evaluation Metrics

Each model is evaluated using the following metrics:

- ✅ **Accuracy**
- 🎯 **F1-Score**
- ⏱️ **Training Time**

---

# 🧪 Methodology

A **Stratified 10-Fold Cross-Validation** is applied:

1. Split the dataset into 10 stratified folds.
2. Train **Logistic Regression**, **SVM**, and **Random Forest** on each fold.
3. Measure **accuracy**, **F1-score**, and **training time**.
4. Rank the classifiers for each metric per fold.
5. Calculate:
   - **Mean & standard deviation** for each metric
   - **Overall average rank across metrics**

---

# 📈 Statistical Significance Testing

To determine whether differences between models are statistically significant:

- 🧮 **Friedman Test** is used to compare multiple algorithms across folds.
- 📐 **Nemenyi Post-hoc Test** evaluates pairwise significance.
- 🔍 **Critical Difference (CD)** is calculated and used to interpret the Nemenyi test results.

---

# 🧾 Output Summary

The code generates:

- 📊 **Average and standard deviation** of each metric for each classifier  
- 📋 **Fold-wise metrics and ranks**  
- 🏆 **Overall classifier ranking**  
- 📐 **Friedman and Nemenyi test results** with interpretation  

---

# ⚙️ Dependencies

Install required Python packages before running the code:

```bash
pip install numpy pandas scikit-learn tabulate ucimlrepo
```

---


## 🚀 Usage

Once dependencies are installed, run the Python script.  
Output will be displayed directly in the console, including **metrics**, **rankings**, and **statistical test results**.

---

## 📜 License

This project is licensed under the **MIT License**.

---

## 🙌 Acknowledgments

- [UCI Machine Learning Repository](https://archive.ics.uci.edu/)
- The Python open-source ML ecosystem

---

## 📫 Contact

For questions or feedback, reach out at:  
📧 **akhilsai96@gmail.com**




