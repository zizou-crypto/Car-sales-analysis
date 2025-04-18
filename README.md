# Car-sales-analysis
Car sales trend in Norway using python

# Norwegian Car Sales Analysis
1. Project Overview
Description: This project analyzes trends in car sales in Norway, a market experiencing a rapid transition towards electric vehicles (EVs) and a reduction in carbon emissions. The analysis is based on three datasets covering car sales data in Norway, with a focus on the top twenty car models sold between 2007 and 2017. The project aims to provide insights into sales trends, fuel type distribution, car model/make performance, used vs. new car sales, import statistics, and sales patterns.
Purpose: The project's objectives are to:
- Analyze car sales trends over time.
- Determine the distribution of fuel types (Electric, Hybrid, Diesel).
- Evaluate the performance of top car models and makes.
- Compare used car sales with new car sales.
- Analyze import statistics and their Year-over-Year (YoY) changes.
- Identify peak and dip periods in car sales.

Target Audience: This project is relevant to:
- Automotive industry analysts
- Market researchers
- Environmental organizations
- Policymakers
- Anyone interested in the trends in the automotive industry, particularly EV adoption.

2. Skills Demonstrated

This project showcases the following data analyst skills:
- Data Analysis with Python: Using Python and the Pandas library to analyze car sales data.
- Data Manipulation: Cleaning, merging, and transforming multiple datasets.
- Exploratory Data Analysis (EDA): Performing EDA to understand data characteristics and identify patterns.
- Statistical Analysis: Calculating summary statistics, correlations, and growth rates.
- Data Visualization: (In a separate section) Creating visualizations (if any were created) to communicate findings.
- Data Interpretation: Deriving meaningful insights and conclusions from the analysis.
- Problem Solving: Analyzing a real-world dataset to provide insights into a specific industry and market.

3. Project Details

Tools Used:
- Python
- Pandas: For data manipulation and analysis.
- Jupyter Notebook: For writing and executing Python code.
- Matplotlib.pyplot: For data visualization.

Data Sources:
The datasets were obtained from Kaggle: https://www.kaggle.com/datasets/dmi3kno/newcarsalesnorway?select=norway_new_car_sales_by_month.csv

Data Description:
The project involves three datasets:
Dataset 1: Contains information about the top 20 car models sold in Norway, including model, model year, month, quantity, and percentage of total sales (4377 rows, 5 columns).
Dataset 2: Contains data about new car passenger sales by car make (2694 rows, 6 columns).
Dataset 3: Provides detailed statistics on sales, fuel types, imports, and YoY changes (121 rows, 17 columns), including year, and quantities for Electric, Diesel, and Hybrid vehicles.

Key Metrics Analyzed:
- Car make sales percentage
- Car make with most sales
- Monthly trend sales
- Most count and average sales for car model
- Correlation between year and total sales percentage
- Fuel type contributions to sales
- New vs. used car sales and their ratio
- Average YoY quantity change and import change for the top 5 months

4. Methodology

The following steps were taken to analyze the data:
Data Loading:
- The datasets were loaded into Pandas DataFrames using the pd.read_csv() function.
- Encoding issues were handled using the 'ISO-8859-1' encoding to correctly read Norwegian characters.

Data Cleaning:
- Duplicate rows were removed using car_sales.drop_duplicates().
- Missing values were checked using car_sales.info().
- Missing values in the merged datasets were replaced with the column's mean using the fillna() function.

Data Merging:
- The three datasets were merged using the pd.merge() function with a left join:
- combined_sales = pd.merge(car_sales, car_make, on=['Make', 'Month', 'Year'], how='left')
- combined_df = pd.merge(combined_sales, month_analysis, on=['Month', 'Year'], how='left')
- Unnecessary columns were dropped using the del function.

Exploratory Data Analysis (EDA):
- Summary statistics for key variables were generated using combined_df.describe().

Analysis:
- Calculated make sales percentages.
- Identified car make with the most sales and analyzed monthly sales trends.
- Determined the most frequent and average sales for each car model.
- Analyzed the correlation between year and total sales percentage.
- Determined the contribution of different fuel types to overall sales.
- Compared new and used car sales over the years.
- Examined the average YoY quantity and import changes for the top 5 months.

Data Visualization:
- Scatter plots were used to visualize the correlation between year and sales percentage.
- Bar charts were used to show fuel type distribution and compare sales across top car makes.
- Line charts were used to visualize trends in car sales quantity and YoY changes.

5. Key Insights
The analysis revealed the following insights:
- Top 20 Models Performance: The top 20 car models consistently contributed a significant portion of total car sales, with their share fluctuating between 1% and 15% over the years.
- Fuel Type Distribution: Diesel car sales showed a steady increase, while electric car sales declined, indicating a lower consumer preference for greener technologies during the period analyzed.
- Top Car Makes: Toyota, Volvo, and Volkswagen were the leading car makes in the Norwegian market. Diesel passenger cars significantly contributed to the sales performance of these top makes.
- New vs. Used Cars: New car sales showed stronger growth than used car sales, with the used-to-new car ratio remaining below 0.5 in most years, suggesting a preference for new cars. However, used car sales gained prominence from 2012 onwards, indicating a shift towards cost-saving options.
- Peak Sales Years: Years around 2007, 2014, and 2016 saw higher-than-average sales contributions from the top 20 models, potentially due to model launches, promotions, or changes in consumer preferences.

6. Challenges and Solutions
- Challenge: Handling encoding issues with the dataset.
  Solution: Used the 'ISO-8859-1' encoding in pd.read_csv() to correctly read Norwegian characters.
- Challenge: Missing values in the merged dataset.
  Solution: Replaced missing values with the mean of the respective column using fillna().

7. Future Enhancements

- Incorporate additional datasets, such as economic indicators or consumer confidence indices, to provide a more comprehensive analysis.
- Develop a predictive model to forecast future car sales trends.
- Perform a more detailed analysis of the factors influencing consumer preferences for different fuel types.
- Create interactive visualizations to allow users to explore the data dynamically.
- Expand the analysis to include other Scandinavian countries to identify regional trends.

8. Conclusion

This project provides a comprehensive analysis of car sales trends in Norway, highlighting the dominance of top car models, the evolution of fuel type preferences, and the dynamics of the new and used car markets. The findings suggest that while new cars were generally preferred, economic factors may have driven consumers towards used cars in certain periods. The analysis also identifies key players and trends in the Norwegian automotive market, providing valuable insights for industry stakeholders.
