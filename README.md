# Customer Behavior Dashboard - Power BI Project

![Dashboard Preview](./dashboard-preview.png)

## 📊 Project Overview

This project analyzes customer shopping trends and behaviors using **Power BI** for visualization and **Python** for data cleaning and transformation. The dashboard provides actionable insights into customer demographics, purchasing patterns, and product preferences to help drive data-driven business decisions.

## 🎯 Key Metrics & Insights

The dashboard tracks and visualizes:

- **1,053K Total Customers** analyzed across all segments
- **$59.49 Average Purchase Amount** per transaction
- **3.75 Average Review Rating** indicating customer satisfaction
- **100% Subscription Status** tracking for customer engagement
- Revenue and sales analysis by:
  - Product category (Clothing, Accessories, Footwear, Outerwear)
  - Age group (Young Adult, Adult, Middle-aged, Senior)
  - Subscription status
  - Demographics and preferences

## 🧹 Data Cleaning Process

The raw dataset was cleaned and prepared using Python (Pandas) in a Jupyter Notebook. Key data cleaning steps included:

### 1. **Data Exploration**
- Loaded dataset with 3,900 customer records and 19 columns
- Performed initial analysis using `.info()`, `.describe()`, and `.head()`
- Identified data types and statistical distributions

### 2. **Handling Missing Values**
- Checked for null values across all columns using `.isnull().sum()`
- Imputed missing values in the `Review Rating` column with the median rating per product category
- Ensured data completeness for accurate analysis

### 3. **Column Standardization**
- Converted all column names to **snake_case** for consistency
- Renamed `Purchase Amount (USD)` to `purchase_amount`
- Improved readability and documentation standards

### 4. **Feature Engineering**
- **Created `age_group` column**: Segmented customers into 4 categories (Young Adult, Adult, Middle-aged, Senior) using `pd.qcut()`
- **Created `purchase_frequency_days` column**: Mapped purchase frequency text to numeric days:
  - Weekly → 7 days
  - Fortnightly/Bi-Weekly → 14 days
  - Monthly → 30 days
  - Quarterly/Every 3 Months → 90 days
  - Annually → 365 days

### 5. **Data Quality Improvements**
- Identified redundant column: `promo_code_used` was identical to `discount_applied`
- Dropped duplicate column to reduce redundancy
- Finalized dataset with 20 meaningful columns

### 6. **Data Export**
- Exported cleaned dataset as `cleaned_data.csv`
- Ready for import into Power BI

## 📁 Project Structure

```
├── customer_shopping_notebook.ipynb    # Python data cleaning notebook
├── cleaned_data.csv                    # Cleaned dataset (output)
├── shopping_trends.csv                 # Original raw dataset (not included)
├── dashboard.pbix                      # Power BI dashboard file
└── README.md                           # Project documentation
```

## 🛠️ Technologies Used

- **Power BI Desktop** - Data visualization and dashboard creation
- **Python 3.13** - Data cleaning and transformation
- **Pandas** - Data manipulation and analysis
- **Matplotlib** - Data visualization (exploratory analysis)
- **Jupyter Notebook** - Interactive development environment

## 📋 Dataset Details

### Original Dataset Columns
- Customer ID, Age, Gender
- Item Purchased, Category, Purchase Amount
- Location, Size, Color, Season
- Review Rating, Subscription Status
- Payment Method, Shipping Type
- Discount Applied, Promo Code Used
- Previous Purchases, Preferred Payment Method
- Frequency of Purchases

### Engineered Features
- `age_group`: Categorical age segmentation
- `purchase_frequency_days`: Numeric representation of purchase frequency

### Data Statistics
- **Records**: 3,900 customer transactions
- **Features**: 20 columns (after cleaning)
- **Categories**: 4 product categories
- **Age Range**: 18-70 years
- **Purchase Range**: $20-$100 USD

## 🚀 How to Use This Project

### Prerequisites
- Power BI Desktop installed
- Python 3.x with Pandas and Jupyter Notebook (for data cleaning)

### Steps to Run

1. **Data Cleaning** (Optional - cleaned data already available)
   ```bash
   jupyter notebook customer_shopping_notebook.ipynb
   ```
   - Run all cells to reproduce the data cleaning process
   - Output: `cleaned_data.csv`

2. **Power BI Dashboard**
   - Open `dashboard.pbix` in Power BI Desktop
   - Refresh data source if needed
   - Explore interactive visualizations and filters

3. **Customize Analysis**
   - Adjust filters for specific demographics or time periods
   - Create additional calculated measures as needed
   - Export insights or publish to Power BI Service

## 📊 Dashboard Features

### Interactive Filters
- **Subscription Status**: Yes/No
- **Gender**: Male/Female
- **Category**: Accessories, Clothing, Footwear, Outerwear
- **Shipping Type**: Multiple shipping options

### Visualizations
- **KPI Cards**: Total customers, average purchase amount, average review rating
- **Donut Chart**: Customer distribution by subscription status
- **Bar Charts**: 
  - Revenue by category
  - Sales by category
  - Revenue by age group
  - Sales by age group

## 🔍 Key Insights Discovered

1. **Clothing dominates** both revenue and sales across all categories
2. **Young Adults** show the highest purchasing volume
3. **100% subscription tracking** enables customer retention analysis
4. **Middle-aged customers** contribute significantly to revenue
5. **Product preferences** vary distinctly across age groups

## 📈 Future Enhancements

- Add time-series analysis for trend forecasting
- Implement customer segmentation using clustering algorithms
- Include profitability analysis with cost data
- Add predictive analytics for customer churn
- Integrate real-time data refresh capabilities

## 📞 Contact & Contributions

Feel free to fork this project and submit pull requests for improvements. For questions or suggestions, please open an issue in the repository.

## 📝 License

This project is available for educational and portfolio purposes.

---

**Note**: The raw dataset (`shopping_trends.csv`) should be placed in the appropriate directory before running the Jupyter notebook. Update the file path in the notebook according to your local setup.
