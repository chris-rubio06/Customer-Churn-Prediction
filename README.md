# Customer Churn Prediction Using Machine Learning

## About This Project

For this project, I used Python and machine learning to predict whether customers at a telecommunications company would cancel their service.

I wanted to see if I could use customer information, like how long someone has been with the company, their contract type, and their monthly bill, to predict who might leave.

I worked with a dataset of 7,043 customers, cleaned the data, created charts to look for patterns, and trained two different machine learning models. I also built an interactive tool that lets users test different customer scenarios and see the predicted chance of cancellation.

## Tools and Technologies

- **Python:** Main programming language
- **Pandas:** Cleaning and analyzing customer data
- **Matplotlib:** Creating charts and visualizations
- **Scikit-learn:** Training and testing machine learning models
- **ipywidgets:** Building the interactive prediction tool
- **Google Colab:** Writing and running the code

## Dataset

I used the [IBM Telco Customer Churn dataset](https://github.com/IBM/telco-customer-churn-on-icp4d), which contains 7,043 customer records and 21 original columns.

The dataset includes information about customers' contracts, internet services, monthly payments, and how long they've been with the company.

Before training the models, I cleaned the data by converting the `TotalCharges` column into numbers and replacing 11 blank values with zero. These records belonged to customers who had not completed their first month.

After preparing the data, I used 19 customer features to train the models.

## What I Found

Before building the prediction models, I analyzed the data to see which customer characteristics were connected to cancellations.

**Contract Type**

| Contract | Churn Rate |
|---|---|
| Month-to-month | 42.71% |
| One year | 11.27% |
| Two year | 2.83% |

Customers with month-to-month contracts had much higher cancellation rates than customers with longer contracts.

**Monthly Charges**

Customers who canceled paid an average of $74.44 per month, compared to $61.27 for customers who stayed.

**Customer Tenure**

Customers who stayed had been with the company for an average of 37.6 months, while customers who canceled averaged 18 months.

These results showed me that contract type, monthly charges, and customer tenure were worth looking at when building the prediction model.

## Machine Learning Models

I trained two machine learning models to predict customer churn:

1. Logistic Regression
2. Random Forest

I used 80% of the data for training and 20% for testing.

I also used StandardScaler and OneHotEncoder to prepare the numerical and categorical data so the models could work with it.

### Model Results

| Metric | Logistic Regression | Random Forest |
|---|---|---|
| Accuracy | 80.55% | 78.28% |
| Precision | 65.7% | 61.9% |
| Recall | 55.9% | 47.3% |
| F1 Score | 0.604 | 0.536 |

The precision, recall, and F1 scores focus on predicting customers who canceled.

**Logistic Regression performed better overall**, reaching 80.55% accuracy on the testing data.

One thing I learned was that accuracy doesn't tell the whole story. Even though Logistic Regression had good overall accuracy, it only identified about 56% of customers who actually canceled. This showed me why it's important to look at other evaluation metrics too.

## Most Important Features

I also looked at which features were most useful to the Logistic Regression model when making predictions.

The top three were:

1. Customer tenure
2. Internet service
3. Contract type

This helped me better understand what information the model relied on when predicting whether a customer would leave.

## Charts and Visualizations

I created several charts throughout the project, including:

- Customer churn rates by contract type
- Average monthly charges for customers who stayed or canceled
- Logistic Regression confusion matrix
- Logistic Regression vs. Random Forest performance comparison
- Top 10 most important features for predicting churn

These charts helped me understand the data and compare my results.

## Interactive Prediction Tool

One of the final things I added was an interactive prediction tool using ipywidgets.

Users can change a customer's tenure, contract type, and monthly charges using sliders and a dropdown menu.

The tool then uses my trained Logistic Regression model to predict whether the customer will stay or cancel and displays the estimated probability of cancellation.

For this demonstration, the tool keeps some information from an existing sample customer and estimates total charges. It is meant to show how the model works rather than predict outcomes for completely new customer profiles.

## How to Run the Project

1. Download `Customer_Churn_Prediction.ipynb` from this repository.
2. Open the notebook in Google Colab.
3. Run the code cells in order.
4. Explore the charts and machine learning results.
5. Try the interactive prediction tool near the bottom of the notebook.

The dataset loads directly from an IBM GitHub repository, so an internet connection is needed.

## What I Learned

This project gave me more experience using Python for data analysis and machine learning.

I practiced cleaning a dataset, finding patterns in customer behavior, training different models, and comparing their results using accuracy, precision, recall, and F1 score.

I also learned that a more complicated model isn't always better. In this case, Logistic Regression performed better than Random Forest.

Overall, this project helped me better understand how machine learning can be used to predict customer behavior and how important it is to test and explain a model's results.
