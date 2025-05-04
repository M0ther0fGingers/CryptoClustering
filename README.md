# CryptoClustering
Module 19 Challenge

## Folder Structure
**Resources** folder contains the .csv file for this challenge. 
**CryptoClustering.ipynb** file contains the jupyter notebook python code for this challenge. 

## Code Development
**Sources** This code was developed from Module 19 class exercises and video recordings. Online documentation was used to create the plots and dataframes. 

## Code Elements
 - Import Dependencies: Pandas, hvplot, and sklearn including KMeans, PCA and StandardScaler
 - Prepare the data
   - create a dataframe, run a .describe and create a plot of the data.
   - use StandardScaler and .fit_transform on all column with numberical data.
   - Create a dataframe from the scaled data, then copy over the "coin_id" column from the original dataset and set it as the index of the new dataframe. 
 - Run KMeans
   - Create a list for k-values 1-11 (creates 1-10 on the plot)
   - Create an empty list for the inertia values, then write a for loop to fit and append the values into the k and inertia lists. 
   - Use the k and inertia data to create an elbow curve plot.
   - Based on this elbow curve, the best value for k is 4. That is the most acute angle before the line becomes considerably smooth. 
 - Create Clusters
   - fit and predict the scaled data to create clusters. 
   - Create a copy the scaled data to a new dataframe and combine the predictions into that dataframe. 
   - Create a scatter plot to view the clusters. 
 -  Optimize Clusters using PCA
    -  Set the n_components value to 3 to create a PCA model
    -  Use fit_transform on the scaled data with the pca model.
    -  Run .explained_variance_ratio_ to verify the dataset contains a reasonable amount of the original data. In this case, nearly 90% of the original data is present, which is a good results. 
    -  Create a new dataframe for the PCA data, pull in the coin_id as the index
 -  Find the best value for k
 -  Using the same KMeans method, find the best value for k
 -  4 was the best value in this dataset as well
-  Create clusters using PCA data
   -  Using the same clustering method, create data clusters using the pca data
   -  create a scatterplot of the pca clusters
-  Compare results
   -  print both elblow plots side by side to see the difference. 
      -  the results of both elbow plots is 4
      -  however, the pca elbow curve plot has a lower inerta than the first plot. 
      -  A lower inertia value indicates the data is clustered more tightly together, which should yield a better result
   -  print both cluster plots side by side to see the difference. 
      -  You can see that the pca data is clustered more tightly together as indicated by the pca elbow curve.