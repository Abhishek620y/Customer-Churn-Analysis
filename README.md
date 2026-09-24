# Customer Churn Analysis

A data analytics project focused on understanding **customer churn, retention, revenue at risk, customer behavior, and churn risk** using Python, Pandas, SQL, Matplotlib, and Seaborn.

The analysis is implemented in the Jupyter Notebook [`churn_analysis.ipynb`](./churn_analysis.ipynb).

## Project Overview

Customer churn is an important business metric because losing customers can directly affect revenue and long-term growth. This project analyzes customer, subscription, and support data to identify churn patterns and calculate key business KPIs.

The workflow includes:

- Loading data from a SQLite database
- Inspecting database tables and columns
- Cleaning and standardizing customer data
- Handling missing values and unnecessary columns
- Combining customer, subscription, and support data
- Creating a churn flag
- Performing customer churn and revenue analysis
- Creating a churn-risk category
- Building visualizations using Matplotlib and Seaborn
- Creating correlation analysis and pivot tables
- Exporting the cleaned analysis dataset to CSV

## Tech Stack

- **Python**
- **Jupyter Notebook**
- **Pandas** – data manipulation and analysis
- **NumPy** – numerical operations
- **Matplotlib** – data visualization
- **Seaborn** – statistical visualization
- **SQLite** – database and SQL queries

## Project Workflow

```text
SQLite Database
      ↓
Data Extraction using SQL
      ↓
Data Inspection
      ↓
Data Cleaning & Standardization
      ↓
Feature Engineering
      ↓
Customer / Subscription / Support Data Merge
      ↓
Churn & Revenue Analysis
      ↓
Churn Risk Classification
      ↓
Visualization & Correlation Analysis
      ↓
Business Insights
```

## Data Preparation

The notebook performs several data-cleaning steps, including:

- Renaming columns where required
- Removing unnecessary columns such as `interests` and `pincode`
- Converting the `DOB` field to a date type
- Standardizing gender values
- Handling missing values
- Creating a `churn flag` from cancellation information
- Counting customer complaints
- Keeping the latest support record for each customer
- Merging customer, subscription, and support tables

After cleaning and merging the data, the final analysis dataframe contains **21 customers and 21 columns**.

## Key KPIs Analyzed

The project calculates the following business metrics:

| KPI | Result |
|---|---:|
| Churn Rate | 28.57% |
| Retention Rate | 71.43% |
| Average Revenue per User (ARPU) | 18.85 |
| Average Customer Tenure | 1546 days |
| Revenue at Risk from Churned Users | 73.94 |
| Escalation Rate | 19.05% |
| Average Complaints per User | 0.43 |
| Escalation vs Churn Correlation | 0.77 |

> The values above are the results produced by the uploaded notebook and depend on the dataset used with the project.

## Churn Analysis

### Churn by Plan Type

The notebook calculates churn rates for each plan:

| Plan Type | Churn Rate |
|---|---:|
| Basic | 60.00% |
| Standard | 22.22% |
| Premium | 14.29% |

### Churn by Subscription Type

| Subscription Type | Churn Rate |
|---|---:|
| Organic | 0.00% |
| Paid | 16.67% |
| Refferal | 83.33% |

### Churn by State

The analysis also compares churn rates across states, including Delhi, Karnataka, Kathmandu, Maharashtra, Meghalaya, Nagaland, Rajasthan, Telangana, and Uttar Pradesh.

For the dataset analyzed in the notebook, Karnataka has a 100% churn rate, Meghalaya 66.67%, Telangana 50%, and Delhi 25%. Several other locations have 0% churn in this dataset.

Because the dataset is small, these percentages should be interpreted as descriptive results for this dataset rather than general population-level conclusions.

## Revenue at Risk

The notebook calculates revenue associated with churned customers.

- **Revenue loss due to churned users: 73.94**
- Revenue loss is also analyzed by state and subscription type.
- Subscription-type analysis shows revenue loss of **12.99** for Paid users and **60.95** for Refferal users in the analyzed data.

## Customer Support & Churn

The project investigates whether customer escalations are associated with churn.

The notebook calculates an **escalation-to-churn correlation of 0.77** for the analyzed dataset.

This is a correlation measure, not proof that escalations cause churn.

## Churn Risk Classification

A `churn_risk` feature is created from `churn_score`:

- **Low:** churn score below 50
- **Med:** churn score from 50 to below 70
- **High:** churn score 70 or above

This classification is then used for further visualization and comparison.

## Data Visualizations

The notebook includes visual analysis such as:

- Monthly churn trend
- Churn by plan type
- Churn by state
- Churn by gender
- Churn by subscription type
- Correlation heatmap
- Pairplot
- Multi-dimensional categorical analysis using Seaborn
- Pivot tables for plan-level analysis

## Sample Business Insights

Based on the analyzed dataset:

1. The overall churn rate is **28.57%**, while the retention rate is **71.43%**.
2. The **Basic plan** has the highest churn rate among the three plan types in this dataset.
3. The **Refferal** subscription category has a substantially higher churn rate than Organic and Paid categories in the analyzed data.
4. Churn and revenue impact are examined at state and subscription-type levels.
5. The notebook finds a **0.77 correlation** between escalations and churn, providing a useful area for further investigation.
6. Churn-risk categories allow customers to be grouped into Low, Medium, and High risk based on the existing churn score.

## Project Structure

```text
Customer-Churn-Analysis/
│
├── churn_analysis.ipynb
├── customer_churn.db
├── exported_churn_data.csv
└── README.md
```

> If you do not want to upload the SQLite database or generated CSV to GitHub, remove them from the project structure above and add them to `.gitignore`.

## How to Run the Project

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd Customer-Churn-Analysis
```

### 2. Install dependencies

```bash
pip install numpy pandas matplotlib seaborn jupyter
```

### 3. Start Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open the notebook

Open:

```text
churn_analysis.ipynb
```

Make sure the SQLite database file used by the notebook is available in the expected project location.

### 5. Run the notebook

Run the cells from top to bottom to reproduce the data cleaning, analysis, visualizations, and KPI calculations.

## Output

The notebook also exports the processed dataset as:

```text
exported_churn_data.csv
```

## Future Improvements

Possible improvements for the project include:

- Build an interactive Power BI or Tableau dashboard
- Add more historical customer data
- Perform statistical significance testing
- Develop a machine-learning churn prediction model
- Improve the churn-risk scoring methodology
- Add automated data pipelines
- Create customer-level retention recommendations
- Deploy the analysis as an interactive web application

## Author

**Abhishek Kumar Yadav**

This project was created as a data analytics project to practice SQL, Python, data cleaning, exploratory data analysis, KPI analysis, and data visualization.
