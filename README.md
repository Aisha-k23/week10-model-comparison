# week10-model-comparison

A beginner machine learning project comparing Linear Regression and Decision Tree models.



# Week 10 - Machine Learning Model Comparison

## Overview

This project builds on my Week 9 Linear Regression project by comparing two machine learning models:

- Linear Regression
- Decision Tree Regression

The aim was to understand how different models can be trained, evaluated and compared using the same dataset.

## Dataset

A small practice dataset was created containing:

- Hours Studied
- Exam Score

The dataset contains 10 observations.

## Machine Learning Process

The project followed these steps:

1. Created a dataset using Pandas
2. Separated the features and target variable
3. Split the data into training and testing sets
4. Trained a Linear Regression model
5. Trained a Decision Tree Regression model
6. Made predictions using both models
7. Evaluated both models using MAE and R²
8. Compared the results
9. Visualised the predictions

## Results

| Model | MAE | R² |
|---|---:|---:|
| Linear Regression | 0.76 | 1.00 |
| Decision Tree | 4.50 | 0.94 |

The exact R² values were approximately:

- Linear Regression: 0.997
- Decision Tree: 0.941

On this particular test split, Linear Regression produced lower prediction error and a higher R² score.

## Important Limitation

This dataset is very small, with only 10 observations and 2 test observations. Therefore, these results should not be treated as evidence that Linear Regression will always perform better than Decision Tree Regression.

A larger dataset and more robust evaluation would be needed to make stronger conclusions.

## Skills Demonstrated

- Python
- Pandas
- Scikit-learn
- Train/test splitting
- Linear Regression
- Decision Tree Regression
- Model evaluation
- Mean Absolute Error (MAE)
- R²
- Data visualisation
- Model comparison

## What I Learned

This project helped me understand that machine learning involves more than simply training a model. Different models can produce different results, so models need to be evaluated and compared using appropriate metrics.

I also learned how to communicate model performance and recognise limitations in a dataset.

## Code summery 
## Code Summary

The code in this project follows a simple machine learning workflow:

1. **Create the dataset** – Pandas is used to create a small dataset containing hours studied and exam scores.

2. **Prepare the data** – The `Hours_Studied` column is used as the input feature (`X`), while `Exam_Score` is the target (`y`) that the models try to predict.

3. **Split the data** – The dataset is divided into training data and testing data. The models learn from the training data and are evaluated using the unseen testing data.

4. **Train Linear Regression** – A Linear Regression model is created and trained to learn the relationship between hours studied and exam scores.

5. **Train Decision Tree Regression** – A Decision Tree model is created and trained using the same training data.

6. **Make predictions** – Both models predict exam scores for the testing data.

7. **Evaluate the models** – Mean Absolute Error (MAE) and R² are calculated to measure how well each model performed.

8. **Compare the models** – The results from both models are placed into a comparison table so their performance can be easily reviewed.

9. **Visualise the results** – Charts are used to compare model errors and show the actual exam scores against the model predictions.

Overall, the code demonstrates the basic machine learning workflow of **preparing data → training models → making predictions → evaluating models → comparing results**.

