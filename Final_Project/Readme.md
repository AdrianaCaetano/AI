# Final Project 

## Project Overview 

The loan prediction problem dataset, downloaded from Kaggle, was used for our project. After a thorough analysis and visualization to understand the data, the dependencies, and the limitations, we use 3 machine learning models and compare the performances.

## Motivation
Dream Housing Finance company deals in all home loans. They have a presence across all urban, semi-urban, and rural areas. Customer-first applies for a home loan after that company validates the customer eligibility for a loan.

With the automation of many different sectors, loan approval is also an area that could be automated. The client could fill up a form online and a program could pre-approve a client, to be reviewed by a person for checking documentation only after passing the first screening of the algorithm. This could accelerate the process for approved clients while minimizing the risk for the institutions. It leads to reduced wait times and a more efficient loan application and approval process. Dream Housing Finance company aims to achieve these goals and made this dataset accessible, enabling researchers to develop models for this purpose.

To develop an efficient model for this purpose, we need to first try out different models, run a number of experiments aiming to increase the prediction accuracy, with a high metric for recall because we don’t want to grant a loan to someone that should not be eligible..


## Dataset

### Problem category

1. Supervised Learning:  learning from the data based on sample input-output pairs. Our dataset has input fields and an output label, hence, it is a supervised learning problem.
  - Input: Customer Attributes, Loan Amount, Term
  - Output/Label:  Loan Status
2. Binary Classification:  The output label only has 2 values, i.e., loan status is either Y(Yes) or N(No). Therefore, it is a binary classification problem.

### Dataset description

It is a short dataset with 13 columns and 614 rows. 

### Dataset Visualizations


### Preprocessing

Loan ID was dropped since this feature was not relevant for the classification problem.

The missing values were first categorized as missing completely at random (MCAR) or Missing not at random (MNAR). The fields with missing values which were unrelated to any other field were considered MCAR and 2 fields(dependents and credit history) were considered MNAR since we assumed that the missing values in this field are related to the reason it's missing, also known as nonignorable nonresponse.

The missing values were filled up using the below criteria:
- MCAR categorical features : Mode
- MCAR numerical features : Mean or Median
- Zero for dependents(MNAR): if a person "forgot" to fill up the number of dependents, most likely they don't have dependents
- Zero for credit history(MNAR): if a person "forgot" to fill up the credit history, most likely they don't have history


### Encoding

The ML models (discussed later), used in our project are compatible with both categorical and numerical features. However, the scikit-learn libraries for the models in use do not support both categorical and numerical features. Therefore, we have to encode the categorical features into numerical ones.


## Methods
We selected the below 3 models to experiment with: 
  
  1. Decision Tree Classifier
  - simple and easy to interpret
  - trees can be visualized
  
  2. Random Forest Classifier
  - have much higher accuracy than the single decision tree
  - doesn’t overfit the model, thus gives a good prediction on unseen datasets
  - low bias and low variance

3. Logistic Regression
  - efficient for linear dataset
  - it can handle both dense and sparse input

## Model Evaluation

For each ML algorithm we computed the results of True Positive - TP, False Positive - FP, True Negative - TN, and False Negative - FN. Then, we used these values to evaluate our models using confusion matrix, accuracy,precision, recall and F1-score.

  - **Confusion Matrix**: Cij is equal to the number of observations known to be in group 'i' and predicted to be in group 'j'. Confusion matrix whose i-th row and j-th column entry indicates the number of samples with true label being i-th class and predicted label being j-th class
  - **Accuracy**:  A fraction of correctly classified samples over the total samples on dataset (% total correct predictions)
  - **F1score**: The F1 score can be interpreted as a harmonic mean of the precision and recall, where an F1 score reaches its best value at 1 and worst score at 0  
       `F1 = 2 * (precision * recall) / (precision + recall)` 
  - **Precision**: The fraction of correctly classified positive over the total predicted positive (measures how precise the predictions are)
  - **Recall**: The fraction of correctly classified positive over the total true positive (indicates what percentage of the classes we’re interested in were actually captured by the model)

## Results

### Decision Tree Classifier
Our test accuracy using decision tree classifier was 69%, with recall for granted loans of 79%

### Random Forest Classifier
Our test accuracy using random forest classification was 71%, with recall for granted loans of 77%.

### Logistic Regression
Our test accuracy using logistic regression was 71%, with recall for granted loans of 75%.

## Conclusion

After data preprocessing and applying different models to our dataset, none of our models produced high scores on the measured metrics for this problem. We modified our models to use less hyperparameters, since our previous models with more fine-tuning were overfitting the model. In the end, Logistic Regression produced slightly better results than Random Forest.
