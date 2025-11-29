# Water-Quality-Analytics-Brisbane
This project analyzes real-world water-quality parameters (Temperature, pH, Conductivity, DO Oxygen, Salinity, Turbidity, etc.) and presents insights through a multi-page Power BI dashboard. The dashboard allows environmental analysts to explore trends, anomalies, seasonal patterns, parameter variance, and daily drill-downs for individual sample days.

**Key Features**

Total samples & readings KPIs
Avg / Min / Max / Std-Dev monitoring
Monthly & rolling 7-day trend detection
Parameter-aware filtering
Seasonality analysis by month
Variance from long-term historical average
Drill-through "sample insight" page for individual dates
Quality control checks that flag abnormal readings

**Data Model**

Fact-water-quality table
Date dimension
Parameter dimension
Star-schema with clean relational structure


**Tools & Technologies**

Power BI
Power Query
DAX
CSV sensor data


**Key DAX Measures**

Total Samples
Total Readings
Avg Value
Avg Value This Month



**Data Model**
<img width="753" height="473" alt="image" src="https://github.com/user-attachments/assets/f86ecf75-0f2f-4519-bcb9-51b49fb006d8" />


**1. Total Samples — 31K**
This counts unique RecordIDs.
Each RecordID = one water sampling event.
This number does not change when you use the slicer, because it shows total unique samples overall.

**2. Total Readings (Selected Parameter)  309K**
This does change when you select a parameter (Temperature, pH, etc.) from the slicer.
It tells you:
How many measurement rows exist for the selected parameter?
The number is higher than Total Samples because each sample contains multiple parameter readings.

**3. Avg Value — 41.56**
This is the average of Value for the selected parameter.
If you select:
Temperature → this becomes average temperature
pH → this becomes average pH
Turbidity → this becomes average turbidity
This is your main number to monitor parameter performance.

**4. Avg Value Last 7 Days — 45.21**
This shows the short-term trend.
Formula:
Average of the selected parameter over the most recent 7 days.
Useful for:
Detecting recent spikes or drops
Comparing with long-term trend

**5. Max Value — 359.99**
Highest recorded value for the selected parameter.

**6. Min Value — 0.00**
Lowest recorded value.
This can help flag anomalies (like 0 values that may be sensor errors).


**Insights**

Which parameters dominate on this day
Heavy-impact parameters
Outlier-high parameters
Possible sensor biases
Values are very large because your units (e.g., µS/cm, °C) differ.


































**Purpose**
To provide environmental agencies, local councils, and scientific analysts with a data-driven view of water-quality performance, supporting decisions around environmental monitoring and sustainability.
