# Relax-Inc.-Take-Home-Challenge

## 1. Data 
- User table included data on 12,000 users who signed up for the product in the last two years.
- A usage summary table that has a row for each day that a user logged into the product.

## 2. Data Cleaning 
- Converted time stamp columns into datetime.
- Checked that usage summary table did not include more than one login per day for a given user.
- Checked for users who signed up more than once with the same email. (20 users identified) 

## 3. EDA 

## 4. Feature Engineering
- After grouping the usage summary table by user id, a rolling 7 day count that included at least 3 log-ins was applied to identify adopted users. 
- The adopted users identified in the usage summary table was then mapped to the user table to identify each user as adopted or not.
- Nan values in "invited_by_user" were filled with 0 to indicate that these users were not invited by another user.
- Nan values in "adopted" were filled with 0 since these users were not included in the usage summary table and thus had not logged in. 
- Dummy features were created for the 5 values in the creation source column. 
- The following columns were not considered for the model: user id, creation time, name, email, last session creation time

## 5. Modeling
- Logistic Regression: cross-validation with 5 folds found the best C to be 0.001. This gave an accuracy score of 0.87 but the confusion matrix showed that the model did not predict any adopted users.
- Decisioon Tree:
- Random Forest: 

## 6. Improvements 
## 7. Conclusions & Recommendations 
