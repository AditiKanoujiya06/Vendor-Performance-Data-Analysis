# Vendor Performance Data Analysis

## Project Overview

This project analyzes vendor performance, procurement efficiency, sales
performance, profitability, and inventory management using transactional
retail and wholesale data.

The analysis focuses on identifying opportunities to improve
profitability, reduce vendor concentration risk, optimize purchasing
decisions, and manage slow-moving inventory.

The project was developed using Python and includes exploratory data
analysis, data cleaning, profitability analysis, vendor concentration
analysis, bulk-purchasing analysis, inventory turnover analysis,
statistical validation, and business recommendations.

------------------------------------------------------------------------

## Business Problem

Effective inventory and sales management are critical for optimizing
profitability in the retail and wholesale industry.

The analysis addresses the following business questions:

1.  Which brands have relatively low sales but high profit margins and
    may benefit from promotional or pricing adjustments?
2.  Which vendors contribute most to total purchases and sales?
3.  How does bulk purchasing affect unit costs?
4.  Which vendors or products have low inventory turnover and high
    amounts of tied-up inventory capital?
5.  How do profit margins differ between high-performing and
    low-performing vendors?
6.  Are the observed differences in vendor profitability statistically
    significant?

------------------------------------------------------------------------

## Dataset

The project uses the following source files contained in the project
dataset:

-   `purchases.csv`
-   `purchase_prices.csv`
-   `vendor_invoice.csv`
-   `begin_inventory.csv`
-   `end_inventory.csv`
-   `sales.csv`

The analysis combines purchasing, sales, inventory, pricing, and vendor
information to create business-level performance metrics.

> Note: The raw sales dataset is very large. For reproducibility and
> GitHub usability, the raw dataset should be kept outside the
> repository or provided separately rather than committed directly to
> GitHub.

------------------------------------------------------------------------

## Tools and Technologies

-   Python
-   Pandas
-   NumPy
-   Matplotlib
-   Seaborn
-   SciPy
-   Jupyter Notebook
-   Statistical Analysis
-   Data Visualization
-   Business Analytics

------------------------------------------------------------------------

## Analytical Workflow

### 1. Data Loading

The source CSV files are loaded into Python and inspected for:

-   Number of rows and columns
-   Data types
-   Missing values
-   Duplicate records
-   Numeric and categorical variables
-   Basic descriptive statistics

### 2. Data Cleaning

The analysis prepares the data for reliable business calculations by:

-   Handling missing values
-   Converting numeric fields to appropriate data types
-   Aggregating transactional data where required
-   Handling zero sales and zero quantities
-   Creating consistent vendor and product-level metrics
-   Removing or filtering inconsistent observations where appropriate

The original analysis also examined negative/zero gross profit,
zero-sales products, extreme prices, freight-cost variation, and
stock-turnover variation.

------------------------------------------------------------------------

## Key Metrics

The project calculates several performance indicators, including:

### Gross Profit

`Gross Profit = Total Sales Dollars - Estimated Cost of Goods Sold`

### Profit Margin

`Profit Margin = Gross Profit / Total Sales Dollars`

### Unit Cost

`Unit Cost = Purchase Dollars / Purchase Quantity`

### Purchase Contribution

`Vendor Purchase Contribution = Vendor Purchases / Total Purchases`

### Stock Turnover

`Stock Turnover = Total Sales Quantity / Total Purchase Quantity`

These metrics are used to compare brands, vendors, purchasing
strategies, and inventory performance.

------------------------------------------------------------------------

# Key Business Findings

## 1. Low-Sales / High-Margin Brands

The analysis identified **198 brands** exhibiting lower sales but
relatively higher profit margins.

These brands represent potential opportunities for:

-   Targeted promotions
-   Pricing optimization
-   Marketing campaigns
-   Distribution improvements
-   Increasing sales volume without unnecessarily sacrificing margins

The objective is to convert strong margins into higher sales volume.

------------------------------------------------------------------------

## 2. Vendor Purchase Concentration

The analysis found that the **top 10 vendors contribute 65.69% of total
purchases**, while the remaining vendors contribute 34.31%.

This indicates significant procurement dependency on a relatively small
number of suppliers.

### Business implication

High vendor concentration can increase exposure to:

-   Supply-chain disruptions
-   Vendor-specific pricing changes
-   Availability constraints
-   Procurement risk

### Recommendation

Diversifying vendor partnerships while maintaining relationships with
strategically important suppliers can reduce concentration risk.

------------------------------------------------------------------------

## 3. Bulk Purchasing and Unit-Cost Savings

The analysis found that vendors purchasing in larger quantities achieved
approximately **72% lower unit costs**, with the report identifying a
unit cost of approximately **\$10.78 per unit** for the bulk-purchasing
group.

### Business implication

Bulk purchasing can provide substantial cost advantages and support
competitive pricing.

However, bulk purchasing should be balanced against inventory carrying
costs and the risk of overstocking.

### Recommendation

Use historical demand and inventory turnover to determine appropriate
bulk-order quantities rather than maximizing order size
indiscriminately.

------------------------------------------------------------------------

## 4. Slow-Moving Inventory

The analysis identified approximately **\$2.71 million in unsold
inventory capital** associated with slow-moving inventory.

Slow-moving inventory can:

