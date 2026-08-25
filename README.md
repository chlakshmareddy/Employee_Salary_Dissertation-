# Employee_Salary_Dissertation-

# Evaluation of a Machine Learning-Based Employee Salary Prediction Prototype Using Multiple Regression Models and Hyperparameter Optimisation

# Author Name : Challa Lakshma Reddy

### Project Overview

This project develops and evaluates a machine learning based employee salary prediction solution using structured employee information. The main objective is to predict annual employee salary from relevant employee characteristics, evaluate multiple regression models, improve model performance through Hyperparameter Optimisation, interpret the final model using SHAP and LIME, and demonstrate the final solution through an interactive salary prediction prototype.

The final solution integrates data preprocessing, regression modelling, model validation, overfitting analysis, hyperparameter optimisation, explainability, prototype implementation and human evaluation.

### Research Aim

The aim of the project is to develop and evaluate an accurate, reliable and interpretable machine learning based employee salary prediction solution using structured employee data, model optimisation, explainability techniques and human feedback.

### Research Question

How can employee salary regression be developed and optimised for accurate prediction, with SHAP and LIME supporting interpretability and human evaluation providing user feedback?

### Dataset

The project uses an employee salary dataset containing 10,000 observations and 10 attributes. The target variable is Salary.

The original dataset contains Employee_ID, Name, Age, Gender, Department, Job_Title, Experience_Years, Education_Level, Location and Salary.

Employee_ID and Name were removed because they are identification attributes and do not provide useful predictive information for salary estimation.

The final modelling features were Age, Job_Title, Experience_Years, Education_Level, Department and Location. Salary was retained as the continuous prediction target.

The dataset contained no missing values, so missing value imputation was not required.

### Data Preprocessing

The dataset was inspected to identify the number of observations, data types, missing values and relevant prediction variables.

Employee_ID and Name were removed from the modelling dataset because they represent identification information rather than meaningful salary predictors.

Categorical variables including Department, Job_Title, Education_Level and Location were converted into numerical representations using label encoding.

The independent variables were separated from the Salary target variable.

The dataset was divided into 80 percent training data and 20 percent testing data.

StandardScaler was applied to standardise the feature values so that numerical differences in feature scale did not dominate the learning process.

The same preprocessing components were retained for use with the final prediction prototype.

### Machine Learning Models

Four regression models were implemented and evaluated.

Linear Regression was used as the baseline model because it is simple, computationally efficient and provides an interpretable starting point for salary prediction.

Random Forest Regression was selected because it combines multiple decision trees and can model nonlinear relationships and interactions between employee characteristics.

Gradient Boosting Regression was selected because trees are constructed sequentially, with later trees correcting errors made by previous trees. This provides a strong approach for modelling complex salary relationships.

LightGBM Regression was selected as an efficient gradient boosting approach for structured datasets. It provided the strongest default performance and was therefore selected as the leading candidate for further optimisation.

### Evaluation Metrics

Mean Absolute Error was used to measure the average absolute difference between predicted and actual salaries. Lower values indicate better predictive performance.

Mean Squared Error was used to measure the average squared prediction error and gives greater influence to larger errors. Lower values indicate better performance.

Root Mean Squared Error was calculated as the square root of Mean Squared Error and expresses prediction error in the same unit as salary. Lower values indicate better performance.

R2 Score was used to measure the proportion of variation in salary explained by the model. Higher values indicate stronger explanatory and predictive performance.

### Model Validation

K-Fold Cross-Validation was used to assess the consistency of model performance across different subsets of the data.

Overfitting was assessed by comparing training and testing R2 scores. The small differences between training and testing performance indicated that the evaluated models generalised well to unseen employee salary records.

### Default Model Results

Linear Regression produced an MAE of 11,534.41, MSE of 216,277,179.76, RMSE of 14,706.37 and R2 of 0.8974. This means that approximately 89.74 percent of salary variation was explained by the baseline model.

Random Forest Regression produced an MAE of 3,796.68, MSE of 22,405,821.88, RMSE of 4,733.48 and R2 of 0.9894. This represented a substantial improvement over Linear Regression and demonstrated the benefit of ensemble learning for the structured employee data.

Gradient Boosting Regression produced an MAE of 3,466.56, RMSE of 4,324.04 and R2 of 0.9911. The model provided stronger predictive performance than Random Forest.

LightGBM Regression produced an MAE of 3,434.16, MSE of 18,255,551.54, RMSE of 4,272.65 and R2 of 0.9913. It provided the strongest overall default performance and was selected for further optimisation.

### Default Model Interpretation

The default results showed a clear performance improvement from the simple linear baseline to tree based ensemble methods.

Linear Regression had substantially higher prediction errors, indicating that a simple linear relationship was not sufficient to represent the complex relationships between employee characteristics and salary.

Random Forest substantially reduced the prediction error and explained 98.94 percent of salary variation.

