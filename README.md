# Machine-Learning---2
Classification
# 📊 Social Network Ads Classification Project

## 📁 Dataset Overview
The dataset `Social_Network_Ads.csv` contains information about users and their purchase behavior on social network advertisements. It includes the following columns:

| Column           | Description                          |
|------------------|------------------------------------|
| User ID          | Unique identifier for each user    |
| Gender           | Male or Female                     |
| Age              | Age of the user                    |
| EstimatedSalary  | Estimated annual salary            |
| Purchased        | Target variable (0 = No, 1 = Yes) |

### 🧾 Sample Data

| User ID  | Gender | Age | EstimatedSalary | Purchased |
|----------|--------|-----|-----------------|-----------|
| 15624510 | Male   | 19  | 19000           | 0         |
| 15810944 | Male   | 35  | 20000           | 0         |
| 15668575 | Female | 26  | 43000           | 0         |
| 15603246 | Female | 27  | 57000           | 0         |
| 15804002 | Male   | 19  | 76000           | 0         |

---

## 🔍 Exploratory Data Analysis (EDA)

### 🔄 Data Preprocessing
- **Binary Encoding** applied to categorical features (e.g., Gender encoded as Female=0, Male=1).
- **Standardization** of numerical features (Age and EstimatedSalary) before modeling.

### 📊 Correlation Matrix Summary
| Feature Pair             | Correlation Coefficient | Interpretation                      |
|--------------------------|-------------------------|-----------------------------------|
| Purchased & Age          | **0.62**                | Moderately strong positive        |
| Purchased & EstimatedSalary | 0.36                  | Weak positive                     |
| Purchased & Gender       | -0.04                   | Very weak negative                |
| Age & EstimatedSalary    | 0.16                    | Weak positive                    |
| Gender & Age             | -0.07                   | Very weak negative                |
| Gender & EstimatedSalary | -0.06                   | Very weak negative                |

- The strongest predictor for purchase is **Age**, followed by EstimatedSalary.
- Gender shows almost no linear relationship with the target variable.

---

## ⚙️ Classification Models & Performance

### Models Tested:
- Gaussian Naive Bayes
- K-Nearest Neighbors (K=3, 5, 7)
- Decision Tree (Gini criterion)
- Decision Tree (Entropy criterion)

### 📈 Accuracy Overview
| Model                     | Accuracy |
|---------------------------|----------|
| Gaussian Naive Bayes       | 93%      |
| K-Nearest Neighbors (K=3) | 91%      |
| K-Nearest Neighbors (K=5) | 92%      |
| K-Nearest Neighbors (K=7) | 93%      |
| Decision Tree (Gini)       | 84%      |
| Decision Tree (Entropy)    | 84%      |

---

### 🔍 Detailed Model Insights

#### Gaussian Naive Bayes
- **Class 0 (Not Purchased):**
  - Precision: 0.92  
  - Recall: 0.97  
  - F1-score: 0.95  
- **Class 1 (Purchased):**
  - Precision: 0.94  
  - Recall: 0.86  
  - F1-score: 0.90  
- Strength: Excellent at identifying non-purchasers; slight miss rate on actual purchasers.

#### K-Nearest Neighbors (K=7)
- **Class 0 (Not Purchased):**
  - Precision: 0.97  
  - Recall: 0.92  
  - F1-score: 0.94  
- **Class 1 (Purchased):**
  - Precision: 0.88  
  - Recall: 0.95  
  - F1-score: 0.91  
- Strength: Very good at identifying actual purchasers, minimizing false negatives.

#### Decision Trees (Gini & Entropy)
- Accuracy: 84% for both
- Moderate precision and recall for Class 0, weaker for Class 1.
- Struggled more with identifying purchasers, with more false negatives.

---

## 🔎 Model Selection Recommendations

- **Top performers:** Gaussian Naive Bayes and K-Nearest Neighbors (K=7), both with 93% accuracy.
- **If minimizing false negatives on purchasers is a priority:**  
  Choose **K-Nearest Neighbors (K=7)** due to higher recall (0.95) for Class 1.
- **If balanced performance is preferred:**  
  Choose **Gaussian Naive Bayes**, which has better recall on Class 0 and strong overall precision.

---

## 📌 Conclusion
This classification analysis demonstrates the importance of feature preprocessing and model selection. Age is the most influential factor in predicting purchases, with estimated salary also contributing. KNN (K=7) and Gaussian Naive Bayes offer robust and reliable performance for this task.

---

> 🔚 End of Report
