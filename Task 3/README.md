# Superstore Sales Analysis (2014–2017)

Exploratory data analysis of a retail sales dataset covering Category, Sub-Category, Region, and Customer Segment performance from 2014–2017. The goal was to identify what's driving profit vs. what's just driving revenue, and turn that into concrete business recommendations.

## Dataset Overview

| Metric | Value |
|---|---|
| Total Sales | $2,297,200 |
| Total Profit | $286,397 |
| Total Quantity Sold | 37,873 |
| Average Discount | 15% |
| Overall Profit Margin | ~12.5% |
| Time Period | 2014–2017 |

## Tools Used

- Python (Pandas, Matplotlib, Seaborn)
- Jupyter / Notebook environment

## Analysis Performed

- Sales & profit breakdown by Category and Sub-Category
- Top 10 / Bottom 10 products by Sales and Profit
- Sales & profit by Customer Segment and Region
- Yearly and monthly sales/profit trends
- Year-vs-month sales heatmap (seasonality)
- Discount vs. Profit relationship
- Profit margin by category
- Correlation matrix (Sales, Quantity, Discount, Profit)

## Key Insights

**1. Overall margin is thin relative to what's achievable.** The dataset converts $2.3M in sales into $286K profit (12.5% margin) — well below the ~17% margins that two of the three categories individually achieve.

**2. Furniture is the core profitability problem, not a sales problem.** Furniture sales ($742K) are nearly on par with Technology ($836K), but its profit is just $18.5K — a 2.5% margin vs. 17.4% (Technology) and 17.0% (Office Supplies). It sells almost as much as the top categories but earns almost nothing.

**3. Discounting is the mechanism behind the losses.** Discount correlates negatively with profit (-0.22). At 0% discount, profits cluster high and positive (up to $8,400). Past ~30–40% discount, profit turns predominantly negative, and at 70–80% discount, losses of -$4,000 to -$6,700 appear — concentrated in Technology and Furniture.

**4. Some high-revenue "hero" products are actually loss-makers.** The Cisco TelePresence EX90 and GBC DocuBind P400 both appear in the *Top 10 by Sales* **and** the *Bottom 10 by Profit* — high revenue is masking heavy discounting into the red. The Canon imageCLASS 2200 Copier, by contrast, tops both Sales and Profit lists.

**5. Furniture's losses trace back to one sub-category type.** 4 of the Bottom 10 profit products are conference/meeting tables. Chairs, meanwhile, is a top-2 sales sub-category overall — the fix is fixing Tables, not deprioritizing Furniture as a whole.

**6. Volume doesn't reliably drive profit.** Office Supplies has the highest quantity sold (22,906 units) but similar total profit to Technology (6,939 units). Quantity-Profit correlation is a weak 0.07 — margin per sale matters far more than units moved.

**7. Central region underperforms on efficiency.** Central's margin (~8%) trails West (~15%) and East (~13%) despite solid sales volume.

**8. Home Office is the most efficient segment.** Smallest by sales, but best margin (~14%) vs. Corporate (~13%) and Consumer (~11%).

**9. Growth is real, but margin compressed in the latest year.** Sales and profit both grew 2014→2017, but 2016→2017 sales growth (+20.5%) outpaced profit growth (+14%), nudging margin down from ~13.4% to ~12.7%.

**10. Strong, consistent seasonality.** November is the peak month by far (2017 hit $118K), with September and December also strong — a clear Q4 buying surge. February is consistently the weakest month across all four years.

## Recommendations

1. **Fix Furniture margins first** — audit cost/pricing on Tables and Bookcases specifically; Chairs is healthy and doesn't need intervention.
2. **Cap discounting** — require approval above ~30% discount, since profit turns negative broadly past that point; Technology deals need the tightest control.
3. **Re-price the "fake hero" SKUs** (Cisco TelePresence EX90, GBC DocuBind P400) — high sales are currently subsidizing losses.
4. **Double down on Technology and Office Supplies** — both run ~17% margins and deserve priority marketing/inventory investment.
5. **Investigate Central region's discount/cost practices** — its margin gap isn't explained by sales volume alone.
6. **Target Home Office for growth** — best margin of the three segments, with the most room to scale profitably.
7. **Plan inventory, staffing, and cash flow around the Sep–Nov–Dec surge**, and use the February trough for promotions or maintenance.
8. **Monitor the 2017 margin dip** to confirm whether it's a trend before it compounds.

## Visualizations

- Total Sales / Profit by Category
- Sales by Sub-Category
- Top & Bottom 10 Products by Sales / Profit
- Sales & Profit by Customer Segment
- Sales & Profit by Region
- Yearly & Monthly Sales/Profit Trends
- Sales Heatmap (Year vs. Month)
- Discount vs. Profit Scatter Plot
- Profit Margin by Category
- Correlation Matrix
