## Step 1: Data Collection

For this project, I’ve chosen to collect the financial statements of San Miguel Corporation, a publicly traded company with the stock ticker SMGBF. The financial data can be accessed from this [website](https://finance.yahoo.com/quote/SMGBF/financials?p=SMGBF)

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/3794105f-3d5f-4129-83cf-96860292218d)

I began by manually copying the financial statement and pasting it into an Excel spreadsheet. However, I encountered a formatting issue where the data did not distribute across individual cells as expected, but instead clustered into a single cell. This is what we refer to as ‘dirty data’, which is not ideal for analysis.

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/28bbaa54-6364-4faf-a6e4-5fabfd950664)
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/2ee89d64-7890-476c-8c8f-429c5f5c8a92)
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/f0da75a5-3e1e-49f9-bf27-c589291907d5)


To clean this data, there are two methods that I’m aware of: manual cleaning using Excel or utilizing Python’s pandas library. For this project, I’ve opted to use pandas in Python. The cleanup code can be found in the repository.

### Before:
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/39a2864f-7d69-4de7-99e1-76ed874d1484)
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/d281ff1d-650e-4091-8526-3773bac10509)
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/35627e6e-19ac-49d8-a037-0f9a845d4a15)


Comparing the ‘before’ and ‘after’ states of the data reveals a significant difference. With the data now clean and ready for analysis, it can be stored in a database.

### After:
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/8c26fa94-4526-4374-bd89-cf34c41619db)
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/ec681fe4-b2d8-4d77-bc39-6c9a3d6e66dc)
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/840a1d21-1046-41f9-a3b5-33a51f1fb8c4)

Export the cleaned table, transpose it locally in Excel for more efficient querying when it’s uploaded to the database.
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/97e0aadb-6563-4fc0-92b9-a2a2183be11f)
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/ec4a25c3-2501-49f3-a614-803f5d272df9)
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/5cc346b3-0649-4066-af3c-27472bd8928d)

Key learnings:
- The art of data cleaning and how it’s crucial for effective data analysis.
- The power of Pandas, a software library for Python, and its various functionalities.
- The use of loops in programming to automate repetitive tasks.
- The application of the substitution function to replace specific values in a dataset.
- The utility of the transpose function to rotate data frames, making rows into columns and vice versa.

## Step 2: Data Storage

Open pgAdmin (a GUI for PostgreSQL) or another database of your choice, and create a table that aligns with the column names of your cleaned data from Excel. Otherwise, the import process will not proceed.

```sql
CREATE TABLE income_statement (
    breakdown VARCHAR(100),
    total_revenue DECIMAL(30, 0),
	cost_of_revenue DECIMAL(30, 0),
	gross_profit DECIMAL(30, 0),
	operating_expense DECIMAL(30, 0),
	operating_income DECIMAL(30, 0),
	net_non_operating_interest_income_expense	 DECIMAL(30, 0),
	pretax_income DECIMAL(30, 0),
	tax_provision DECIMAL(30, 0),
	net_income_common_stockholders DECIMAL(30, 0),
	diluted_ni_available_to_com_stockholders DECIMAL(30, 0),
	basic_eps DECIMAL(30, 0),
	diluted_eps DECIMAL(30, 0),
	basic_average_shares DECIMAL(30, 0),
	diluted_average_shares DECIMAL(30, 0),
	rent_expense_supplemental DECIMAL(30, 0),
	total_expenses DECIMAL(30, 0),
	net_income_from_continuing_and_discontinued_operation DECIMAL(30, 0),
	normalized_income DECIMAL(30, 0),
	interest_income DECIMAL(30, 0),
	interest_expense DECIMAL(30, 0),
	net_interest_income DECIMAL(30, 0),
	ebit DECIMAL(30, 0),
	ebitda DECIMAL(30, 0),
	reconciled_cost_of_revenue DECIMAL(30, 0),
	reconciled_depreciation DECIMAL(30, 0),
	net_income_from_continuing_operation_net_minority_interest DECIMAL(30, 0),
	total_unusual_items_excluding_goodwill DECIMAL(30, 0),
	total_unusual_items DECIMAL(30, 0),
	normalized_ebitda DECIMAL(30, 0),
	tax_rate_for_calcs DECIMAL(30, 0),
	tax_effect_of_unusual_items DECIMAL(30, 0)
);
```

```sql
CREATE TABLE balance_sheet 
	breakdown VARCHAR(100),
    total_assets DECIMAL(30, 0),
    total_liabilities_net_minority_interest DECIMAL(30, 0),
	total_equity_gross_minority_interest DECIMAL(30, 0),
	total_capitalization DECIMAL(30, 0),
	preferred_stock_equity DECIMAL(30, 0),
	common_stock_equity DECIMAL(30, 0),
	capital_lease_obligations DECIMAL(30, 0),
	net_tangible_assets DECIMAL(30, 0),
	working_capital DECIMAL(30, 0),
	invested_capital DECIMAL(30, 0),
	tangible_book_value DECIMAL(30, 0),
	total_debt DECIMAL(30, 0),
	net_debt DECIMAL(30, 0),
	share_issued DECIMAL(30, 0),
	ordinary_shares_number DECIMAL(30, 0),
	preferred_shares_number DECIMAL(30, 0),
	treasury_shares_number DECIMAL(30, 0)
	
);
```

```sql
CREATE TABLE cash_flow (
	breakdown VARCHAR(100),
    operating_cash_flow DECIMAL(30, 0),
    investing_cash_flow DECIMAL(30, 0),
	financing_cash_flow DECIMAL(30, 0),
	end_cash_position DECIMAL(30, 0),
	capital_expenditure DECIMAL(30, 0),
	issuance_of_capital_stock DECIMAL(30, 0),
	issuance_of_debt DECIMAL(30, 0),
	repayment_of_debt DECIMAL(30, 0),
	repurchase_of_capital_stock DECIMAL(30, 0),
	free_cash_flow DECIMAL(30, 0)
	
);
```

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/c1bacb22-6e2f-4fbb-8bf9-f67ac960c4ee)

After creating the table, refresh the interface and navigate to your table name. 

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/e575dc64-336c-45d0-8e01-79dcdd7973eb)

Right-click on it and look for the import button.

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/5a40dbad-2df5-46a2-83e1-acae35974946)

Select the directory of the filename, and check the options and columns. You may need to enable the header option, depending on your data.

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/4dedb7c6-69b0-4e65-926f-f1e064d6e769)


Once the data is successfully imported, double-check to ensure its accuracy. After confirming that the data is correct, it’s ready for analysis. Remember, accurate data is crucial for reliable analytical results.

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/f592f26a-90b8-462d-b225-21bbd46a5f4d)

Key learnings:
- Create table
- Importing csv to database





