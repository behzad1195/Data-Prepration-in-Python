## Intro
In most cases the chance that you get a prepared data ready to feed in your model is very low or close to zero. Here you can find all steps necessary for data preprations. Each section contains a jupyter notebook (Notes) that provide a short summary to answer why we need to do these stpes as well as theories and logics behind each step. 

## Table of Contents
### 1. Foundations ->  Foundations (Notes).md
+ 1.1 Data cleansing
+ 1.2 Feature Selections
+ 1.3 Data Tranforms
+ 1.4 Feature Engineering
+ 1.5 Dimensionality Reduction
+ 1.6 Data Leakage
+ 1.7 Case Study: Data Leakage: Train/Test/Split -> (Data Preparation With Training and Testing Sets.ipynb)

### 2. Data Cleansing -> Data Cleansing (Notes).md
+ 2.1 Identify columns that contains a single values -> (Sparse Column Identification and Removal.ipynb)
+ 2.2 Identify column with few Values -> (Sparse Column Identification and Removal.ipynb)
+ 2.3 Identify Columns with low variance -> (Sparse Column Identification and Removal.ipynb) 
+ 2.4 Identify and removes rows that contain duplicate data -> (Identify and Remove Duplicate Rows.ipynb)
+ 2.5 Remove outliers - the STD approach (Outlier Removal - Standard Deviation Approach.ipynb)
+ 2.6 Remove outliers - The IQR approach(Outlier Removal - IQR Approach.ipynb)
+ 2.7 Automatic Outlier Detection -> (Automatic Outlier Detection.ipynb)
+ 2.8 Mark missing values -> (Mark Missing Values.ipynb)
+ 2.9 Remove rows with missing values -> (Remove Missing Values.ipynb)
+ 2.10 Statistical imputation -> (Statistical Imputation with Simple Imputer.ipynb)
+ 2.11 Simple imputer with model evaluation -> (Simple Imputer With Model Evaluation.ipynb)
+ 2.12 Compare different statistical imputation strategites -> (Compare Different Imputed Statistics.ipynb)
+ 2.13 Statistcal imputation with KNN -> (Statistical Imputation With KNN.ipynb)
+ 2.14 Iterative Imputation -> (Iterative Imputer Data Transform.ipynb)
+ 2.15 IterativeImputer and Model Evaluation -> (IterativeImputer and Model Evaluation.ipynb)
+ 2.16 IterativeImputer and different imputaion order -> (IterativeImputer and Different Number of Iterations.ipynb)

### 3. Feature Selection -> Feature Selection (Notes).md
+ 3.1 Feature selection for categorical data -> (Categorical Feature Selection.ipynb)
    - most common techinques are avialable within the above notebook. For more info about the specifics of each techinque look at (Feature Selection (Notes.ipynb)
+ 3.2 Feature selection for numerical data -> (Choosing Numerical Input Features.ipynb)
    - most common techinques are avialable within the above notebook. For more info about the specifics of each techinque look at (Feature Selection (Notes.ipynb) 
+ 3.3 Select features for numerical output -> (Select Features for Numerical Output.ipynb)
+ 3.4 Select features using RFE -> (Selecting Features using RFE.ipynb)
    - RFE methods for classification and regression as well as RFE Hyperparameters are avialable within the above notebook. For more info about the specifics of each techinque look at (Feature Selection (Notes.ipynb) 
+ 3.5 Feature importance score -> (Feature Importance (Notes).ipynb)
+ 3.6 Feature importance scores: Linear Regression, Logistic Regression, CART, Random Forest, Permutation and feature selection with importance -> (Feature Importance Scores.ipynb)

### 4. Data Transforms -> Data Transforms (Notes).md
+ 4.1 For numerical data: MinMaxScaler, Standardscaler, Robust Scaling. For categorical data: Ordinal Encoding, One-Hot Encoding, Dummy Variables -> (Data Rescaling .ipynb) 
    - For more info about the specifics of each techinque look at (Data Transforms (Notes).ipynb)
+ 4.2 Power Transforms: Box-Cox, Yeo-Johnson -> (Power Transforms.ipynb)
    - For more info about the specifics of each techinque look at (Data Transforms (Notes).ipynb)
+ 4.3 Polynomial Features: Polynomial Feature Transform.ipynb 
    - For more info about the specifics of each techinque look at (Data Transforms (Notes).ipynb)

### 5. Advanced Transforms - > Advanced Transforms (Notes).md
+ 5.1 Transforming different data types, the column transformer, automatically transform target variable, save model and data scaler, load and apply saved scaler -> (Advanced Transforms.ipynb)

### 6. Dimensionality Reduction -> Dimensionality Reduction (Notes).md
+ 6.1 Dimensionality Reduction methods: Linear Discriminant Analysis(LDA) and  Principal Component Analysis (PCA) -> (Dimensionality Reduction.ipynb)
    - For more info about the specifics of each techinque look at (Dimensionality Reduction (Notes).ipynb)
