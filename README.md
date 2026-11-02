# shop_smart_E_commerce

## 🚀 Model Architecture & Data Pipeline

This project features a fully automated, scalable machine learning pipeline built with Scikit-Learn. It seamlessly handles raw data processing and model training in a single workflow:

* **Advanced Feature Preprocessing (`ColumnTransformer`):**
  * **Numerical Data:** Processed using `StandardScaler` to bring all features to a uniform scale, preventing any single feature from dominating the model due to large values.
  * **Categorical Data:** Transformed using `OneHotEncoder` to convert text-based categories into a structured, machine-readable format.
* **Predictive Modeling (`DecisionTreeClassifier`):** 
  * The engineered features are fed into a Decision Tree algorithm, which learns complex decision rules from the dataset to make highly accurate classifications.

---

## 📊 Performance & Evaluation Metrics

The model was rigorously tested on an unseen dataset of **2,466 records**, achieving a robust overall **Accuracy of 85%**. 

### 1. Classification Report
Here is the detailed breakdown of the model's predictive power:

| Metric | Class 0 | Class 1 |
| :--- | :---: | :---: |
| **Precision** | 0.97 | 0.50 |
| **Recall** | 0.85 | 0.83 |
| **F1-Score** | 0.90 | 0.63 |
| **Support** | 2084 | 382 |

* **Macro Average F1-Score:** 0.77
* **Weighted Average F1-Score:** 0.86

### 2. Confusion Matrix Insights
A deep dive into the model's exact prediction distribution across the test set:

* ✅ **True Negatives (1,771):** Model accurately predicted Class 0.
* ✅ **True Positives (318):** Model successfully detected Class 1.
* ⚠️ **False Positives (313):** Model incorrectly flagged Class 0 as Class 1.
* ⚠️ **False Negatives (64):** Model missed Class 1 and predicted Class 0.

### 💡 Key Takeaways
* **High Recall (83%):** The model is highly effective at identifying the minority class (Class 1), missing only 64 cases out of 382. 
* **Strong Baseline:** With a 97% precision for Class 0 and an 85% overall accuracy, the model provides a highly reliable foundation for this classification task.
