# Financial-Statement-Analysis

## Step 1: Data Collection

For this project, I’ve chosen to analyze the financial statements of San Miguel Corporation, a publicly traded company with the stock ticker SMGBF. The financial data can be accessed from this [website](https://finance.yahoo.com/quote/SMGBF/financials?p=SMGBF)

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/3794105f-3d5f-4129-83cf-96860292218d)

I began by manually copying the income statement and pasting it into an Excel spreadsheet. However, I encountered a formatting issue where the data did not distribute across individual cells as expected, but instead clustered into a single cell. This is what we refer to as ‘dirty data’, which is not ideal for analysis.

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/28bbaa54-6364-4faf-a6e4-5fabfd950664)
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/2ee89d64-7890-476c-8c8f-429c5f5c8a92)
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/f0da75a5-3e1e-49f9-bf27-c589291907d5)


To clean this data, there are two methods that I’m aware of: manual cleaning using Excel or utilizing Python’s pandas library. For this project, I’ve opted to use pandas in Python. The cleanup code can be found in the repository.

### Before:
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/19ca9fa2-8187-4bbc-8c21-b3e22c5e1891)

Comparing the ‘before’ and ‘after’ states of the data reveals a significant difference. With the data now clean and ready for analysis, it can be stored in a database.

### After:
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/9638c7c4-78d3-4d5d-8803-9ca34e24840d)


## Step 2: Data Storage

Open pgAdmin (a GUI for PostgreSQL) or another database of your choice, and create a table that aligns with the column names of your cleaned data from Excel. Otherwise, the import process will not proceed.

```sql
CREATE TABLE Income_Statement (
    Breakdown VARCHAR(100),
    TTM DECIMAL(15, 2),
    End_of_2022 DECIMAL(15, 2),
    End_of_2021 DECIMAL(15, 2),
    End_of_2020 DECIMAL(15, 2),
    End_of_2019 DECIMAL(15, 2)
);
```

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/c1bacb22-6e2f-4fbb-8bf9-f67ac960c4ee)

After creating the table, refresh the interface and navigate to your table name. 

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/e575dc64-336c-45d0-8e01-79dcdd7973eb)

Right-click on it and look for the import button.

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/5a40dbad-2df5-46a2-83e1-acae35974946)

Select the directory of the filename, and check the options and columns. You may need to enable the header option, depending on your data.

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/f66967ab-da64-451d-8a3f-12488818b288)

Once the data is successfully imported, double-check to ensure its accuracy. After confirming that the data is correct, it’s ready for analysis. Remember, accurate data is crucial for reliable analytical results.

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/036087d8-5265-4e93-becb-b63c0d2c4ade)




