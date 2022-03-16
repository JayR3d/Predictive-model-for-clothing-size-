# Predictive-model-for-clothing-size-
Create a Predictive model that can show a customer what size of clothing will fit them from an online catalog. 
The dataset consists of different clothing products using different sizing conventions,the sizes were standardized into a single numerical scale preserving the order.

The data cleaning process consists of  Re-labeling inconsistent column names first, then Identifying the percentage of missing values. 

Now that I can see the percentage of missing values. 
The Waist, Hips and Bust columns have many missing values but we can handle that a bit later with an imputer.

I will begin with the selection of features relevant to the business problem. Then
I will check each column for uniqueness. 

The Bust column has one irregular entry to clean up.I will do this by selecting the first index of the distribution entered in the cell.

The Cup_size column must be converted to numerical data. After that I will select the first index of the distribution entered in the cell.

And drop the original Cup_size column.

The Height column must be converted from feet and inches to centimeters.

Now the data is ready for the knn Imputer.This Imputer will use a knn model to predict the missing values in the database. After that I will drop the numeric columns of the original dataset and concatenate the imputations data with the original dataset.

Now the outliers will be removed using a boxplot for each feature and an  InterQuartile Range calculation to find the lower & upper range. 

Once I have the lower range and the upper range. The next code cell will total the amount of rows and columns less than the lower range and those greater than the higher range

 the last code cell will remove outliers, reset the index & show the new shape of the data. This was done for all the features besides. The Target column ‘Size’.

Before I Split the data into X and y data. I will use a Feature Correlation heatmap. to identify the features most related to the size column and determine the relationship/association between the 'size' column (which is the target variable) and the other variables. The darker the colour, the stronger the relationship with 'size'. Waist, Bust, Hips and Bra_size have been selected for X features. 

The data is split into features ‘X’ and targets ‘y’. And then split into training and test sets.I apply principal component analysis with a number of components as two. To reduce the dimensionality of the features.

And lastly insert an XGBRegressor model to predict continuous data. And the MAE is 2.513
