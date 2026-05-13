# Dataset Notes

This file contains analysis of the four datasets for the securitisation risk analytics project.

## 1. auto_loan_securitisation_data.csv

### Column Names
- Loan_ID
- Borrower_ID
- Loan_Amount
- Interest_Rate
- Term
- Origination_Date
- Maturity_Date
- Current_Balance
- Payment_Status
- Credit_Score
- Vehicle_Make
- Vehicle_Model
- Vehicle_Year
- Securitisation_Pool_ID

### Column Explanations
- **Loan_ID**: A unique number for each loan, like a license plate for tracking.
- **Borrower_ID**: Unique ID for the person who borrowed the money.
- **Loan_Amount**: The original amount of money lent for the car.
- **Interest_Rate**: The percentage charged as extra for borrowing, like a fee.
- **Term**: How many months the loan lasts.
- **Origination_Date**: When the loan was first given.
- **Maturity_Date**: When the loan should be fully paid back.
- **Current_Balance**: How much money is still owed right now.
- **Payment_Status**: If payments are on time, late, or paid off.
- **Credit_Score**: A number showing how trustworthy the borrower is with money.
- **Vehicle_Make**: The brand of the car (e.g., Toyota).
- **Vehicle_Model**: The specific type of car (e.g., Camry).
- **Vehicle_Year**: The year the car was made.
- **Securitisation_Pool_ID**: ID of the group of loans bundled together for investment.

### Data Types
- **Numeric**: Loan_Amount, Interest_Rate, Term, Current_Balance, Credit_Score, Vehicle_Year
- **Categorical**: Payment_Status, Vehicle_Make, Vehicle_Model, Securitisation_Pool_ID
- **Date**: Origination_Date, Maturity_Date

### Missing Values
- Possible missing: Credit_Score (some borrowers might not have scores), Vehicle details if not recorded.

### KPIs and Business Insights
- Default Rate: % of loans not paid back.
- Average Loan Amount: Typical size of loans.
- Delinquency Rate: % of loans behind on payments.
- Insights: Identify risky borrowers, assess pool health for investors.

### Connections to Other Datasets
- Links to static_pool_vintage_data via Securitisation_Pool_ID for vintage analysis.
- Links to dynamic_loss_monthly via Pool_ID for loss tracking.
- Links to dpd_snapshot_history via Loan_ID for delinquency details.

### Power BI Visuals
- Bar chart: Payment status distribution.
- Scatter plot: Credit score vs. current balance.
- Line chart: Loan origination trends.

## 2. static_pool_vintage_data.csv

### Column Names
- Vintage_Year
- Month
- Original_Balance
- Current_Balance
- Cumulative_Losses
- Delinquency_Rate
- Default_Rate

### Column Explanations
- **Vintage_Year**: The year the loans were originated.
- **Month**: The month of the report.
- **Original_Balance**: Total money lent initially for the vintage.
- **Current_Balance**: How much is still owed now.
- **Cumulative_Losses**: Total money lost so far from defaults.
- **Delinquency_Rate**: % of loans that are late on payments.
- **Default_Rate**: % of loans that have defaulted (not paid back).

### Data Types
- **Numeric**: Original_Balance, Current_Balance, Cumulative_Losses, Delinquency_Rate, Default_Rate
- **Categorical**: Vintage_Year (as category for grouping), Month
- **Date**: None explicit, but Month can be combined with Vintage_Year.

### Missing Values
- Possibly none, as it's aggregated data.

### KPIs and Business Insights
- Vintage Performance Curve: How defaults change over time.
- Loss Rate: Losses as % of original balance.
- Insights: Compare vintages to see economic trends affecting loans.

### Connections to Other Datasets
- Links to auto_loan_securitisation_data via pool ID for detailed loan info.
- Provides context for loss data in dynamic_loss_monthly.

### Power BI Visuals
- Line chart: Default rate over months for each vintage.
- Area chart: Cumulative losses.

## 3. dynamic_loss_monthly.csv

### Column Names
- Month
- Pool_ID
- Gross_Losses
- Net_Losses
- Recovery_Rate
- Loss_Severity

### Column Explanations
- **Month**: The month the losses are reported.
- **Pool_ID**: ID of the securitisation pool.
- **Gross_Losses**: Total losses before any recoveries.
- **Net_Losses**: Losses after subtracting recovered money.
- **Recovery_Rate**: % of lost money that was recovered (e.g., from selling the car).
- **Loss_Severity**: Average loss per defaulted loan.

### Data Types
- **Numeric**: Gross_Losses, Net_Losses, Recovery_Rate, Loss_Severity
- **Categorical**: Pool_ID
- **Date**: Month

### Missing Values
- Recovery_Rate might be missing if no recoveries.

### KPIs and Business Insights
- Monthly Loss Trend: How losses change over time.
- Recovery Effectiveness: How well money is recovered.
- Insights: Assess risk mitigation strategies.

### Connections to Other Datasets
- Links to securitisation data via Pool_ID.
- Provides loss details for loans in dpd_snapshot_history.

### Power BI Visuals
- Time series line chart: Net losses over months.
- Bar chart: Recovery rates by pool.

## 4. dpd_snapshot_history.csv

### Column Names
- Snapshot_Date
- Loan_ID
- Days_Past_Due
- Bucket
- Amount_Past_Due

### Column Explanations
- **Snapshot_Date**: Date when the snapshot was taken.
- **Loan_ID**: Unique loan identifier.
- **Days_Past_Due**: How many days the payment is late.
- **Bucket**: Category of lateness (e.g., 30-59 days late).
- **Amount_Past_Due**: How much money is overdue.

### Data Types
- **Numeric**: Days_Past_Due, Amount_Past_Due
- **Categorical**: Bucket
- **Date**: Snapshot_Date

### Missing Values
- Amount_Past_Due might be zero for current loans.

### KPIs and Business Insights
- Delinquency Distribution: How many loans in each bucket.
- Average DPD: Typical lateness.
- Insights: Early warning for defaults.

### Connections to Other Datasets
- Links to auto_loan_securitisation_data via Loan_ID for borrower details.
- Feeds into loss calculations in dynamic_loss_monthly.

### Power BI Visuals
- Histogram: Distribution of days past due.
- Trend line: DPD over time.