## Feature Selection
* It is desired to reduce the number of features to reduce the computation cost of modeling and in many cases to improve the performance of model. There are lots of statistical models that can help us to find out wich features have strong relation to our target. Yet choosing these methods is highly dependent on datatype of both input and output variables.
* Future Selection Goals
 + Two Core Types -> Supervised (Target variable) and Unsupervised (No Target Variable)
 + Filter Based -> uses statistical measures to score the correlation and dependence between input variables that can be filtered to choose the most relevant feature
 + Carefully Chosen -> the feature selection method most be carefully chosen based on the input and output data type  
* Supervised Feature Selection Methods: Intrinsic, Filter, Wrapper (all belongs to Dimensionality Reduction Techniques)
 + Intrinsic: Auto Feature Selection (algorithems during training-> Lasso and Decision Trees)
 + Filter: Relationship to target (Use statistical techniques to find realtionship between feature and target)
 + Wrapper: According to Model (search the subset of features that performs according to predictive model/computationaly expensive)
### Categorical Feature Selection
* For a dataset with only categorical data we use `OrdinalEncoder` for input variables (works for more than one variable) and `LabelEncoder` for output variable (single variable) by importing them from `sklearn.preprocessing`
* There are two methods for feature selection for categorical variables: 
 + Chi-Squared: larger the Chi-squared better feature and vice versa. However there is no defined threshold for magnitude of Chi-squared for feature selection so the selction of feature is our own judgment/or by evaluating of model with different subset  
 + Mutual Information: typical used in Decission Trees/Random Forest model
* The best approach is to evaluate the model (Logestic Regression is the best model for evaluation the feature selection technique for categorical data) with each technique to see which one works better. For doing so you can automate the model evaluation process. 
* It is always to better to check the cross-validation instead or in addition to simple model accuracy.
### Feature Selection with ANOVA on Numerical Input with Categorical Output
* The most common technique for Feature Selection for numerical inputs are:
 + **ANOVA F-test**: ANOVA stands for **analysis of variance** and is parametric statistical hypothesis test for determining whether the means from two or more samples of data come from same distribution or not. An F-satatistic or **F-test**, is a class of statistical test that calculates the ratio between **variances values**, such as the variance from two different samples or the explained and unexplained variance by a statistical test, like ANOVA. ANOVA is used when one variable is categorical and other is numerical. Similar to Chi-Squared the higher the F-Test higher the relation between feature and target.  
 + **Mutual Information**: from the field of information theory, it is the application of information gain (typically used in construction of Decision Trees) to feature selection. Mutual Information is calculated between two variables and measures the reduction in uncertainty of one variable given a known value of the other variables. Mutual Information is a straight forward, we consider the distribution of two discrete categorical or ordinal variable, such as categorical input and categorical output. Therefore it could be also adapted to use between numerical input and categorical output.
* The best approach is to evaluate the model (with each technique to see which one works better. For doing so you can automate the model evaluation process.

### Tuning Number of Selected Features
* The best pratice to find which features should be used we can use the **GridSearchCV** function. For doing so we should combine the `RepeatedSartifieldKFold()` for cross-validation then creating a pipeline by passing our Feature Selection Method together with the model and then building a dictionary for grid to pass all number of possible features through a for loop and then use a grid search to find the accuracy of each one of them.
* However the best practice for tuning the number of features, is to additionaly looking at the relationship between each selected number of features with model accuracy by drawing the box-whisker plot and then decide the number of selected features.

### Select Features for Numerical Output
* For selecting the number of features between numerical input and output variable(s) especially in case of linear regression. Because the strength of relation between input and output can be caluclated by correlation statistics or Mutual Information. 
 + **Correlation (Pearson):** we are interested to positive numbers which are close to 1. Hence we can convert the linear correlation to only with positive values statistics via importing `f_regression from sklearn.feature_selection`. However when we calculate the correlation with this method to final score is not a number between 0 and 1. Yet it is always a positive number. The higher the better.
 + **Mutual Information**: when we have numerical output we should import `mutal_info_regression* from sklearn`.feature_selection*. same with correlation higher the score better the feature.
* same with previous techniques we should test each method with model accuracy.
### Recursive Feature Elimination (RFE): 
*  RFE is a feature selection algorithm. RFE is a **Wrapper** style feature selection model. This means that different machine learning model was given and used as a core method wrapped by RFE and used to help select features. Now this is in contrast with basic feature selection techniques that score each feature and then select the beast feature with the largest or smallest score. Technically RFE is a wrapper style feature selection model that also uses further feature selection internally. RFE works by selecting f subset of features by starting all the futures in training dataset and then successfully removing features until the desired number of features remains. This is achieved by feeding the machine learning algorithm used by the core model and ranking features by their importance and discarding the least important features and then refeeding that model. This process then repeated until the specified numbers of features remains. Features are scored either using provided machine learning models i.e some algorithm such as Decission Trees or by using statistical methods. There are two configuration options for using RFE.
 + **Choice in the Number of Features**
 + **Choice of the Algorithm used to Select Features** 
 