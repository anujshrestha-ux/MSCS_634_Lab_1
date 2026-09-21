# MSCS 634 – Lab 1: Data Visualization, Data Preprocessing, and Statistical Analysis

**Name:** Anuj Shrestha

## Purpose
This lab applies data visualization, data preprocessing, and statistical analysis in a Jupyter Notebook using Pandas, NumPy, Matplotlib, and Seaborn. The dataset is the Kaggle Titanic passenger data (`titanic.csv`, 891 rows and 12 columns).

## Repository Contents
- `Lab1_Assignment_Anuj_Shrestha.ipynb` – the full notebook
- `titanic.csv` – dataset used
- `screenshots/` – required screenshots for each step
- `Lab1_Assignment_Anuj_Shrestha.docx` – screenshots with short descriptions

## Key Insights
- Passenger class mattered a great deal for survival: about 63% of 1st-class passengers survived, compared with 47% in 2nd class and only 24% in 3rd class.
- About 65% of passengers were male and 35% female. Children aged 10 or under had the highest survival rate (about 59%), while passengers over 60 had the lowest (about 23%).
- Fare is heavily right-skewed. After the outliers were removed, the mean fare is 17.82 and the median is 13.00.
- Fare and passenger class have the strongest correlation (-0.59). Survival is negatively correlated with class (-0.24) and positively with fare (0.23).

## Preprocessing Decisions and Challenges
- **Missing values:** Age was filled with the median and Embarked with the mode. Cabin was dropped because about 77% of its values were missing.
- **Outliers:** The IQR method on Fare (bounds -26.72 and 65.63) flagged 116 outliers, which were removed, leaving 775 of the original 891 rows.
- **Data reduction:** A 50% random sample (388 rows) was taken, and PassengerId, Name, and Ticket were dropped, leaving 8 columns.
- **Scaling and discretization:** Min-Max scaling was applied to Age and Fare, and Z-score standardization to Fare. Age was grouped into 5 categories and Fare into 3 quantile-based levels.
- **Challenge:** The hardest decision was how to handle missing values and outliers. The extreme fares are real data, so removing them changes the results (the mean fare dropped from 32.20 to 17.82). The trimmed data better represents a typical passenger, so the statistics describe that group rather than everyone on board.
