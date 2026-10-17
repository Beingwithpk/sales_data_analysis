# 🛍️ Customer Shopping Behavior Analysis

An end-to-end data analysis project that uses transactional data from **3,900 purchases** to uncover spending patterns, customer segments, product preferences, and subscription behavior, in order to guide strategic business decisions.

**Workflow:** Python (cleaning + EDA) → PostgreSQL (business queries) → Power BI (dashboard)

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Dataset Summary](#-dataset-summary)
- [Tech Stack](#-tech-stack)
- [Exploratory Data Analysis (Python)](#-exploratory-data-analysis-python)
- [Data Analysis (SQL)](#-data-analysis-sql)
- [Dashboard (Power BI)](#-dashboard-power-bi)
- [Business Recommendations](#-business-recommendations)
- [How to Run](#-how-to-run)
- [Author](#-author)

---

## 🎯 Project Overview

This project analyzes how customers shop across different product categories. The goal is to answer questions such as:

- Who spends more, and on what?
- Do discounts and subscriptions actually change buying behavior?
- Which products and customer segments drive the most revenue?

The findings are turned into actionable recommendations for marketing, pricing, and customer retention.

---

## 📊 Dataset Summary

| Property | Value |
|----------|-------|
| Rows | 3,900 |
| Columns | 18 |
| Missing data | 37 values in the `Review Rating` column |

**Key features**

- **Customer demographics:** Age, Gender, Location, Subscription Status
- **Purchase details:** Item Purchased, Category, Purchase Amount, Season, Size, Color
- **Shopping behavior:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type

---

## 🧰 Tech Stack

- **Python:** pandas for data loading, cleaning, and feature engineering
- **PostgreSQL:** structured business analysis with SQL
- **Power BI:** interactive dashboard

---

## 🐍 Exploratory Data Analysis (Python)

Data preparation and cleaning were done in Python:

1. **Data loading:** imported the dataset with pandas.
2. **Initial exploration:** used `df.info()` to check structure and `df.describe()` for summary statistics.
3. **Missing data handling:** checked for null values and imputed the missing `Review Rating` values using the **median rating of each product category**.
4. **Column standardization:** renamed columns to `snake_case` for readability and easier documentation.
5. **Feature engineering:**
   - Created an `age_group` column by binning customer ages.
   - Created a `purchase_frequency_days` column from the purchase frequency data.
6. **Data consistency check:** verified whether `discount_applied` and `promo_code_used` were redundant, then dropped `promo_code_used`.
7. **Database integration:** connected the Python script to PostgreSQL and loaded the cleaned DataFrame into the database for SQL analysis.

---

## 🗄️ Data Analysis (SQL)

Structured analysis in PostgreSQL answered ten key business questions:

| # | Analysis | What it answers |
|---|----------|-----------------|
| 1 | **Revenue by Gender** | Total revenue from male vs. female customers |
| 2 | **High-Spending Discount Users** | Customers who used discounts but still spent above the average purchase amount |
| 3 | **Top 5 Products by Rating** | Products with the highest average review ratings |
| 4 | **Shipping Type Comparison** | Average purchase amount for Standard vs. Express shipping |
| 5 | **Subscribers vs. Non-Subscribers** | Average spend and total revenue by subscription status |
| 6 | **Discount-Dependent Products** | The 5 products with the highest percentage of discounted purchases |
| 7 | **Customer Segmentation** | Customers classified as New, Returning, or Loyal based on purchase history |
| 8 | **Top 3 Products per Category** | The most purchased products within each category |
| 9 | **Repeat Buyers & Subscriptions** | Whether customers with more than 5 purchases are more likely to subscribe |
| 10 | **Revenue by Age Group** | Total revenue contribution of each age group |

---

## 📈 Dashboard (Power BI)

An interactive Power BI dashboard presents the insights visually, so stakeholders can explore revenue, customer segments, and product performance without writing any queries.

> 📸 *Add a dashboard screenshot here:* `![Dashboard](images/dashboard.png)`

---

## 💡 Business Recommendations

- **Boost subscriptions:** promote exclusive benefits for subscribers.
- **Customer loyalty programs:** reward repeat buyers to move them into the "Loyal" segment.
- **Review discount policy:** balance sales boosts with margin control.
- **Product positioning:** highlight top-rated and best-selling products in campaigns.
- **Targeted marketing:** focus efforts on high-revenue age groups and express-shipping users.

---

## ▶️ How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/<your-repo-name>.git
   cd <your-repo-name>
   ```

2. **Install dependencies**
   ```bash
   pip install pandas numpy sqlalchemy psycopg2-binary jupyter
   ```

3. **Set up PostgreSQL**
   - Create a database for the project.
   - Update the connection details (username, password, host, database name) in the Python script or notebook.

4. **Run the Python analysis**
   - Open the notebook or script, run the cleaning and feature engineering steps, and load the cleaned DataFrame into PostgreSQL.

5. **Run the SQL queries**
   - Execute the ten business queries against the loaded table in PostgreSQL.

6. **Open the dashboard**
   - Open the `.pbix` file in Power BI Desktop.

---

## 👤 Author

**Pranjal**, B.Tech Computer Science, IIIT Bhopal
GitHub: [Beingwithpk](https://github.com/Beingwithpk)
