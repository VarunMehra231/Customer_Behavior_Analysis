📊 Customer Shopping Behavior Analysis
🔍 Overview

This project analyzes customer shopping behavior using transactional data to uncover patterns in spending, customer segments, and purchase drivers. The goal is to help businesses improve customer engagement, optimize marketing strategies, and increase revenue.

Business Problem:
“How can the company leverage consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?”

📁 Dataset

Total Records: 3,900 purchases

Features: 18 columns

Missing Values: 37 (Review Rating column)

Key Data Includes:

Customer demographics (Age, Gender, Location, Subscription Status)

Purchase details (Item, Category, Amount, Season)

Behavior data (Discount usage, Frequency, Reviews, Shipping type)

🛠️ Tools & Technologies

Python (Pandas, NumPy, Matplotlib, Seaborn)

SQL (PostgreSQL)

Power BI

Jupyter Notebook

Gamma (Presentation)

⚙️ Project Workflow
1. Data Preparation (Python)

Loaded dataset using Pandas

Handled missing values (median imputation for review ratings)

Standardized column names (snake_case)

Feature engineering:

Created age_group

Derived purchase frequency

Removed redundant columns (promo_code_used)

Loaded cleaned data into PostgreSQL

2. Data Analysis (SQL)

Key business queries performed:

Revenue by gender

High-spending discount users

Top-rated products

Shipping type comparison

Subscription vs non-subscription revenue

Customer segmentation (New, Returning, Loyal)

Top products per category

Revenue by age group

Example query:

SELECT item_purchased,
       ROUND(100.0 * SUM(CASE WHEN discount_applied = 'Yes' THEN 1 ELSE 0 END)/COUNT(*),2) AS discount_rate
FROM customer
GROUP BY item_purchased
ORDER BY discount_rate DESC
LIMIT 5;

📊 Key Insights (ACTUAL — not generic)

Revenue by Gender

Male: 157,890

Female: 75,191

Top Rated Products

Gloves (3.86), Sandals (3.84), Boots (3.82)

Shipping Behavior

Express: $60.48 avg

Standard: $58.46 avg
→ Express users spend more

Subscription Impact

Subscribers: 62,645 revenue

Non-subscribers: 170,436 revenue
→ Large revenue still comes from non-subscribers

Customer Segments

Loyal: 3116

Returning: 701

New: 83

Discount Dependency (Top Products)

Hat: 50%

Sneakers: 49.66%

Coat: 49.07%

📈 Dashboard (Power BI)

An interactive dashboard was created to visualize:

Revenue trends

Customer segmentation

Category-wise sales

Age group analysis

Subscription insights

(Refer to dashboard screenshot in repository)

💡 Business Recommendations

Increase Subscription Conversion

Most revenue comes from non-subscribers → opportunity gap

Target High-Spending Discount Users

These users spend above average even with discounts

Promote Express Shipping

Higher average purchase value

Focus on Loyal Customers

Majority of users fall in this segment

Optimize Discount Strategy

Some products heavily rely on discounts → margin risk

▶️ How to Run
# Clone repo
git clone https://github.com/your-username/customer-behavior-analysis.git

# Install dependencies
pip install -r requirements.txt

# Run notebook
jupyter notebook
SQL

Import cleaned data into PostgreSQL

Run queries from customer_behavior_sql_queries.sql

📂 Project Structure
customer-behavior-analysis/
│── data/
│── notebooks/
│── sql/
│── dashboard/
│── presentation/
│── README.md
🚀 Outcome

This project demonstrates:

End-to-end data analysis workflow

SQL-based business problem solving

Data visualization & storytelling

Real-world decision-making insights
