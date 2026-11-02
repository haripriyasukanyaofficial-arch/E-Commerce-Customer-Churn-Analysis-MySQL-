# E-Commerce Customer Churn Analysis (SQL)

**Business question:** Which customers stop buying from an online store (churn), and what do they have in common?

**Tool:** MySQL 

## At a glance

| Dataset | 5,630 customers, 20 columns (one row per customer) |
| Churned customers | 948 (about 17%) |
| Main table | `customer_churn` |
| Bonus table | `customer_returns` (8 returns, linked by `CustomerID`) |
| Output | Cleaned data + answers to 17 business questions + 1 bonus join |


**1. Built the database**
Created the `ecomm` database and tables, and loaded all the data with the script itself (no import needed).

**2. Cleaned the data**
- Found missing values (about 250-300 rows in each of 7 columns).
- Filled numeric gaps with the **mean** (distance, app hours, order hike, days since last order) or the **mode** (tenure, coupons used, order count).
- Removed 2 unrealistic outliers (warehouse distance over 100).
- Standardised labels, e.g. "Phone" became "Mobile Phone".

**3. Transformed the data**
- Fixed column names (`PreferedOrderCat` became `PreferredOrderCat`).
- Created readable columns: `ChurnStatus` (Churned / Active) and `ComplaintReceived` (Yes / No).
- Dropped the old 0/1 columns.

**4. Answered 17 business questions**
Examples: churn vs active counts, share of churned customers who complained, churn by city tier, favourite payment mode of active users, top 3 categories by cashback, and customers grouped by warehouse distance (Very Close to Far) with their churn status.

**5. Bonus: joined two tables**
Used a `JOIN` to list returns made by customers who both churned and complained.

**6. Final checks**
Confirmed no NULLs remain and checked the final record count.



