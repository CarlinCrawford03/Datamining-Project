# Data Mining Project – Nutritional Analysis & Outlier Detection

## Overview
This project analyzes a dataset of food items based on nutritional content to identify patterns, relationships, and potential misclassified items. Using data mining techniques, we explored correlations between nutrients, selected important features for classification, and detected outliers within food categories.

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
- Identify important features for classifying food items
- Detect misfit or outlier rows within food categories

## Methods

### Correlation Analysis
We examined relationships between nutritional variables using correlation analysis. This helped identify strong positive and negative relationships and provided insight into how nutrients interact across food categories.

### Feature Selection
We selected the following three key variables for classification:

- Sugar
- Total Fat
- Kilocalories

These variables were chosen because they capture sweetness, fat content, and energy density, making them useful for distinguishing between food groups.

### Outlier Detection
To identify unusual or misfit rows, we:

1. Calculated category-level averages using a **GroupBy** node
2. Joined category averages back to the original dataset using a **Joiner** node
3. Computed a misfit score based on deviation from category averages
4. Applied a threshold of **mean + 2 × standard deviation** to flag outliers

## Key Findings

### Correlation Insights
- Sugar and carbohydrates showed a moderate positive relationship
- Total fat and saturated fat were strongly correlated
- Total fat strongly correlated with kilocalories
- Water and kilocalories showed a strong negative relationship

### Feature Insights
Sugar, total fat, and kilocalories were effective for separating food items based on nutritional density and composition.

### Outliers Identified
A total of **331 outlier rows** were identified.

Examples included:
- Milk products with unusually high sugar levels
- Whey products with extreme nutrient values
- Egg products with higher-than-expected fat or calorie values

These outliers may represent:
- Specialty or highly processed foods
- Potential labeling inconsistencies
- Category mismatches or unusual product formulations

## Conclusion
This project demonstrates how data mining techniques can be used to uncover meaningful nutritional patterns and identify unusual observations in food data. By comparing each item to its category average, we were able to detect misfit rows that may reflect either real product variation or possible data quality issues.

## Contributors
- Jack Resnick
- Carlin Crawford
- Gustave Mensah
- Mason Cooper
