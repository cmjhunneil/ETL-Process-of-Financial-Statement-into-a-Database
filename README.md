# Financial-Statement-Analysis

## Step 1: Data Collection

For this project, I’ve chosen to analyze the financial statements of San Miguel Corporation, a publicly traded company with the stock ticker SMGBF. The financial data can be accessed from this website("https://finance.yahoo.com/quote/SMGBF/financials?p=SMGBF").

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/3794105f-3d5f-4129-83cf-96860292218d)

I began by manually copying the income statement and pasting it into an Excel spreadsheet. However, I encountered a formatting issue where the data did not distribute across individual cells as expected, but instead clustered into a single cell. This is what we refer to as ‘dirty data’, which is not ideal for analysis.

![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/cb0e8894-94bf-4c82-afa1-7e618422dfb8)


To clean this data, there are two methods that I’m aware of: manual cleaning using Excel or utilizing Python’s pandas library. For this project, I’ve opted to use pandas in Python. The cleanup code can be found in the repository.

### Before:
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/19ca9fa2-8187-4bbc-8c21-b3e22c5e1891)

Comparing the ‘before’ and ‘after’ states of the data reveals a significant difference. With the data now clean and ready for analysis, it can be stored in a database.

### After:
![image](https://github.com/cmjhunneil/Financial-Statement-Analysis/assets/63811723/0e3f3333-7ef2-49c7-bfb5-ab8220075fdf)