-   Increase storage costs
-   Tie up working capital
-   Reduce cash-flow efficiency
-   Increase the risk of obsolescence
-   Reduce overall inventory efficiency

### Recommendation

Potential actions include:

-   Revising purchase quantities
-   Running targeted clearance promotions
-   Adjusting pricing
-   Improving demand forecasting
-   Revising storage and replenishment strategies

------------------------------------------------------------------------

## 5. High-Performing vs. Low-Performing Vendors

The analysis compared vendor groups based on performance.

### Top-performing vendors

-   Mean profit margin: **31.17%**
-   95% confidence interval: **30.74%--31.61%**

### Low-performing vendors

-   Mean profit margin: **41.55%**
-   95% confidence interval: **40.48%--42.62%**

An important business insight is that the lower-performing vendors by
sales performance can still maintain higher profit margins. Their
challenge may therefore be sales volume, pricing, marketing reach, or
distribution rather than profitability alone.

------------------------------------------------------------------------

## 6. Statistical Validation

The project formally tested whether profit margins differed between the
two vendor groups.

### Null Hypothesis (H₀)

There is no significant difference in profit margins between
top-performing and low-performing vendors.

### Alternative Hypothesis (H₁)

There is a significant difference in profit margins between the two
vendor groups.

The analysis rejected the null hypothesis, supporting the conclusion
that the two vendor groups operate under significantly different
profitability models.

This statistical validation strengthens the business interpretation
beyond simply comparing average margins.

------------------------------------------------------------------------

# Exploratory Data Analysis Insights

The analysis also identified several important characteristics of the
dataset.

### Gross Profit

Gross profit contains negative observations, with a minimum reported
value of approximately **-\$52,002.78**, indicating transactions where
costs exceeded revenue.

### Profit Margin

Extreme negative profit-margin values occur when revenue is zero or
lower than total cost.

### Sales Quantity

Some products have zero sales despite being purchased, indicating
potential slow-moving or obsolete inventory.

### Purchase and Actual Prices

The dataset contains substantial price variation, including premium
products with significantly higher purchase and actual prices.

### Freight Cost

Freight cost shows substantial variation, which may reflect differences
in shipment size, logistics, or other procurement conditions.

### Stock Turnover

Stock turnover varies considerably across products, indicating that some
products sell rapidly while others remain in inventory for extended
periods.

------------------------------------------------------------------------

# Correlation Analysis

The analysis examined relationships between major business variables.

Key observations included:

-   Purchase price vs. total sales dollars: weak negative correlation
-   Purchase price vs. gross profit: weak negative correlation
-   Total purchase quantity vs. total sales quantity: very strong
    positive correlation
-   Profit margin vs. total sales price: negative correlation
-   Stock turnover vs. gross profit: weak negative correlation
-   Stock turnover vs. profit margin: weak negative correlation

These relationships indicate that higher purchasing or sales volume does
not automatically translate into higher profitability.

------------------------------------------------------------------------

# Business Recommendations

Based on the analysis, the following strategies are recommended:

### Pricing and Promotions

Re-evaluate pricing for low-sales, high-margin brands and use targeted
promotions to increase sales volume while protecting profitability.

### Vendor Diversification

Reduce excessive procurement dependency on a small number of vendors by
developing a broader supplier base.

### Bulk Purchasing

Leverage bulk-purchasing discounts where demand is sufficiently
predictable, while monitoring inventory holding costs.

### Inventory Optimization

Reduce slow-moving inventory through improved purchasing decisions,
clearance strategies, pricing adjustments, and better demand planning.

### Vendor Strategy

Separate sales performance from margin performance when evaluating
vendors. Vendors with high margins but low sales may require stronger
marketing and distribution rather than simple cost reductions.

------------------------------------------------------------------------

# Project Structure

``` text
Vendor-Performance-Data-Analysis/
│
├── data.zip
│
├── Final_Vendor_Analysis.ipynb
│
└── README.md
```

The notebook contains the complete analytical workflow, while `data.zip`
contains the source datasets used for the analysis.

For GitHub, the large raw dataset should preferably be stored outside
the repository or replaced with a smaller sample dataset and clear
instructions for obtaining the original data.

------------------------------------------------------------------------

# Reproducibility

To reproduce the analysis:

1.  Download or place the project dataset in the expected location.
2.  Extract the source CSV files.
3.  Open `Final_Vendor_Analysis.ipynb`.
4.  Install the required Python libraries.
5.  Run the notebook from the first cell through the final business
    recommendations.

Because the sales dataset is large, memory-efficient loading and
aggregation should be used where necessary.

------------------------------------------------------------------------

# Conclusion

This project demonstrates how transactional sales, purchasing, vendor,
pricing, and inventory data can be transformed into actionable business
insights.

The analysis identified:

-   **198** low-sales/high-margin brands
-   **65.69%** procurement concentration among the top 10 vendors
-   Approximately **72%** unit-cost savings associated with bulk
    purchasing
-   Approximately **\$2.71M** in slow-moving inventory capital
-   A statistically significant difference in profit margins between
    vendor performance groups

Together, these findings support data-driven decisions around pricing,
sourcing, vendor diversification, procurement strategy, and inventory
optimization.

------------------------------------------------------------------------

## Author

**Aditi Kanoujiya**

B.Sc. Physics \| Business Analytics & Data Science

This project demonstrates practical application of Python, data
analysis, statistical testing, and business-oriented problem solving.
