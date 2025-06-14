# 🌿 NDVI-Based Land Cover Classification

This repository contains a solution for classifying land cover types using **Multinomial Logistic Regression** on NDVI time-series features extracted from satellite imagery. The project was developed as part of the **Summer Analytics First Hackathon**.

🛰️ Problem Statement

Given time-series NDVI (Normalized Difference Vegetation Index) data for various locations, predict the land cover category from the following classes:
- Water
- Impervious
- Farm
- Forest
- Grass
- Orchard

📁 Dataset

The following files are expected to be present in the `/kaggle/input/summer-analytics-mid-hackathon/` directory:
- `hacktrain.csv`: Training data with 27 NDVI time-point features and ground truth labels.
- `hacktest.csv`: Test data with the same NDVI features (without labels).

🧰 Tech Stack

- Python
- NumPy, Pandas
- Matplotlib, Seaborn
- Scikit-learn
- Statsmodels

🔍 Model Pipeline

1. **Preprocessing**
   - Missing NDVI values handled using mean imputation
   - Features scaled using `StandardScaler`
   - Class labels encoded using `LabelEncoder`

2. **Modeling**
   - `LogisticRegression` model (multinomial, `lbfgs` solver)
   - Hyperparameter tuning with `GridSearchCV`

3. **Evaluation**
   - Classification report with accuracy, precision, recall
   - Confusion matrix heatmap
   - Feature importance plot
   - PCA for class clustering
   - Seasonal decomposition of NDVI series

4. **Prediction**
   - Trained model is used to predict test data
   - Predictions are inverse transformed into class labels
   - Submission file is saved as `submission.csv`

📊 Sample Visualizations

- **Confusion Matrix**
- **Feature Importance**
- **PCA Clustering of Classes**
- **Seasonal Decomposition of NDVI Trends**

📤 Submission Format

```csv
ID,class
1,Water
2,Grass
3,Farm
....
