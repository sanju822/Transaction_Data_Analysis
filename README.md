# Transaction_Data_Analysis
Detailed Analysis based on the transaction details from 1500 customers

A. Dataset Understanding
========================

Likely Business Domain
----------------------

This appears to be a **Banking / Financial Services / Digital Payments** transactional dataset containing customer financial transactions.

Likely Dataset Type
-------------------

A **transaction-level fact table**, where each record represents an individual financial transaction performed by a customer.

Available Dimensions
--------------------

*   Customer
    
    *   customer\_id
        
    *   account\_type
        
*   Transaction
    
    *   transaction\_id
        
    *   transaction\_type
        
    *   transaction\_status
        
    *   transaction\_amount
        
    *   currency
        
*   Merchant
    
    *   merchant\_name
        
    *   merchant\_category
        
*   Payment
    
    *   payment\_method
        
    *   transaction\_channel
        
*   Geography
    
    *   location\_city
        
*   Time
    
    *   transaction\_date
        
*   Account Balance
    
    *   balance\_before
        
    *   balance\_after
        

Assumptions
-----------

*   Each row represents one unique transaction.
    
*   transaction\_amount contains the monetary value of each transaction.
    
*   transaction\_status identifies whether a transaction succeeded, failed, or was otherwise processed.
    
*   balance\_before and balance\_after represent the account balance immediately before and after each transaction.
    
*   Multiple currencies may exist in the dataset; comparisons across currencies may require filtering or normalization since no exchange rates are provided.
    
*   Recommendations below are limited to analyses supported by the listed columns only.
    

B. Five Business Problems
=========================

1\. Understand Overall Transaction Volume Across Transaction Types
------------------------------------------------------------------

### Business Problem

Determine which transaction types generate the highest transaction activity.

### Required Columns

*   transaction\_type
    
*   transaction\_amount
    
*   transaction\_id
    

### Recommended Visualization

**Clustered Bar Chart**

### What the Visualization Helps Conclude

*   Compare transaction activity across transaction types.
    
*   Identify transaction types contributing most to transaction count or value.
    
*   Support prioritization of products or services with higher customer usage.
    

2\. Evaluate Transaction Success vs Failure Performance
-------------------------------------------------------

### Business Problem

Analyze operational performance by reviewing transaction outcomes.

### Required Columns

*   transaction\_status
    
*   transaction\_id
    

### Recommended Visualization

**Donut Chart**

### What the Visualization Helps Conclude

*   Understand the distribution of transaction statuses.
    
*   Highlight operational areas that may require investigation if certain statuses occur frequently.
    
*   Support service quality monitoring.
    

3\. Analyze Customer Payment Method Preferences
-----------------------------------------------

### Business Problem

Understand which payment methods customers prefer.

### Required Columns

*   payment\_method
    
*   transaction\_amount
    
*   transaction\_id
    

### Recommended Visualization

**Horizontal Bar Chart**

### What the Visualization Helps Conclude

*   Compare usage across payment methods.
    
*   Inform investment in payment technologies.
    
*   Support decisions on customer experience improvements.
    

4\. Identify High-Activity Merchant Categories
----------------------------------------------

### Business Problem

Determine which merchant categories receive the most customer spending.

### Required Columns

*   merchant\_category
    
*   transaction\_amount
    
*   transaction\_id
    

### Recommended Visualization

**Treemap**

### What the Visualization Helps Conclude

*   Identify major spending categories.
    
*   Support partnership strategies with merchants.
    
*   Guide promotional campaigns by merchant category.
    

5\. Compare Transaction Activity Across Cities
----------------------------------------------

### Business Problem

Understand geographical distribution of customer transactions.

### Required Columns

*   location\_city
    
*   transaction\_amount
    
*   transaction\_id
    

### Recommended Visualization

**Column Chart**

### What the Visualization Helps Conclude

*   Compare transaction activity across cities.
    
*   Support regional marketing strategies.
    
*   Assist operational planning by location.
    

C. Five KPIs
============

1\. Total Transaction Amount
----------------------------

### Calculation Logic

**SUM(transaction\_amount)**

