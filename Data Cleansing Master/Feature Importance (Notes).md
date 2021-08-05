
### Feature Importance
    * It refers to a class of techniue for assigning scores to input features to a predictive model that indicates the relative importance of each feature when making a prediction. Feature importance scores can be calulated for problems that involve that predict the numerical values(e.g. regressions). And those problems that involve predicting the class labels (e.g. classification), the scores are useful and can be used in a range of situations and predictive modeling such as:
        + Better understanding the Data
        + Better Understanding the Model
        + Reducing Input Features
    * Features scores then can be fed to a **Wrapper Model**
    * There is no Best Feature Importance Approach. Each dataset and each model could use different techniques.
    * There are many approaches to define the importance of features. Here we look at three core types
        + 1. Feature importance from model coefficients
        + 2. Feature importance from decision trees
        + 3. Feature importance from premutation testing
        
#### Feature Importance Score: Linear Regression (For Numerical Output)
    * we can use all types of regressions (e.g. linear regression, Logistic Regression, lasso, elastic band, and Ridge) and pass our splitted data and fit them into these models. The coefficients that will be find by these models later on give us the importance of each feature. And as always higher the coefficient higher the importance of a feature. Yet he judgement is always personal and data related.
   
#### Feature Importance Score: Logistic Regression (For Categorical Output)
    * We should make sure that our features are scaled before fitting them to the model. Yet it works mostly on binary classification models.
   
#### Feature Importance Score: Decission Trees Classification Regression aka CART 
    * Offer coefficient based on reduction in the criteria used to split the points. The same approach can be used by samples of decission trees such as random forest and stochastic gradient boosting algorithems.
    * if your output is categorical use DecessionTreeClassifier and for numerical output use DecissionTreeRegressor. Same goes for Random Forest and Gradient Boosting. 
   
#### Feature Importance Score: Permutation 
    * Calculating the relative feature importance score that are independet from the model that we want to use. First the model fits into the dataset such as model that doesn't support naive feature importance score (such as KNeighborsregressor / For Numerical Output). Then the model used to make prediction on the dataset. Although the value of features/columns in the data scrambeld. This is repeated for each feature in the dataset. Then this whole process repeated many times (one time per feature). The result is the mean importance score for each input feature and a distribution of scores given the repeat. This approach can be used for regression or classification and requires as a performance metrics be choosen as the basis of importance score such as MSE for regression or accuracy for classification.
    * Permutation feature selection can be used via `from sklearn.inspection import permutation_importance` 
    * We use `from sklearn.feature_selection import SelectFromModel` to allow us use two different model one for feature selection and another for our own model 

   