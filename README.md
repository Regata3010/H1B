Customer Churn Prediction

Overview
Customer churn is a critical business issue where customers stop doing business with a company. Accurately predicting which customers are likely to churn can help businesses proactively retain valuable customers. This project builds a machine learning model to predict customer churn based on demographic, account, and service usage data.

Dataset
The dataset used for this project was provided by Kaggle and contains the following features:
customerID: Unique ID for each customer.
gender, SeniorCitizen, Partner, Dependents: Demographic information.
tenure: Number of months the customer has been with the company.
PhoneService, MultipleLines, InternetService, StreamingTV, StreamingMovies: Service details.
Contract, PaperlessBilling, PaymentMethod: Contractual and payment information.
MonthlyCharges, TotalCharges: Payment information.
Churn: The target variable indicating whether the customer has churned (1) or not (0).


Objective
To build a machine learning model that predicts whether a customer is likely to churn based on the given features.

Data Preprocessing
Handling Missing Data: Missing values in TotalCharges were imputed using the mean.
Feature Engineering: Converted categorical variables into numeric form using one-hot encoding.
Scaling: Standardized continuous features such as tenure, MonthlyCharges, and TotalCharges.


Modeling Approach
Multiple machine learning models were evaluated:

Logistic Regression: Achieved 82% accuracy after hyperparameter tuning.
Support Vector Classifier (SVC): Tuned hyperparameters but max accuracy was 81.5%.
Random Forest: Tried various configurations, but the best accuracy achieved was 81%.
XGBoost: Trained but resulted in lower recall.
Voting Classifier: Combined Logistic Regression, SVC, and XGBoost to achieve an accuracy of 82%.

After various Hyperparameter Tunings of models trying to increase the accuracy went to the Stacking Classifier with Logistic Regression as the Final Estimator to produce results.

Evaluation
The model's performance was evaluated using:

Accuracy: 86% on the test set.
Confusion Matrix: [[697 118]
                   [112 736]]
Classfication Report:           precision   recall  f1-score   support
                          0       0.86      0.86      0.86       815
                          1       0.86      0.87      0.86       848



Business Value
By using this model, companies can:

1)Identify customers likely to churn and take targeted actions to retain them.
2)Improve customer retention strategies by offering discounts or personalized offers to high-risk customers.
3)Optimize marketing spend by focusing on customers who are more likely to churn.

Future Work
Model Optimization: Further tuning using advanced techniques like hyperparameter search with Optuna or Bayesian Optimization.
Explainability: Implement SHAP or LIME to explain individual predictions and model behavior.
Deployment: Deploy the model on a cloud platform like Heroku or AWS for real-time predictions.

Conclusion: This project successfully built a model to predict customer churn with an accuracy of 86%. By integrating this solution, businesses can retain more customers and reduce churn-related revenue loss.
