# Alphabet Soup Charity Prediction Model Report

## Overview of the Analysis
The purpose of this analysis is to create a binary classifier deep learning model to predict whether applicants will be successful if funded by Alphabet Soup. The data we used comes from Alphabet Soup's database and includes over 34,000 organizations that have received funding from Alphabet Soup over the years.

## Results

### Data Preprocessing

- **Target Variable:** The target for our model is 'IS_SUCCESSFUL', indicating whether the money was used effectively.

- **Feature Variables:** The features for our model include every column in the dataset except 'EIN' and 'IS_SUCCESSFUL'. These features are a mixture of numerical and categorical data about the application, including 'NAME', 'APPLICATION_TYPE', 'AFFILIATION', 'CLASSIFICATION', 'USE_CASE', 'ORGANIZATION', 'STATUS', 'INCOME_AMT', 'SPECIAL_CONSIDERATIONS', and 'ASK_AMT'.

- **Variables to be Removed:** The 'EIN' (Employer Identification Number) is an identifier, not feature, and has been removed from the input data.

### Compiling, Training, and Evaluating the Model

- The optimal model is a neural network with sigmoid activation functions. The best performing model had two hidden layers, with the first layer consisting of 21 neurons and the second layer having 61 neurons. The choice of neurons and layers was determined using the Keras Tuner's Hyperband optimization, which performs an intelligent search over the hyperparameter space.

- The model was able to achieve a best validation accuracy of around 75.7%, which is marginally above the target model performance of 75%.

- Multiple attempts were made to increase the model's performance. Firstly, we performed data preprocessing, including testing different model features (e.g., 'CLASSIFICATION' vs. 'NAME'), binning categorical variables with too many unique categories, and applying one-hot encoding. We also scaled the numeric input data. In terms of model architecture, we experimented with various numbers of neurons, layers, and activation functions through the use of Keras Tuner's Hyperband optimization. Finally, we implemented early stopping during training to prevent overfitting.

## Summary

The overall results of the deep learning model were satisfactory, as it achieved a validation accuracy above our target of 75%. However, further optimization could potentially improve the model. 

As a recommendation for a different model, a Random Forest Classifier or a Gradient Boosting Classifier could be considered. These models are robust, handle both numerical and categorical data well, and can provide feature importances, which could give insights into what features are most important in determining whether the money will be used effectively. For Alphabet Soup, this could be valuable information for determining what to look for in applications.

Alternatively, if we stick with deep learning, we could consider using a larger neural network with more layers and neurons. With more data, we could use a convolutional neural network (CNN) or recurrent neural network (RNN), but these models might be overkill for the current dataset size.

Finally, further feature engineering could also be performed on the dataset to try to create new features that may be more predictive of success. For example, a feature could be created that categorizes the 'ASK_AMT' into bins, or the 'CLASSIFICATION' could be further categorized.
