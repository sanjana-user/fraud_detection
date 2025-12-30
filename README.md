# Fraud Detection
# Problem Statement:

The objective of this project is to build a machine learning model that can proactively detect fraudulent financial transactions. 

# Dataset:

The dataset consists of customer demographic and purchasing behavior data, including age, annual income, and spending score. It is used for unsupervised learning to identify distinct customer segments.

- Rows: 6,362,620

- Features: Age, Annual Income, Spending Score

- Target Variable: isFraud 

# Tools:

Pandas

Numpy 

Matplotlib

Seaborn 

Scikit Learn

# Approach and Methodology:

## Data Cleaning:

- Checked for null/ missing values and duplicates. 

- Dropped unnecessary columns that do not affect the target variable and data analysis, like 'nameDest', 'isFlaggedFraud'.

## Outlier analysis:

- Plotted boxplot for amounts. 

- Plotted boxplot of amounts vs fraud, isFraud has a higher mean value for amounts.

## Data Visualization: 

- Which type has more fraud possibility - bar plot of type and fraud_rate (since isFraudt is very imbalanced)

- One hot encoded type (for correlation), and visualized through a heatmap.

- New balance and Old balances have a very high correlation - multi-collinearity. 

- Account Balances in general have a very less correlation with the target variable.

## Feature Engineering: 

- Absolute errors are calculated and used as new features (maths).

- Logical flags are identified - if the new balance does not change or is zero after the transaction.

- New balance features (origin and destination) are removed since they are directly derivable. 

## Model Development:

- The data is split into training and testing data using the Scikitlearn function, train_test_split().

- Training the data using the logistic regression model, a test data recall of 96% is obtained. 

 
# Models used:

## Logistic Regression Model:
It outputs a probability between 0 and 1, representing the likelihood of the event occurring. The model uses a special function called the sigmoid function, which produces an S-shaped curve that maps any real-valued number into a value between 0 and 1.

# Evaluation Metrics:

## Precision:
Precision tells us, out of all transactions predicted as fraud, how many were actually fraud.

## Recall:
Recall tells us, out of all actual fraud cases, how many the model was able to catch.

## F1 Score:
F1 score balances precision and recall, showing how well the model performs when both false alarms and missed fraud matter.

## ROC-AUC Score:
ROC-AUC measures how well the model separates fraud from non-fraud across all decision thresholds.

# Insights:

- Fraudulent transactions are strongly influenced by:

 a) Transaction type (e.g., transfers and cash-out transactions)


b) Transaction amount


c) Sudden changes in account balances


- Existing rule-based flags (isFlaggedFraud) fail to capture a large portion of actual fraud cases


- Logistic Regression provided better control over false negatives, making it more suitable for fraud detection than Random Forest in this context


- Model probabilities can be effectively used to design risk-based prevention strategies such as blocking, step-up authentication, or monitoring


# How to run the project:

- Download or clone the repository.

- Open the project folder.

- Open the Jupyter Notebook file (.ipynb).

- Run all the cells from top to bottom.

# Project Structure: 

├── fraud_detection.csv        # Dataset used in the project

├── fraud_detection.ipynb      # Jupyter Notebook with full code

├── README.md          # Project explanation
