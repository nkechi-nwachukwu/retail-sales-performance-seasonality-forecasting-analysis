# 📊 Retail Sales Performance, Seasonality & Forecasting Analysis
 
**SQL | Tableau | Retail Analytics | Time-Series Analysis | Forecasting**
 
## 🎯 Project Overview
 
This project analyzes historical Walmart retail sales to understand sales performance, recurring seasonal patterns, store and department performance, business drivers, and future sales patterns.
 
The analysis combines multiple datasets into a structured relational data model, uses SQL for data preparation and reusable analytical views, and connects the resulting analytical dataset to Tableau for interactive reporting and forecasting.
 
The project covers **45 stores, 81 departments, more than three years of historical sales, and $6.74B+ in sales**.
 
The objective is not only to report what happened, but to translate historical sales behavior into insights that can support inventory planning, workforce planning, promotional planning, and resource allocation.
 
---
## 📈 Dashboard Preview
<img width="1600" height="1200" alt="Retail Sales Performance Mockup" src="https://github.com/user-attachments/assets/611c7290-71ad-4149-bc04-7ce4a8263a85" />

---
 
## ⚠️ Business Problem
 
Retail sales fluctuate over time because of recurring seasonal patterns, holidays, store characteristics, department mix, promotions, and broader operating conditions.
 
A retail business therefore needs to answer questions such as:
 
- How are sales performing over time?
- Which stores and departments contribute most to sales?
- Which periods consistently generate stronger or weaker demand?
- How significant is holiday-period demand?
- Are observed sales patterns primarily seasonal, operational, or associated with external variables?
- How can historical sales patterns support future planning?
- Where should inventory, staffing, promotions, and operational resources be prioritized?
This project addresses these questions through SQL-based data preparation and Tableau-based analytical reporting and forecasting.
 
---
 
## 🎯 Project Objectives
 
1. Measure overall retail sales performance.
2. Analyze sales trends across the historical period.
3. Identify recurring seasonal and holiday patterns.
4. Compare performance across stores and departments.
5. Evaluate the relationship between sales and selected external variables.
6. Identify periods of elevated or reduced demand.
7. Apply forecasting to historical sales patterns.
8. Translate analytical findings into operational recommendations.
   
---
 
## 🧠 Dataset Scope
 
| Metric | Coverage |
|---|---:|
| Stores | 45 |
| Departments | 81 |
| Historical period | 3+ years |
| Total sales analyzed | $6.74B+ |
| Primary analytical grain | Store × Department × Week |
 
The project integrates historical sales with supporting store and external-factor datasets.
 
**Core data domains** 
- Weekly department-level sales
- Store characteristics
- Holiday indicators
- Temperature
- Fuel prices
- CPI
- Unemployment
- Promotional/markdown variables where available
---
 
**Data Architecture** 

Multiple source datasets were integrated into a relational analytical structure.
 
```text
                    ┌──────────────────┐
                    │   Store Data     │
                    │ Store / Type /   │
                    │ Size             │
                    └────────┬─────────┘
                             │
                             │ Store
                             ▼
┌──────────────────┐   ┌──────────────────────┐
│ External Factors │──▶│  Sales Master View   │◀──┐
│ Date / Store     │   │ Store × Dept × Date  │   │
│ Temp / Fuel /    │   │ Weekly Sales         │   │
│ CPI / Unemployment│  └──────────┬───────────┘   │
└──────────────────┘              │               │
                                  │               │
                           Store + Department     │
                                  │               │
                                  ▼               │
                         ┌─────────────────┐       │
                         │ Sales / Dept.   │       │
                         │ Performance     │       │
                         └─────────────────┘       │
                                                   │
                         Holiday / Date ───────────┘
```
 
SQL was used to load, clean, validate, join, and transform the source datasets and create reusable analytical views.
 
---
 
## 🔄 Analytical Workflow

```text
Raw Datasets
     ↓
Data Profiling
     ↓
Data Cleaning & Validation
     ↓
Relational Data Model
     ↓
SQL Joins & Transformations
     ↓
Reusable Analytical Views
     ↓
Master Analytical Dataset
     ↓
Sales Performance Analysis
     ↓
Trend & Seasonality Analysis
     ↓
Store & Department Analysis
     ↓
External Driver Analysis
     ↓
Forecasting
     ↓
Tableau Dashboards
     ↓
Business Insights & Recommendations
```
 
---
 
## Key Performance Indicators
 
| KPI | Definition | Business Meaning |
|---|---|---|
| Total Sales | Sum of weekly sales across the analysis population | Overall sales performance |
| Average Weekly Sales | Average weekly sales over the selected period | Typical weekly sales level |
| Store Coverage | Number of stores represented in the analysis | Operational coverage |
| Department Coverage | Number of departments represented | Product/category coverage |
| Holiday Sales Contribution | Holiday-period sales as a share of total sales | Holiday demand significance |
| Store Sales Contribution | Store sales as a share of total sales | Store-level concentration |
| Department Sales Contribution | Department sales as a share of total sales | Department-level concentration |
| Sales Growth | Change in sales between comparison periods | Performance direction |
| Forecast Sales | Projected future sales based on historical patterns | Planning baseline |
 
