# Nova-Mart-Revenue-Profitability-Analysis-for-2014
Nova Mart’s 2014 Revenue &amp; Profitability Dashboard delivers clear, data-driven insights into sales trends, product margins, and regional performance. Built to turn complex financial data into actionable visual metrics, it highlights core profit drivers and operational costs to help optimize retail strategies and drive bottom-line growth.


<img width="1852" height="885" alt="Lesson 8 - Replicated Dashboard" src="https://github.com/user-attachments/assets/fb27d28c-532d-411e-999f-d3fae8a8b6cf" />

1. Outline
1.	Introduction
2.	Story of Data
3.	Data Splitting and Preprocessing
4.	Pre-Analysis
5.	In-Analysis
6.	Post-Analysis and Insights
7.	Data Visualizations & Charts
8.	Recommendations and Observations
9.	Conclusion
10.	References & Appendices
 
2. Introduction
Objective of the Project
The objective of this project is to analyze one full fiscal year (January–December 2014) of sales and distribution transactions for Nova Mart., a Fast-Moving Consumer Goods (FMCG) distributor, in order to uncover performance trends across regions, states, cities, sales representatives, product categories, and customers. The analysis is designed to translate raw transactional data into a consolidated, interactive Excel dashboard and a set of actionable recommendations that management can use to guide strategic decisions for the coming year, including resource allocation, sales coaching, regional expansion, and inventory planning.
Problem Being Addressed
Prior to this analysis, sales performance data existed only as a flat, transaction-level export with 369 individual order records and 26 fields per record. In this raw form, the data could not answer basic strategic questions — which regions, salespeople, products, and customers drive the majority of revenue, how sales fluctuate through the year, and where the business is over-exposed to a small number of high-performing accounts or individuals. The analysis therefore aims to answer: Where is revenue concentrated, where is it lagging, and what specific actions should management take to grow underperforming segments while protecting the segments the business currently depends on?

Key Datasets and Methodologies
A single dataset was used: a 2014 order-level sales transaction log ("Data" sheet) containing 369 rows and 26 columns, covering order and shipping details, customer and salesperson identity, geography, product/category, pricing, quantity, revenue, and shipping fees. The analysis was carried out entirely in Microsoft Excel using the following methodologies:
●	PivotTables — to aggregate revenue by region, state, city, salesperson, customer, product category, and month.
●	PivotCharts — bar charts, pie charts, radar/web charts, line charts, and a treemap to visualize the pivoted summaries.
●	Calculated groupings/bins — to bucket transactions by revenue-amount ranges (e.g., 10–1010, 1010–2010) for a distribution analysis.
●	A consolidated interactive dashboard — combining the individual PivotCharts, KPI cards, and slicers into a single management-facing view.
●	Narrative insight boards — structured pre-analysis, in-analysis, post-analysis, and recommendations write-ups documenting the reasoning behind each visualization.
 
3. Story of Data
Data Source
The dataset is a company-internal sales and distribution transaction log for Nova Mart., covering the 2014 calendar year. It captures order-level detail generated through the company's order processing and shipping workflow rather than survey or third-party market data.
Data Collection Process
Each row of the dataset represents a single order transaction, automatically generated at the point of sale/shipment and recorded with its associated order date, shipped date, customer, salesperson, product, and financial details. The data was extracted from the internal sales/order system as a structured export and consolidated into a single "Data" worksheet for analysis in Excel.

Data Structure
The dataset is organized with each row representing one order-line transaction and each column representing a distinct variable. It spans 369 transaction rows and 26 columns, including:
●	Order details: Order ID, Order Date, Shipped Date, Shipper Name
●	Customer details: Customer ID, Customer Name, Address, City, State, ZIP/Postal Code, Country/Region
●	Sales details: Salesperson, Region
●	Shipping details: Ship Name, Ship Address, Ship City, Ship State, Ship ZIP/Postal Code, Ship Country/Region, Payment Type
●	Product details: Product Name, Category, Unit Price, Quantity
●	Financial outcomes: Revenue, Shipping Fee
Important Features and Their Significance

