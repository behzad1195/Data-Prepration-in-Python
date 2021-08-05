
### Feature Engineering
* Feature Engineering is the process of transforming raw data into features that better represent the underlying data.
* Although the majority of people are mostly looking for models and algorithms the most important part of the job is the feature engineering (cleaning data, adding/droping new and/or existing features). Without feature engineering what we do is mostly garbage in, garbage out.
* The quality of the features we feed the model is the primary limiting factor on the performance of that model.
* **Benefits of Feature Engineering:** Flexibility, Simplistic Model, Faster Model Executation Time

#### ML Pipeline
* Step 1 (Dataset) : Import and visualize the dataset (For Visualization techniques look at 'Visualization' folder - will be added later). We do it to get an idea about the types of features (columns/independent variables) that we have in a dataset. What they look like and how do they related to target variable (y/ dependent variable). 
 + In this step we use some data cleaning techniques and adding new features. This is the mmost crucial step in data science/ ML engineering (80% of what we do in each project). 
 + The 'Intro data cleansing' and 'Data Cleansing Master' folders provide sample of codes and documentation for each techniques according the list provided in each folder).
* Step 2 (Split Data): Segment the data into training/testing sets or use K-folds.
* Step 3 (Fit and Evaluate on Training data): Then we are using 5-folds cross-validation method to explore the variaty of different hyperparameters.
* Step 4 (Tune Hyperparameters) : Twak the models' knobs and switches called hyperparameters. 
* Step 5 (GridSearch CV): we will fold the step 3 and 4 into one step.
* Step 6 (Evaluate on Testing Data): In this step we choose a group of related models to the type of dataset that we have and chose the one  with best performance on our training dataset and then evaluate that model on the testing dataset.
* In reality the process should be repeated many times. You add a feature you evaluate model with it. and then you decide to whether keep it or not. You repeat this process until you reach to the model accuracy that satisfies the goal of project.
  
#### Feature Engineering Toolbox
* 1. Common Sence (e.g. Fraud Detection)
* 2. Dropping Features: Get rid of irrelevant features. 
* 3. Cleaning Features: Immuting missing values, Outliers detection, etc. 
* 4. Data Scaling: MinMAxScaler, StandardScaler etc.
* 5. Fix Skewed Data: PowerTransformer (Cox-Box, Yoe-Johnson)
* 6. Combining Features 

### Titanic Project 
* Here mostly the all steps from loading a dataset up to the execution of models are applied in a sequence which is kind of ML procedure standard and is practiced by majority of data scientist/ML engineers. Nothing new but I thought it wouldn't be a bad idea to write them here in steps. 
 - For general notes -> Feature Engineering (Notes).md
* 1. Loading and first glance on data -> Titanic Dataset - loading and first glance on data.ipynb
* 2. Exploring numerical data -> Titanic - Explore Continuous Features.ipynb
* 3. Plotting numerical data -> Titanic - Plotting.ipynb
* 4. Exploring categorical data -> Titanic - Explore categorical Features.ipynb
* 5. Plotting categorical data -> Titanic-PlotCategoricalFeatures.ipynb
* 6. Crafting and cleansing Features 
 + 6.1 Treat Missing Values in the Data -> Titanic-MeanValueImputation.ipynb
 + 6.2 Outlier Detection -> Titanic - RemoveOutliers.ipynb
 + 6.3 Transforming Skewed Features -> Titanic-TransformingSkewedFeatures.ipynb
 + 6.4 Craft New Features from Text -> Titanic - CraftNewFeaturesfromText.ipynb
 + 6.5 Create new feature -> Titanic - CreatingIndicators.ipynb
 + 6.6 Combining existing features into a new one -> Titanic - CombineExistingFeaturesIntoaNewFeatuer.ipynb
 + 6.7 Transforming categorical features to numerical -> Titanic - CategoricalFeaturestoNumeric.ipynb
* 7. Train/test split -> Titanic - CreateTrainingandTestingSets.ipynb
 + Well it seems that there is no consensus among Data scientist that where exactly we should do the train/test split. But personally think that where ever that our Data cleansing,Feature engineering, and Feature selection techniques may lead to the Data Leakage then we should do those steps after trian/test split. Where Data Leakage happens? good question! I don't know, I think it somehow depends to our personal judgement but I would say if you are not sure then do some googleing. 
* 8. Scaling features -> Titanic - ScalingFeatures.ipynb
* 9. Create Datasets for Modeling -> Titanic - CreateFinalDatasets.ipynb
* 10. Baseline Model -> Titanic - ModelRawFeatures.ipynb
* 11. Model with cleaned but original features -> Titanic - BuildModelwithCleanedOriginalFeatures.ipynb
* 12. Model with all features -> Titanic - ModelAllFeatures.ipynb
* 13. Model with reduced set of features -> Titanic - ModelReducedSetofFeatures.ipynb
* 14. Evaluate and compare all models -> Titanic - CompareandEvaluateAllModels.ipynb