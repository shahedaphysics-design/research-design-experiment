# Titanic Passenger Survival Prediction Using Machine Learning

## 1. Project Overview

This project aims to predict whether a passenger survived the Titanic disaster using machine learning techniques. Two models, Linear Regression and Logistic Regression, were implemented and evaluated to compare their predictive performance.

## 2. Research Question

How effectively can Linear Regression and Logistic Regression predict passenger survival using demographic and travel-related features?

## 3. Dataset

The dataset contains 889 passenger records and 13 variables. The target variable is `Survived`, where 0 represents a passenger who did not survive and 1 represents a passenger who survived.

Features include passenger class, sex, age, family relationships, fare, and port of embarkation.

## 4. Methods

- Data cleaning and handling missing values
- Categorical feature encoding
- Feature engineering using `FamilySize` and `IsAlone`
- Train-test split (80:20)
- Linear Regression and Logistic Regression
- Model evaluation using accuracy and other performance metrics

## 5. Results

| Model | Accuracy |
|---|---:|
| Linear Regression | 81.46% |
| Logistic Regression | 82.02% |

Logistic Regression achieved slightly higher accuracy and is more suitable for this binary classification problem.

## 6. Project Files

- [Research Paper](paper.md)
- [Literature Review](literature_review.md)
- [Methodology](methodology.md)
- [Experiment Notebook](experiment.ipynb)
- [Dataset](output_train.csv)
- [Presentation](slides/presentation.pptx)
- [Charts and Figures](figures/)

## 7. Conclusion

The results show that both models can predict Titanic passenger survival reasonably well. Logistic Regression performed slightly better than Linear Regression. Future work could explore additional machine learning models and improved feature engineering.

## 8. Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook