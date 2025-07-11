# **Business Problem**

Effective inventory and sales management are critical for optimizing profitability in the retail and wholesale industry. Companies need to ensure that they are not incurring losses due to inefficient pricing, poor inventory turnover, or vendor dependency. The goal of this analysis is to:

- Identify underperforming brands that require promotional or pricing adjustments.
- Determine top vendors contributing to sales and gross profit.
- Analyze the impact of bulk purchasing on unit costs.
- Assess inventory turnover to reduce holding costs and improve efficiency.
Investigate the profitability variance between high-performing and low-performing vendors.

# **Exploratory Data Analysis Insights**

## Summary Statistics

![Statistics](/images/statistics.png)

![Statistics_1](/images/output.png)

**Negative & Zero Values**:

Gross Profit: Minimum value is -52,002.78, indicating losses. Some products or transactions may be selling at a loss due to high costs or selling at discounts lower than the purchase price.
- Profit Margin: Has a minimum of -∞, which suggests cases where revenue is zero or even lower than costs.
- Total Sales Quantity & Sales Dollars: Minimum values are 0, meaning some products were purchased but never sold. These could be slow-moving or obsolete stock.

**Outliers Indicated by High Standard Deviations**:
- Purchase & Actual Prices: The max values (5,681.81 & 7,499.99) are significantly higher than the mean (24.39 & 35.64), indicating potential premium products.
- Freight Cost: Huge variation, from 0.09 to 257,032.07, suggests logistics inefficiencies or bulk shipments.
- Stock Turnover: Ranges from 0 to 274.5, implying some products sell extremely fast while others remain in stock indefinitely. Value more than 1 indicates that Sold quantity for that product is higher than purchased quantity due to either sales are being fulfilled from older stock.

## **Data Filtering**

To enhance the reliability of the insights, we removed inconsistent data points where:
- Gross Profit ≤ 0 (to exclude transactions leading to losses).
- Profit Margin 0 (to ensure analysis focuses on profitable transactions).
- Total Sales Quantity = 0 (to eliminate inventory that was never sold).

## **Correlation Insights**

![Heatmap](/images/output_1.png)

**Purchase Price vs. Total Sales Dollars & Gross Profit**: Weak correlation (-0.012 and -0.016), indicating that price variations do not significantly impact sales revenue or profit.

**Total Purchase Quantity vs. Total Sales Quantity**: Strong correlation (0.999), confirming efficient inventory turnover.

**Profit Margin vs. Total Sales Price**: Negative correlation (-0.179), suggesting increasing sales prices may lead to reduced margins, possibly due to competitive pricing pressures.

**Stock Turnover vs. Gross Profit & Profit Margin**: Weak negative correlation (-0.038 & -0.055), indicating that faster stock turnover does not necessarily equate to higher profitability.

## **Research Questions & Key Findings**

**1. Brands or Promotional or Pricing Adjustments**

![Brands with Low sales but High Profit Margins](/images/Brand_performance.png)

106 brands exhibit lower sales but higher profit margins, which could benefit from targeted marketing, promotions, or price optimizations to increase volume without compromising profitability.

![ScatterPlot](/images/output_2.png)

**2. Top Vendors by Sales & Purchasing Contribution**

The top 10 vendors contribute 58.69% of total purchases, while the remaining vendors contribute only 41.31%. This over-reliance on a few vendors may introduce risks such as supply chain disruptions, indicating a need for diversification.

![Pie_chart](/images/output_3.png)

**3. Impact of Bulk Purchasing on Cost Savings**


Vendors buying in large quantities receive a 72% lower unit cost ($10.78 per unit vs. higher unit costs in smaller orders).

Bulk pricing strategies encourage larger orders, increasing total sales while maintaining profitability.

![UnitPurchase](/images/Screenshot%202025-07-11%20201801.png)

**4. Identifying Vendors with Low Inventory Turnover**

Total Unsold Inventory Capital: $4.03M

Slow-moving inventory increases storage costs, reduces cash flow efficiency, and affects overall profitability.

Identifying vendors with low inventory turnover enables better stock management, minimizing financial strain.

![StockTurnover](/images/Stockturnover.png)
![UnsoldInventoryValue](/images/Unsoldinventory.png)

**5. Profit Margin Comparison: High vs Low-Performing Vendors**

- The confidence interval for low-performing vendors (33.06% to 36.45%) is significantly higher than that of top-performing vendors (8.95% to 10.29%). 
- This suggests that vendors with lower sales tend to maintain higher profit margins, potentially due to premium pricing or lower operational costs.
- For High-Performing Vendors: If they aim to improve profitability, they could explore selective price adjustments, cost optimization, or bundling strategies. 
- For Low-Performing Vendors: Despite higher margins, their low sales volume might indicate a need for better marketing, competitive pricing, or improved distribution strategies.

![Bar_Graph](/images/output_4.png)


**6. Statistical Validation of Profit Margin Differences Hypothesis Testing**:

**Ho (Null Hypothesis)**: No significant difference in profit margins between top and low-performing vendors.

**H1 (Alternative Hypothesis)**: A significant difference exists in profit margins between the two vendor groups.

**Result**: The null hypothesis is rejected, confirming that the two groups operate under distinctly different profitability models.

**Implication**: High-margin vendors may benefit from better pricing strategies, while top-selling vendors could focus on cost efficiency.

## **Final Recommendations**

- Re-evaluate pricing for low-sales, high margin brands to boost sales volume without sacrificing profitability.

- Diversify vendor partnerships to reduce dependency on a few suppliers and mitigate supply chain risks.

- Leverage bulk purchasing advantages to maintain competitive pricing while optimizing inventory management.

- Optimize slow-moving inventory by adjusting purchase quantities, launching clearance sales, or revising storage strategies.

- Enhance marketing and distribution strategies for low-performing vendors to drive higher sales volumes without compromising profit margins.

- By implementing these recommendations, the company can achieve sustainable profitability, mitigate risks, and enhance overall operational efficiency.