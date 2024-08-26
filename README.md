# deep-learning-challenge
# Analysis Report

The purpose of this analysis is to develop a predictive model for Alphabet Soup, a nonprofit foundation. The model aims to identify applicants who are most likely to succeed if awarded funding. By analyzing a dataset of over 34,000 organizations that have previously received funding, the model will predict whether future applicants will effectively utilize the funds they receive. 

## Results
# Data Preprocessing
* Target Variable(s):

    IS_SUCCESSFUL. This variable indicates whether the funding provided to an applicant was used       effectively, which is the outcome we want to predict.

* Feature Variable(s):

    
      APPLICATION_TYPE: The type of application submitted.
      AFFILIATION: The sector or industry with which the organization is affiliated.
      CLASSIFICATION: The classification type assigned by the government.
      USE_CASE: The purpose or use case for the requested funding.
      ORGANIZATION: The type of organization applying for funding.
      STATUS: The operational status of the organization.
      INCOME_AMT: The income classification of the organization.
      SPECIAL_CONSIDERATIONS: Indicates if there are any special considerations for the application.
      ASK_AMT: The amount of funding requested.
These could all potentially affect the outcome of a candidate's eligibility. These variables could be used to determine patterns and trends that could improve the accuracy of the model's predictive model.

* Variables to Remove:
    
  EIN and NAME: These are identification columns that do not provide predictive value to the model.

## Compiling, Training, and Evaluating the Model

### Model Architecture:

* Neurons and Layers:

- **Input Layer**: Based on the number of input features after preprocessing.
- **Hidden Layers**: Three hidden layers were used.
  - **First Hidden Layer**: 5 neurons, activation function `ReLU`.
  - **Second Hidden Layer**: 5 neurons, activation function `ReLU`.
  - **Third Hidden Layer**: 5 neurons, activation function `ReLU`. 
    - *(Added a third layer in the optimization file to improve accuracy. The model achieved 1.0 accuracy with both, but reached 1.0 sooner with the addition of a third layer.)*
- **Output Layer**: 1 neuron, activation function `Sigmoid`, to predict the binary outcome (successful or not).


* Activation Functions:
  ReLU (Rectified Linear Unit) was chosen for the hidden layers due to its effectiveness in handling non-linear relationships and avoiding the vanishing gradient problem.
  Sigmoid was chosen for the output layer to produce a probability score indicating the likelihood of success.

* Model Performance:

* Target Performance: The goal was to achieve a high level of accuracy in predicting successful funding outcomes.
Achieved Performance: The initial model did reach the accuracy level of 1.0. But by adding the third layer in optimization accuracy was achieved sooner. 

## Steps to Improve Model Performance:

* Data Preprocessing: Additional preprocessing steps were taken to better encode categorical variables and scale numerical features, ensuring the model had a clearer signal from the input data. I added another hidden layer and removed the "Special_Classification" column as I think the model could function accurately without the added data it provides. 

## Summary
The deep learning model developed for Alphabet Soup provides a foundational approach to predicting the success of funding applicants.

### Recommendation:

Use of a Random Forest Classifier: A Random Forest classifier could be a suitable alternative model. This ensemble learning method is good for overfitting and works well with both categorical and numerical data, making it well-suited for the diverse range of features present in the dataset. It can handle non-linear relationships and interactions between features more effectively than a simple neural network.