### Required Columns

*   transaction\_amount
    

### Recommended KPI Card or Visualization

**KPI Card**

### Business Meaning

Measures the overall monetary value of transactions processed during the selected period.

2\. Total Number of Transactions
--------------------------------

### Calculation Logic

**COUNT(transaction\_id)**

### Required Columns

*   transaction\_id
    

### Recommended KPI Card or Visualization

**KPI Card**

### Business Meaning

Indicates the overall transaction volume handled by the business.

3\. Average Transaction Amount
------------------------------

### Calculation Logic

**AVERAGE(transaction\_amount)**

### Required Columns

*   transaction\_amount
    

### Recommended KPI Card or Visualization

**KPI Card**

### Business Meaning

Shows the typical monetary value of a transaction and helps understand customer spending behavior.

4\. Successful Transaction Rate
-------------------------------

### Calculation Logic

**(Count of successful transactions ÷ Total transactions)**

_(The exact "successful" status depends on the values present in transaction\_status.)_

### Required Columns

*   transaction\_status
    
*   transaction\_id
    

### Recommended KPI Card or Visualization

**Gauge Chart**

### Business Meaning

Measures operational effectiveness of transaction processing.

5\. Active Customers
--------------------

### Calculation Logic

**COUNT DISTINCT(customer\_id)**

### Required Columns

*   customer\_id
    

### Recommended KPI Card or Visualization

**KPI Card**

### Business Meaning

Shows how many unique customers performed transactions during the selected period.

D. Five Management Questions
============================

1\. Which transaction types generate the highest transaction value?
-------------------------------------------------------------------

### Required Columns

*   transaction\_type
    
*   transaction\_amount
    

### Recommended Visualization

**Bar Chart**

### What Decision It Can Support

*   Product prioritization.
    
*   Resource allocation.
    
*   Service optimization.
    

2\. Which merchant categories account for the largest share of customer spending?
---------------------------------------------------------------------------------

### Required Columns

*   merchant\_category
    
*   transaction\_amount
    

### Recommended Visualization

**Treemap**

### What Decision It Can Support

*   Merchant partnership strategy.
    
*   Marketing campaign planning.
    
*   Customer rewards design.
    

3\. Which payment methods are used most frequently?
---------------------------------------------------

### Required Columns

*   payment\_method
    
*   transaction\_id
    

### Recommended Visualization

**Bar Chart**

### What Decision It Can Support

*   Investment in payment infrastructure.
    
*   Customer experience improvements.
    
*   Payment feature prioritization.
    

4\. How does transaction activity vary over time?
-------------------------------------------------

### Required Columns

*   transaction\_date
    
*   transaction\_amount
    
*   transaction\_id
    

### Recommended Visualization

**Line Chart**

### What Decision It Can Support

*   Operational capacity planning.
    
*   Identification of recurring transaction patterns.
    
*   Scheduling of promotions or maintenance windows.
    

5\. Which cities have the highest transaction activity?
-------------------------------------------------------

### Required Columns

*   location\_city
    
*   transaction\_amount
    
*   transaction\_id
    

### Recommended Visualization

**Column Chart**

### What Decision It Can Support

*   Regional business expansion.
    
*   Branch or service investment.
    
*   Targeted local marketing initiatives.
    

E. Final Recommended Dashboard Layout
=====================================

Top Section – Executive Summary
-------------------------------

Display key KPI cards:

*   Total Transaction Amount
    
*   Total Number of Transactions
    
*   Average Transaction Amount
    
*   Successful Transaction Rate
    
*   Active Customers
    

Left Panel – Transaction Overview
---------------------------------

*   Line Chart: Transaction activity over time (transaction\_date)
    
*   Bar Chart: Transaction value by transaction\_type
    

Center Panel – Customer & Payment Insights
------------------------------------------

*   Horizontal Bar Chart: Transactions by payment\_method
    
*   Donut Chart: Distribution by transaction\_status
    

Right Panel – Merchant & Geographic Insights
--------------------------------------------

*   Treemap: Transaction amount by merchant\_category
    
*   Column Chart: Transaction activity by location\_city