---
 
# Sales Performance Analysis
 
The first analytical layer evaluates the overall sales trajectory and the distribution of sales across the retail network.
 
The analysis considers:
 
- Total sales
- Average weekly sales
- Sales trends over time
- Store-level contribution
- Department-level contribution
- Period-over-period changes
- Concentration of revenue across stores and departments
### Key observations
 
- The dataset represents **$6.74B+ in sales** across 45 stores and 81 departments.
- Sales are not evenly distributed across the retail network; a relatively smaller group of stores and departments accounts for a substantial share of sales.
- Performance varies across the historical period, creating clear opportunities for time-based planning and resource allocation.
---
 
# Trend & Seasonality Analysis
 
Time-series analysis was used to identify recurring patterns in sales.
 
The analysis examines:
 
- Monthly sales patterns
- Quarterly performance
- Weekly sales movement
- Holiday periods
- Peak and lower-demand periods
- Recurring seasonal behavior
### Key findings
 
**July and Q3 were among the strongest sales periods** in the historical data.
 
The analysis also identified a meaningful holiday effect, with **holiday-period sales contributing approximately 7.5% of total revenue**.
 
These patterns demonstrate why retail planning should account for recurring demand cycles rather than relying only on overall averages.
 
---
 
# Store & Department Performance
 
Store and department performance were analyzed separately to identify concentration and differences in sales contribution.
 
### Store analysis
 
The store-level analysis supports:
 
- Identification of high-performing stores
- Comparison of sales contribution
- Detection of performance variation
- Resource allocation
- Store-specific planning
### Department analysis
 
The department-level analysis supports:
 
- Identification of high-contribution departments
- Comparison of department sales patterns
- Demand planning
- Inventory prioritization
- Promotion planning
Revenue concentration across higher-performing stores and departments indicates that operational planning can benefit from prioritizing areas with the largest sales contribution.
 
---
 
# External Driver Analysis
 
The project also evaluates sales alongside selected external variables:
 
- Temperature
- Fuel prices
- CPI
- Unemployment
- Holiday indicators
- Promotional/markdown variables where available
The purpose is to determine whether changes in these variables correspond with meaningful changes in observed sales patterns.
 
### Interpretation
 
The analysis found that several external variables showed **limited influence relative to the stronger recurring effects associated with seasonality, holidays, and operational sales patterns** in this dataset.
 
This should be interpreted as an observational finding rather than evidence that these variables have no causal relationship with retail demand.
 
---
 
# Forecasting
 
Forecasting was performed using historical sales patterns in Tableau.
 
The forecasting layer provides a forward-looking planning baseline based on the historical time series.
 
### Forecasting objectives
 
- Extend observed sales trends into future periods.
- Identify expected future demand patterns.
- Support inventory planning.
- Support workforce planning.
- Support operational preparation for seasonal periods.
- Provide a quantitative baseline for planning discussions.
### Forecast interpretation
 
The forecast should be treated as a **planning baseline rather than a guaranteed future outcome**.
 
Forecast accuracy can be affected by:
 
- Structural changes in customer demand
- New promotions
- Store changes
- Supply constraints
- Economic conditions
- Unexpected events
- Changes in product mix
---
 
# Tableau Dashboards
 
The Tableau reporting layer was organized around four analytical views.
 
## 1. Executive Sales Overview
 
Provides a high-level view of:
 
- Total sales
- Average weekly sales
- Store coverage
- Department coverage
- Holiday contribution
- Overall sales trends
## 2. Seasonality & Holiday Analysis
 
Focuses on:
 
- Monthly sales patterns
- Quarterly trends
- Holiday vs. non-holiday performance
- Seasonal peaks
- Lower-demand periods
## 3. Store & Department Performance
 
Focuses on:
 
- Store ranking and contribution
- Department performance
- Sales concentration
- Comparative performance
- Drill-down analysis
## 4. Sales Drivers & Forecasting
 
Combines:
 
- Historical sales trend
- External variables
- Observed sales drivers
- Forecasted sales
- Forward-looking planning context
---
 
# 📊 Business Findings
 
### 1. Sales show meaningful seasonal variation
 
Sales performance changes across the year, with July and Q3 representing particularly strong periods in the historical data.
 
### 2. Holiday periods have material revenue importance
 
Holiday-period sales account for approximately **7.5% of total revenue**, making holiday planning an important component of retail operations.
 
### 3. Sales are concentrated across stores and departments
 
