
### Data Rescaling
 * Your preprocessed data may contain attributes with a mixture of scales. Many Machine learning methods expect or ARE MORE EFFECTIVE IF THE DATA ATTRIBUTES HAVE THE SAME SCALE.
 * The two most important scaling techniques are **Standardization and Normalization**.
  * **Normalization**: betweeon 0 and 1 `MinMaxScaler()`. The normalization is done when our data has already a normal distribution. If not then use Standardization.
  * **Standardization**: guassian/normal distribution with the mean of 0 and std of 1 
 * **Scaling Works Across Model Types**: many machine learning algorithems expect that scale of input and sometimes even output being equivalent (Such as Linear Regression and Logistic Regression)
 * **When to Scale Your Data**: It's difficult to know when your models will benefit from scaling. Hence creating secondary scaled datasets and testing each one is a good first step.
 
### Robust Scaling Data
 * One approach to data scaling involves calculating the mean and standard deviation of each variable and using these values to scale the values to have a mean of 0 and STD of 1, a so called **standard normal probability distribution**.
 * Another approach of standardizing input variables in the presence of outliers is to ignore the outliers from the calculation of the mean and standard deviation, then use the calculated values to scale the variable. This is called **robust standardization**. 
 * Sometimes an input variable may have outlier values. These are values on the edge of distribution then may have a very low probability yet over represented for some reason. Outliers can skewed the probability. In this case using normalization and standardization may not work very well. One approach is to ignore the outliers from calculation of the Mean and STD and then used the calculated values to scale the variable. This can be achieved by calculating the mean of 50th percentile and then the 25th and 75th percentile. The robust scaler transformers available in `from sklearn.preprocessing import RobustScaler`  
 * We can go even one step further and change the range of our `RobustScaler()` by default it will use IQR (75th -25th) but we can change its range and see if it works better especially for detecting the outlier. 

### Nominal and Ordinal Variables
 * Machine needs that all features would be in a numerical type so if we have some categorical data in string type. we need to change it to numerical. Two most popular technique are **Ordinal Encoding** and **One-Hot Encoding**  
 * Some categories may have relationship with each other such as natural ordering, this type of categorical variable called **Ordinal Variable**, because their values can be ordered or ranked. A numerical variable can be converted into the ordinal variable by dividing the range of numerical variable (binning) and then assigning each values into the bins. This is called **Dicretization**.
 * **Nomial** variables comprise a finite set of discrete values with **no rank-order relationship** between values.
 * Some algorithm such as **Decission Trees** can deal directly ith categorical variables and you don't need to convert them. But generaly is not recommendable to pass directly categorical variable to the ML models.
 * **Very Important Note:** if we have input data that are combination of categorical variable (assuming they all already changed to the number) and numerical variables. You can count them as numerical variable and then choose your Feature Selection technique. **OR** you can divide your data into the categorical and numerical then use feature techniques seprately on them. At the end you need to check the model accuracy of both approach and see which one works better.

### Ordinal Encoding
 * In ordinal encoding each category will take one value. Often integer values starting with 0. For some variable ordinal encoding may be enough. The Integer values have natural relationship with each other and the machine may be able to understand and harness a relationship. Hence it may create a realtionship between categorical variables where such an order may not exist. This can cause problems and **One-Hot Encoding** should be used instead.  
 * Available in `from sklearn.preprocessing import OrdinalEncoder`
 * Ordinal Encoding works for single variable if you have more than one categorial variable then the **LabelEncoder** works better.
  
### Dummy Variable Encoding 
 * The One-Hot-Encoding creates a binary variable for each category. The problem is that presentation includes redundancy. For example if we have three categories like 'red', 'blue' and 'green' by One-Hot-Encoding we will have arrays like [1,0,0], [0,1,0], and [0,0,1] where we can have arrays like [1,0], [0,1], and [0,0] and reduce our features by at least one column and hence reduce the dimensionality. This is called **Dummy Variable Encoding** and the result is that we will have n-1 column where n is the number of categories.  
 * In addition to be slicely less redundant, the dummy variable representation is required for some models. For example in the case of Linear Regression models and other regression models that have bias term, a One-Hot-Encoding causes that input data to become singular, meaning it can't be inverted and linear coefficients cannot be calculated using linear algebra. For these types of models **Dummy Variable Encoding** must be used instead.
 * we can make a dummy variable via One-Hot-Encoding by using `drop` arguments. By doing that we are determining which category become the one that assigned all the zero values, it is called the base line. We can set this to 'first' so the first category is used. 
 
### Make Distribution More Guassian (Make Distribution Great Again!!!!)
 * ML algorithems (especially Linear and Logistic Regression) assume that our variables follow a normal/guassian distribution. But there is a high chance that your data doesn't have normal distribution. Therefore you may achieve better performance if you could change their distribution to normal. For input variable it is better that we do that for both categorical and numerical data while for output only for numerical data.
 * Techniques such as  **Box-Cox**, or **Yeo-Johnson** will do this for us.

#### Power Transforms
 * It refers to a class of techniques that use a power function (like a logarithm or exponent) to make a probability distribution of a variable Gaussian or more Gaussian like.
  + **Box-Cox** technique can only be applied for data that are strictly positive it doesn't support data with zero and/or negative value in it. (so it doesn't work on sonar data cause it has zero in it.) In order to prevent this problem we can use MinMaxScaler for making the data strictly positive by changing the default range (0,1) to any range that is strictly positive such as range (1,2).
  + **Yeo-Johnson** unlike box-cox transform it can deal with zero and negative values. This help us to directly use it without scaling the data first. Yet scaling the data first would increase the efficiency of Yeo-Johnson as well.
 * At the end of the day the only thing that can help us to choose between these method is our model performance. So automating these process always allow us to first, save more time and second, test various techniques and choose the best of them.

### Polynomial Features
 * **Transformers** such as raising input variables to a power can help to better expose the important relationship between input variables and the target variables. These features are called **Interaction Polynomial Features**. They allow us to use simple modeling algorithem as some of the complixity of the interpreting the input variables and the relationships pushed back on the data prepration stage. Some times these features can result in an improvement of our model although at the cost of thousend and even millions of addition of input variables.
  + **Polynomial Features** are those features created by raising existing features to an exponent. Hence they are a **type of feature engineering**, the creation of new input features based on the existing features.   
   

