## Power Outage Duration Prediction Project

### Prediction Problem and Type
- **Type:** Regression  
- **Response Variable:** Duration of Power Outage

### Project Objective
The primary objective is to predict the duration of power outages using a comprehensive dataset. This prediction is crucial for enabling prompt and effective response strategies. By estimating outage durations more accurately, utility companies and emergency services can optimize their resource allocation and minimize the overall impact on affected areas.

### Dataset
Our analysis utilizes historical outage data collected since 2012. This dataset is rich in features that potentially influence outage durations. After thorough data cleaning, the following key attributes are retained for model training:
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
- **Rationale:** MAE is chosen as the primary evaluation metric for its direct interpretability and robustness against outliers. Unlike metrics like Mean Squared Error, MAE does not overly penalize large errors, which is beneficial in our dataset that exhibits a significant number of outliers and irregular patterns. This makes MAE a more reliable measure of central tendency in predicting outage durations, providing a more realistic assessment of model performance.


### Data Preprocessing
Following procedures from our data cleaning, we converted the dataset from XLSX to CSV. We dropped irrelevant rows and columns, retaining only features correlated with `OUTAGE.DURATION`.
| OBS | NERC.REGION | CLIMATE.REGION      | ANOMALY.LEVEL | CLIMATE.CATEGORY | CAUSE.CATEGORY     | CUSTOMERS.AFFECTED | POPULATION | U.S._STATE | CAUSE.CATEGORY.DETAIL | PI.UTIL.OFUSA | OUTAGE.DURATION |
|-----|-------------|---------------------|---------------|------------------|--------------------|--------------------|------------|------------|-----------------------|---------------|-----------------|
| 1.0 | MRO         | East North Central  | -0.3          | normal           | severe weather     | 70000.0            | 5348119.0  | Minnesota  | NaN                   | 2.2           | 3060            |
| 2.0 | MRO         | East North Central  | -0.1          | normal           | intentional attack | NaN                | 5457125.0  | Minnesota  | vandalism             | 2.2           | 1               |
| 3.0 | MRO         | East North Central  | -1.5          | cold             | severe weather     | 70000.0            | 5310903.0  | Minnesota  | heavy wind            | 2.1           | 3000            |
| 4.0 | MRO         | East North Central  | -0.1          | normal           | severe weather     | 68200.0            | 5380443.0  | Minnesota  | thunderstorm          | 2.2           | 2550            |
| 5.0 | MRO         | East North Central  | 1.2           | warm             | severe weather     | 250000.0           | 5489594.0  | Minnesota  | NaN                   | 2.2           | 1740            |
| ... | ...         | ...                 | ...           | ...              | ...                | ...                | ...        | ...        | ...                   | ...           | ...             |



