# Methodology

## 1. Research Question

How effectively can Linear Regression and Logistic Regression predict
passenger survival using demographic and travel-related features?

## 2. Dataset Description

The dataset contains passenger information used to predict survival.

The target variable is `Survived`, where 0 represents a passenger who did
not survive and 1 represents a passenger who survived.

Important features include:
- Pclass
- Sex
- Age
- SibSp
- Parch
- Fare
- Embarked

The dataset contains 889 observations and 13 variables.

### Limitations

The dataset may contain missing values and may not represent all passenger
populations. Some variables may also have limited predictive power.
Therefore, model results should not be generalized beyond the dataset
without further investigation.

## 3. Data Cleaning

The following cleaning steps will be performed:

1. Identify missing values.
2. Fill missing numerical values using appropriate statistics such as the
   median.
3. Fill missing categorical values using the mode.
4. Remove unnecessary columns such as passenger identifiers when appropriate.
5. Convert categorical variables into numerical form.

## 4. Feature Engineering

Additional features will be created where appropriate.

For example:

- `FamilySize = SibSp + Parch + 1`
- `IsAlone` will indicate whether the passenger travelled alone.

Categorical variables such as Sex and Embarked will be encoded so that
machine learning models can process them.

## 5. Models

Two models will be trained.

### Linear Regression

Linear Regression will be used as a baseline model to examine whether a
linear relationship can provide useful predictions of the survival target.

### Logistic Regression

Logistic Regression will be used as the main classification model because
the target variable, Survived, has two possible outcomes: 0 and 1.

## 6. Evaluation Metrics

For Logistic Regression, the following metrics will be used:

- Accuracy
- Precision
- Recall
- F1-score

These metrics provide different views of classification performance.

For Linear Regression, Mean Squared Error (MSE) and Root Mean Squared Error
(RMSE) will be used to measure prediction error.

## 7. Experimental Procedure

The cleaned dataset will be divided into training and testing sets.
Both models will be trained using the training data and evaluated using
the unseen testing data.

The results of the two models will then be compared to determine which
approach performs better for predicting passenger survival.