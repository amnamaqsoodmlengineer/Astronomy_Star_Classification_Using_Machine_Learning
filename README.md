├── data/
│ └── star_classification.csv
├── images/
│ └── *.png
├── star_classification.ipynb
└── README.md

## 📁 Directory Structure

```bash
├── data/
│   └── star_classification.csv
├── images/
│   ├── class_distribution.png
│   ├── ra_dec_plot.png
│   ├── magnitude_histograms.png
│   ├── boxplots_by_class.png
│   └── confusion_matrix_random_forest.png
├── star_classification.ipynb
└── README.md


---

## ⚙️ Preprocessing

- Removed non-informative columns
- Encoded target variable
- Normalized features with `MinMaxScaler`
- Splitting using `train_test_split`

---

## 🤖 Model Evaluations

### 🔹 Classifier 1: K-Nearest Neighbors (KNN)

- **Accuracy**: `0.93`
- **Best Recall**: GALAXY → `0.96`
- **Lowest Recall**: QSO → `0.87`

📌 *Performs well with local neighborhood structure but struggles to distinguish QSOs clearly.*

![KNN Confusion Matrix](https://github.com/user-attachments/assets/6efef840-5305-4382-add7-f97d97369ead)

---

### 🔹 Classifier 2: Logistic Regression

- **Accuracy**: `0.93`
- **Highest Precision**: STAR → `0.94`
- **Lower Recall**: QSO → `0.83`

📌 *Fast and interpretable model; decent performance, but not suited for complex decision boundaries.*

![Logistic Regression Confusion Matrix](https://github.com/user-attachments/assets/176bddb1-e41d-424e-8ae2-18e0e9805974)

---

### 🔹 Classifier 3: Support Vector Machine (SVM)

- **Estimated Accuracy**: `~0.94`
- **Strength**: High recall for STAR
- **Weakness**: Confusion between GALAXY and QSO

📌 *Performs well with the right kernel, but tuning is crucial for class separation.*

*No confusion matrix available.*

---

### 🔹 Classifier 4: Random Forest

- **Accuracy**: `0.98`
- **Recall**: GALAXY → `0.99`, QSO → `0.92`, STAR → `1.00`

📌 *Best overall model. Excellent generalization, robust to outliers, and lowest class confusion.*

![Random Forest Confusion Matrix](https://github.com/user-attachments/assets/2af383d6-3851-4c88-8fae-b9480bd4a4f2)

---

## 📋 Results Comparison

| Model               | Accuracy | Precision | Recall | F1-Score |
|--------------------|----------|-----------|--------|----------|
| KNN                | 0.93     | 0.93      | 0.91   | 0.92     |
| Logistic Regression| 0.93     | 0.93      | 0.91   | 0.92     |
| SVM (RBF)          | ~0.94    | ~0.94     | ~0.92  | ~0.93    |
| Random Forest      | 0.98     | 0.98      | 0.97   | 0.98     |

---

## ✅ Conclusion

- 🔥 **Random Forest** is the most accurate and generalizable model, achieving **98% accuracy** and perfect classification for the **STAR** class.
- 🧠 **SVM** performed well but showed class overlap for QSO and GALAXY.
- ✅ **KNN** and **Logistic Regression** offer good baseline performance, but struggle with more nuanced patterns, particularly in the QSO class.

---

## 🏷️ Tags

`#MachineLearning` `#Astronomy` `#StarClassification` `#SDSS` `#Python`  
`#RandomForest` `#KNN` `#LogisticRegression` `#SVM` `#Classification`  
`#DataScience` `#SupervisedLearning` `#SkySurvey` `#AstroML`
