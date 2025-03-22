# Delayed Oil Transfer Project
## **PROJECT OVERVIEW**
**Objective**
This project investigates the root causes of delays in the oil transfer process and proposes a strategic solution plan. Through data analysis of operational workflows, resource allocation, and process efficiency, this project seeks to identify trends and key areas for improvement.

**Scope**

The analysis covers:
+ Current transfer and handling protocols
+ Staffing and equipment utilization patterns
+ Service delay patterns and external influencing factors
+ Operational bottlenecks and improvement opportunities

**Methodology**

+ Data Collection: Gathering logs, staffing data, equipment status, and service records.
+ Analysis: Identifying delay trends and correlating them with operational factors.
+ Root Cause Analysis: Diagnosing main delay contributors.
+ Solution Proposal: Recommending solutions, such as process optimization and resource allocation.

---
**DATA SOURCE**
The data set provided by the client as a CSV file, which was downloaded and processed for analysis.
---

**Tools Used**
+ **Microsoft Excel:** Utilized for preliminary data correction and initial review of the dataset.
+ **SQL Server:** Employed for data cleaning and in-depth analysis to extract meaningful insights.
+ **Power BI**: Used to visualize insights and provide detailed, interactive reports.

**EXPLORATORY DATA ANALYSIS (EDA)**
In this EDA phase, we will examine the human resource dataset to address key operational questions that can impact the efficiency and reliability of oil transfer services. These insights will help identify potential areas for improvement and facilitate data-driven decision-making.

Key Questions to Address:
1. Total Number of Truck Drivers
  + Determine the number of truck drivers to assess if current staffing meets operational demands.
3. Number of Efficient Trucks
  + Identify the count of trucks classified as efficient to understand fleet reliability and potential operational constraints.
3. Coverage Areas (Distances in Kilometers)
  + Analyze distances covered to evaluate the geographic reach and the adequacy of logistical support across areas served.
4. Truck Breakdown and Maintenance Frequencies.
  + Assess the frequency of truck breakdowns and scheduled maintenance to pinpoint areas needing additional support or preventive measures.
    
**Note**: _These insights from EDA will contribute to optimizing workforce planning, improving fleet management, and enhancing the overall efficiency of oil transfer services._

**USED SQL CODES**
*SQL*
```SELECT COUNT(*) AS TotalTruckDrivers
FROM employees
WHERE job_title = 'Truck Driver';
SELECT COUNT(*) AS EfficientTrucks FROM trucks WHERE efficiency_status = 'Efficient';
SELECT truck_id, SUM(distance_in_km) AS TotalDistanceCovered FROM deliveries GROUP BY truck_id;
SELECT truck_id, COUNT(*) AS BreakdownCount FROM maintenance_log WHERE maintenance_type = 'Breakdown' GROUP BY truck_id;
SELECT truck_id, COUNT(*) AS MaintenanceCount FROM maintenance_log GROUP BY truck_id;
SELECT COUNT(*) AS EmployeesHiredInLastYear FROM employees WHERE hire_date >= DATE_SUB(CURDATE(), INTERVAL 1 YEAR);
SELECT YEAR(hire_date) AS Year, MONTH(hire_date) AS Month, COUNT(*) AS EmployeesHired FROM employees GROUP BY YEAR(hire_date), MONTH(hire_date) ORDER BY YEAR(hire_date) DESC, MONTH(hire_date) DESC;
```


