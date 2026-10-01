# Predicting Bank Term-Deposit Subscription

**Student:** Sanaa Arora  
**Student ID:** 26067203
**Subject:** Advanced Data Analytics Algorithms  
**Assessment:** A2 Option 2  

## Notebook link

PUBLIC NOTEBOOK LINK WILL GO HERE

## 1. Problem definition

The purpose of this project is to predict whether a bank customer will
subscribe to a term deposit.

The model uses customer information available before a marketing call.
It returns a probability of subscription and a YES or NO prediction.

## 2. Dataset

I used the Bank Marketing dataset from the UCI Machine Learning Repository.

The dataset contains 45,211 customer records.

The target results were:

- 39,922 customers did not subscribe.
- 5,289 customers subscribed.

## 3. Features and target

The customer information was stored in X.

The correct subscription answer was stored in y.

The target was converted into numbers:

- yes = 1
- no = 0

The features were age, job, marital status, education, default, balance,
housing, loan, pdays, previous and poutcome.

## 4. Data leakage

The duration feature was removed because it records the length of the
current marketing call.

The call length is not known before making the call. Using it would give
the model future information and create data leakage.

## 5. Preprocessing

Missing numerical values were replaced using the median.

Numerical values were standardised using StandardScaler.

Missing categorical values were replaced using the most frequent value.

Categorical words were converted into numbers using OneHotEncoder.

## 6. Models

Three models were compared:

1. Majority-class baseline
2. Logistic Regression
3. Random Forest

The baseline always predicts the most common answer.

Logistic Regression calculates a subscription probability using learned
feature weights.

Random Forest combines predictions from multiple decision trees.

## 7. Training and validation

The dataset was divided into:

- 31,647 training records
- 6,782 validation records
- 6,782 test records

Training data was used to train the models.

Validation data was used to compare the models and select the threshold.

Test data was used only for the final evaluation.

## 8. Evaluation metrics

The models were compared using accuracy, precision, recall, F1,
Average Precision and ROC-AUC.

Accuracy alone was not sufficient because subscribers were the smaller class.

## 9. Results

| Model | Accuracy | Precision | Recall | F1 | Average Precision | ROC-AUC |
|---|---:|---:|---:|---:|---:|---:|
| Baseline | 0.883 | 0.000 | 0.000 | 0.000 | 0.117 | 0.500 |
| Logistic Regression | 0.894 | 0.675 | 0.175 | 0.278 | 0.348 | 0.715 |
| Random Forest | 0.829 | 0.300 | 0.344 | 0.320 | 0.256 | 0.680 |

Logistic Regression was selected because it achieved the highest
validation Average Precision of 0.348.

The selected probability threshold was 0.20.

The final test results were:

| Threshold | Accuracy | Precision | Recall | F1 |
|---|---:|---:|---:|---:|
| 0.50 | 0.895 | 0.729 | 0.166 | 0.271 |
| 0.20 | 0.875 | 0.448 | 0.306 | 0.364 |

The final test Average Precision was 0.365.

The final test ROC-AUC was 0.729.

## 10. Error analysis

The confusion matrix at the selected threshold was:

PASTE THE TWO ROWS FROM YOUR STEP 25 CONFUSION MATRIX HERE

The confusion matrix shows correct NO predictions, incorrect YES
predictions, missed subscribers and correct YES predictions.

A false positive could create an unnecessary marketing call.

A false negative could cause the bank to miss a possible subscriber.

## 11. Live prediction

A live prediction function was created for one new customer.

The function uses the trained Logistic Regression model and returns the
subscription probability, selected threshold and YES or NO prediction.

The function uses the existing model and does not retrain it.

## 12. Limitations

The dataset is historical and comes from a Portuguese bank campaign.

The results may be different for another country, bank or period.

The model identifies statistical patterns but does not prove that a
customer feature causes subscription.

## 13. Future improvements

Future work could test additional models, tune model settings and use
newer customer data.

The threshold could also be selected according to the bank's business costs.

## 14. Implementation log

| Date | Work completed |
|---|---|
| September 2026 | Created the Python environment and notebook |
| September 2026 | Downloaded and inspected the UCI dataset |
| September 2026 | Defined X and y |
| September 2026 | Removed duration to prevent data leakage |
| September 2026 | Created training, validation and test sets |
| September 2026 | Prepared numerical and categorical features |
| September 2026 | Trained the baseline |
| September 2026 | Trained Logistic Regression |
| September 2026 | Trained Random Forest |
| September 2026 | Compared validation results |
| September 2026 | Selected Logistic Regression |
| September 2026 | Selected the 0.20 threshold |
| September 2026 | Evaluated the test data |
| September 2026 | Tested the live prediction function |

## 15. AI assistance

I used AI assistance to explain the assignment requirements, Python
setup, preprocessing, machine-learning models and evaluation metrics.

I checked the work by running the code in VS Code, examining the outputs
and testing the live prediction function.

## 16. References

UCI Machine Learning Repository, Bank Marketing dataset:  
https://archive.ics.uci.edu/dataset/222/bank+marketing

Scikit-learn documentation:  
https://scikit-learn.org/stable/