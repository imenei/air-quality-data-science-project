#  Air Quality Prediction & Classification — UCI Dataset

A complete machine learning project for predicting and classifying **C6H6 (Benzene)** gas concentration using the **AirQualityUCI** dataset collected in Italy between March 2004 and February 2005.

---

##  Project Structure

```
├── air-Quality.ipynb           # Main notebook     
└── README.md
```

---

##  Objectives

- **Regression** : Predict the continuous concentration of C6H6(GT) from air quality sensor data
- **Binary Classification** : Classify C6H6 levels as *Low* / *High*
- **Multi-class Classification** : Classify C6H6 levels as *Low* / *Medium* / *High*

---

## Project Description

This project is a comprehensive analysis of air quality data from the **AirQualityUCI** dataset (UCI Machine Learning Repository), collected in Italy between March 2004 and February 2005. The main objective is to predict and classify the concentration of **C6H6 (Benzene)** gas using data from chemical sensors and environmental measurements.

### Data Preparation & Cleaning
The raw dataset presented several quality issues: missing values encoded as `-200`, unusable columns, incorrect data types, and duplicates. A complete cleaning pipeline was implemented including:
- Removal of non-exploitable variables (`NMHC(GT)`, empty columns)
- Date/time conversion and parsing
- Extraction of temporal features (year, month, day, hour, minute, second)
- Replacement of aberrant values with `NaN` and imputation via **linear interpolation**
- Duplicate removal
- **StandardScaler normalization** to homogenize feature scales

### Exploratory Data Analysis (EDA)
An in-depth visual exploration was conducted using distribution histograms, a **correlation matrix** (heatmap), boxplots for outlier detection, and a skewness analysis of feature distributions.

### Regression Modeling
Three supervised regression models were trained to predict the continuous C6H6 concentration:
- **Linear Regression**
- **Support Vector Regression (SVR)**
- **Random Forest Regressor**

Models were evaluated using **R², RMSE, and MAE** metrics, compared on train/test sets, and benchmarked in terms of **training and prediction time**.

### Binary Classification
The target variable was discretized into two classes (*Low / High*) based on the median. Four classification algorithms were applied:
- **Naive Bayes**
- **SVM (SVC)**
- **K-Nearest Neighbors (KNN)**
- **Decision Tree** (with decision boundary visualization using PCA 2D)

Each model was evaluated via a classification report, a **confusion matrix**, and a **ROC curve with AUC score**.

### Multi-class Classification
A finer segmentation into three levels (*Low / Medium / High*) was performed using 33rd and 66th percentile thresholds. The **SVM model with RBF kernel** was used with a full multi-class evaluation including a **per-class ROC curve** and a **2D PCA projection** to visualize class separation in a reduced space.

---

##  Models Summary

### Regression
## Regression Model Performance

| Model | R² | RMSE | MAE |
|---|---|---|---|
| Linear Regression | 0.9849 | 0.1243 | 0.0852 |
| Random Forest | 0.9997 | 0.0183 | 0.0047 |
| SVR | 0.9951 | 0.0710 | 0.0416 |

**Insight:** Random Forest achieved the best performance with near-perfect R² and minimal error, indicating strong non-linear modeling capability.

 ## Binary Classification Performance
| Model               | Train Accuracy | Test Accuracy | F1-score (weighted) |
| ------------------- | -------------- | ------------- | ------------------- |
| Decision Tree       | 1.00           | 1.00          | 1.00                |
| K-Nearest Neighbors | 0.97           | 0.96          | 0.96                |
| SVM                 | 0.98           | 0.98          | 0.98                |
| Naive Bayes         | 0.92           | 0.91          | 0.91                |


**Insight:** Decision Tree achieved perfect accuracy for binary classification, while SVM and KNN also performed very well. Naive Bayes showed slightly lower performance but remains solid.

## Multi-class Classification Performance (SVM) 
| Model | Train Accuracy | Test Accuracy | F1-score (weighted) |
| ----- | -------------- | ------------- | ------------------- |
| SVM   | 0.97           | 0.96          | 0.96                |



---

## 📈 Visualizations

- Feature distribution histograms
- Correlation matrix heatmap
- Boxplots for outlier detection
- ROC curves + AUC scores per model
- Confusion matrices
- Real vs Predicted scatter plots
- Model performance comparison (bar chart)
- 2D PCA projection of classes
- PCA visualization 

---

## 🚀 How to Run

### 1. Open in Google Colab
Open `air-quality.ipynb` directly in [Google Colab](https://colab.research.google.com/).

### 2. Upload the dataset
Upload `AirQualityUCI.csv` to your Colab session or mount your Google Drive.

### 3. Run all cells
Go to **Runtime → Run all**

### 4. Download the dataset
Available at [UCI ML Repository — Air Quality](https://archive.ics.uci.edu/ml/datasets/Air+Quality)

---

## 🛠️ Technologies & Libraries

| Category | Tools |
|---|---|
| Language | Python 3 |
| Data Manipulation | pandas, numpy |
| Visualization | matplotlib, seaborn |
| Machine Learning | scikit-learn |
| Environment | Google Colab |

---

## 📂 Dataset

- **Source** : [UCI Machine Learning Repository — Air Quality](https://archive.ics.uci.edu/ml/datasets/Air+Quality)
- **Features** : CO, NOx, NO2, C6H6, O3, Temperature, Relative Humidity, Absolute Humidity, PT08.S1–S5 sensors

---

