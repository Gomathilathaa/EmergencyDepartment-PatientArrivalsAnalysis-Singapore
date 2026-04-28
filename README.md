# Emergency Department Patient Arrivals Analysis (Singapore)

## Project Overview

Efficient hospital operations depend heavily on understanding patient arrival patterns. Overstaffing increases operational costs, while understaffing leads to long waiting times and potential risks to patient care.
This project analyzes emergency department (ED) patient arrival data from major public hospitals in Singapore to uncover:

- Arrival trends by time, day, and hospital
- Differences in waiting time distributions
- Insights to support data-driven staffing decisions
  
## Objectives
- Analyze whether male patients prefer specific hospitals

- Compare waiting time distributions across hospitals

- Identify hourly patient arrival patterns

- Evaluate weekday vs weekend effects on patient inflow

- Provide insights for optimal staffing and resource allocation

## Dataset
- Source: Simulated dataset (EDdata_new.csv)

- Time Period:

October 2011 - April 2012

- Hospitals included:

Tan Tock Seng Hospital,
Singapore General Hospital,
National University Hospital,
Changi General Hospital,
Alexandra Hospital,
Khoo Teck Puat Hospita,
KK Women’s and Children’s Hospital. 

## Tools & Technologies
Python,
Pandas,
NumPy,
Jupyter Notebook.

## Key Analysis & Methodology

**Hospital Preference Analysis (Male Patients)**

Filtered dataset:
Gender = Male
Excluded KKH 

Computed:
Distribution of visits across hospitals

👉 Goal: Identify whether patient load is evenly distributed or skewed

**Waiting Time Analysis**

Calculated waiting time using:
Registration time (reg_sec)
Triage time (triage_sec)
Handled edge cases:
Cross-midnight scenarios

Metrics computed:

Mean,
Median,
Q1 (25th percentile),
Q3 (75th percentile),
99th percentile.

👉 Goal: Compare efficiency across hospitals

**Feature Engineering**

Created new columns:

REGIS_HOUR → Hour of arrival,
REGIS_DAY → Day of month,
REGIS_YEAR → Year.

👉 Enables time-based pattern analysis

**Hourly Arrival Pattern (2011 Data)**
Built a 31 × 24 matrix:
Rows → Days,
Columns → Hours.

Computed:
Average patient arrivals per hour

👉 Goal: Identify peak hours for staffing decisions

**Weekday Effect Analysis**
Derived WEEKDAY column
Aggregated arrivals by:
Day of week,
Hour of day.

👉 Goal: Understand differences between weekdays and weekends

## Key Insights

🔹 Hospital Preference

Patient arrivals are not evenly distributed
Certain hospitals consistently receive higher patient volumes

🔹 Waiting Time Variability

Significant variation across hospitals
Presence of extreme wait times (99th percentile) indicates bottlenecks

🔹 Peak Hours

Patient arrivals cluster around specific hours (typically daytime & evening)
Overnight periods show lower demand

🔹 Weekday Patterns

Weekends and weekdays show different demand patterns
Some days experience consistently higher load
## Business Recommendations
📈 Dynamic Staffing

Increase staffing during peak hours.
Reduce excess staffing during low-demand periods.

🏥 Load Balancing Across Hospitals

Redirect non-critical cases to less crowded hospitals.

⏱️ Reduce Extreme Wait Times

Focus on outliers (99th percentile cases).
Improve triage efficiency.

📅 Weekday-Based Planning

Adjust staffing models based on day-specific demand.
