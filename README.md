# 🌌 Astronomy Star Classification Using Machine Learning

[![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange?logo=scikit-learn)](https://scikit-learn.org/)
[![pandas](https://img.shields.io/badge/Pandas-DataFrame-green?logo=pandas)](https://pandas.pydata.org/)
[![Status](https://img.shields.io/badge/Status-Completed-brightgreen)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## 🚀 Project Overview
Astronomers study celestial bodies such as **stars**, **galaxies**, and **quasars (QSOs)** using large datasets captured by telescopes. This project aims to automate the classification of these celestial objects using supervised machine learning techniques.

### 🧠 Objective
Build a robust machine learning model that classifies objects into:
- ⭐ **STAR**
- 🌌 **GALAXY**
- 🔭 **QSO (Quasi-Stellar Object)**

---

## 📊 Dataset Description

**Source**: Sloan Digital Sky Survey (SDSS)  
**File**: `star_classification.csv`

Each entry includes:
- `u`, `g`, `r`, `i`, `z`: Apparent magnitudes in photometric bands
- `alpha`, `delta`: Spatial coordinates
- `redshift`: Light displacement
- `class`: Target label (GALAXY, QSO, STAR)
- Plus observation metadata (removed in preprocessing)

---

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
```

## Classifier 1: K-Nearest Neighbors (KNN)
Key Metrics:
- Accuracy: 0.93
- Highest Recall: Class 0 (GALAXY) - 0.96
- Lowest Recall: Class 1 (QSO) - 0.87
![K-Nearest Neighbors](images/K-Nearest%20Neighbors.png)



## Classifier 2: Logistic Regression
Key Metrics:
- Accuracy: 0.93
- Class 2 (STAR) had the highest precision: 0.94
- QSO had relatively lower recall: 0.83

![Logistic Regression](images/Logistic%20Regression.png)


## Classifier 3: Support Vector Machine (SVM)
Expected high performance on Class 2 (STAR) and moderate confusion between GALAXY vs QSO.

## Classifier 4: Random Forest
Key Metrics:
- Accuracy: 0.98
- STAR detection: Perfect (Recall: 1.00, Precision: 0.99)
- Lowest confusion overall compared to other models

![Random Forest](images/Random%20Forest.png)



## Conclusion
Random Forest Classifier outperformed all other models, achieving an overall accuracy of 98%. It demonstrated excellent class-wise performance, with a recall of 99% for GALAXY, 92% for QSO, and a near-perfect 100% for STAR. The high recall and precision across all classes indicate that the model generalizes well and is robust against class imbalance or feature noise. This makes Random Forest the most reliable model for this multi-class classification task.
The SVM classifier also showed strong performance, achieving 94% accuracy, with especially good results for the STAR class, where it attained a recall of 99%. However, it underperformed in classifying QSO, with a slightly lower recall of 86%, indicating some difficulty in capturing the nuances of that class.
K-Nearest Neighbors and Logistic Regression each achieved 93% accuracy, showing nearly equivalent performance. These models exhibited strong recall for the GALAXY and STAR classes, but, like SVM, struggled more with the QSO class. This suggests that simpler models such as logistic regression or instance-based methods like KNN may not capture the complex relationships and boundaries that distinguish QSOs from other celestial bodies.