Gradient Boosting further improved the results, reaching an R2 of 0.9911.

LightGBM achieved the strongest default performance, with the lowest MAE, lowest MSE, lowest RMSE and highest R2 among the default models.

### Overfitting Analysis

The overfitting analysis compared training and testing R2 scores.

Linear Regression achieved a training R2 of 0.8982 and testing R2 of 0.8974, producing a difference of 0.0008.

Random Forest Regression achieved a training R2 of 0.9937 and testing R2 of 0.9894, producing a difference of 0.0043.

Gradient Boosting Regression achieved a training R2 of 0.9910 and testing R2 of 0.9911, producing a difference of 0.0001.

LightGBM Regression achieved a training R2 of 0.9921 and testing R2 of 0.9913, producing a difference of 0.0007.

All differences were small. Therefore, no substantial overfitting was detected across the evaluated regression models. The results indicate good generalisation from the training data to unseen testing data.

### Hyperparameter Optimisation

Hyperparameter Optimisation was performed using GridSearchCV.

GridSearchCV systematically evaluates predefined combinations of hyperparameters using cross-validation rather than relying on manual trial and error. The approach was used to identify improved configurations for the regression models.

The optimised models were retrained using their selected configurations and evaluated using the same performance metrics as the default models.

### Optimised Model Results

Linear Regression remained unchanged after optimisation, with an MAE of 11,534.41, MSE of 216,277,179.76, RMSE of 14,706.37 and R2 of 0.8974. This indicates that the limitations of the linear baseline were primarily associated with its linear modelling assumptions rather than parameter selection.

Random Forest Regression improved after optimisation. MAE decreased from 3,796.68 to 3,508.72. MSE decreased from 22,405,821.88 to 19,044,592.98. RMSE decreased from 4,733.48 to 4,364.01. R2 increased from 0.9894 to 0.9910.

Gradient Boosting Regression also improved after optimisation. The optimised model achieved an MAE of 3,405.47, MSE of 18,057,669.96, RMSE of 4,249.43 and R2 of 0.9914.

Optimised LightGBM Regression achieved an MAE of 3,416.64, MSE of 18,055,475.28, RMSE of 4,249.17 and R2 of 0.9914.

### Final Model Selection

Optimised LightGBM Regression was selected as the final model.

The model achieved an MAE of 3,416.64, meaning the average absolute difference between predicted and actual salary was approximately 3,416.64 salary units.

The MSE was 18,055,475.28.

The RMSE was 4,249.17.

The R2 score was 0.9914, meaning that approximately 99.14 percent of the variation in employee salary was explained by the model.

Although Optimised Gradient Boosting also achieved an R2 of 0.9914 and a slightly lower MAE of 3,405.47, Optimised LightGBM produced the lowest MSE and RMSE among the final optimised models. LightGBM was therefore selected as the final model based on its overall predictive performance and strong generalisation.

### Final Model Performance

The final Optimised LightGBM model achieved the following results.

MAE: 3,416.64

MSE: 18,055,475.28

RMSE: 4,249.17

R2: 0.9914

The R2 value indicates that the final model explains approximately 99.14 percent of the variation in employee salary within the evaluated test data.

The low MAE and RMSE indicate that the final predictions were close to the observed salary values on average.

### SHAP Analysis

SHAP was applied to the optimised LightGBM model to understand the global influence of employee characteristics on salary predictions.

Age was the most influential feature. The mean absolute SHAP value for Age was approximately 44,798.14.

Job_Title was the second most influential feature, with an average SHAP contribution of approximately 6,157.17.

Experience_Years was the third most influential feature, with a SHAP importance value of approximately 4,287.

Education_Level, Department and Location had smaller contributions compared with Age, Job_Title and Experience_Years.

The SHAP results therefore indicate that Age, Job_Title and Experience_Years were the main variables influencing salary predictions in the final model.

### LIME Analysis

LIME was used to explain an individual salary prediction generated by the optimised LightGBM model.

For the analysed employee, the predicted salary was approximately 86,487.43.

Job_Title was the strongest positive contributor, increasing the prediction by approximately 11,757 units.

Age contributed positively by approximately 270.32.

Experience_Years contributed positively by approximately 209.64.

Education_Level contributed negatively by approximately 143.26 for this specific prediction.

Location contributed positively by approximately 83.68.

Department contributed a smaller positive amount of approximately 10.71.

The LIME explanation demonstrated how individual feature contributions combined to produce the final predicted salary.

The LIME results were consistent with the SHAP findings because Age, Job_Title and Experience_Years were also identified as the main influential variables. This consistency provided additional support for the interpretability of the final model.

### Prototype

The optimised LightGBM model was integrated into an interactive salary prediction prototype.

The prototype allows users to enter employee characteristics including Age, Department, Job Title, Experience, Education Level and Location.

The application applies the saved preprocessing components, including the label encoders and feature scaler, before passing the processed information to the trained LightGBM model.

