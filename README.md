# Relax-Inc.-Take-Home-Challenge

[Code](https://github.com/dinqui/Relax-Inc.-Take-Home-Challenge/blob/main/Relax%20Inc.%20Take-Home%20Challenge.ipynb)

## Data 
- User table included data on 12,000 users who signed up for the product in the last two years.
- A usage summary table that has a row for each day that a user logged into the product.

## Data Cleaning 
- Converted time stamp columns into datetime.
- Checked for users who signed up more than once with the same email. (20 users identified) 

## Feature Engineering
- After grouping the usage summary table by user id, a rolling 7 day count that included at least 3 log-ins was applied to identify adopted users. 
- The adopted users identified in the usage summary table was then mapped to the user table to identify each user as adopted or not.
- Nan values in "invited_by_user" were filled with 0 to indicate that these users were not invited by another user.
- Nan values in "adopted" were filled with 0 since these users were not included in the usage summary table and thus had not logged in. 
- Calculated total visits by user 
- Dummy features were created for the 5 values in the creation source column. 
- The following columns were not considered for the model: user id, creation time, name, email, last session creation time

## Modeling
- Logistic Regression: Cross-validation with 5 folds found the best C to be 100. This gave an accuracy score of 0.985. The confusion matrix showed a total of 53 false labels (20 FP and 33 FN). 
- Decision Tree: The best decision tree model was entropy with max-depth of 5. This had an accuracy score of 0.98, and a balanced accuracy score of 0.97. The confusion matrix showed a total of 56 false labels (28 FP and 28 FN). 
- Random Forest: The best random forest model had a max-depth of 10. This had an accuracy score of 0.98 and a balanced accuracy score of 0.96. The confusion matrix showed a total of 55 false labels (23 FP and 32 FN). 

## Improvements 
- It could be helpful to have additional information about users such as demographics or the ways in which they interacted with the site. 