●	Revenue: the core performance metric used throughout the analysis — the sum of Revenue underpins every regional, product, state, city, and salesperson comparison in the report.
●	Region / State / City / Ship City: the geographic dimensions used to identify where the business is strong (e.g., the North region, New York) and where it is underdeveloped (e.g., the South and West regions).
●	Salesperson: identifies the individual driving each transaction, enabling analysis of sales-force concentration risk (e.g., Nancy Freehafer and Anne Larsen jointly generating roughly 45.5% of total revenue).
●	Product Name / Category: enables product-mix analysis, showing that Beverages and Sauces are the two dominant categories.
●	Order Date: used to build the monthly Sales Trend, revealing the business's seasonal boom-and-bust pattern.
●	Customer Name: used to identify high-value, high-dependency accounts such as Company D.

Data Limitations or Biases
●	Single fiscal year (2014): the dataset covers only one calendar year, so year-over-year growth trends and multi-year seasonality cannot be confirmed from this data alone.
●	Limited geographic footprint: revenue is recorded for only 12 states and a small cluster of cities; large parts of the U.S. (e.g., the Northeast beyond New York) show no recorded activity, which may reflect either a genuine coverage gap or incomplete data capture.
●	Small salesperson roster: only eight salespeople appear in the data, so per-rep averages are sensitive to the performance of any single individual.
●	Transaction volume skew: the transaction-amount distribution is heavily right-skewed (221 of 369 transactions fall in the smallest $10–$1,010 bucket), which can compress the visual scale of pivot charts and make high-value outliers harder to read.
●	No cost/margin data: the dataset provides Revenue and Shipping Fee but not cost of goods sold, so profitability (as opposed to top-line revenue) could not be assessed.
 
4. Data Splitting and Preprocessing
Data Cleaning
The 369-row transaction export was reviewed for duplicate Order IDs, blank critical fields (Revenue, Region, Product Name), and inconsistent text values (e.g., city/state naming) prior to building PivotTables. The data was confirmed to be a clean, ready-to-aggregate transaction log with one row per order line.
Handling Missing Values
No material gaps were found in the core fields used for aggregation (Revenue, Region, Salesperson, Product/Category, Order Date). Where a field was not required for a given analysis (e.g., ZIP/Postal Code is uniformly recorded as a placeholder), it was simply excluded from the relevant PivotTable rather than imputed, since it had no bearing on the revenue-based metrics being reported.

Data Transformations
The Order Date field was grouped by month (Jan–Dec) to build the Sales Trend report. Revenue values were also bucketed into fixed ranges (10–1010, 1010–2010, 2010–3010, 3010–4010, 4010–5010, 6010–7010, 7010–8010) to produce the Transactions by Amount distribution. All other summaries (by Region, Salesperson, Customer, Product Category, State, and City) were produced directly through PivotTable grouping of the existing categorical fields with Sum of Revenue as the value field.
Data Splitting
Consistent with standard analytical practice, the dataset's fields were split conceptually into Independent Values (the inputs, drivers, or descriptive characteristics) and Dependent Values (the outcomes being measured):
Independent Values (drivers/inputs): Customer Name, Salesperson, Region, City, Ship Name, Product Name, Category, Ship City, Ship Name, Payment Type.
Dependent Values (outcomes/results): Revenue, Unit Price, Quantity, Shipping Fee, Order Date, Order ID, Customer.
For example, Revenue (dependent) is consistently analyzed as a function of independent drivers such as Product Name or Region — i.e., "how much revenue did each region/product/salesperson generate," rather than the reverse.

Industry Context
The dataset belongs to the Fast-Moving Consumer Goods (FMCG) industry — specifically a food and beverage distribution business (product categories include Beverages, Sauces, Jams & Preserves, Dairy Products, Dried Fruit & Nuts, and Canned Meat), sold and shipped to business customers across multiple U.S. states.
Stakeholders
●	The Chief Sales and Distribution Officer (CSDO) and other C-level executives
●	The Sales and Commercial Director
●	Regional Sales Managers
●	Individual Sales Managers and Representatives

Value to the Industry
In the FMCG distribution industry, success is largely defined by generating more revenue and expanding sales coverage to increase market share. This analysis directly supports both goals: it identifies exactly which regions, products, cities, and salespeople are already driving revenue (so the company can defend and reinforce them) and which segments are underdeveloped (so leadership can target expansion, coaching, and marketing investment where it will close the gap fastest).
 
