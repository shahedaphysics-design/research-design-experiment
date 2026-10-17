# Predicting Titanic Passenger Survival Using Machine Learning

## Abstract

This study investigates how effectively machine learning models can predict Titanic passenger survival using demographic and travel-related information. The research compares Linear Regression as a baseline model with Logistic Regression as a binary classification model. The dataset contains 889 passenger records and 13 variables. Data preprocessing included handling missing values, encoding categorical variables, standardizing numerical features, and engineering family-related features. The models were evaluated using an 80:20 training-test split. Linear Regression achieved an accuracy of 81.46%, while Logistic Regression achieved 82.02% accuracy, with a precision of 80.00%, recall of 70.59%, and F1-score of 75.00%. Logistic Regression performed slightly better in accuracy and is more suitable for the binary survival prediction task. The findings demonstrate that passenger characteristics can provide useful information for survival prediction, although the results are limited to the dataset and experimental setup used.

## 1. Introduction

Predicting passenger survival is a useful machine learning problem because it allows researchers to examine how demographic and travel-related characteristics relate to survival outcomes. The Titanic dataset is widely used for learning and evaluating classification techniques. It includes variables such as passenger class, sex, age, fare, family relationships, and embarkation point.

Previous resources provide a foundation for this study. The Kaggle Titanic competition presents passenger survival as a prediction problem using passenger information. The scikit-learn documentation explains that Logistic Regression is designed for classification tasks, while Linear Regression predicts continuous numerical values. The Seaborn Titanic dataset also provides a commonly used example for exploring passenger characteristics and survival patterns.

This study addresses the following research question:

**How effectively can Linear Regression and Logistic Regression predict passenger survival using demographic and travel-related features?**

The objective is to prepare the dataset, engineer useful features, train both models, compare their evaluation results, and identify which model is more appropriate for this binary prediction task.

## 2. Methodology

### 2.1 Dataset Description

The study uses the Titanic passenger dataset stored in `output_train.csv`. After the initial data preparation, the dataset contains 889 observations and 13 variables. The target variable is `Survived`, where 0 represents a passenger who did not survive and 1 represents a passenger who survived.

The main predictor variables include:

- `Pclass`: passenger class
- `Sex`: passenger sex
- `Age`: passenger age
- `SibSp`: number of siblings or spouses aboard
- `Parch`: number of parents or children aboard
- `Fare`: ticket fare
- `Embarked`: port of embarkation

### 2.2 Data Preprocessing

The dataset was inspected for missing values and unnecessary columns. Numerical missing values were handled using median imputation, while categorical missing values were handled using the most frequent value. Categorical variables were converted into numerical representations using one-hot encoding, and numerical features were standardized as part of the preprocessing pipeline.

The preprocessing steps were incorporated into the modeling workflow to prepare the features for machine learning.

### 2.3 Feature Engineering

Two additional features were created to represent family circumstances:

- `FamilySize = SibSp + Parch + 1`
- `IsAlone`, an indicator of whether a passenger travelled alone.

These features were included alongside the selected demographic and travel-related variables.

### 2.4 Models

Two regression-based approaches were compared.

**Linear Regression:** This model was used as a baseline. Because it produces continuous predictions, a threshold of 0.5 was applied to convert predictions into survival classes for accuracy calculation.

**Logistic Regression:** This model was used for binary classification because the target variable has two possible outcomes. The model was configured with `max_iter=1000` and `random_state=42`.

### 2.5 Experimental Procedure and Evaluation

The dataset was divided into 80% training data and 20% testing data, using `random_state=42` and stratification. This produced 711 training observations and 178 testing observations.

Linear Regression was evaluated using Mean Absolute Error (MAE), Mean Squared Error (MSE), R-squared, and threshold-based accuracy. Logistic Regression was evaluated using accuracy, precision, recall, F1-score, and a confusion matrix.

## 3. Results

### 3.1 Model Performance Comparison

Table 1 presents the test-set results obtained from the experiment notebook.

**Table 1. Comparison of Linear Regression and Logistic Regression**

| Metric | Linear Regression | Logistic Regression |
|---|---:|---:|
| Accuracy | 81.46% | 82.02% |
| MAE | 0.2988 | Not reported |
| MSE | 0.1426 | Not reported |
| R-squared | 0.3961 | Not reported |
| Precision | Not reported | 0.8000 |
| Recall | Not reported | 0.7059 |
| F1-score | Not reported | 0.7500 |

Logistic Regression achieved an accuracy of 82.02%, slightly higher than the 81.46% obtained by Linear Regression. The difference was 0.56 percentage points. Logistic Regression also achieved a precision of 0.80, recall of 0.7059, and F1-score of 0.75.

### 3.2 Logistic Regression Confusion Matrix

**Table 2. Confusion Matrix for Logistic Regression**

| Actual outcome | Predicted not survived | Predicted survived |
|---|---:|---:|
| Not survived (0) | 98 | 12 |
| Survived (1) | 20 | 48 |

The model correctly classified 98 passengers who did not survive and 48 passengers who survived. It incorrectly classified 12 passengers who did not survive as survivors and failed to identify 20 passengers who survived.

These results indicate that the model performed reasonably well overall, but some surviving passengers were missed.

## 4. Discussion

The results indicate that both models were able to predict Titanic passenger survival with test-set accuracy above 80%. Logistic Regression achieved slightly higher accuracy than Linear Regression and is the more appropriate model for this task because the target represents two classes.

The precision score of 0.80 indicates that 80% of the passengers predicted to have survived were correctly classified as survivors. The recall score of 0.7059 indicates that the model identified approximately 70.59% of the actual survivors. Therefore, the model missed some passengers who survived. The F1-score of 0.75 provides a combined measure of precision and recall.

The experiment also demonstrates the value of preprocessing and feature engineering in preparing passenger data for machine learning. Features such as family size and travelling alone allow the models to consider family circumstances in addition to individual passenger characteristics.

However, this study has limitations. The dataset contains only 889 observations and may not represent other passenger populations or survival situations. Only two models were compared, and the evaluation used a single train-test split. The results do not establish that one model will perform better on every dataset. Furthermore, Linear Regression is not naturally designed for binary classification, so its accuracy should be interpreted as a baseline comparison rather than a fully equivalent classification approach.

Future work could evaluate Random Forest, Gradient Boosting, and Support Vector Machine models. Cross-validation, hyperparameter tuning, and additional feature engineering could also provide a more comprehensive evaluation.

## 5. Conclusion

This study compared Linear Regression and Logistic Regression for predicting Titanic passenger survival using demographic and travel-related features. Logistic Regression achieved the higher test accuracy of 82.02%, compared with 81.46% for Linear Regression, and produced an F1-score of 0.75. These findings suggest that Logistic Regression is a suitable approach for this binary classification task. However, the results are limited by the dataset size, the small number of models tested, and the use of a single train-test split. Future studies should evaluate additional algorithms and use cross-validation to assess the reliability of the results.

## 6. References

1. Kaggle. (n.d.). *Titanic: Machine Learning from Disaster*. https://www.kaggle.com/competitions/titanic

2. scikit-learn developers. (n.d.). *LogisticRegression*. scikit-learn documentation. https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html

3. scikit-learn developers. (n.d.). *LinearRegression*. scikit-learn documentation. https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html

4. Seaborn developers. (n.d.). *Titanic dataset*. Seaborn documentation. https://github.com/mwaskom/seaborn-data
