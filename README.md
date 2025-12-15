# Senioritis-Diagnosis-via-Machine-Learning-Classifiers
Senioritis Diagnosis via Machine Learning Classifiers. which explores probabilistic and non-parametric classification methods for automated diagnosis of *Senioritis* using synthetic biomedical data.  The project compares multiple classifiers against the **ideal Bayes classifier** and evaluates performance using clinically meaningful metrics.

# 📁 Repository Structure

- `Exercise4.ipynb` — Fully executed Jupyter notebook (main submission)
- `SenioritisTrainingData.csv` — Training dataset
- `SenioritisTestData.csv` — Test dataset
- `README.md` — Project overview and explanation

---

## 🧪 Problem Overview

Medical researchers collected concentrations of two chemicals (ChemA, ChemB) from 400 students to diagnose Senioritis.  
The goal is to determine whether machine learning classifiers can accurately and reliably distinguish between:

- **Senioritis**
- **No Senioritis**

All classifiers are implemented **from scratch**, without high-level ML libraries.

---

## 🔹 What Was Implemented

### 1. Data Loading & Visualization
- Loaded training and test datasets
- Generated scatter plots with class-colored labels
- Inspected class overlap and separability in feature space

---

### 2. Classifier Training (From Scratch)

Implemented the following classifiers using first-principles probability and geometry:

- **Linear Discriminant Analysis (LDA)**  
  - Shared covariance assumption
  - Linear decision boundary

- **Quadratic Discriminant Analysis (QDA)**  
  - Class-specific covariance matrices
  - Quadratic decision boundary

- **Gaussian Naïve Bayes (GNB)**  
  - Feature independence assumption
  - Diagonal covariance structure

- **k-Nearest Neighbor (k-NN)**  
  - Euclidean distance
  - Evaluated initially with k = 3

---

### 3. Performance Evaluation (Test Data)

Each classifier was evaluated using:

- Empirical probability of error
- Confusion-matrix metrics:
  - True Positives (TP) & True Positive Rate (TPR)
  - False Positives (FP) & False Positive Rate (FPR)
  - True Negatives (TN) & True Negative Rate (TNR)
  - False Negatives (FN) & False Negative Rate (FNR)

These metrics reflect **real diagnostic tradeoffs**, not just accuracy.

---

### 4. Decision Boundary Visualization

Overlaid classification decision boundaries on training data for:

- LDA
- QDA
- Gaussian Naïve Bayes
- k-NN (k = 3)

This highlights how modeling assumptions reshape decision regions in feature space.

---

### 5. Ideal Bayes Classifier (Gold Standard)

- Implemented the **ideal Bayes classifier** using known true Gaussian parameters
- Derived the optimal decision boundary under 0–1 loss
- Used this boundary as a benchmark to compare learned classifiers
- Analyzed how closely each practical classifier approximates Bayes-optimal behavior

---

### 6. k-NN Bias–Variance Analysis

- Computed training and test error for k = 1 to 10
- Plotted training and test error curves on a single figure
- Observed:
  - Overfitting at small k
  - Underfitting at large k
- Selected an optimal k value for deployment based on generalization performance

---

### 7. Final Recommendation

- Compared classifiers based on sensitivity, specificity, and overall risk
- Recommended a classifier suitable for automated Senioritis diagnostics
- Justified selection using empirical metrics and decision-theoretic reasoning

---

## 📌 Key Takeaways

- Different classifiers impose different geometric and probabilistic assumptions
- Lowest error does not always imply best diagnostic performance
- The ideal Bayes classifier provides a principled benchmark for evaluation
- k-NN clearly illustrates the bias–variance tradeoff in practice

---

## 🛠️ Tools & Restrictions

- Implemented using: `numpy`, `pandas`, `scipy.stats`, `matplotlib`, `seaborn`
- No high-level ML libraries (e.g., scikit-learn) were used
- Notebook structure preserved per assignment instructions
- Submitted notebook is fully executed (Restart & Run All)
