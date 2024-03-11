# Credit_Risk_Classification

BACKGROUND

Credit risk poses a classification problem that’s inherently imbalanced. This is because healthy loans easily outnumber risky loans. In this project, you’ll use various techniques to train and evaluate models with imbalanced classes. You’ll use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.
Using your knowledge of the imbalanced-learn library, you’ll use a logistic regression model to compare two versions of the dataset. First, you’ll use the original dataset. Second, you’ll resample the data by using the RandomOverSampler module from the imbalanced-learn library.
For both cases, you’ll get the count of the target classes, train a logistic regression classifier, calculate the balanced accuracy score, generate a confusion matrix, and generate a classification report.


OVERVIEW OF THE ANALYSIS

The purpose of this analysis is to compare accuracy scores of balanced and unbalanced data. The data is based on healthy and high-risk loans. The goal is to create a logistic regression model that will predict whether a loan is healthy or high-risk (the 'y' variable). The initial sample contained 75,036 healthy loans and 2,500 high-risk loans. The factors taken ito consideration to compute the loan status are loan size, interest rate, borrower income, debt-to-income ratio, number of accounts, number of derrogatory remarks, and total debt (the 'x' variables). 

The project begins by splitting the data into 'x' and 'y' variable data frames and then splitting each into train and test datasets using the train_test_split function. I then create a logistic regression model, fit it using the 'x' and 'y' train data, and find the predictions of the model. Recall that the data contains 75,036 healthy loans and 2,500 high-risk loans. So, I resample the data using the RandomOverSampler function. The resampled data contains 56,277 healthy and high-risk loans alike. I then recreate a logistic regression model, fit it, and find the predictions. 


RESULTS

Machine Learning Model 1:
    - Accuracy 97.21%
    - Precision
      - Healthy 100%
      - High-risk 87%
    - Recall
      - Healthy 100%
      - High-risk 95%

Machine Learning Model 2:
    - Accuracy 99.4%
    - Precision
      - Healthy 99%
      - High-risk 99%
    - Recall
      - Healthy 99%
      - High-risk 99%


SUMMARY

The second model (resampled) performs better than the first. The accuracy of model 1 is superb, but the accuracy of model 2 is better. Precision and recall for healthy loans score perfectly, so the risks are found in high-risk loan scores. High-risk loan precision scored 87%. This suggests an business inefficiency because there is a 13% margin of error where loans are categorized as high-risk when they are not. High-risk recall scores better with a 95%. Still, this leaves a 5% margin of error where loans are categorized as healthy when they are not. Fortunately, recall is higher than precision, because in the credit business, it is more important to not tie up money with risky borrowers, risking losses, than to miss opportunities with healthy borrowers. Nonetheless, a 13% rate of missed opportunities seems high. 

By contrast, model two scores 99% on precision and recall for healthy and high-risk borrowers. So, the risks of inefficient business and missed opportunities are minimized under the high-risk profile. This comes at a cost to healthy precision and recall. However, a 1% downgrade in healthy precision and recall is worth the 12% and 4% upgrade in high-risk precisiona and recall, respectively. For the reasons mentioned, I recommend model two. 


CODE SOURCE

Code was sourced from classwork assignments.


TECHNOLOGIES

This project requires the use of numpy, pandas, pathlib, sklearn, and imblearn metrics. Balanced accuracy score and confusion matrix were imported from sklearn. The project was developed using Python as the coding language on Visual Studio Code. 