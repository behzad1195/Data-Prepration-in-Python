### Titanic Project
 * Here mostly the all steps from loading a dataset up to the execution of models are applied in a sequence which is kind of ML procedure standard and is practiced by majority of data scientist/ML engineers. Nothing new but I thought it wouldn't be a bad idea to write them here in steps.
 For general notes -> Feature Engineering (Notes).md
 * 1. Loading and first glance on data -> Titanic Dataset - loading and first glance on data.ipynb
 * 2. Exploring numerical data -> Titanic - Explore Continuous Features.ipynb
 * 3. Plotting numerical data -> Titanic - Plotting.ipynb
 * 4. Exploring categorical data -> Titanic - Explore categorical Features.ipynb
 * 5. Plotting categorical data -> Titanic-PlotCategoricalFeatures.ipynb
 * 6. Crafting and cleansing Features
    6.1 Treat Missing Values in the Data -> Titanic-MeanValueImputation.ipynb
    6.2 Outlier Detection -> Titanic - RemoveOutliers.ipynb
    6.3 Transforming Skewed Features -> Titanic-TransformingSkewedFeatures.ipynb
    6.4 Craft New Features from Text -> Titanic - CraftNewFeaturesfromText.ipynb
    6.5 Create new feature -> Titanic - CreatingIndicators.ipynb
    6.6 Combining existing features into a new one -> Titanic - CombineExistingFeaturesIntoaNewFeatuer.ipynb
    6.7 Transforming categorical features to numerical -> Titanic - CategoricalFeaturestoNumeric.ipynb
* 7. Train/test split -> Titanic - CreateTrainingandTestingSets.ipynb
 + Well it seems that there is no consensus among Data scientist that where exactly we should do the train/test split. But personally think that where ever that our Data cleansing,Feature engineering, and Feature selection techniques may lead to the Data Leakage then we should do those steps after trian/test split. Where Data Leakage happens? good question! I don't know, I think it somehow depends to our personal judgement but I would say if you are not sure then do some googleing.
* 8. Scaling features -> Titanic - ScalingFeatures.ipynb
* 9. Create Datasets for Modeling -> Titanic - CreateFinalDatasets.ipynb
* 10. Baseline Model -> Titanic - ModelRawFeatures.ipynb
* 11. Model with cleaned but original features -> Titanic - BuildModelwithCleanedOriginalFeatures.ipynb
* 12. Model with all features -> Titanic - ModelAllFeatures.ipynb
* 13. Model with reduced set of features -> Titanic - ModelReducedSetofFeatures.ipynb
* 14. Evaluate and compare all models -> Titanic - CompareandEvaluateAllModels.ipynb
