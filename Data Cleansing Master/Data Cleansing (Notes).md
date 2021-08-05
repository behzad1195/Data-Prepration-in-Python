
### Data Cleansing Overview
**Data Cleaning** refers to identifying and correcting errors in the dataset that may negatively impact a predictive model
* In structred data you can use lots of statistical analysis and data visualization techniques that we can use to explore our data in order to define the data cleansing operation that we want to perform.
* There are some very simple yet crucial steps before more sophisticated techniques that may be overlooked and if they being skipped our model may break or perform overly optimistic.
  
#### Step1: identify and deletlumns that contain a Single Value
#### Step2: identify Columns with Values
#### Step3: Remove Columns with Low Vace
#### Step4: Identify and Remove Rows that ain duplicate data
#### Step 5: Identifying and Removing Outliers* It is important to know not all outliers should be removed and it's kind of personal judgement for each dataset
* for the quicl check a scatterplot would help a lot
 + First Approach : IQR
 + Second Approach: Automatic Outlier Detection
* look at related notebook
  
### Step 6: Mark Missing Values
* Some columns may have 0 instaed of missing values first we should make sure whether 0 could be a true observation or not by using `.describe()` function and looking at the min and max. After we made sure that 0 are missing value then we can replace them ba nan using .`replace(0 nan)`
 + First Approach: Removing missing values (not recommended especially with large number of nan or small datasets
 we can use `df.dropna(inplace=True)`.
 + Second Approach: Statistical Imputation `SimpleImputer()`
 + Third Approach : Simple Imputer with Model Evaluation
    * here we want to deal with missing value in train and test data seprately in order to prevent the data leakage for doing so we use `pipeline`
 + Fourth Approach: Compare Different Statistical Imputation Strategies
    * After finding out which strategy works better then we can choose that startegy for our model
 + Fifth Approach: K-Nearest Neighbors Imputation (model that can predict missing values)
 + Sixth Approach: Iterative Imputation 
    * in this approach the machine try to fill missing values by looking at each feature as a function of another feature and its iterative because it keeps repeat this process until all missing values being filled
    * the most common model for doing that is linear regression as if we are trying to predict the missing value by using other columns(features)
    * by default the Iterative Imputer repeat the number of iteration 10 times. It is possible the large number of iteration may begin to bias or skewed the estimate hence few iteration may be preffered to check which number of iteartion works better looks at the related notebook
    