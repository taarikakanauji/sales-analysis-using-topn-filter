# Sales Analysis using Top N Filter - Power BI 

![Power BI Report - Home View](https://github.com/taarikakanauji/sales-analysis-using-topn-filter/raw/main/images/home.jpg)

## Problem Statement

Stakeholders currently lack a dynamic, consolidated view to monitor real-time sales performance based on top-performing customers, products, and revenue segments. This gap restricts visibility into which customer segments and product lines are driving the highest value, and makes it difficult to assess temporal trends in revenue performance such as monthly growth, cumulative revenue, and gross vs. net margins.

The Sales Analysis dashboard fills this need by offering an interactive interface that allows users to filter sales data by Top N customers, track running totals by month, and analyze revenue contributions by individual products. With time period slicing (e.g., by quarter) and revenue type switching (Gross, Net, Profit), the dashboard enables clear and flexible insight into revenue dynamics.

This solution supports stakeholders in uncovering top contributors, spotting underperformers, and identifying opportunities to increase revenue and optimize offerings. It is particularly useful for:

- Business Executives – To quickly assess overall performance and identify key growth drivers.

- Sales Managers – To focus efforts on high-performing clients and products.

- Product Managers – To refine product strategy based on contribution to revenue.

- Finance Teams – To evaluate profit margins across customers and timeframes.

# Objective

`Identify Top Performing Customers` -
Enable stakeholders to dynamically view the top N customers contributing the highest revenue, helping prioritize key accounts for retention and growth initiatives.

`Analyze Revenue Breakdown by Type` -
Provide a clear comparison of Gross Revenue, Net Revenue, and Gross Profit across months to understand profitability drivers and track financial performance over time.

`Monitor Monthly and Cumulative Sales Trends` -
Visualize both individual month-wise revenue and the running total to detect seasonal patterns, assess momentum, and forecast upcoming performance.

`Evaluate Product-Level Revenue Contribution` -
Highlight the highest-grossing products to support data-driven product assortment decisions and optimize inventory and marketing strategies.

`Enable Time-Based Sales Comparison` -
Allow users to analyze revenue performance across different quarters (e.g., Q2 2017 vs. Q3 2017) to identify temporal trends and evaluate the impact of sales strategies.

## Key Questions

    Q : Which customers are contributing the most to overall revenue in the selected quarter?

    Q : How does revenue differ when filtering by Top 3, Top 10, or Top 50 customers?

    Q : Which products generated the highest revenue in Q2 2017?

    Q : What is the Gross Revenue, Net Revenue, and Gross Profit trend across May and June?

    Q : Is there a significant difference between Gross Revenue and Net Revenue? What could be causing it?

    Q : What is the running total revenue as of June 2017, and how has it grown since May?

    Q : How does Q2 2017 sales performance compare to Q3 or Q4 2017? 

    Q : Are any products underperforming despite being stocked in high quantities?

    Q : Which customer segments or individuals appear consistently in the Top 10 across quarters?

    Q : How do revenue figures vary across different Top N selections for the same time period?   

## Steps followed 

As a Business Analyst for a major retail enterprise, I spearheaded the creation of an interactive Sales Analysis Dashboard featuring Top N filters, aimed at providing stakeholders with a centralized, real-time view of revenue performance, product contributions, and customer value across time periods and sales segments.

The objective was to deliver meaningful insights that empower data-driven decisions—helping teams refine product strategies, enhance sales focus, improve profitability, and align operational efforts with measurable business outcomes.

To build the Sales Analysis dashboard in Power BI with Top N filtering, I followed a structured approach focused on data quality, performance, and interactivity:

- Step 1: I began by importing all relevant CSV files into MySQL Workbench and establishing a connection to Power BI using the MySQL connector. After authentication, I selected the required tables directly from the database for use in the model.

- Step 2: Within Power Query Editor, I enabled Column Distribution, Column Quality, and Column Profile under the View tab. This helped assess the structure and integrity of the data early in the process.

- Step 3: To ensure comprehensive profiling beyond the default 1,000-row limit, I modified the data profiling setting to analyze the entire dataset—enabling deeper validation and better data preparation.

- Step 4: I performed thorough data cleansing to address missing or erroneous values, ensuring the dataset was fully reliable before proceeding with modeling and visual development.

- Step 5: In Report View, I applied a default theme under the View tab to establish visual consistency across the dashboard, enhancing the professional look and feel of the Sales Analysis report.
           
- Step 6 : **Revenue by Top N** – I incorporated a horizontal bar chart to illustrate revenue contribution segmented by different Top N customer groups. This visual helps compare how revenue varies when filtered by the Top 3, Top 5, Top 10, Top 20, Top 50, and all customers.

        Fields Used:

        Y-axis: Top N Group (All, Top 50, Top 20, etc.)

        Values (X-axis): Total Revenue

        Data Labels: Revenue Amount in $K

        Color Saturation: Gradient from dark to light based on revenue amount

  The chart also uses a 100% scale bar for context, showing what percentage each Top N group contributes relative to the total revenue. The primary benefit of this chart is that it allows stakeholders to easily see the impact of top-tier customers on overall revenue, supporting decisions around customer prioritization and retention strategies.

  All customers generated approximately $1.42K in total revenue. The Top 50 customers alone contributed ~$1.07K, which is ~75% of total revenue. As the Top N count narrows, the revenue sharply drops, indicating a classic Pareto distribution where ~20% of customers are responsible for ~80% of revenue.

  ![Power BI Report - Revenue by TopN](https://github.com/taarikakanauji/sales-analysis-using-topn-filter/raw/main/images/revenue%20by%20topn.jpg)

- Step 7  : **Products Bar Chart** – I included a horizontal bar chart to display the total revenue generated by individual products during the selected time period. This helps stakeholders identify the best-performing products.

        Fields used:

        Y-axis: Product Names 

        X-Axis: Total Revenue

   Each bar represents the revenue contribution of a product, allowing users to instantly compare product performance. The visual supports scroll functionality to view all products and enables prioritization for stocking, promotions, and sales strategies.

   Foil Cont Round, Squid – Breaded, and Shichimi Togarashi Paste are top sellers. These products each generated close to or above $60 in revenue during the selected quarter.

  ![Power BI Report - Products View](https://github.com/taarikakanauji/sales-analysis-using-topn-filter/raw/main/images/products.jpg)


- Step 8 :  **Revenue by Date** – This clustered column chart provides a month-wise breakdown of different revenue types—Gross Revenue, Net Revenue, and Gross Profit—offering a comparative view of financial performance across time.

        Fields used:

        X-Axis: Month (e.g., May, June)

        Y-Axis: Amount in dollars

        Legend: Revenue Type (Gross Revenue, Net Revenue, Gross Profit)

  This visual is key for analyzing monthly performance across different financial metrics and detecting shifts in profit margins or net earnings.

  Gross Revenue was higher in May than in June, with May exceeding $900, and June slightly below that. Net Revenue closely tracks Gross Revenue, suggesting low discounting or operational costs. Gross Profit, however, remains significantly lower (~$100–$150 range), which could indicate high cost of goods sold (COGS) or operating expenses.

  ![Power BI Report - Revenue by Date](https://github.com/taarikakanauji/sales-analysis-using-topn-filter/raw/main/images/revenue%20by%20date.jpg)


- Step 9 : **Running Total by Date** - I used an area chart to illustrate the cumulative revenue trend over time. It provides a visual representation of how revenue is building month over month.

        Fields used:

        X-axis: Date (Month)

        Y-axis: Cumulative Revenue

        Values Display Type: Area shading

  This chart is useful to understand momentum in sales—whether revenue is accelerating or flattening—and is particularly valuable for forecasting and target tracking.

  The cumulative revenue is growing steadily from May to June, reaching over $1,400. This indicates consistent sales performance without revenue drops, although the slope slightly flattens in June, which aligns with lower revenue seen in the bar chart.


    ![Power BI Report - Running Total](https://github.com/taarikakanauji/sales-analysis-using-topn-filter/raw/main/images/running%20total.jpg)

- Step 10: **Adding Slicers to the Dashboard** - To enhance user experience and promote interactive exploration, I incorporated multiple slicers across the top and left side of the dashboard. These slicers allow users to customize the view dynamically based on time period, customer segments, and ranking tiers. Positioned prominently, these slicers empower stakeholders to explore the data from various dimensions without overwhelming the interface.

  Setting Up Slicers for Interactive Filtering –
  I configured the slicers to support dynamic data exploration, allowing users to filter the report by customer name, ranking (Top N), and quarter. These filters serve as intuitive tools to analyze performance trends over time, highlight top contributors, and drill into specific customers or timeframes for more focused insights.

  I added slicers for:

      Top N (Button Slicer)

      Quarter of the year (Button Slicer)

      Customer Name (Checklist slicer)

  To ensure a clean and professional design, I utilized button and checklist style slicers that apply to all visuals within the report. This configuration empowers stakeholders to easily compare trends over different time periods or evaluate performance across various regions with minimal effort.

  ![Power BI Report - TopN Page](https://github.com/taarikakanauji/sales-analysis-using-topn-filter/raw/main/images/topn.jpg)



  ![Power BI Report - Year Quarter View](https://github.com/taarikakanauji/sales-analysis-using-topn-filter/raw/main/images/year-quarter.jpg)



  ![Power BI Report - Name Page](https://github.com/taarikakanauji/sales-analysis-using-topn-filter/raw/main/images/name.jpg)

# **Project Resources: Sales Analysis using Top N Filter**  

### **Detailed Report (PDF)**  
[Insights of Sales Analysis using Top N Filter](https://github.com/taarikakanauji/customer-segmentation-of-the-superstore/blob/main/Insights%20of%20Customer%20Segmentation%20of%20the%20Superstore.pdf)  

### **Power BI Desktop Demo**  
[Power BI Demo (MKV)](https://github.com/taarikakanauji/customer-segmentation-of-the-superstore/blob/main/Power%20BI%20Demo.mkv)  


### **PBIP Files**  
- **Report:** [Report Files](https://github.com/taarikakanauji/sales-analysis-using-topn-filter/tree/main/Sales%20Analysis%20using%20TopN%20Filter%20DAX.Report) 
- **Semantic Model:** [Semantic Model Files](https://github.com/taarikakanauji/sales-analysis-using-topn-filter/tree/main/Sales%20Analysis%20using%20TopN%20Filter%20DAX.SemanticModel)  
- **Project File:** [Sales Analysis using Top N Filter PBIP](https://github.com/taarikakanauji/sales-analysis-using-topn-filter/blob/main/Sales%20Analysis%20using%20TopN%20Filter%20DAX.pbip)  
- **Gitignore:** [.gitignore](https://github.com/taarikakanauji/sales-analysis-using-topn-filter/blob/main/.gitignore)  

### **Project README (Setup Guide)**  
[README.md](https://github.com/taarikakanauji/sales-analysis-using-topn-filter/blob/main/README.md)  

# Conclusion

This Top N Sales Analysis Dashboard empowers stakeholders to::

- `Prioritize High-Value Customers` - Focus efforts on top-performing customers who contribute the majority of revenue, enhancing retention strategies and personalized engagement.

- `Maximize Product Profitability` - Identify best-selling products and align marketing or bundling strategies to capitalize on high-revenue items while phasing out underperformers.

- `Enhance Sales Targeting` - Use Top N and quarterly filters to analyze sales trends and performance across time, enabling timely adjustments in campaigns and outreach.

- `Drive Data-Backed Decision Making` - Access a centralized, interactive view of sales by customer, product, and period—supporting faster, evidence-based decisions across departments.

- `Improve Forecasting & Planning` - Running totals and time filters offer a clear view of revenue momentum, helping stakeholders set realistic targets and proactively manage resources.


By utilizing the insights from this dashboard, sales and marketing teams can strategically focus on top-revenue-generating customers and high-performing products, while also identifying and addressing underperforming segments with targeted, data-driven actions. The interactive filters—such as Top N selectors and quarterly views—allow users to seamlessly drill into specific metrics and reset views for flexible exploration. This intuitive experience supports quick, informed decisions and empowers stakeholders to monitor performance trends, refine sales strategies, and ultimately contribute to overall business growth.


