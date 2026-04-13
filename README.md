# Data Mining Project – Nutritional Analysis, Outlier Detection, PCA & Clustering

## Overview
This project analyzes a dataset of food items based on nutritional content to identify patterns, relationships, unusual observations, and grouping structure in the data. Using data mining techniques, we explored correlations, selected important features for classification, detected outliers within categories, and applied PCA with k-means clustering to better understand the dataset.

## Dataset
The dataset includes the following nutritional variables for each food item:

- Carbohydrates
- Fiber
- Kilocalories
- Protein
- Sugar
- Water
- Saturated Fat
- Total Fat (Lipids)

## Objectives
The main goals of this project were to:

- Understand relationships between nutritional variables
- Identify key features for classifying food items
- Detect misfit or outlier rows within categories
- Reduce the dataset into lower-dimensional space using PCA
- Apply k-means clustering to identify natural groupings in the data
- Compare clustering results across different values of k

## Methods

### Correlation Analysis
We examined relationships between nutritional variables using correlation analysis. This helped identify strong positive and negative relationships and better understand how nutrients interact.

### Feature Selection
We selected three key variables for classification:

- Sugar
- Total Fat
- Kilocalories

These variables were chosen because they best capture sweetness, fat content, and energy density, which are useful for distinguishing between food categories.

### Outlier Detection
We identified misfit rows by:

1. Calculating category-level averages with a **GroupBy** node  
2. Joining category averages back to the original dataset with a **Joiner** node  
3. Computing a misfit score based on deviation from category averages  
4. Applying a threshold of **mean + 2 × standard deviation** to flag outliers  

### Principal Component Analysis (PCA)
We applied PCA to reduce the nutritional dataset to two dimensions for visualization and clustering. The first two principal components captured approximately **67.7% of the total variance**, allowing us to represent most of the dataset’s variation in a 2D space.

### k-Means Clustering
We used k-means clustering on the PCA-transformed data to group similar food items. Different values of k were tested to compare how the clusters changed. Smaller values of k produced broader groups, while larger values created more detailed subgroupings.

## Key Findings

### Correlation Insights
- Sugar and carbohydrates showed a moderate positive relationship
- Total fat and saturated fat were strongly correlated
- Total fat strongly correlated with kilocalories
- Water and kilocalories showed a strong negative relationship

### Feature Insights
Sugar, fat, and calories were effective in separating food items based on nutritional density and composition.

### Outliers Identified
A total of **331 outlier rows** were identified.

Examples included:
- Milk products with unusually high sugar
- Whey products with extreme nutrient values
- Egg products with higher-than-expected fat or calorie values

These outliers may represent:
- Specialty or processed food products
- Labeling inconsistencies
- Category assignment issues

### PCA & Clustering Insights
- The first two principal components captured **67.7%** of the dataset’s variance
- PCA made it easier to visualize the structure of the data in two dimensions
- k-means clustering showed that the dataset contains several distinct groups based on nutritional similarity
- With higher values of k, clusters became more detailed and allowed for more specific subgrouping of food items
- In PCA space, many clusters appeared reasonably well defined, with some overlap in denser regions

## Conclusion
This project demonstrates how data mining techniques can be used to uncover meaningful relationships and identify unusual patterns in nutritional data. By combining correlation analysis, feature selection, outlier detection, PCA, and clustering, we were able to better understand both the nutritional structure of the dataset and the natural grouping of food items.

## Contributors
- Jack Resnick
- Carlin Crawford
- Gustave Mensah
- Mason Cooper
