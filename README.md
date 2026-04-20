Data Mining Project – Nutritional Analysis, Outlier Detection, PCA & Clustering
Overview

This project analyzes a dataset of food items based on nutritional content to identify patterns, relationships, anomalies, and underlying grouping structures. Using a combination of data mining techniques, we explored correlations, selected key features, detected outliers, applied dimensionality reduction, and evaluated clustering performance.

Dataset

The dataset includes the following nutritional variables for each food item:

Carbohydrates
Fiber
Kilocalories
Protein
Sugar
Water
Saturated Fat
Total Fat (Lipids)
Objectives

The primary objectives of this project were to:

Understand relationships between nutritional variables
Identify key features for classification
Detect misfit or outlier observations within categories
Reduce dimensionality using Principal Component Analysis (PCA)
Apply clustering techniques to identify natural groupings
Evaluate clustering performance using validation techniques
Methods
Correlation Analysis

Correlation analysis was conducted to examine relationships between nutritional variables. This helped identify strong positive and negative associations and provided insight into how different nutrients interact.

Feature Selection

Three key variables were selected for classification:

Sugar
Total Fat
Kilocalories

These features were chosen because they capture sweetness, fat content, and energy density, which are critical in distinguishing food categories.

Outlier Detection

Outliers were identified using a deviation-based approach:

Category-level averages were computed using a GroupBy node
A Joiner node was used to merge averages back to the dataset
A misfit score was calculated based on deviation from category means
A threshold of mean + 2 × standard deviation was applied

A total of 331 outliers were identified.

Principal Component Analysis (PCA)

PCA was applied to reduce the dataset into two dimensions. The first two principal components captured approximately 67.7% of the total variance, enabling effective visualization and clustering in a lower-dimensional space.

k-Means Clustering

k-means clustering was applied to the PCA-transformed data. Multiple values of k were tested:

Lower k values produced broader clusters
Higher k values created more detailed subgroupings
Cluster Validation & Analysis (Week 5)
Analysis 1: Cluster Purity

Cluster purity was evaluated by grouping data by cluster and category and counting observations in each combination. Results showed:

Some clusters were dominated by a single category (high purity)
Other clusters contained multiple categories (low purity)
Certain clusters exhibited significant overlap between food categories
Analysis 2: Confusion Matrix

Clusters were mapped to their dominant category, and predictions were compared to actual labels using a confusion matrix.

Sample size: 2,000 observations
Correct classifications: 584
Incorrect classifications: 1,416
Accuracy: 29.2%

Findings:

Some categories (e.g., Fats and Oils, Sweets and Snacks) were classified more accurately
Other categories (e.g., Meat, Grains and Bread, Fruits, Beverages) were frequently misclassified
Results indicate substantial overlap between clusters
Analysis 3: Silhouette Scores

Silhouette coefficients were computed to evaluate cluster quality.

Overall mean silhouette score: 0.375

Interpretation:

Scores around 0.5–0.6 indicate well-defined clusters
Scores near 0 indicate overlapping clusters
Some negative values suggest potential misclassification

Overall, clustering demonstrated moderate structure with noticeable overlap.

Key Findings
Correlation Insights
Sugar and carbohydrates showed a moderate positive relationship
Total fat and saturated fat were strongly correlated
Total fat strongly correlated with kilocalories
Water and kilocalories showed a strong negative relationship
Feature Insights

Sugar, fat, and calories were effective in distinguishing food items based on nutritional composition.

Outlier Insights

Outliers included:

Milk products with unusually high sugar
Whey products with extreme nutrient values
Egg products with higher-than-expected fat or calorie values

These may represent:

Processed or specialty products
Data inconsistencies
Misclassification within categories
Clustering Insights
PCA captured most dataset variance in two dimensions
Clustering revealed natural groupings based on nutrition
Some clusters were well-defined, while others overlapped
Validation metrics confirmed moderate clustering quality
Conclusion

This project demonstrates how data mining techniques can be used to extract meaningful insights from nutritional data. While clustering revealed some structure, validation results (purity, confusion matrix, silhouette scores) indicate that food categories are not perfectly separable based on nutritional features alone. This suggests inherent overlap in nutritional profiles across food groups.

Contributors
Jack Resnick
Carlin Crawford
Gustave Mensah
Mason Cooper
Resources
KNIME Analytics Platform
Nutritional Dataset
