<h1 align="center">IIT Jodhpur</h1>
<h2 align="center">Fraud Detection Project - Machine Learning</h2>

<p align="center">
  <img src="https://github.com/user-attachments/assets/c73094c2-10ed-45b7-a930-3201cc705995" alt="IIT Jodhpur Logo" />
</p>

**Name:** Vedant A. Pandya  
**Roll Number:** G24AIT181  
**Subject:** Machine Learning

---

## 1. Introduction

This project focuses on developing a Decision Tree model for fraud detection in loan applications. The objective is to classify applicants as either "Risky" or "Good" based on various features provided in the dataset.

## 2. Data Preprocessing

The dataset used for this project is 'Fraud_check.csv'. The following preprocessing steps were performed:

1. Creation of a 'Risk' column based on 'Taxable.Income':
   - If taxable income <= 30000, labeled as 'Risky'
   - Otherwise, labeled as 'Good'
2. Removal of irrelevant columns: 'City.Population' and 'Taxable.Income'

Python code for data preprocessing:

```python
import pandas as pd
import numpy as np

data = pd.read_csv('Fraud_check.csv')
data['Risk'] = np.where(data['Taxable.Income'] <= 30000, 'Risky', 'Good')
data = data.drop(['City.Population', 'Taxable.Income'], axis=1)
```

## 3. Exploratory Data Analysis

### 3.1 Risk Distribution

![Risk _Distribution](https://github.com/user-attachments/assets/019155be-d669-495a-b4a2-f223413d512d)

This bar chart illustrates the distribution of 'Risky' and 'Good' cases in the dataset. There is an imbalance between the two categories, with 'Good' cases outnumbering 'Risky' ones. This imbalance needs to be considered during model training to prevent bias.

### 3.2 Feature Correlation

![Correlation_Heatmap](https://github.com/user-attachments/assets/501a21e7-55df-4e5a-bd05-113c51e2c461)

The correlation heatmap shows the relationships between different features. There are no strong correlations between the features and the Risk category, which may present challenges in predictive modeling.

### 3.3 Feature Distributions

![Feature_Distributions](https://github.com/user-attachments/assets/b170f605-5597-4704-ad75-08a287263539)


These plots show the distribution of features for 'Risky' and 'Good' categories:

- Work Experience: 'Good' applicants tend to have slightly more work experience on average.
- Undergrad: Minor differences observed between risk categories.
- Marital Status: Shows some variation across risk categories.
- Urban: Similar distribution for both risk categories.

## 4. Decision Tree Implementation

The Decision Tree algorithm was implemented with the following structure:

```python
class DecisionTree:
    def __init__(self, max_depth=None, min_samples_split=2):
        self.max_depth = max_depth
        self.min_samples_split = min_samples_split
        self.root = None

    def fit(self, X, y):
        self.root = self._grow_tree(X, y)

    def _grow_tree(self, X, y, depth=0):
        # Recursive tree-growing logic implementation
        pass

    def predict(self, X):
        # Prediction logic implementation
        pass
```

## 5. Model Performance

The trained model achieved the following performance metrics:

- Accuracy: 84.17%
- Precision: 87%
- Recall: 84%

These metrics indicate a reasonably good performance for initial implementation, with room for improvement.

## 6. Conclusions

Key findings from this project include:

1. Work experience has some influence on risk assessment.
2. Marital status shows potential as a predictive feature.
3. The urban/rural distinction does not significantly impact risk classification.

## 7. Future Work

Potential areas for improvement and expansion include:

1. Implementation of ensemble methods such as Random Forests.
2. Collection of additional data, particularly for underrepresented groups.
3. Feature engineering to create more predictive variables.

---

**References:**
1. James, G., Witten, D., Hastie, T., & Tibshirani, R. (2013). An introduction to statistical learning. Springer New York.
2. Scikit-learn documentation: https://scikit-learn.org/stable/modules/tree.html
