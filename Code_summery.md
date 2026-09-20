Pandas is imported so that I can create and work with tables of data.

2. Create the Dataset
data = {
    "Hours_Studied": [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    "Exam_Score": [42, 45, 51, 58, 62, 68, 71, 78, 84, 91]
}

This creates a small practice dataset.

Hours_Studied represents the number of hours a student studied.

Exam_Score represents the student's exam score.

3. Create a DataFrame
df = pd.DataFrame(data)

df

The dictionary is converted into a Pandas DataFrame so that the data can be easily analysed and used by the machine learning models.

4. Separate the Features and Target
X = df[["Hours_Studied"]]
y = df["Exam_Score"]

X contains the input feature that the models use to make predictions.

In this project, the input is the number of hours studied.

y contains the target variable that the models are trying to predict.

In this project, the target is the exam score.

5. Split the Data
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

train_test_split divides the data into training and testing sets.

The training data is used to teach the models.

The testing data is kept separate so that the models can be evaluated on data they did not train on.

test_size=0.2 means that 20% of the data is used for testing.

random_state=42 ensures that the same split is produced each time the code is run.

6. Import Linear Regression
from sklearn.linear_model import LinearRegression

This imports the Linear Regression machine learning model from scikit-learn.

7. Create the Linear Regression Model
model_lr = LinearRegression()

This creates a Linear Regression model.

The model will learn the relationship between hours studied and exam score.

8. Train the Linear Regression Model
model_lr.fit(X_train, y_train)

The .fit() method trains the model using the training data.

The model learns a relationship between the number of hours studied and exam scores.

9. Import Decision Tree Regression
from sklearn.tree import DecisionTreeRegressor

This imports the Decision Tree Regression model from scikit-learn.

10. Create the Decision Tree Model
model_tree = DecisionTreeRegressor(random_state=42)

This creates a Decision Tree Regression model.

The Decision Tree learns rules from the training data that it can use to make predictions.

11. Train the Decision Tree
model_tree.fit(X_train, y_train)

The Decision Tree is trained using the same training data as the Linear Regression model.

Using the same training data allows the two models to be compared fairly.

12. Make Predictions
lr_predictions = model_lr.predict(X_test)

tree_predictions = model_tree.predict(X_test)

The .predict() method asks each model to predict exam scores for the testing data.

The Linear Regression predictions are stored in lr_predictions.

The Decision Tree predictions are stored in tree_predictions.

13. Calculate MAE
from sklearn.metrics import mean_absolute_error, r2_score

lr_mae = mean_absolute_error(y_test, lr_predictions)
tree_mae = mean_absolute_error(y_test, tree_predictions)

MAE stands for Mean Absolute Error.

It measures the average size of the errors between the predicted values and the actual values.

A lower MAE means the predictions are closer to the actual values.

14. Calculate R²
lr_r2 = r2_score(y_test, lr_predictions)
tree_r2 = r2_score(y_test, tree_predictions)

R² measures how well the model explains the variation in the target values.

A value closer to 1 generally indicates that the model fits the test data more closely.

15. Print the Results
print("Linear Regression")
print(f"MAE: {lr_mae:.2f}")
print(f"R²: {lr_r2:.2f}")

print("\nDecision Tree")
print(f"MAE: {tree_mae:.2f}")
print(f"R²: {tree_r2:.2f}")

This displays the MAE and R² results for both models.

The :.2f formats the numbers to two decimal places.

16. Create a Comparison Table
comparison = pd.DataFrame({
    "Model": ["Linear Regression", "Decision Tree"],
    "MAE": [lr_mae, tree_mae],
    "R²": [lr_r2, tree_r2]
})

comparison

This creates a table containing the evaluation results for both models.

This makes it easier to compare their performance.

17. Create the MAE Chart
import matplotlib.pyplot as plt

plt.bar(comparison["Model"], comparison["MAE"])

plt.xlabel("Model")
plt.ylabel("Mean Absolute Error")
plt.title("Model Comparison: Mean Absolute Error")

plt.show()

Matplotlib is used to create a bar chart comparing the MAE of the two models.

The chart makes it easier to visually compare their prediction errors.

18. Compare Actual and Predicted Scores
plt.plot(y_test.values, marker="o", label="Actual")
plt.plot(lr_predictions, marker="o", label="Linear Regression")
plt.plot(tree_predictions, marker="o", label="Decision Tree")

plt.xlabel("Test Student")
plt.ylabel("Exam Score")
plt.title("Actual vs Predicted Exam Scores")

plt.legend()

plt.show()

This graph compares the actual exam scores with the predictions from both models.

It helps show how closely each model's predictions match the real scores.

19. Conclusion

The project demonstrates a basic machine learning workflow:

Prepare data → Split data → Train models → Make predictions → Evaluate models → Compare results → Visualise results

The project also demonstrates why it is important to evaluate machine learning models rather than simply training one model and assuming that it performs well.

What I Learned

This project helped me understand:

How to train more than one machine learning model
How to make predictions using different models
How MAE measures prediction error
How R² can be used to evaluate model performance
How to compare models using a table and charts
Why small datasets can limit the reliability of conclusions
