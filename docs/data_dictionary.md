# Data Dictionary

| Dataset | Column Name | Data Type | Description |
|---------|-------------|-----------|-------------|
| auto_loan_securitisation_data.csv | Loan_ID | String/Categorical | Unique identifier for each loan |
| auto_loan_securitisation_data.csv | Borrower_ID | String/Categorical | Unique ID for the borrower |
| auto_loan_securitisation_data.csv | Loan_Amount | Numeric | Original loan amount |
| auto_loan_securitisation_data.csv | Interest_Rate | Numeric | Annual interest rate (%) |
| auto_loan_securitisation_data.csv | Term | Numeric | Loan term in months |
| auto_loan_securitisation_data.csv | Origination_Date | Date | Date loan was originated |
| auto_loan_securitisation_data.csv | Maturity_Date | Date | Date loan matures |
| auto_loan_securitisation_data.csv | Current_Balance | Numeric | Current outstanding balance |
| auto_loan_securitisation_data.csv | Payment_Status | Categorical | Current payment status (e.g., current, delinquent) |
| auto_loan_securitisation_data.csv | Credit_Score | Numeric | Borrower's credit score |
| auto_loan_securitisation_data.csv | Vehicle_Make | Categorical | Vehicle manufacturer |
| auto_loan_securitisation_data.csv | Vehicle_Model | Categorical | Vehicle model |
| auto_loan_securitisation_data.csv | Vehicle_Year | Numeric | Year vehicle was manufactured |
| auto_loan_securitisation_data.csv | Securitisation_Pool_ID | Categorical | ID of the securitisation pool |
| static_pool_vintage_data.csv | Vintage_Year | Numeric/Categorical | Year of loan origination |
| static_pool_vintage_data.csv | Month | Numeric/Categorical | Month of report |
| static_pool_vintage_data.csv | Original_Balance | Numeric | Total original balance for vintage |
| static_pool_vintage_data.csv | Current_Balance | Numeric | Current total balance |
| static_pool_vintage_data.csv | Cumulative_Losses | Numeric | Total losses accumulated |
| static_pool_vintage_data.csv | Delinquency_Rate | Numeric | Percentage of delinquent loans |
| static_pool_vintage_data.csv | Default_Rate | Numeric | Percentage of defaulted loans |
| dynamic_loss_monthly.csv | Month | Date | Reporting month |
| dynamic_loss_monthly.csv | Pool_ID | Categorical | Securitisation pool ID |
| dynamic_loss_monthly.csv | Gross_Losses | Numeric | Total gross losses |
| dynamic_loss_monthly.csv | Net_Losses | Numeric | Net losses after recoveries |
| dynamic_loss_monthly.csv | Recovery_Rate | Numeric | Percentage recovered |
| dynamic_loss_monthly.csv | Loss_Severity | Numeric | Average loss per default |
| dpd_snapshot_history.csv | Snapshot_Date | Date | Date of snapshot |
| dpd_snapshot_history.csv | Loan_ID | String/Categorical | Loan identifier |
| dpd_snapshot_history.csv | Days_Past_Due | Numeric | Number of days past due |
| dpd_snapshot_history.csv | Bucket | Categorical | Delinquency bucket (e.g., 30-59 days) |
| dpd_snapshot_history.csv | Amount_Past_Due | Numeric | Amount overdue |