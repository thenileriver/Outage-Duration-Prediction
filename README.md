## Power Outage Duration Prediction Project

### Prediction Problem and Type
- **Type:** Regression  
- **Response Variable:** Duration of Power Outage

### Project Objective
The aim is to predict the duration of power outages using a comprehensive dataset. Accurate predictions enable swift assessment and response to outages, improving strategies and minimizing impact.

### Dataset
We utilize historical outage data post-2012. The dataset includes key attributes retained after data cleaning:
- `NERC.REGION` (NERC Region)
- `CLIMATE.REGION` (Climate Region)
- `ANOMALY.LEVEL` (Anomaly Level)
- `CLIMATE.CATEGORY` (Climate Category)
- `CAUSE.CATEGORY` (Cause Category)
- `CUSTOMERS.AFFECTED` (Number of Customers Affected)
- `POPULATION` (Population)
- `U.S._STATE` (U.S. State)
- `CAUSE.CATEGORY.DETAIL` (Cause Category Detail)
- `PI.UTIL.OFUSA` (PI Utility of USA)
- `OUTAGE.DURATION` (Outage Duration)

### Model Evaluation Metric
- **Primary Metric:** Mean Absolute Error (MAE)  
MAE is selected due to its robustness against outliers present in the dataset with inconsistent trends.

### Data Preprocessing
Following procedures from our data cleaning, we converted the dataset from XLSX to CSV. We dropped irrelevant rows and columns, retaining only features correlated with `OUTAGE.DURATION`.
| OBS | MONTH | OUTAGE.START.TIME | ANOMALY.LEVEL | CLIMATE.CATEGORY | U.S._STATE | NERC.REGION | CLIMATE.REGION | CAUSE.CATEGORY | CAUSE.CATEGORY.DETAIL | POPULATION | POPPCT_URBAN | POPDEN_URBAN | POPDEN_UC | POPDEN_RURAL | AREAPCT_URBAN | AREAPCT_UC | RES.PRICE | COM.PRICE | IND.PRICE | TOTAL.PRICE | RES.SALES | COM.SALES | IND.SALES | TOTAL.SALES | PI.UTIL.OFUSA | HURRICANE.NAMES | OUTAGE.DURATION | CUSTOMERS.AFFECTED | OUTAGE.START.CATEGORY |
|-----|-------|-------------------|---------------|------------------|------------|-------------|----------------|---------------|-----------------------|------------|--------------|--------------|-----------|--------------|---------------|------------|-----------|-----------|-----------|-------------|-----------|-----------|-----------|-------------|---------------|-----------------|-----------------|--------------------|----------------------|
| 1.0 | 7.0   | 17:00:00          | -0.3          | normal           | Minnesota  | MRO         | East North Central | severe weather | NaN                   | 5348119.0  | 73.27        | 2279         | 1700.5    | 18.2         | 2.14         | 0.6        | 11.6      | 9.18      | 6.81       | 9.28       | 2332915   | 2114774   | 2113291   | 6562520     | 2.2           | NaN               | 3060            | 70000.0             | Afternoon/Evening    |
| 2.0 | 5.0   | 18:38:00          | -0.1          | normal           | Minnesota  | MRO         | East North Central | intentional attack | vandalism            | 5457125.0  | 73.27        | 2279         | 1700.5    | 18.2         | 2.14         | 0.6        | 12.12     | 9.71      | 6.49       | 9.28       | 1586986   | 1807756   | 1887927   | 5284231     | 2.2           | NaN               | 1                | NaN                 | Afternoon/Evening    |
| 3.0 | 10.0  | 20:00:00          | -1.5          | cold             | Minnesota  | MRO         | East North Central | severe weather | heavy wind            | 5310903.0  | 73.27        | 2279         | 1700.5    | 18.2         | 2.14         | 0.6        | 10.87     | 8.19      | 6.07       | 8.15       | 1467293   | 1801683   | 1951295   | 5222116     | 2.1           | NaN               | 3000            | 70000.0             | Afternoon/Evening    |
| ... | ...   | ...               | ...           | ...              | ...        | ...         | ...            | ...           | ...                   | ...        | ...          | ...          | ...       | ...          | ...           | ...        | ...       | ...       | ...        | ...        | ...       | ...       | ...       | ...         | ...           | ...               | ...            | ...                | ...                  |


