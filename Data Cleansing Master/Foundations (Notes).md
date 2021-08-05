### Steps for The Machine Learning Pipeline
    1. Define Problem
        * Classification / Regression
        * EDA / Visualization
    2. Prepare Data
        * Transforming the raw data into a form that is the best for model building
    3. Evaluate Models
        * Design the robust test strategy
        * create a baseline so you could compare your model accuracy with that
        * choose the best features/metrics
        * sampling techniques for train test split
        * k-fold cross-validation
        * hyperparameters tuning
        * ensamble of models
    4. Finalize the Model
        * models slection
  
### Common Data Exploration Tasks
    1. Data Cleaning
    2. Feature Selection
    3. Data Tranforms
    4. Feature Engineering
    5. Dimensionality Reduction
 
### Choosing a Data Prepration Approach
    1. Gather Data
    2. Discuss Project
    3. Choose Inputs/Outputs
    4. Review the Data
    5. Summary Statistics
    6. Plots and Charts

### 80% or more of ML is data prepration
    for data prepration you must know:
    1. Types of Data Prepration
    2. The types of models for your problem
    3. How to Configure Each Technique
  
### Data Preparation - Data Cleansing
    - Fixing systematic problems and errors of messy data  
    1. Basics : Redundant Samples, Redundant Features
    2. Ouliers : Extreme Values
    3. Missing: Mark, Impute
   
### Data Preparation - Feature Selection
    * **Feature Selection** refers to techniques for selecting a subset of input features that are most relevant to the target variable that is being predicted.
    * All things being equal, the simplest solution is often the best one. -William Occam

#### Feature Selection
    1. Unupervised
    2. Supervised:
        * Intrinsic ->Trees
        * Wrapper Methods -> RFE
        * Filter Methods -> Feature Importance / -> Stats
    3. Dimesionality Reduction
  
### Data Preparation - Feature Selection
    * **Data Transforms** are used to change the type or distribution of data variables

#### Data Variable
        1. Numeric: Integer/Float
        2. Categorical: Nominal, Ordinal, Boolean

#### Three Power Transforms
        1. Discretization
        2. Ordinal
        3. One-Hot Encoding

#### Standardize Vs. Normalize
    1. Normalization: Rescale values to a range of 0-1
    2. Standardization: Rescale data to mean of 0 and STD of 1 (Guassian Distribution) 
   
### Data Preparation - Feature Selection
    * **Featue Engineering** refers to the process of creating new input variables from the available data.
 
    ### Data Prepration - Dimensionality Reduction
    * Techniques for reducing the number of input variables in training data.
    * The **Curse of Dimesionality** can be defined as the difficulty of searching through the space gets a lot harder as you have more dimensions.
    * a. Martix Factorization Technique:
        1. Principal Component Analysis (PCA/PCS)
        2. Singular Value Decomposition (SVD)
    * Model Based
        1.LDA
    * Mainfld Learning
        1.SOM
        2.tSNE
   
    ### Data Prepration - Data Leakage
    * Data Leakage happens when data outside the training dataset is used to create the model
    * **Possible Leakage Approach**
        1. Prepare Dataset
        2. Split Dataset
        3. Evaluate Model
    * In order to avoid the **Data Leakage**, the **Data prepration** must be fit **ONLY** on the training dataset.

    #### Fix Leakage Approach
    Split Dataset -> Fit Data Prepration on Training Dataset -> Apply Data Prepration o Training and Testing Dataset   -> Evaluate Model
