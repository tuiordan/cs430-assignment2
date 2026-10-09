# CS 430 — Assignment 2: SLCM Regression Analysis

## Project Overview

This project was completed for **CS 430: Machine Learning**.

The objective is to predict the amount of past-due rent (`past_due_rent`) using household, income, employment, and housing-related information from the SLCM Rent Arrears De-identified Dataset.

The assignment focuses on data preprocessing, building regression models, evaluating their performance, and interpreting the results.

## Dataset

The dataset contains **1,754 observations and 14 columns**.

The target variable is `past_due_rent`, and 12 features are used for prediction, excluding the target and `record_id`.

The dataset includes information such as:
- Household size and composition
- Monthly household income
- Employment status and income sources
- Housing voucher status
- Monthly rent
- Utility and eviction situations

## Methodology

### 1. Data Exploration
- Examined the dataset structure and missing values.
- Calculated descriptive statistics.
- Visualized the target variable using a histogram and boxplot.

### 2. Data Preprocessing
- Handled missing numerical values using conditional imputation and median imputation.
- Replaced missing categorical values with a separate "Missing" category.
- Standardized numerical features using `StandardScaler`.
- Encoded categorical variables using `OneHotEncoder`.
- Split the dataset into 80% training and 20% testing data using `random_state=42`.

### 3. Regression Models

Four regression models were trained and evaluated:

1. Multiple Linear Regression
2. Polynomial Regression (degree 2)
3. Ridge Regression
4. Lasso Regression

Model performance was evaluated using Root Mean Squared Error (RMSE) and R².

## Results

| Model | RMSE | R² |
|---|---:|---:|
| Linear Regression | 1851.52 | 0.164 |
| Polynomial Regression | 1863.35 | 0.153 |
| Ridge Regression | 1837.55 | 0.176 |
| **Lasso Regression** | **1829.02** | **0.184** |

**Lasso Regression** achieved the best performance, with the lowest RMSE and highest R².

However, the relatively low R² indicates that the available features explain only a limited portion of the variation in past-due rent.

## Conclusion

The results show that household and housing-related information can help identify patterns associated with rent arrears, but the models have limited predictive accuracy.

Regularization slightly improved performance, while adding polynomial features did not produce better results.

The models also struggled to predict unusually high amounts of past-due rent.

These findings suggest that additional information may be needed to improve predictions. The models should be used to explore general patterns rather than make decisions about individual households.

## Technologies Used

- Python
- Google Colab / Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Scikit-learn

## Repository Contents

- `CS430_Assignment2.ipynb` — Jupyter notebook containing the analysis, models, visualizations, and interpretations.
- `SLCM_rent_arrears_student_clean.csv` — De-identified dataset used for the analysis.
- `README.md` — Project documentation.

## How to Run

1. Download the notebook and CSV file from this repository.
2. Open the notebook in Google Colab.
3. Upload the CSV file to the Colab environment.
4. Run all notebook cells in order.

The notebook contains the complete analysis, including preprocessing, model training, evaluation, and interpretation.

## Course Information

**Course:** CS 430 — Machine Learning  
**Assignment:** Assignment 2 — SLCM Regression Analysis  
**Academic Year:** Fall 2026
