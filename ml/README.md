# Predictive Model for Chronic Kidney Disease  
*Accurate early detection using machine learning*

---

## 📋 Feature Definitions

| Feature        | Description                          |
|----------------|------------------------------------|
| age            | Patient's age in years              |
| bp             | Blood pressure in mm/Hg             |
| sg             | Specific gravity of urine           |
| al             | Albumin level in urine (0–5)        |
| hemo           | Hemoglobin level in blood (g/dL)    |
| sc             | Serum creatinine level (mg/dL)       |
| htn            | Hypertension status (yes = 1, no = 0)|
| dm             | Diabetes mellitus status (yes = 1, no = 0)|
| cad            | Coronary artery disease status (yes = 1, no = 0)|
| appet          | Appetite condition (good = 1, poor = 0) |
| pc             | Pus cell status in urine (normal = 1, abnormal = 0) |
| classification | CKD diagnosis (ckd/notckd)         |

---

## 🧹 Data Cleaning and Preprocessing

- Missing values were imputed using mean/mode where appropriate.  
- Categorical variables encoded into numerical values (see Encoding section).  
- Numeric features standardized using MinMaxScaler for normalization.  
- Outliers detected and handled to prevent skewed results.  
- Class imbalance addressed with SMOTE to oversample minority class.

---

## 🗂️ Encoding Categorical Variables

| Feature | Encoding          |
|---------|-------------------|
| htn     | yes = 1, no = 0   |
| dm      | yes = 1, no = 0   |
| cad     | yes = 1, no = 0   |
| appet   | good = 1, poor = 0|
| pc      | normal = 1, abnormal = 0 |

---

## ⚖️ Scaling: Normalization

Numeric features (`age`, `bp`, `sg`, `al`, `hemo`, `sc`) were scaled to a 0–1 range using MinMaxScaler:

from sklearn.preprocessing import MinMaxScaler

numeric_cols = ['age', 'bp', 'sg', 'al', 'hemo', 'sc']
scaler = MinMaxScaler()
df[numeric_cols] = scaler.fit_transform(df[numeric_cols])



## ⚖️ Data Balancing

Class imbalance was handled with SMOTE oversampling:

from imblearn.over_sampling import SMOTE

X = df.drop('classification', axis=1)
y = df['classification']

smote = SMOTE(random_state=42)
X_balanced, y_balanced = smote.fit_resample(X, y)

---

## 🚶‍♂️ Workflow Steps

1. Data Cleaning and Preprocessing  
2. Fill missing values  
3. Encoding  
4. Scaling: Normalization  
5. Data Balancing  
6. Train Test Split  
7. Training, Testing Multiple Classifiers  
8. Selecting Best Model  
9. Saving Model, Encoder, Scaler for production  
10. Inference (Prediction on new data)  
11. Creating Streamlit App  
12. Deploy  

---

## 🤖 Models Used

- Logistic Regression  
- Support Vector Machine (SVC)  
- Random Forest Classifier  
- K-Nearest Neighbors (KNN)  
- Decision Tree Classifier  
- Gaussian Naive Bayes  
- AdaBoost Classifier  
- Gradient Boosting Classifier  

---

## 📈 Model Performance

| Model                      | Accuracy |
|----------------------------|----------|
| Logistic Regression         | 0.96     |
| Support Vector Classifier   | 0.97     |
| Random Forest Classifier    | 0.99     |
| K Nearest Neighbors         | 0.97     |
| Decision Tree Classifier    | 0.99     |
| Gaussian Naive Bayes        | 0.96     |
| AdaBoost Classifier         | 1.00     |
| Gradient Boosting Classifier| 0.99     |

---

## 🏆 Selecting Best Model

The **Gradient Boosting Classifier** was chosen as the best model due to:

- High accuracy (0.99) on test data.  
- Excellent precision, recall, and F1-scores for both classes.  
- Robust confusion matrix results:
[[54  0]
 [ 1 45]]
- Balanced performance minimizing false positives and false negatives.
- Strong generalization and flexibility for complex datasets.

## 🏆 Why Select Gradient Boosting Classifier?

- Balanced Performance: Gradient Boosting achieved very high accuracy (0.99) with excellent precision and recall, ensuring minimal false positives and false negatives — critical in medical diagnosis.

- Robustness: Compared to AdaBoost, which showed perfect accuracy on this test set, Gradient Boosting tends to generalize better and is less prone to overfitting, especially on limited data.

- Flexibility: Gradient Boosting offers more hyperparameter tuning options, allowing fine control over model complexity and performance.

- Consistency: While AdaBoost had a perfect score on this dataset, such results can sometimes be due to overfitting or the specific test split. Gradient Boosting’s performance is more consistent and reliable across varied data.

- Computational Efficiency: Gradient Boosting strikes a good balance between accuracy and training time, making it suitable for deployment scenarios.

Overall, Gradient Boosting was chosen for its reliability, robustness, and strong predictive power, making it the best fit for this CKD prediction task.

## 🚀 Running the Streamlit App

To run the app locally, use:

streamlit run app.py