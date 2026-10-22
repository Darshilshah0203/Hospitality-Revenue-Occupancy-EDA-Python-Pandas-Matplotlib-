# Hospitality-Revenue-Occupancy-EDA-Python-Pandas-Matplotlib-
End-to-end EDA on 134K+ hotel bookings across 25 properties in 4 cities. Cleaned and merged 5 datasets in Python/Pandas, then answered 10 business questions on occupancy, revenue, ratings and booking channels, finding a 21-point weekend vs weekday occupancy gap.

## 📌 Overview

**AtliQ Grands** is a hospitality chain with 25 properties across Delhi, Mumbai, Bangalore, and Hyderabad, spanning Luxury and Business categories.

With revenue remaining flat, management lacked visibility into where occupancy and revenue were being won or lost.

This project cleans, transforms, and combines five relational datasets to answer **10 ad-hoc business questions** covering occupancy, revenue, ratings, and booking channels using Python and Pandas.

## 🎯 Business Questions Answered

1. What is the average occupancy rate in each room category?
2. What is the average occupancy rate per city?
3. When is occupancy better: weekday or weekend?
4. What is the occupancy rate for different cities in June?
5. How do we append newly received August data to the existing dataset?
6. What is the revenue realized per city?
7. What is the month-by-month revenue?
8. What is the revenue realized per property?
9. What is the average rating per city?
10. Which booking platforms contribute the most revenue?

## 🔑 Key Insights

| Business Metric | Key Finding |
|---|---|
| **Weekend vs. weekday occupancy** | Weekends average **72.34%**, compared with **50.88%** on weekdays, a gap of approximately 21.46 percentage points. |
| **Top revenue-generating city** | Mumbai leads with approximately **₹669 million** in realized revenue. |
| **Highest occupancy city** | Delhi leads with approximately **61.5%** overall occupancy and **62.5%** in June. |
| **Best-rated city** | Delhi, with an average rating of **3.78**. |
| **Lowest-rated city** | Bangalore, with an average rating of **3.41**. |
| **Top-performing property** | AtliQ Exotica, with approximately **₹320 million** in realized revenue. |
| **Lowest revenue-generating property** | AtliQ Seasons, with approximately **₹66 million** in realized revenue. |
| **Room category occupancy** | Occupancy is broadly similar across room classes, at around 58%, with Presidential rooms leading at approximately **59.3%**. |

## 💡 Business Recommendations

- **Optimize pricing:** Explore premium pricing during high-demand weekends and targeted weekday promotions to improve utilization.
- **Improve guest experience:** Investigate service quality, guest feedback, and operational issues in Bangalore, the lowest-rated market.
- **Strengthen direct bookings:** Evaluate dependence on online travel agencies (OTAs), booking-channel commissions, and opportunities to grow direct reservations.
- **Improve revenue visibility:** Monitor occupancy, realized revenue, average ratings, and booking-channel performance through regular reporting.
- **Validate recommendations:** Run controlled pricing and promotional experiments before scaling changes across properties.

## 🧹 Data Cleaning

Data quality checks were performed before generating business insights.

- Removed **12 records** with negative or zero guest counts, treated as data-entry errors.
- Removed **5 revenue outliers** using a mean + 3 standard deviations rule. These entries were approximately 1,000 times the realized revenue.
- Filtered **6 aggregate records** where successful bookings exceeded available capacity.
- Filled **2 missing capacity values** using the median.
- Left missing ratings, representing approximately **58% of records**, untouched to avoid introducing unsupported assumptions.
- Validated unusually high revenue associated with **RT4 (Presidential)** rooms within the room category to distinguish legitimate premium revenue from outliers.

## 🔄 Data Transformation

The following transformations were performed using Pandas:

- Created an **occupancy percentage** column using successful bookings divided by capacity.
- Merged five relational datasets using their relevant keys.
- Converted mixed-format date strings into proper datetime values.
- Appended newly received August data using `pd.concat()`.
- Aggregated metrics by city, property, month, room class, and booking platform.
- Prepared the cleaned datasets for business analysis and visualization.

## 📂 Dataset

The project uses the following CSV files:

| File | Description |
|---|---|
| `fact_bookings.csv` | Approximately 134K booking-level records. |
| `fact_aggregated_bookings.csv` | Daily capacity and successful booking data. |
| `dim_hotels.csv` | Details of 25 properties, including city and category. |
| `dim_rooms.csv` | Room categories and room classes. |
| `dim_date.csv` | Calendar information, including month, week number, and weekday/weekend classification. |
| `new_data_august.csv` | Additional August data for appending to the existing dataset. |

**Note:** Place all CSV files inside a `datasets/` folder located alongside the Jupyter Notebook.

## 🛠️ Tech Stack

- **Python 3**: Data analysis and processing.
- **Pandas**: Data cleaning, merging, transformation, and aggregation.
- **Matplotlib**: Data visualization.
- **Jupyter Notebook**: Interactive analysis and documentation.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

### 2. Install dependencies

```bash
pip install pandas matplotlib jupyter
```

### 3. Verify the project structure

Ensure that your repository contains the notebook and the required CSV files:

```text
.
├── Hotel_Analysis.ipynb
├── datasets/
│   ├── fact_bookings.csv
│   ├── fact_aggregated_bookings.csv
│   ├── dim_hotels.csv
│   ├── dim_rooms.csv
│   ├── dim_date.csv
│   └── new_data_august.csv
└── README.md
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook Hotel_Analysis.ipynb
```

Run the notebook cells sequentially to reproduce the analysis.

## 📈 Notebook Workflow

The analysis follows four main stages:

1. **Data Import & Exploration**  
   Load datasets and inspect their dimensions, data types, distributions, and missing values.

2. **Data Cleaning**  
   Identify and handle invalid guest counts, revenue outliers, missing capacity values, and inconsistent records.

3. **Data Transformation**  
   Create derived metrics, merge relational datasets, convert dates, and append August data.

4. **Business Insights & Visualization**  
   Answer the ten business questions through aggregations, comparisons, and visualizations.

## 👤 Author

**Darshil**

- **LinkedIn:** [https://www.linkedin.com/in/darshil-shah18/)
- **GitHub:** [https://github.com/Darshilshah0203)

---

⭐ **If you found this project useful, consider giving the repository a star!**
