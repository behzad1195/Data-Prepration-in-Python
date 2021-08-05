### Curse of Dimensionality
 * If we have too many rows and columns it adversly affect the model performance. Hence reducing the features of our model could increase the performance.
 * ML algorithms fit on data with many input features, is referreed to as the **curse dimensionality**.

#### Techniques for Dimensionality Reduction
 * There are many techniques for dimensionality here we look at the most common ones aka **Feature Selection** techniques that use scoring or statistical methods to select which features to keep and which to delete.
  + **Wrapper Methods and Filter Methods** are the most common techniques that we discussed them in detial in *Feature Selection (Notes)* Notebook. 
  + **Matrix Factorization** methods can be used to reduce a datset matrix into its constituent parts. Methods such as *agent decomposition* and *singular value decomposition* are among most common methods for Matrix Factorization. The parts can be ranked and subset of those parts can be selected that best capture the sealan structure of matrix that best represent the dataset. The most common method of ranking these components is known as **Principle Component Analysis (PCA)**.  
  + **Manifold Learning:** techniques for high dimensionality statistics can also be used for dimensionality reduction. These techniques are sometimes referred to as **manifold learning** and are used to create a low-dimensional projection of high-dimensional data. However often for the purpose of **data visualization**. Here you can look at the detailed documentation of various manifold learning techniques https://scikit-learn.org/stable/modules/manifold.html
  + Deep learning neural networks can be constructed to perform dimensionality reduction. A popular approach is called **autoencoders**. more explanation https://machinelearningmastery.com/lstm-autoencoders/
 
#### Linear Discriminant Analysis (LDA)
 * LDA is linear ML algorithms used in multi-class classification. It seeks to seprate or discriminate the samples in training dataset by class value. Specifically the model seeks to find a linear combinations of input variables that achieves the maximum sepration of the sample classes and the minimum sepration of the sample within each class. There are many ways to frame and solve LDA. Yet we should always standardized the data before feeding it to LDA. 
  
#### Principal Component Analysis (PCA)
 * it is the most popular technique in ML for dimensionality reduction and it comes from the field of linear algebra. It helps us to delete the features prior to feeding them to the model. It is better to scaled your data before performing PCA especially when you have unscaled data. 
  
    