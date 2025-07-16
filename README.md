# Strategic-Supplier-Evaluation-Cost--Quality-Metric-using-Excel

## Project Review 

Our Client faces a 40% cost variance across its Asian suppliers, with suspected quality inconsistencies.  Exposes True Value: Pinpoint suppliers offering the optimal 
balance of cost efficiency and quality.
Drives Strategic Decisions: Allocate orders, negotiate terms, and mitigate risks based on data—not guesswork


<img width="1319" height="523" alt="Week 3 Screenshot (102)" src="https://github.com/user-attachments/assets/2e8ff50e-18e8-4336-94cf-8c4095661d61" />

### Data Source

Material_Taxonomy, Quality_matric, Suplier_Cost

### Tools

- Power Query for ETL
- Excel formulas for KPI design (no LAMBDA required)
- Scatter plot and quadrant chart for strategic insights

  
### Data Cleaning/Preparation

Clean and unify multi-source data using Power Query

### Exploratory Data Analysis

EDA involved exploring data to answer key questions:

1. Why do costs vary 40%?
2. Who delivers consistent quality at fair prices?

### Data Analysis 

Include some DAX formula:
```DAX
 Cost_Volume = [Cost/Unit (USD)] * [Volume (kg)]
 Weighted_Cost = SUM(Cost_Volume) / SUM(Volume)
 Delivery_Timeliness_Idex = Number.RoundDown]ist.Max({0,List.Min({ 1, 1 - ([Delivery Time (days)] - 7)/30})}),2)
 True_Quality_Store = =((1 - ([@[Defect Rate (%)]] / 100)) * ([@[Compliance Score]] / 100) * 0.7 + MAX(0, MIN(1, 1 - (([@[Delivery Time (days)]] - 7) / 30))) * 0.3 ) * 100
 Normalized Anomalist = =([@[Cost/Unit (USD)]] - MinCost)/(MaxCost-MinCost)
 Normalist Quality =  =([@[True_Quality_Score]]-MinQuality)/(MaxQuality-MinQuality)
 Supply_Quandrant = Best Value: 
 Cost_Score ≤ 40ANDQuality_Score ≥ 70
 Cost Optimize: Cost_Score ≤ 40ANDQuality_Score < 70
 Cost Risk:  
 Cost_Score > 40ANDQuality_Score ≥ 70
 Re-evaluate: 
 Cost_Score > 40ANDQuality_Score < 70
```
### Result/Findings 

 1. Best Value (Top-Left)
 Cost Score:≤ 40 (cheap!)
 Quality Score: ≥ 70 (great quality!)
 Action: "Best suppliers! Give them more orders and sign 
 long-term contracts."

 2. Cost Risk (Top-Right)←VN-SUP-001 is HERE!
 Cost Score:> 40 (expensive!)
 Quality Score: ≥ 70 (great quality!)
 Action: "Overpriced Suppliers! Negotiate hard for 
 discounts—or find cheaper alternatives with similar 
 quality."

 3. Cost Optimize (Bottom-Left)
 Cost Score:≤ 40 (cheap!)
 Quality Score: < 70 (needs improvement)
 Action:
 "Diamonds in the rough! Help them improve quality 
 through training or joint investments."

 4. Re-evaluate (Bottom-Right)
 Cost Score:> 40 (expensive!)
 Quality Score: < 70 (poor quality)
 Action:
 "Danger zone! Fire them or use only for non-critical 
 orders.



