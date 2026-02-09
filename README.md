# 🏥 NovaGen Labs: Predictive Health Risk Stratification

[cite_start]This project focuses on developing a robust predictive model for **NovaGen Research Labs** to classify individuals as "healthy" (0) or "unhealthy" (1) based on a dataset of 9,800 records[cite: 8, 11]. [cite_start]The primary goal is to support stratified analysis and participant selection for clinical trials[cite: 13].

## 🎯 The Core Challenge
[cite_start]NovaGen requires a consistent method to distinguish between healthy profiles and high-risk individuals[cite: 7]. In this biomedical context, **Recall** is our most critical metric. Missing a high-risk patient is dangerous; therefore, our models are optimized to minimize False Negatives.

## 🛠️ Dataset Features
[cite_start]The dataset includes a comprehensive mix of numerical and categorical indicators[cite: 10]:
* [cite_start]**Physiological:** Age, BMI, Blood Pressure, Cholesterol, Glucose, Heart Rate[cite: 19, 21, 23, 25, 27, 29].
* [cite_start]**Lifestyle:** Sleep, Exercise, Water Intake, Stress Level, Smoking, Alcohol, Diet[cite: 31, 33, 35, 37, 39, 41, 43].
* [cite_start]**Clinical:** Medical History, Allergies, Blood Group, and Diet Type[cite: 49, 51, 53, 56].

---

## 📊 Model Performance & Evaluation

I implemented and compared multiple Supervised Learning algorithms. Below are the results, ranked by their ability to identify "unhealthy" individuals (Recall).

### 🏆 Top Performer: Random Forest Classifier
* **Configuration:** 200 Estimators, `random_state=42`.
* **Accuracy:** 93.82%
* **Recall:** **95.88%** (Highest ability to catch high-risk cases).

### ⚡ Gradient Boosting Classifier
* **Configuration:** 150 Estimators, `learning_rate=0.1`, `max_depth=3`.
* **Accuracy:** 93.04%
* **Recall:** **94.98%**

### 🗳️ Voting Classifier (Soft Voting)
* **Configuration:** Ensemble of Logistic Regression, KNN, and Random Forest.
* **Accuracy:** 91.57%
* **Recall:** **92.97%**

### 📏 Baseline Models (Scaled Data)
* **K-Nearest Neighbors (KNN):** Accuracy 88.32% | Recall 88.35%
* **Logistic Regression:** Accuracy 81.41% | Recall 82.83%

---

## 💡 Key Takeaways
1. **Tree-Based Dominance:** Random Forest and Gradient Boosting outperformed distance-based and linear models significantly in both accuracy and recall.
2. **Recall Focus:** By achieving 95.88% recall with Random Forest, the model ensures that nearly all high-risk participants are flagged for the institute's longitudinal studies.
3. **Scaling Necessity:** Models like Logistic Regression and KNN required scaled features (`X_train_scaled`) to handle the vast differences in units between features like Blood Pressure (mmHg) and Water Intake (litres).



## ⚙️ How to Run
1. Clone this repository to your local machine.
2. Ensure you have the dataset `novagen_dataset.csv` in the same directory.
3. Install dependencies:
   ```bash
   pip install scikit-learn pandas numpy
