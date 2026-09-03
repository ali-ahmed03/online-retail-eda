### **Dataset Overview**



This project uses the UCI Online Retail Dataset, a transactional dataset containing retail sales records from a UK-based online retailer. The dataset covers transactions from December 2010 to December 2011 and includes information about invoices, products, quantities, prices, customers, dates, and countries.



### **Source**

Dataset: UCI Online Retail Dataset

Source: UCI Machine Learning Repository 

License: Creative Commons Attribution 4.0 International (CC BY 4.0)

Dataset page: https://archive.ics.uci.edu/dataset/352/online+retail



### **Original Dataset**



The original dataset contains 541,909 transaction records and 8 columns:



* InvoiceNo
* StockCode
* Description
* Quantity
* InvoiceDate
* UnitPrice
* CustomerID
* Country
* Data Preparation



The dataset was cleaned and prepared for exploratory data analysis (EDA). Key steps included:



* Removing duplicate records.
* Removing cancelled/invalid transactions.
* Removing records with negative or zero quantities.
* Removing records with negative or zero unit prices.
* Handling and documenting missing CustomerID values.
* Investigating extreme values and outliers in numerical variables.
* Creating a TotalAmount feature:TotalAmount = Quantity × UnitPrice
* Creating additional time-based features such as year, month, day of week, and hour.
* Preparing customer-level data for RFM analysis and customer segmentation.
* Preparing product-level metrics for revenue, quantity, order frequency, and performance analysis.



### **Final Dataset**



After cleaning and transformation, the dataset contains:



522,725 rows × 11 columns



The final dataset contains no duplicate rows and no negative or zero quantities/prices.



The additional analytical columns include:



* Quantity\_Outlier
* UnitPrice\_Outlier
* TotalAmount
* Project Purpose



The prepared dataset was used for an end-to-end Exploratory Data Analysis (EDA) project covering:



* Data quality assessment and cleaning
* Numerical distributions and outlier analysis
* Time-based purchasing behavior
* Day-of-week and hourly purchasing patterns
* Country-level purchasing behavior
* Product performance analysis
* Customer revenue and purchasing behavior
* Customer retention and order frequency
* RFM analysis
* Customer segmentation
* Monthly revenue and growth analysis
* Business insights and recommendations
* Attribution



### **License:**

The dataset is provided by the UCI Machine Learning Repository and is licensed under the Creative Commons Attribution 4.0 International (CC BY 4.0) license. Please refer to the original UCI dataset page for the complete dataset description and licensing information.

