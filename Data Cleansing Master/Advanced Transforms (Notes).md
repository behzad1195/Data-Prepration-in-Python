### Transforming Different Data Types
    * We need to transform our data before feeding it to the ML model. This is required to ensure that you exposed the best structure to your predictive modeling problem to the ML. Applying data transform like *scaling and encoding* categorical variables is staright forward when all the variables are in a same type. But it cannbe challenging when you have a dataset with a mix types. In this case you want to applied the data transfer selectively to some but not all of input features.
    * Fortunately `from sklearn.compse import ColumnTransformer` allows us to selectively apply data transforms to different column in your datasets  
    * As mentioned it is important to transform our data prior to modeling this include replacing all missing values, scaling numerical values and One-Hot-Encoding the categorical variables.   
    * The sequence of different transform techniques can be used together using **Pipeline**. 
    * It is very common to want to perform different data prepration techniques on different columns of your data. This may imply to first dividing your numerical and categorical data and then use these techniques on them seprately, prior to combining them back together in order to feed them to your model.
    
#### The Column Transformers
    * The {ColumnTransformer()} allows us to selectively apply data prepration transforms. In order to do that we should specify a list of transforms. Each transformer has three elements tuple that define the name of transformer namely a transformer to apply *e.g. OneHotEncoder()and column indecies to aplly it to *e.g. 'season'*  and the type of that column *e.g. 'cat'* for categorical.  
        + `transformers = ColumnTransformer(transforms=[('cat', OneHotEncoder(), [0,1])]`
    * Yet any column that is not passed through transformers will automatically droped from the data set in order to prevent that you can add `reminder='passthrough'` to your transformers
         + `transformers = ColumnTransformer(transforms=[('cat', OneHotEncoder(), [0,1])], reminder= 'passthrough')`
    * We can use **Pipeline** to transform our column before fitting it to our model. This ensure us that the transformed data is passed automatically to our model before fitting it. 
    * For splitting the numerical and categorical data you can use below codes
        + `numerical = X.select_dtypes(include=['int64', 'float64']).columns`
        + `categorical = X.select_dtypes(include=['object', 'bool']).columns`
    * For detailed process via case study look at 'Advanced Transforms' Notebook.
    * You can make a template for transformers to use it in other projects.
    
#### Transform Target (output) Variable
    * Although transforming input data can be done automatically but for output/target variable we have two options.
        + **1. Manually Transform Target Variable:** it envolves creating the variable, applying the scaling object to data manually. The steps for doing that are as follow
            + 1. Create the transform object (e.g. MinMaxScaler)
            + 2. Fit the transform on the training dataset
            + 3. Apply the transform to the train and test datasets
            + 4. Invert the transform on predictions made (This can be painful as you may not use convienient function in sklearn such as cross_val_score)
        + **2. Automatically Transform Variable:** It can be achieved by 
            + `wrapped_model = TransformedTargetRegressor(regressor = model, transformer=MinMaxScaler())' 
            + `wrapped_model.fit(ytrain, ytest)'
    * HuberRegressor model is a linear regression model that is tuned to detect the outlier automatically. 
    * For detailed process via case study look at 'Advanced Transforms' Notebook.
    
#### Challenge of Preparing New Data for a Model
    * It is critical to perform all data prepreation techniques that we done on Train dataset to do also on Test dateset or even a complete new dataset. The best practice for doing that is to save the methods that we used in a seprate file and put it in a same folder where our model is. 
    * **Very Important Note:** any scaling method should be applied to data set prior to fitting them to model especially for models such as logistic regression, neural network and KNearestNeighbours. This is because variable with higher magnitude may washed out the effect of variables with the lower magnitude.
    * The best practice to choose between different scaler techniques is to applied them to the training data set and find out which performs better.
    
#### Save Model and Data Scaler and later Load and Apply them 
    * Python allows us to save our scaling objects and later use them for the model or even new datasets.
        + The first step is to split our data and find the min and max for each feature
        + Then choose the scaling method that has the best performance on train data
        + Then print the min and max of each feature  
        + lastly we can use *pickle* framwork to save our model and scaling method by
            + `from pickle import dump`
            + `dump(model, open('model.pk1', 'wb'))`
            + `dump(scaler, open('scaler.pk1', 'wb'))`
        + we can later on load and apply them by 
            + `model=load(open('model.pk1', 'rb'))`
            + `scaler=load(open('scaler.pk1', 'rb'))`
    * For detailed process via case study look at 'Advanced Transforms' Notebook.
   