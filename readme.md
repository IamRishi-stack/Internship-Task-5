# Titanic Dataset Exploratory Data Analysis (EDA)

![Titanic Heatmap] (Preview 2.png) 
*Example visualization from the analysis*

## Project Overview
This project performs an in-depth exploratory analysis of the Titanic passenger dataset to identify factors influencing survival rates. The analysis combines statistical methods and visualizations to uncover key patterns and relationships.

## Dataset Information
The dataset contains records for 891 Titanic passengers with the following features:

| Column | Description | Type |
|--------|-------------|------|
| PassengerId | Unique identifier | Integer |
| Survived | Survival status (0 = No, 1 = Yes) | Binary |
| Pclass | Ticket class (1st, 2nd, 3rd) | Ordinal |
| Name | Passenger name | String |
| Sex | Gender | Categorical |
| Age | Age in years | Numeric |
| SibSp | Siblings/spouses aboard | Integer |
| Parch | Parents/children aboard | Integer |
| Ticket | Ticket number | String |
| Fare | Passenger fare | Numeric |
| Cabin | Cabin number | String |
| Embarked | Port of embarkation | Categorical |

## Analysis Approach

### 1. Data Preparation
```python
# Handle missing values
df.dropna(subset=['Age', 'Embarked'], inplace=True)

# Convert types
df['Survived'] = df['Survived'].astype('category')
df['Pclass'] = df['Pclass'].astype('category')

2. Key Analysis Methods
Descriptive Statistics: .describe(), .info(), .value_counts()
Correlation Analysis: sns.heatmap(), df.corr()
Distribution Plots: sns.histplot(), sns.kdeplot()
Comparative Visuals: sns.boxplot(), sns.barplot()
Relationship Plots: sns.pairplot(), sns.scatterplot()

3. Advanced Techniques
# Created derived features
df['FamilySize'] = df['SibSp'] + df['Parch']
df['IsAlone'] = (df['FamilySize'] == 0).astype(int)
Key Findings
Survival Factors
Gender: 74% female vs 19% male survival rate
Class: 63% 1st class vs 24% 3rd class survival
Age: Children (<10) had 59% survival rate
Family: Small families (1-3 members) survived more
Visual Insights
Strong negative correlation between Pclass and Fare (-0.55)
Clear survival clusters in Fare vs Age plots
Most deaths occurred among 3rd class males


How to Run

Install requirements:


pip install pandas matplotlib seaborn jupyter


Launch Jupyter Notebook:


jupyter notebook titanic_analysis.ipynb


Run cells sequentially


File Structure
/titanic-analysis
│── /data
│   ├── titanic.csv              # Raw dataset
│── /outputs
│   ├── visualizations/          # Saved plots
│── titanic_analysis.ipynb       # Main analysis notebook
│── README.md                    # This file
Dependencies
Python 3.8+
pandas >= 1.2.0
matplotlib >= 3.3.0
seaborn >= 0.11.0
jupyter >= 1.0.0
Future Work
Machine learning model for survival prediction
Feature engineering (title extraction from names)
More detailed fare analysis by class

Author

Rishi Sikdar


### Key Features:
1. **Structured Documentation**: Clear sections for easy navigation
2. **Visual Examples**: Embedded sample visualization
3. **Code Snippets**: Key methodology highlights
4. **Reproducibility**: Exact package versions and run instructions
5. **Actionable Findings**: Bullet-pointed insights
6. **Professional Formatting**: Tables for data description
7. **Future Work**: Suggested extensions