Not all stores and departments contribute equally to total sales. High-contribution locations and departments therefore have greater relevance for inventory and resource planning.
 
### 4. Historical sales patterns provide useful forecasting signals
 
Recurring sales behavior creates a basis for forecasting future demand and preparing for expected changes in sales volume.
 
### 5. External variables provide additional context
 
Temperature, fuel prices, CPI, unemployment and promotional variables were examined alongside sales. In this analysis, their observed influence was generally less pronounced than recurring seasonal and operational patterns.
 
---
 
# 💡 Business Recommendations
 
## 1. Incorporate seasonality into inventory planning
 
Use historical seasonal patterns to anticipate periods of higher demand and prepare inventory before demand increases.
 
## 2. Prepare operational capacity for peak periods
 
Higher-demand periods should inform workforce scheduling, store operations, replenishment capacity, and logistics planning.
 
## 3. Prioritize high-contribution stores and departments
 
Resource allocation should account for differences in sales contribution rather than treating all stores and departments identically.
 
## 4. Use forecasting as a planning input
 
Forecast outputs can be incorporated into sales targets, inventory planning, staffing plans, and operational reviews.
 
## 5. Plan promotions around observed demand patterns
 
Promotional activity can be evaluated against historical seasonal demand to understand whether campaigns are supporting incremental demand or coinciding with periods that would naturally be stronger.
 
## 6. Monitor performance continuously
 
A recurring KPI reporting process can help identify deviations from historical patterns early and allow management to respond before performance gaps become material.
 
---
 
# Limitations
 
This project is primarily descriptive and forecasting-oriented.
 
### Data limitations
 
- Historical data does not guarantee future behavior.
- The available variables do not capture every factor affecting retail demand.
- Customer-level behavior is not represented in the primary analysis.
- Profitability cannot be inferred from sales alone.
- Forecasts are sensitive to changes in underlying demand patterns.
### Analytical limitations
 
Observed relationships between sales and external variables should not be interpreted as causal effects without additional experimental or statistical validation.
 
The forecasting output should therefore be used as a planning baseline and evaluated against actual future performance.
 
---
 
# 🚀 Future Improvements
 
Potential extensions include:
 
- Forecast accuracy monitoring using actual vs. predicted sales
- Store-level forecasting
- Department-level forecasting
- Promotion uplift analysis
- Inventory optimization
- Stockout analysis
- Profitability analysis
- Customer-level demand analysis
- Advanced time-series modeling
- Forecast error tracking
- Scenario analysis
- Automated KPI reporting
---
 
# 🛠 Tools & Technologies
 
| Tool | Application |
|---|---|
| SQL | Data cleaning, transformation, joins, validation and analytical views |
| Tableau | Interactive dashboards, visualization and forecasting |
| Relational Database | Structured integration of multiple source datasets |
| Data Modeling | Primary/foreign-key relationships and analytical data structure |
| Time-Series Analysis | Trend and seasonality analysis |
| Forecasting | Historical sales-based forward planning |
 
---
 
# Repository Structure
 
```text
retail-sales-performance-seasonality-forecasting/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── data/
│   ├── raw/
│   ├── processed/
│   └── data_dictionary/
│
├── sql/
│   ├── 01_data_profiling.sql
│   ├── 02_data_cleaning.sql
│   ├── 03_sales_performance.sql
│   ├── 04_time_series_analysis.sql
│   ├── 05_seasonality_analysis.sql
│   ├── 06_store_product_analysis.sql
│   └── 07_forecasting_dataset.sql
│
├── analysis/
│   ├── business_questions.md
│   ├── methodology.md
│   ├── exploratory_analysis.md
│   ├── sales_performance.md
│   ├── seasonality_analysis.md
│   ├── forecasting_methodology.md
│   ├── findings.md
│   ├── recommendations.md
│   └── limitations.md
│
├── forecasting/
│   ├── forecast_methodology.md
│   ├── forecast_results.md
│   └── model_evaluation.md
│
├── powerbi/
│   ├── retail-sales-analysis.pbix
│   └── dashboard-overview.png
│
├── visuals/
│   ├── dashboard-overview.png
│   ├── sales-trend.png
│   ├── monthly-seasonality.png
│   ├── store-performance.png
│   ├── product-performance.png
│   └── sales-forecast.png
│
└── docs/
    ├── project-methodology.md
    └── technical-notes.md
```
 
> **Note:** The analytical work for this project was performed with SQL and Tableau. The `powerbi/` directory is retained only if a Power BI version of the dashboard is actually part of the repository; otherwise it should be removed.
 

## 👤 Author
Nkechi Nwachukwu Business Analyst | Data & Operations Analytics

Portfolio: https://dorothy-data-portfolio.lovable.app

GitHub: https://github.com/nkechi-nwachukwu

LinkedIn: https://linkedin.com/in/nkechi-nwachukwu-82ba911bb
