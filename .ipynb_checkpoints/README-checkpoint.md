# 📊 Customer Churn & Retention Analysis 

## 📝 Project Overview
This project focuses on analyzing customer churn for a subscription-based service. The goal was to extract data from a relational database, clean and format it, and engineer key business metrics to uncover *why* customers are leaving and *how much* revenue is at risk. 

This end-to-end data analysis project was built using Python (Pandas, NumPy, Matplotlib) and SQL (SQLite).

## 🗄️ Data Architecture
The data was ingested from a local SQLite database (`customer_churn.db`) consisting of three relational tables:
1. **`customer`**: Demographics, location, and personal details.
2. **`subscription`**: Plan types, monthly charges, contract types, and lifetime value (CLTV).
3. **`support`**: Customer service interactions, escalation flags, and CSAT scores.

## 🛠️ Key Technical Skills Demonstrated
* **SQL Database Connection:** Connected to a SQLite database and queried multiple tables directly into pandas DataFrames.
* **Data Cleaning & Standardization:** Handled missing values, converted date strings to `datetime` objects, and standardized categorical variables.
* **Feature Engineering:** * Created a binary `churn_flag` based on cancellation dates.
  * Calculated `tenure_days` (customer lifetime) and `age_cust` (customer age in days).
  * Calculated `monthly_revenue_lost` to quantify the financial impact of churn.
  * Categorized customers into 'low', 'med', and 'high' `churn_risk` buckets.
* **Relational Data Merging:** Used Left JOINs to combine the three tables into one unified master dataset while dropping duplicate support tickets.
* **Statistical Analysis:** Used NumPy's `np.where()` and pandas `.corr()` to prove a high correlation (0.77) between customer service escalations and churn.

## 📈 Key Business Insights Uncovered
* **Overall Churn Rate:** 28.57% (Retention Rate: 71.43%).
* **Churn by Plan Type:** Customers on the 'Basic' plan churned at a significantly higher rate (60.0%) compared to Premium (14.29%) and Standard (22.22%) tiers.
* **Financial Impact (ARPU & Revenue at Risk):** The Average Revenue Per User (ARPU) is $18.85. The total monthly revenue currently at risk due to churned users is $73.94.
* **Customer Service Impact:** The escalation rate is 19.05%. There is a **strong positive correlation (0.77)** between support escalations and customer churn, indicating that resolving service issues quickly is critical to retention.

## 🚀 How to Run the Project
1. Clone the repository to your local machine.
2. Ensure you have the required libraries installed: `pip install pandas numpy matplotlib seaborn sqlite3`.
3. Ensure the `customer_churn.db` file is in the same directory as the notebook.
4. Open `CUSTOMERCHRUN.ipynb` in Jupyter Notebook or VS Code and run all cells.
5. 