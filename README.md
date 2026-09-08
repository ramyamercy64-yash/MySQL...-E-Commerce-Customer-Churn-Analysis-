# 📊 E-Commerce Customer Churn Analysis – MySQL

## 📌 Project Overview

This project analyzes **customer churn in an e-commerce company** using MySQL.

The objective is to clean, transform, and analyze customer data to identify patterns related to **customer churn, customer behavior, payment preferences, order activity, satisfaction, and distance from the warehouse**.

The analysis helps understand why customers may churn and provides insights that can support customer retention strategies.

---

## 🎯 Objectives

* Clean and prepare the customer churn dataset.
* Handle missing values using mean and mode imputation.
* Identify and remove outliers.
* Standardize inconsistent categorical values.
* Transform columns for better analysis.
* Analyze churned and active customers.
* Identify customer behavior and purchasing patterns.
* Analyze payment modes, order categories, coupons, and cashback.
* Study the relationship between warehouse distance and churn.
* Generate useful business insights using SQL.

---

## 🛠️ Tools & Technologies

* **MySQL**
* **SQL**
* **GitHub**
* Customer Churn Dataset

---

## 🗂️ Dataset

The dataset contains customer-level information such as:

* Customer ID
* Tenure
* Preferred Login Device
* City Tier
* Warehouse-to-Home Distance
* Preferred Payment Mode
* Gender
* Hour Spend on App
* Number of Devices Registered
* Preferred Order Category
* Satisfaction Score
* Marital Status
* Number of Coupons Used
* Order Count
* Cashback Amount
* Complaint
* Churn

---

# 🧹 Data Cleaning

The following data-cleaning operations were performed.

### Missing Value Treatment

**Mean imputation:**

* `WarehouseToHome`
* `HourSpendOnApp`
* `OrderAmountHikeFromlastYear`
* `DaySinceLastOrder`

**Mode imputation:**

* `Tenure`
* `CouponUsed`
* `OrderCount`

### Outlier Treatment

Rows where:

```sql
WarehouseToHome > 100
```

were removed from the dataset.

### Data Standardization

The following inconsistent values were standardized:

| Column               | Original | Standardized     |
| -------------------- | -------- | ---------------- |
| PreferredLoginDevice | Phone    | Mobile Phone     |
| PreferredOrderCat    | Mobile   | Mobile Phone     |
| PreferredPaymentMode | COD      | Cash on Delivery |
| PreferredPaymentMode | CC       | Credit Card      |

---

# 🔄 Data Transformation

### Column Renaming

```text
PreferedOrderCat → PreferredOrderCat
HourSpendOnApp → HoursSpentOnApp
```

### New Columns

#### ComplaintReceived

* `Complain = 1` → **Yes**
* Otherwise → **No**

#### ChurnStatus

* `Churn = 1` → **Churned**
* Otherwise → **Active**

#### DistanceCategory

Customers were categorized based on their warehouse-to-home distance:

| Distance | Category            |
| -------- | ------------------- |
| ≤ 5 km   | Very Close Distance |
| ≤ 10 km  | Close Distance      |
| ≤ 15 km  | Moderate Distance   |
| > 15 km  | Far Distance        |

---

# 📈 Data Analysis

The following business questions were answered using SQL:

1. Count of churned and active customers.
2. Average tenure and total cashback amount of churned customers.
3. Percentage of churned customers who complained.
4. City tier with the highest number of churned Laptop & Accessory customers.
5. Most preferred payment mode among active customers.
6. Total order amount hike from last year for single customers preferring mobile phones.
7. Average number of devices registered by UPI users.
8. City tier with the highest number of customers.
9. Gender that utilized the highest number of coupons.
10. Customer count and maximum hours spent on the app by preferred order category.
11. Total order count for Credit Card users with the maximum satisfaction score.
12. Average satisfaction score of customers who complained.
13. Preferred order categories among customers who used more than 5 coupons.
14. Top 3 preferred order categories based on average cashback.
15. Preferred payment modes for customers with the required tenure and order count.
16. Churn status breakdown by warehouse-to-home distance category.
17. Order details of married customers living in City Tier 1 with above-average order counts.

---

# 🔍 Sample SQL Query

To display the cleaned customer data:

```sql
SELECT *
FROM customer_churn;
```

This query retrieves all records from the cleaned `customer_churn` table.

---

# 💡 Key Business Insights

The analysis can help the business:

* Identify the proportion of **churned vs active customers**.
* Understand customer preferences for **payment methods and order categories**.
* Identify customer groups with higher churn.
* Understand whether **warehouse distance** is associated with customer churn.
* Identify customers with high order activity.
* Understand the impact of complaints and satisfaction on churn.
* Identify categories generating higher cashback.
* Support customer retention and engagement strategies.

---

# 📁 Project Structure

```text
E-Commerce-Customer-Churn-Analysis/
│
├── E-Commerce Customer churn db.sql
│
├── README.md

```

---

# 🚀 Conclusion

This project demonstrates how **SQL and MySQL** can be used to clean, transform, explore, and analyze an e-commerce customer churn dataset.

The analysis provides meaningful insights into **customer churn, purchasing behavior, satisfaction, payment preferences, coupons, cashback, and customer activity**, which can help businesses develop better customer retention strategies.

---

## 👩‍💻 Author

**Y. RAMYAKRISHNA**

**Skills:**
SQL | MySQL | Excel | Power Query | Power BI | Data Analytics
