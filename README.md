# Supervised Learning – Credit Risk Assignment




## Purpose – 

The purpose of this assignment was to build different machine learning models that attempt to predict whether a loan from the Lending Club will become high-risk or not. For this assignment, we compared the Logistic Regression and Random Forest Classifiers.


## Data – 

We were provided with training (i.e., 2019) and testing (i.e., 2020) data sets. These data were oversampled for high-risk loans to ensure an equal proportion of high and low-risk loans in the testing and training data files.


## Preprocessing – 

Initially, the data were preprocessed by one-hot encoding the categorical variables (i.e., columns) in the data file, which resulted in a total of 96 columns. Next, the target variables were separated into separate data frames for analysis purposes. Lastly, the data were scaled using StandardScaler to determine whether scaling the data resulted in an improved fit.


## Statistical Analyses – 

All analyses were conducted in Python using Jupyter Lab. The following packages were used: Numpy, Pandas, and sklearn. Scaled and unscaled Logistic Regression and Random Forest models were computed. We tuned the unscaled model using recommended parameters to determine whether an improved model could be found. Rather than the standard 3-fold cross-validation, we utilized only 2-fold in an effort to reduce time. Classification reports were produced for each analysis.  

## Results


The results are bulleted below, followed by an image of the classification table. We reported the R-square values in the test.

•	Model1: The first Logistic Regression model accounted for 69% and 57% of the variance (i.e., R-square) in determining high-risk loans for the training and testing data, respectively. Below is the classification of our first logistic regression model, which was not tuned or scaled.

![image](https://user-images.githubusercontent.com/82011523/139775638-d68b1bd5-abc2-46ff-be1a-aa7fe69b914f.png)

•	Model 2. The Logistic Regression model was then retrained using GridsearchCV to determine whether we could enhance the model's performance. The resulting R-square for the testing sample was 56%, which was a marginal improvement over the initial model. Below is the classification of our second logistic regression model, which was tuned but not scaled.

 ![image](https://user-images.githubusercontent.com/82011523/139775676-b76ab93d-7b73-428e-8360-5b08041f9e76.png)


•	Model 3. The first Random Forest model accounted for 100% of the variance in the training data, indicating that the model was overfitting the data and, therefore, not generalizable. However, it only accounted for 64% of the variance in the testing sample. Therefore, additional feature selection procedures were computed. A total of 35 or 96 features were identified as relevant. In the future, it would be wise to retrain the model with the specified features. See our table below.

![image](https://user-images.githubusercontent.com/82011523/139775729-c22a19f6-0e6c-4c41-88d3-8fc48037725c.png)

Model 4. 
•	A subsequent Random Forest model was developed, which consisted of tuning the model based on the n_estimators, max_features, max_depth, min_samples_split, min_samples_leaf, and bootstrap. The model was tuned using RandomizedSearchCV. Unfortunately, tuning the model did not result in an improved model fit. The model accounted for 97% and 66% of the variance in outcomes for the training and testing data, respectively. The classification table is depicted below. Overall, this model performed marginally better than the prior model. However, overfitting was reduced slightly in this model.
 
![image](https://user-images.githubusercontent.com/82011523/139775810-7b7a1634-2803-4fbe-b436-4ded6b3a8b00.png)


•	Model 5. The scaled logistic regression model accounted for 71% and 54% of the variance in the outcome for the training and testing data, respectively. However, the improvement over Models 1 and 2 appear to be marginal at best. See the classification report below for additional model parameters.

![image](https://user-images.githubusercontent.com/82011523/139775852-9b58da60-b607-44c2-8089-9afe8f90f38f.png)

•	Model 6. We computed another Random Forest Model with the default model parameters. The scaled model continued to overfit the testing (R-square= 100%) data but only accounted for 64% of the variance in the outcome for the testing data. The final classification report is depicted below.

![image](https://user-images.githubusercontent.com/82011523/139775898-68cc6cec-b339-40cc-bcc4-aeb1b725394a.png)

## Summary

The Random Forest models appeared to have the best fit to the data when examining the R-square values (i.e., score). Of note, the scaled Logistic Regression model resulted in the highest estimate of precision (0.75) when compared to the other models. However, the percentage of variance accounted for was lowest for this model. Overall, the models we computed were marginal at best. Other variables may be better predictors of high-risk status that were not included in this model. It could also be that 2020 represented an unusual year due to historical events (i.e., COVID-19) that interfered with our ability to predict high-risk status. Additional machine learning models and more time-series data may be warranted to predict loan status better.


 

