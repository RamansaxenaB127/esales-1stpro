# 🛒 E-Commerce Sales Analytics Dashboard

### An end-to-end data analytics project using MySQL, Power BI, and Python

---

## 📌 Project Overview

This project analyzes **5,000 e-commerce sales transactions** to uncover business insights around regional performance, product category trends, payment behavior, and revenue patterns.

The goal was to simulate a real-world business analyst workflow — from raw data to a fully interactive dashboard — helping stakeholders make data-driven decisions.

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| MySQL | Data cleaning & SQL analysis |
| Power BI | Interactive dashboard & visualization |
| Python (Pandas) | Data preprocessing & feature engineering |
| Excel | Initial data exploration |

---

## 📂 Project Structure

```
ecommerce-sales-analytics/
│
├── data/
│   └── ecommerce_sales_analytics_5000.csv   ← raw dataset
│
├── sql/
│   └── queries.sql                           ← all analysis queries
│
├── python/
│   └── data_cleaning.py                      ← cleaning & preprocessing
│
├── dashboard/
│   └── sales_dashboard.pbix                  ← Power BI file
│
├── screenshots/
│   └── dashboard_preview.png                 ← dashboard screenshot
│
└── README.md
```

---

## 📊 Dataset Overview

| Field | Details |
|-------|---------|
| Source | Custom E-Commerce Dataset |
| Records | 5,000 orders |
| Time Period | 2022 – 2035 |
| Columns | order_id, order_date, customer_id, product_category, region, quantity, unit_price, discount, payment_method, delivery_days, customer_rating, revenue |

---

## 🔍 Key Business Questions Answered

- Which region generates the highest revenue?
- Which product category drives the most sales?
- What is the monthly and yearly revenue trend?
- Which payment method is most preferred by customers?

---

## 💡 Key Insights

- 📍 **West region** leads with **₹13.45L in revenue**, outperforming all other regions
- 🛍️ **Electronics** is the top performing category with **₹18.29L in revenue** — 35% of total sales
- 💳 Revenue is fairly distributed across **Card, COD and Wallet** payment methods
- 👗 **Clothing** is the second highest category at **₹15.31L** showing strong consumer demand
- 💄 **Beauty** is the lowest revenue category at **₹7.65L** — a potential growth opportunity
- ⭐ Customer ratings and delivery days can be analyzed to improve customer satisfaction scores
- 🌍 All four regions (East, West, North, South) show relatively balanced revenue — West leads by ~8%

---

## 📈 Dashboard Preview

![Sales Dashboard](screenshots/dashboard_preview.png)

> The dashboard includes KPI cards, revenue by region (pie chart), category performance (bar chart), payment method analysis (sankey chart), and yearly revenue trend (line chart).

---

## 🗄️ SQL Analysis

Key queries written for this project:

```sql
--select * FROM Sales limit 100; 

-- for top region which has highest sales
Select region , round(sum(revenue),1) as Total_revenue
from Sales
group by region
order by Total_revenue desc ;



-- for top product sales
Select product_category , round(sum(revenue),1) as topproduct 
from Sales
group by product_category
order by topproduct desc 
limit 5;

-- for monthly sales trend
select date_format(order_date,'%y-%m') as month, round(sum(revenue),2) as monthly_sales
from Sales
group by month 
order by month asc;

-- loss order 
select product_category , count(*) as lossorder , round(sum(revenue),1) as total_loss
from  Sales
where revenue <109
group by product_category
order by lossorder desc;```


---

## 🐍 Python Cleaning Steps

- Removed null values and duplicate records
- Converted `order_date` to proper datetime format
- Created new columns: `Profit Margin %`, `Order Year`, `Order Month`
- Exported cleaned CSV for Power BI consumption

---

## 🚀 How to Run This Project

1. Clone this repository
```bash
git clone https://github.com/ramansaxena/ecommerce-sales-analytics.git
```

2. Load the CSV into MySQL
```sql
CREATE DATABASE sales_project;
USE sales_project;
```

3. Run queries from `/sql/queries.sql` in MySQL Workbench

4. Open `/dashboard/sales_dashboard.pbix` in Power BI Desktop

---

## 🎓 Learning Outcomes

- Writing business-focused SQL queries using GROUP BY, DATE_FORMAT
- Building interactive multi-visual dashboards in Power BI
- Performing data cleaning and feature engineering using Python
- Translating raw data into clear business insights

---

## 👤 Author

**Raman Saxena**
📧 ramanshri2003@gmail.com
🔗 [LinkedIn](hhttps://www.linkedin.com/public-profile/settings/?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_self_edit_contact_info%3BBAA5NlhsQfGGtkpLDg8mYw%3D%3D)
💻 [GitHub](https://github.com/ramansaxena)

---

⭐ *If you found this project useful, feel free to star the repository!*