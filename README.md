#Online Retail EDA & Customer Behavior Analysis
#Project Overview

This project presents an end-to-end Exploratory Data Analysis (EDA) of the UCI Online Retail dataset, containing transactional data from a UK-based online retailer.

The project focuses on transforming raw transactional data into a clean analytical dataset and extracting meaningful insights into:

Data quality and cleaning
Outlier detection and treatment
Numerical distributions
Time-based purchasing behavior
Geographical purchasing behavior
Product performance
Customer purchasing behavior
Customer retention and recency
RFM analysis
Customer segmentation
Monthly revenue and growth
Product performance segmentation

#Dataset

Source: UCI Machine Learning Repository — Online Retail Dataset

The original dataset contains approximately 541,909 transactions and 8 columns:

| Column      | Description                  |
| ----------- | ---------------------------- |
| InvoiceNo   | Transaction/invoice number   |
| StockCode   | Product identifier           |
| Description | Product description          |
| Quantity    | Number of products purchased |
| InvoiceDate | Date and time of transaction |
| UnitPrice   | Price per product            |
| CustomerID  | Customer identifier          |
| Country     | Customer's country           |

The dataset contains transactions recorded primarily during 2010–2011, with the analysis focusing on the available transactional period and particularly the 2011 purchasing behavior.

#Data Preparation

The original dataset contained several data-quality issues, including:

Missing Customer IDs
Duplicate records
Cancelled transactions
Negative quantities
Invalid/zero prices
Extreme quantity and transaction values
Product-level anomalies

#Cleaning process

The analysis followed a structured cleaning pipeline:

Raw Dataset
Data Quality Inspection
Duplicate Detection
Cancellation / Invalid Transaction Removal
Quantity & Price Validation
Outlier Investigation
Missing CustomerID Analysis
Feature Engineering
Final Analytical Dataset

The final analytical dataset contained 522,725 rows × 11 columns and had:

0 duplicate rows
0 negative quantities
0 zero quantities
0 negative prices
0 zero prices
131,429 missing CustomerIDs

The missing CustomerID values were retained for transaction-level analysis because removing them would unnecessarily discard valid sales transactions. However, customer-level analyses such as RFM and customer segmentation were performed only on identifiable customers.

#Feature Engineering

Several analytical features were created during the project, including:

TotalAmount
Year
Month
DayOfWeek
Hour
YearMonth
RecencyDays
RFM metrics
RFM scores
Customer segments
Product performance categories

#Exploratory Data Analysis
1. Numerical Distribution Analysis

The distributions of:

Quantity
UnitPrice
TotalAmount

were examined using descriptive statistics, percentiles and histograms.

The variables were highly right-skewed, with most observations concentrated at relatively low values while a small number of transactions contained extremely large values.

For example:

Median Quantity: 4
Median Unit Price: £2.08
Median Transaction Value: £9.90

This demonstrated why relying only on mean values could be misleading.

#2. Outlier Analysis

Outliers were investigated using:

Boxplots
Percentiles
IQR-based analysis
Extreme-value inspection

Rather than automatically deleting every statistical outlier, extreme observations were manually investigated to determine whether they represented legitimate transactions or anomalies.

For example, the analysis identified an extremely large transaction involving:

Customer 12346 with a quantity of 74,215 units.

This transaction was examined separately rather than blindly treating every extreme observation as invalid.

#3. Temporal Analysis

Transaction behavior was analyzed by:

Month
Day of week
Hour
Day × Hour

The analysis showed that purchasing activity was concentrated during weekdays and normal daytime business hours.

Thursday recorded the highest transaction activity i.e. 99,807 transactions and the highest revenue: £2.13M

Hourly analysis showed that 12 PM had the highest transaction activity.

#4. Geographical Analysis

Country-level purchasing behavior was analyzed using:

Transaction volume
Revenue
Average transaction value

The United Kingdom dominated transaction volume and revenue.

However, several international markets demonstrated substantially higher average transaction values, including the Netherlands and Australia.

This highlighted an important distinction between transaction volume and transaction value.

#5. Product Analysis

Products were evaluated based on:

Revenue
Quantity sold
Number of orders
Revenue per order
Revenue per unit

Top-performing products included REGENCY CAKESTAND 3 TIER and WHITE HANGING HEART T-LIGHT HOLDER

The analysis also showed that products with high sales volume were not necessarily the products generating the highest revenue.

#6. Customer Analysis

Customer behavior was analyzed through:

Total revenue
Number of orders
Total quantity purchased
Average order value
Order frequency
Recency

A total of 4,334 identifiable customers were included in customer-level analysis.

The analysis found:

1,505 one-time customers
2,829 repeat customers

The highest-revenue customer generated approximately: £279K

#7. RFM Analysis

Customers were evaluated using:

Recency: How recently the customer made a purchase.
Frequency: How many unique orders the customer placed.
Monetary: How much revenue the customer generated.

Customers were scored using quantile-based RFM scoring, producing scores from 1–5 for each RFM dimension.

The individual scores were combined into an overall RFM score:

RFM Score = Recency Score + Frequency Score + Monetary Score

This produced an overall score ranging from 3 to 15.

#8. Customer Segmentation

RFM metrics and behavioral thresholds were used to create practical customer segments.

The final segments were:

| Segment                      | Customers | Revenue Contribution |
| ---------------------------- | --------: | -------------------: |
| Loyal Customers              |       956 |               67.20% |
| High-Value Customers         |       539 |               12.54% |
| Frequent Buyers              |       504 |               10.26% |
| Occasional Customers         |     1,199 |                5.69% |
| Idle / Inactive Customers    |       848 |                3.25% |
| Recent / Potential Customers |       288 |                1.05% |

#9. Product Performance Segmentation

Products were classified using median-based thresholds for:
Revenue
Quantity

This produced four categories:
| Category                   | Products |
| -------------------------- | -------: |
| High Revenue & High Volume |      721 |
| High Revenue & Low Volume  |      318 |
| Low Revenue & High Volume  |      319 |
| Low Revenue & Low Volume   |    2,797 |

This matrix provides a useful framework for identifying:

Core products
Premium products
High-volume low-value products
Underperforming products

#Key Findings
Customer concentration

The top 10 customers contributed approximately 16.6% of customer revenue, while the top 50 contributed approximately 31.9%.

Customer loyalty

Approximately 65% of identifiable customers were repeat customers, although a substantial one-time customer segment remained.

Customer segmentation

Loyal customers represented only about 22% of customers but generated approximately 67% of customer revenue.

Product performance

High-revenue/high-volume products represented the strongest product category and generated the majority of product revenue.

Purchasing behavior

Purchasing was heavily concentrated during weekdays and daytime hours.

Geographic concentration

The United Kingdom overwhelmingly dominated transaction volume and revenue, while some international markets showed much higher average transaction values.

Revenue trend

Revenue showed significant month-to-month fluctuations, with strong growth during September–November 2011 followed by a sharp decline in December.

#Tools & Technologies
Python
Pandas
NumPy
Matplotlib
Seaborn
Jupyter Notebook
Exploratory Data Analysis
Statistical Analysis
RFM Analysis
Customer Segmentation
