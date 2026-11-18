# Customer Churn Prediction Using Machine Learning

## Project Overview

Customer churn is one of the major challenges faced by subscription-based businesses. Losing existing customers can affect revenue and long-term business growth.

This project focuses on developing a Machine Learning model to predict whether a customer is likely to discontinue their subscription.

The objective is to identify potential churn customers, understand the factors associated with customer churn, and provide data-driven recommendations to improve customer retention.

## Dataset

**Dataset:** IBM Telco Customer Churn

**Source:** [Kaggle – Telco Customer Churn Dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

- Total Records: 7,043 customers
- Target Variable: `Churn`
- Features include customer demographics, subscription services, contract type, tenure, payment methods, and charges.

*Note: This project uses a telecommunications dataset as a sample subscription-business use case. It does not contain actual digital newspaper subscriber data.*

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
- Joblib

## Project Workflow

### 1. Data Collection and Understanding
- Loaded the IBM Telco Customer Churn dataset.
- Examined dataset dimensions, columns, and data types.
- Identified missing values and potential data quality issues.

### 2. Data Cleaning and Preprocessing
- Converted `TotalCharges` into numeric format.
- Handled missing values using SimpleImputer.
- Applied StandardScaler to numerical features.
- Applied OneHotEncoder to categorical features.
- Used a ColumnTransformer and Pipeline for preprocessing.

### 3. Exploratory Data Analysis (EDA)
- Analysed customer churn distribution.
- Examined customer tenure and contract types.
- Investigated payment methods and subscription services.
- Identified patterns associated with customer churn.

### 4. Feature Engineering
Created additional features:
- `TenureGroup`: Categorised customers according to subscription duration.
- `TotalServices`: Counted the number of subscribed services.

### 5. Model Building

Implemented and compared three Machine Learning algorithms:

1. Logistic Regression
2. Decision Tree Classifier
3. Random Forest Classifier

Also experimented with class weighting to improve the detection of churn customers.

### 6. Model Evaluation

Evaluated model performance using:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC Score
- Confusion Matrix

## Model Performance

The following table compares the three initial models and the Balanced Logistic Regression model.

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 79.84% | 65.10% | 51.87% | 57.74% | 84.21% |
| Decision Tree | 74.30% | 51.70% | 48.90% | 50.30% | 66.20% |
| Random Forest | 77.50% | 60.10% | 45.50% | 51.80% | 81.90% |
| **Balanced Logistic Regression** | **73.31%** | **49.83%** | **79.14%** | **61.16%** | **84.20%** |

### Selected Model: Balanced Logistic Regression

The Balanced Logistic Regression model was selected as the preferred candidate because it achieved the highest recall and F1 score among the four tested models.

It identified approximately 79% of actual churn customers in the test dataset.

Although its accuracy and precision were lower than the original Logistic Regression model, it demonstrated better churn detection.

## Key Business Insights

The analysis identified several patterns associated with customer churn:

- Month-to-month contracts were associated with higher churn likelihood.
- Longer customer tenure was associated with lower churn likelihood.
- Two-year contracts were associated with lower churn likelihood.
- Fiber optic internet service showed a positive association with churn predictions.

These findings can help subscription businesses investigate customer behaviour and develop retention strategies.

## Customer Risk Segmentation

Customers in the test dataset were classified into three categories using predicted churn probabilities.

| Risk Category | Probability | Customers |
|---|---|---:|
| High Risk | 70% or above | 356 |
| Medium Risk | 40% to below 70% | 344 |
| Low Risk | Below 40% | 709 |

### Business Recommendations

- Prioritise high-risk customers for retention campaigns.
- Offer personalised subscription benefits and loyalty rewards.
- Monitor customer engagement during the early subscription period.
- Investigate pricing, service quality, and customer satisfaction.
- Encourage long-term subscriptions through suitable offers.

## Model Saving

The trained model was saved using Joblib in a `.pkl` file.

This allows the complete preprocessing and prediction pipeline to be reused without retraining the model every time.

## Future Improvements

- Experiment with XGBoost and other advanced algorithms.
- Perform hyperparameter tuning.
- Incorporate customer engagement and behavioural data.
- Develop an interactive Power BI dashboard.
- Deploy the model using Flask or FastAPI.
- Evaluate retention campaign effectiveness using real business outcomes.

## Project Structure

```text
Customer_Churn_Prediction/
│
├── Subscription_Churn_Prediction.ipynb
├── customer_churn_model.pkl
├── README.md
└── churn_analysis_charts/
```

## Conclusion

This project demonstrates how Machine Learning can be used to predict customer churn and support data-driven customer retention strategies.

Through data preprocessing, exploratory analysis, feature engineering, model comparison, and evaluation, the project provides a practical understanding of how predictive analytics can help subscription-based businesses identify customers at risk of leaving.

**Skills Demonstrated:** Data Cleaning | Exploratory Data Analysis | Feature Engineering | Python | Machine Learning | Model Evaluation | Business Analysis
