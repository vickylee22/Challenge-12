# Module 12 Report

## Overview of the Analysis
Credit risk poses a classification problem that’s inherently imbalanced. This is because healthy loans easily outnumber risky loans. We will use various techniques to train and evaluate models with imbalanced classes and use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

This report consists of the following analysis:
  - Split the Data into Training and Testing Sets
  - Create a Logistic Regression Model with the Original Data
  - Predict a Logistic Regression Model with Resampled Training Data

First, we take lending data and create labels set into two classes - 0 (healthy loan) and 1 (high-risk loan). You will notice credit risk is imbalanced, with 0 (healthy loan) easily outnumbering 1 (high-risk loan). 

75036 of 0 (healthy loan) vs 2500 of 1 (high-risk loan). 
  ![Picture1](https://user-images.githubusercontent.com/103230949/178077432-e75d237b-b0eb-4e78-896b-18f6c83e1d91.png)

So, we split the data into training and testing sets. We create a Logistic Regression Model with original data, then we predict a Logistic Regression Model with resampled training data. 
 ![Picture2](https://user-images.githubusercontent.com/103230949/178077447-2b9ae835-2949-4c4d-bfb8-bf2499d78ffb.png)

After we achieved balanced data, we can now perform analysis. We were able to get an improved performance with resampled training data to predict high-risk loans. 

## Steps
1. Split the Data into Training and Testing Sets:
  - Read the lending_data.csv lending data into a Pandas DataFrame.
  - Create the labels set (y) from the “loan_status” column, and then create the features (X) DataFrame from the remaining columns.
  - Check the balance of the labels variable (y) by using the value_counts function.
  - Split the data into training and testing datasets by using train_test_split.

2. Create a Logistic Regression Model with the Original Data:
  - Fit a logistic regression model by using the original training data (X_train and y_train) 
  - Save the predictions on the testing data labels by using the testing feature data (X_test) and the fitted model 
  - Evaluate the model’s performance by calculating the accuracy score of the model, generate a confusion matrix and print the classification report

3. Predict a Logistic Regression Model with Resampled Training Data:
  - Use the RandomOverSampler module from the imbalanced-learn library to resample the data. Confirm that the labels have an equal number of data points for healthy and high-risk loans.
  - Use the LogisticRegression classifier and the resampled data to fit the model and make predictions 
  - Evaluate the model’s performance by calculating the accuracy score of the model, generate a confusion matrix and print the classification report

## Results

* Machine Learning Model 1:
Original Data - Logistic Regression with imbalanced training data.
  - Precision for 0 (healthy loan): 1.00 
  - Recall for 0 (healthy loan): 0.99 (99% accurate in predicting healthy loans as healthy)
  - Precision for 1 (high-risk loan): 0.85 (85% accurate in the high-risk loans predictions)
  - Recall for 1 (high-risk loan): 0.91 (91% accurate in predicting high-risk loans as high risk)
![Picture3](https://user-images.githubusercontent.com/103230949/178077461-b861d454-3dff-4bc1-a5b6-a5def9166b77.png)

* Machine Learning Model 2:
Resampled Data - Logistic with balanced training data
  - Precision for 0 (healthy loan): 1.00
  - Recall for 0 (healthy loan): 0.99 (99% accurate in predicting healthy loans as healthy)
  - Precision for 1 (high-risk loan): 0.84 (84% accurate in the high-risk loans prediction)
  - Recall for 1 (high-risk loan): 0.99 (99% accurate in predicting high-risk loans as high risk))
![Picture4](https://user-images.githubusercontent.com/103230949/178077470-d37fad4e-5cc4-4a96-ae91-bb5a14b3919f.png)

## Summary
Oversampled data performs better than the original data, even though there’s a slight drop on precision for 1 (high-risk loan) 85% vs 84% from the original data, but the recall for 1 (high-risk loan) increased 8% from 91% to 99%. The cost of associated with approving high-risk loans outweighs the loss of potential profit associated with not approving healthy loans. Therefore, I would recommend the model using resampled data. 