5. Pre-Analysis
Identify Key Trends
●	The North region alone accounts for approximately 32.6% of total revenue ($141,680.34), indicating a high dependency on a single geographic area.
●	North and East together generate $249,955.85 — roughly 57% of total sales — while South and West contribute the remaining 43%, revealing a two-tier regional maturity split.
●	South ($93,858.33) and West ($91,251.98) sit within $2,606.35 of each other, effectively operating at the same scale.
●	Nancy Freehafer alone accounts for nearly 24% of total sales revenue across the eight-person sales team, creating significant key-person risk.
●	Company D is a clear outlier customer, generating $67,180.50 — more than triple the revenue of the 10th-ranked customer, Company K ($21,937.08).
●	The business shows a volatile, "boom and bust" seasonal pattern rather than a steady monthly revenue stream — the gap between the June peak ($55,601.61) and the following July trough ($27,318.54) exceeds 50%.
●	Beverages ($110,577.11) generates more revenue on its own than the bottom three categories combined (Dairy, Dried Fruit & Nuts, and Canned Meat total $86,594.70).
●	The 10–1010 transaction-value bucket alone accounts for 221 of 369 transactions (roughly 60%), showing the business runs on a high-frequency, lower-value transactional model.

Potential Correlations
●	Salesperson performance appears correlated with regional assignment: Anne Larsen's total sales ($93,858.33) match the South region's total revenue exactly to the cent, suggesting she is the primary — possibly sole — representative driving that territory.
●	Sales spikes are consistently followed by steep drop-offs the following month (June → July, October → November), suggesting a cyclical pipeline-exhaustion pattern where closing a high-volume month depletes the pipeline for the next.
●	Revenue concentration by geography mirrors revenue concentration by salesperson and by customer — in each dimension (region, rep, customer, product) a small top tier drives a disproportionate share of total revenue.
Initial Insights
Before deeper statistical slicing, several promising and question-raising patterns emerge: the business's overall revenue baseline of $435,066.16 is heavily reliant on a concentrated set of drivers — one region (North), two salespeople (Nancy and Anne), one customer (Company D), and two product categories (Beverages and Sauces). This concentration is a double-edged sign: it shows the company knows how to win in these segments, but it also exposes real risk if any one of these pillars weakens. The year-end trend (an all-time-high December) is a positive signal that growth initiatives implemented earlier in the year may be compounding effectively.
 
6. In-Analysis
Unconfirmed Insights
Sales by Region: Reading the pie chart clockwise from the top (darkest green), revenue breaks down as North $141,680.34 (32.6%), East $108,275.51 (24.9%), South $93,858.33 (21.6%), and West $91,251.98 (21.0%). North is the clear powerhouse, outperforming the lowest region (West) by over $50,000, while South and West are effectively tied.
Sales by Salesperson: Nancy Freehafer ($104,252.34) and Anne Larsen ($93,858.33) together generate $198,110.67 — about 45.5% of total team revenue. Nancy alone outsells the bottom three reps combined (Michael, Robert, and Jan total $86,309.10) and brings in over six times Jan Kotas's revenue ($16,350.50). Mariya, Laura, and Michael cluster tightly in the $37k–$42k range as "baseline steady performers."

Top 10 Customers: Company D leads by a significant margin ($67,180.50), with Company D, Company H, and Company BB together forming the top bracket. Revenue declines gradually and evenly from Company F ($37,428.00) down through Company K ($21,937.08).
Sales Trend: December is the annual peak ($66,642.78) and June a strong mid-year peak ($55,601.61); February is the low point of the year ($19,985.50), closely followed by April ($20,771.79). Each major peak is followed by a sharp one-month decline, consistent with a pipeline-exhaustion cycle.
Product Category Performance: Beverages ($110,577.11) is the clear leader on the treemap, with Sauces ($69,000.00) as a strong secondary category — together they total $179,577.11. Jams, Preserves ($51,541.00) forms a healthy mid-tier bridge, while Dairy Products, Dried Fruit & Nuts, and Canned Meat sit tightly clustered at the bottom of the mix ($25.5k–$33.1k each).
States' Performance: New York ($67,180.50) is the top-performing state by a wide margin. Oregon ($50,208.35) and Washington ($36,839.99) anchor a strong Pacific Northwest presence, while Nevada, Colorado, and Idaho sit at the bottom of the active revenue range (roughly $15k–$17k).
Cities' Performance by Revenue: New York leads all cities ($67,180.50), roughly 34% ahead of second-place Portland ($50,208.35). Portland and Miami ($50,145.33) are separated by only $63.02, forming a near-identical secondary tier, with Memphis ($43,713.00) and Chicago ($41,095.01) close behind.
Top 6 Ship Cities by Revenue: On the radar chart, New York sits furthest from the center ($67,180.50), while Portland and Miami form a symmetrical pair on opposite coasts. Chicago and Milwaukee, though smaller individually, combine for $78,523.01 as a dense Midwestern pocket; Milwaukee ($37,428.00) marks the minimum threshold to enter this "top 6" tier.
Transactions by Amount: The 10–1010 bucket dominates with 221 transactions, followed by a rapid step-down to 82 (1010–2010) and 32 (2010–3010). Transactions above $6,010 are rare (2 and 1 transactions respectively), and the 5010–6010 bucket is empty entirely — a clear gap in the transaction-value distribution.

