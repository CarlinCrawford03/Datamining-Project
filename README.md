📊 Data Mining Project – Nutritional Analysis & Outlier Detection
📌 Overview

This project analyzes a dataset of food items based on their nutritional content to identify patterns, relationships, and potential misclassified items. Using data mining techniques, we explored correlations, selected key features for classification, and detected outliers within categories.

📂 Dataset

The dataset contains the following nutritional variables for each food item:

Carbohydrates
Fiber
Kilocalories
Protein
Sugar
Water
Saturated Fat
Total Fat (Lipids)
🔍 Objectives
Understand relationships between nutritional variables
Identify key features for classifying food items
Detect misfit or outlier rows within categories
📈 Methods
1. Correlation Analysis

We examined relationships between all nutritional variables using correlation metrics. Strong relationships were identified and interpreted to understand how nutrients interact.

2. Feature Selection

We selected three key variables:

Sugar
Total Fat
Kilocalories

These features capture sweetness, fat content, and energy density, making them effective for distinguishing between food categories.

3. Outlier Detection

We identified misfit rows by:

Calculating category-level averages using a GroupBy node
Joining averages back to the dataset using a Joiner node
Computing a misfit score based on deviation from category averages
Applying a threshold (mean + 2×standard deviation) to detect outliers
📊 Key Findings
Correlation Insights
Sugar and carbohydrates show a moderate positive relationship
Total fat and saturated fat are strongly correlated
Total fat strongly correlates with kilocalories
Water and kilocalories have a strong negative relationship
Feature Insights

Sugar, fat, and calories effectively separate food items based on nutritional density and composition.

Outliers
Identified 331 outlier rows
Examples include:
Milk products with unusually high sugar
Whey products with extreme nutrient values
Egg products with higher-than-expected fat/calories
These may represent:
Specialty or processed foods
Potential labeling or categorization inconsistencies
🛠 Tools Used
KNIME Analytics Platform
CSV Reader
Column Filter
GroupBy
Joiner
Math Formula / Column Expressions
Statistics
Row Filter
Sorter
📁 Workflow Summary
CSV Reader → Data Cleaning → GroupBy (Category Means)
→ Joiner → Feature Engineering (Misfit Score)
→ Statistics → Row Filter (Outliers) → Analysis
📌 Conclusion

This project demonstrates how data mining techniques can be used to uncover relationships and identify unusual patterns in nutritional data. By comparing each item to its category average, we were able to detect misfit rows that may indicate meaningful product variations or potential data inconsistencies.

👥 Contributors
Jack Resnick
Carlin Crawford
Gustave Mensah
Mason Cooper