The system then generates a predicted employee salary.

The prototype also includes prediction and reset functionality and provides access to the human evaluation component.

The prototype demonstrates that the final model can be moved from an experimental machine learning environment into a practical salary prediction application.

### Human Evaluation

Human evaluation was conducted using 150 participant responses.

The evaluation examined ease of use, understanding of predictions, clarity of explanations, usefulness of predictions and overall prototype satisfaction.

Ease of Use received an average rating of 4.64 out of 5.

Prediction Understanding received an average rating of 4.75 out of 5.

Explanation Clarity received an average rating of 4.69 out of 5.

Prediction Usefulness received an average rating of 4.75 out of 5.

Prototype Satisfaction received an average rating of 4.59 out of 5.

The overall prototype rating was 4.79 out of 5.

Most participant ratings were 4 or 5, with very few ratings of 3 and no ratings below 3.

Participant comments were generally favourable. The interface was described as simple, intuitive and useful, while some participants recommended providing more detailed explanations.

### Overall Results

The project successfully developed an end-to-end employee salary prediction solution.

The baseline evaluation demonstrated that ensemble regression models were substantially more effective than Linear Regression for the selected salary dataset.

LightGBM provided the strongest default performance and remained one of the strongest models after Hyperparameter Optimisation.

The optimised LightGBM model achieved an R2 of 0.9914, an MAE of 3,416.64, an MSE of 18,055,475.28 and an RMSE of 4,249.17.

The overfitting analysis showed very small differences between training and testing R2 scores, supporting good model generalisation.

SHAP identified Age, Job_Title and Experience_Years as the most influential features.

LIME demonstrated how individual employee characteristics contributed positively or negatively to a specific salary prediction.

The prototype demonstrated practical use of the final model.

Human evaluation with 150 participants produced an overall rating of 4.79 out of 5, supporting the usability, understanding and perceived usefulness of the prototype.

### Project Contributions

The project contributes an evaluated regression based employee salary prediction solution using structured employee information.

It demonstrates the value of Hyperparameter Optimisation for improving ensemble model performance.

It provides global and local model explanations using SHAP and LIME.

It integrates the final prediction model into an interactive prototype.

It evaluates the practical usability and usefulness of the solution through human feedback.

### Limitations

The study uses one secondary salary dataset, which may limit generalisability to other countries, industries and changing labour markets.

The dataset represents a particular set of employee characteristics and may not capture every factor that influences real world salary decisions.

The final results therefore should not automatically be assumed to generalise to every organisation, industry or geographical location.

### Future Work

Future research could evaluate the model using larger, longitudinal and multi-source salary datasets.

Future work could investigate concept drift and continuous monitoring to identify changes in salary distributions over time.

Further research could incorporate fairness metrics and bias auditing to assess whether predictions differ systematically across relevant groups.

Conformal prediction could be investigated to provide prediction intervals rather than only point estimates.

Adaptive learning and automated drift explanation could also be considered to support long-term model reliability.

### Technologies and Methods

The project uses Python based machine learning development and includes data preprocessing, categorical encoding, feature scaling, regression modelling, cross-validation, GridSearchCV based Hyperparameter Optimisation, SHAP analysis, LIME analysis and prototype development.

The principal regression algorithms are Linear Regression, Random Forest Regression, Gradient Boosting Regression and LightGBM Regression.

### Project Workflow

The project workflow begins with dataset inspection and data quality checking.

The next stage removes identification attributes and prepares the relevant employee characteristics.

Categorical variables are encoded and numerical features are scaled.

The dataset is divided into training and testing subsets.

Four regression models are trained and evaluated.

Cross-validation and overfitting analysis are conducted.

Hyperparameter Optimisation is performed using GridSearchCV.

The optimised models are evaluated using MAE, MSE, RMSE and R2.

Optimised LightGBM is selected as the final model.

SHAP is applied for global feature interpretation.

LIME is applied for individual prediction explanation.

The final model and preprocessing components are integrated into the salary prediction prototype.

Human evaluation is conducted using participant feedback.

### Final Conclusion

The final results demonstrate that the developed employee salary prediction solution achieved strong predictive performance while also providing model explanations and practical user interaction.

Optimised LightGBM was selected as the final model because it achieved an R2 of 0.9914, MAE of 3,416.64, MSE of 18,055,475.28 and RMSE of 4,249.17. The model demonstrated strong generalisation with no substantial overfitting identified.

SHAP and LIME provided complementary explanations of the model. SHAP identified the most influential features at the global level, while LIME explained the contribution of individual features for a specific prediction.

The prototype demonstrated practical salary prediction functionality, and human evaluation produced an overall rating of 4.79 out of 5 from 150 responses.

Overall, the project successfully combines predictive modelling, Hyperparameter Optimisation, model validation, explainability, prototype implementation and human evaluation into an integrated employee salary prediction solution.
