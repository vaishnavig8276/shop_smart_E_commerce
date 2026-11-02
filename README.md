# shop_smart_E_commerce

## 🚀 Model Architecture & Data Pipeline

This project features a fully automated, scalable machine learning pipeline built with Scikit-Learn. It seamlessly handles raw data processing and model training in a single workflow.

### 🏗️ Pipeline Diagram
```mermaid
flowchart TD
    subgraph Pipeline [Pipeline]
        direction TB
        subgraph Preprocess [preprocess: ColumnTransformer]
            direction TB
            num[num] --> SS(StandardScaler)
            cat[cat] --> OHE(OneHotEncoder)
        end
        SS --> DTC(DecisionTreeClassifier)
        OHE --> DTC
    end

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


## 🚀 Model Architecture & Data Pipeline

This project features a fully automated, scalable machine learning pipeline built with Scikit-Learn. It seamlessly handles raw data processing and model training in a single workflow:

* **Advanced Feature Preprocessing (`ColumnTransformer`):**
  * **Numerical Data (`num`):** Processed using `StandardScaler` to bring all features to a uniform scale.
  * **Categorical Data (`cat`):** Transformed using `OneHotEncoder` to convert text-based categories into a structured format.
* **Predictive Modeling:** The engineered features are fed into a `DecisionTreeClassifier` to make the final predictions.

---

## 💻 Model Prediction & Evaluation

To evaluate the model's performance on unseen data, we generated predictions using the trained pipeline and calculated key classification metrics.

### Implementation Code
```python
# Generate predictions on the test dataset
y_pred = pipe.predict(X_test)

# Output the evaluation metrics
print("F1 score:", f1_score(y_test, y_pred))
print("\nClassification Report:\n", classification_report(y_test, y_pred))
print("\nConfusion Matrix:\n", confusion_matrix(y_test, y_pred))
