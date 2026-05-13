# Initial EDA Plan

Exploratory Data Analysis (EDA) is the process of investigating datasets to summarize their main characteristics, often with visual methods.

## Steps for EDA

1. **Data Loading and Inspection**
   - Load each CSV file into Python (using pandas).
   - Check the shape (rows, columns) of each dataset.
   - Display first few rows (head) and last few rows (tail).
   - Get data types and basic info.

2. **Data Cleaning**
   - Handle missing values: Identify, impute or remove.
   - Check for duplicates.
   - Correct data types (e.g., dates as datetime).
   - Outlier detection and treatment.

3. **Univariate Analysis**
   - For numeric columns: Describe statistics (mean, median, std, min, max).
   - Histograms and box plots for distributions.
   - For categorical: Value counts, bar charts.

4. **Bivariate Analysis**
   - Correlations between numeric variables.
   - Scatter plots, heatmaps.
   - Cross-tabs for categorical vs categorical.

5. **Multivariate Analysis**
   - Analyze relationships across datasets (joins on IDs).
   - Time series analysis for date columns.

6. **Key Insights and Visualizations**
   - Identify patterns, trends, anomalies.
   - Create dashboards in Power BI.

7. **Risk Analytics Specific**
   - Calculate delinquency and default rates.
   - Vintage analysis: Performance by origination year.
   - Loss projections.

## Tools
- Python: pandas, matplotlib, seaborn
- Jupyter Notebooks for code
- Power BI for dashboards

## Timeline
- Week 1: Data loading and cleaning
- Week 2: Univariate and bivariate analysis
- Week 3: Multivariate and insights
- Week 4: Reporting and Power BI