Recommendations
Based on these preliminary patterns, early-stage recommendations include: (1) study what drove the North region's and Nancy/Anne's outsized results and test whether those tactics can be transferred to the South, West, and lower-performing reps; (2) investigate the drivers behind the June and October peaks so similar promotional or sales-incentive tactics can be timed intentionally rather than occurring incidentally; and (3) evaluate cross-sell opportunities that pair the high-traffic Beverages/Sauces categories with the lower-performing Dairy, Dried Fruit & Nuts, and Canned Meat lines.

Analysis Techniques Used in Excel
●	PivotTables — used to aggregate Sum of Revenue by Region, Salesperson, Customer, Product Category, State, City, and Month, and to build a Count of Revenue distribution by transaction-amount bucket.
●	PivotCharts — bar charts (Sales by Salesperson, Cities' Performance), pie chart (Sales by Region), line chart (Sales Trend), radar/web chart (Top 6 Ship Cities), and treemap (Product Category Performance).
●	Grouping/Binning — Order Date grouped into months; Revenue grouped into fixed-width value ranges for the transaction distribution.
●	Slicers — used on the interactive dashboard to allow stakeholders to filter the consolidated view dynamically.
●	KPI/summary cards — built alongside the PivotCharts to surface headline metrics (Top Performing Month, Customer of the Year, Best Region by Revenue, Top Grossing State, Product of the Year) at a glance.
 
7. Post-Analysis and Insights
Key Findings
Key Performance Indicators (KPI Summary):
●	Top Performing Month: December, with total revenue of $66,642.78.
●	Customer of the Year: Company D, contributing $67,180.50.
●	Best Region by Revenue: North Region, generating $141,680.34.
●	Top Grossing State: New York, with total revenue of $67,180.50.
●	Product of the Year: Beverages, dominating sales at $110,577.11.

Salesperson Performance: Nancy Freehafer leads the team with $104,252.34, closely followed by Anne Larsen ($93,858.33). Andrew Cencini ($67,180.50), Mariya Sergienko ($42,370.88), and Laura Giussani ($41,095.01) form a stable mid-tier core, while Jan Kotas ranks lowest at $16,350.50.
Regional & Geographic Performance: The North ($141,680.34) and East ($108,275.51) regions drive the bulk of company sales, while the South ($93,858.33) and West ($91,251.98) represent clear growth opportunities. The top performing cities are New York ($67,180.50), Portland ($50,208.35), Miami ($50,145.33), Memphis ($43,713.00), Chicago ($41,095.01), and Milwaukee ($37,428.00).
Sales Trend (Seasonality): The business shows a volatile but generally upward trajectory across the year. Mid-year spikes occur in June ($55,601.61), followed by a steady autumn climb to an absolute maximum in December ($66,642.78). Troughs appear in February ($19,985.50) and April ($20,771.79), consistent with a post-holiday drop-off and spring slump.
Product Category Performance: Beverages ($110,577.11) remains the definitive primary revenue driver. Sauces ($69,000.00) and Jams, Preserves ($51,541.00) form strong secondary categories, while Dairy Products ($33,129.60), Dried Fruit & Nuts ($27,999.50), and Canned Meat ($25,465.60) round out the bottom of the portfolio.

Comparison with Initial Findings
The post-analysis results largely confirm the pre-analysis and in-analysis hypotheses: revenue concentration in the North region, in two lead salespeople, in Company D, and in the Beverages/Sauces categories persisted through the deeper analysis rather than being an artifact of an incomplete first look. The seasonal boom-and-bust pattern identified early on (June and October peaks followed by sharp declines) was also validated at the KPI level, confirming that December is the strongest month of the year by a wide margin. No major counter-intuitive surprises emerged; the initial hypotheses about concentration risk and seasonal volatility were consistently reinforced as the analysis moved from a first pass into full PivotTable/PivotChart detail, giving management confidence that the recommendations that follow are grounded in a consistent, well-supported pattern rather than a single-view coincidence.
 
8. Data Visualizations & Charts
Charts and Graphs
The following PivotChart types were built in Excel to visualize the aggregated PivotTable summaries:
●	Bar chart — Sales by Salesperson (Nancy Freehafer to Jan Kotas, ranked descending)
●	Pie chart — Sales by Region (North, East, South, West)
●	Line chart — Sales Trend (monthly revenue, Jan–Dec, with trendline)
●	Radar / web chart — Top 6 Ship Cities by Revenue
●	Horizontal bar chart — Cities' Performance by Revenue (Top 5 cities)
●	Treemap — Product Category Performance
●	Column chart — Transactions by Amount (distribution by revenue-value bucket)

Dashboard
The individual PivotCharts above were consolidated into a single interactive management dashboard (shown below), giving stakeholders a one-glance view of overall sales performance, complete with slicers for on-demand filtering.
 
Figure 1. Consolidated Sales Performance Dashboard — Nova Mart., FY2014
Explanation of Visualizations
●	Sales by Salesperson (bar chart): shows a steep, descending ranking from Nancy Freehafer ($104,252.34) down to Jan Kotas ($16,350.50) — the reader should take away that sales performance is heavily top-weighted across the eight-person team.
●	Sales by Region (pie chart): the North slice is visibly the largest at 32.6% of total revenue, with East as a clear second and South/West forming a near-equal remainder — the reader should take away that two of four regions (South, West) are under-indexed relative to North and East.
●	Sales Trend (line chart): the jagged, saw-tooth shape with a rising trendline shows a volatile month-to-month pattern (June and October peaks, February and July troughs) that nonetheless ends the year at its highest point in December.
●	Top 6 Ship Cities (radar chart): New York's point extends furthest from the center, visually confirming its outsized contribution, while Portland and Miami form a near-mirror-image pair on the chart.
●	Cities' Performance by Revenue (bar chart): confirms New York's lead over Portland, Miami, Memphis, and Chicago, with a clear step-down in revenue moving down the ranking.
●	Product Category treemap: the Beverages box visually dwarfs all other categories, while Dairy Products, Dried Fruit & Nuts, and Canned Meat appear as similarly-sized, smaller boxes — the reader should take away that the product portfolio is currently a two-category business (Beverages, Sauces) with room to grow the smaller categories.
●	Transactions by Amount (column chart): one bar (the $10–$1,010 bucket) towers over the rest, showing that the overwhelming majority of orders are lower-value, high-frequency transactions rather than large one-off deals.
 
9. Recommendations and Observations
1. Product Optimization & Inventory Management
Recommendation: Prioritize supply chain allocation and aggressive marketing for the Beverages and Sauces categories, while reviewing cross-merchandising strategies for lower-performing lines like Canned Meat and Dried Fruit & Nuts.
Reason: Beverages is the clear "Product of the Year," generating $110,577.11 — nearly double the third-highest category, Jams & Preserves ($51.5k). Sauces is a strong secondary pillar at $69,000.00. Canned Meat ($25,465.60) and Dried Fruit & Nuts ($27,999.50) lag significantly behind, dragging down overall inventory turnover.

2. Regional Expansion & Localized Marketing
Recommendation: Replicate the operational and promotional playbooks used in the North region and New York across the lower-performing West and South regions and establish regional hubs or targeted distribution campaigns in high-performing coastal logistics hubs like Portland and Miami.
Reason: The North is the dominant region, driving $141,680.34 in revenue, with New York alone contributing $67,180.50 (the top-grossing state and shipping city). A stark disparity exists between the North/East and the West ($91,251.98) and South ($93,858.33) regions; capitalizing on secondary star cities like Portland ($50.2k) and Miami ($50.1k) can help bridge this regional gap.

3. Sales Force Empowerment & Knowledge Sharing
Recommendation: Implement a peer-mentorship or sales coaching program where top-tier performers anchor training sessions for lower-performing reps, and review resource allocation or account assignments for lagging territories.
Reason: There is a heavy reliance on the top two individual contributors — Nancy Freehafer ($104,252.34) and Anne Larsen ($93,858.33) collectively generate a massive share of total revenue, while the bottom three salespersons (including Jan Kotas at $16,350.50) combined do not match the output of a single top performer, indicating an uneven distribution of sales skills, leads, or territorial potential.

4. Demand Forecasting & Seasonal Capital Shifts
Recommendation: Align cash flow, marketing spend, and inventory stocking cycles to a dual-peak seasonal calendar — implement aggressive mid-year promotions in May to boost the June spike, and prepare major logistics pipelines starting in October to handle the Q4 surge.
Reason: The Sales Trend chart reveals distinct seasonal patterns: a sharp dip in February ($19,985.50), a climb to a mid-year peak in June ($55,601.61), a post-summer slump in July ($27,318.54), and an aggressive, continuous climb to the annual peak in December ($66,642.78). Understanding these cyclical dips and peaks prevents stockouts during high-demand months and minimizes holding costs during dry spells.

Optimizations or Business Decisions
Taken together, these recommendations point to three business-level decisions for the coming year: (1) rebalance sales-territory and account assignments so revenue generation is less concentrated in two individuals; (2) fund a deliberate regional-expansion initiative for the South and West rather than treating them as steady-state markets; and (3) build a formal seasonal operating calendar (procurement, staffing, and marketing spend) around the now-confirmed June and Q4 demand peaks.

Unexpected Outcomes
Two findings stood out as more striking than initially expected. First, Anne Larsen's individual sales total ($93,858.33) matched the entire South region's revenue to the cent — a level of exact correspondence that suggests she may be effectively the sole representative covering that territory, which is a concentration risk not immediately obvious from the regional chart alone. Second, Portland and Miami's revenue figures ($50,208.35 vs. $50,145.33, a gap of only $63.02) were nearly identical despite the two cities having entirely different regional economies and climates — an outcome worth investigating further rather than dismissing as coincidence.
 
10. Conclusion
Key Learnings
●	Nova Mart. generated $435,066.16 in total revenue across 369 transactions in FY2014, with performance heavily concentrated in the North region, two lead salespeople (Nancy Freehafer and Anne Larsen), one standout customer (Company D), and two product categories (Beverages and Sauces).
●	The business follows a volatile, seasonal revenue pattern rather than a steady month-to-month trend, with a mid-year peak in June and an annual peak in December, each preceded by a sharp trough.
●	Geographic performance is led by New York, with Portland and Miami forming a closely matched secondary tier — while large parts of the country remain unrepresented in the current customer base.
●	The transaction base is high-frequency and lower-value, with roughly 60% of all orders falling under $1,010, indicating a volume-driven rather than large-deal-driven sales model.

Limitations
●	The analysis is based on a single fiscal year (2014); trends described as "seasonal" or "growth" reflect one year's pattern and have not been confirmed against multiple years of data.
●	Coverage gaps exist in the underlying dataset — only 12 states and a small set of cities are represented, and no cost or margin data was available, limiting the analysis to top-line revenue rather than profitability.
●	Findings tied to individual salespeople or customers (e.g., Anne Larsen / South region, Company D) are based on a small sample (8 salespeople, a limited customer list) and should be validated against a larger dataset before being used for major workforce or account-management decisions.

Future Research
●	Incorporate multiple fiscal years of data to confirm whether the identified seasonal pattern (June and December peaks) is a recurring trend or specific to 2014.
●	Layer in cost-of-goods and margin data to shift the analysis from revenue concentration to profitability concentration.
●	Expand the geographic dataset to test whether the North/New York success pattern can be statistically linked to specific marketing, staffing, or logistics investments that could be replicated in the South and West.
●	Build a rolling/updated version of the dashboard (rather than a single static FY2014 snapshot) so management can track whether the recommended actions (coaching, regional expansion, seasonal planning) are actually shifting the underlying metrics over time.
 
11. References & Appendices
References
●	Primary data source: Nova Mart. FY2014 internal sales and distribution transaction log ("Data" worksheet), 369 order records across 26 fields, provided for this analysis.
●	Analysis and reporting tool: Microsoft Excel — PivotTables, PivotCharts, slicers, and dashboard/report layout.

