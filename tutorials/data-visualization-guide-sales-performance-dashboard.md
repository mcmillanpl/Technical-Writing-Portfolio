# Data Visualization Guide: Sales Performance Dashboard

## Overview
This document outlines the architecture, data transformations, and visualization logic for the **Sales Performance Power BI Dashboard**. This report provides executive leadership with real-time insights into regional revenue trends and salesperson KPIs.

---

## 1. Data Connectivity & Transformation
The report utilizes a **Star Schema** to optimize performance and ensure data integrity.



### Data Sources
* **SQL Server:** Primary sales transactions and historical data.
* **Excel (SharePoint):** Monthly quota targets and regional mapping.

### Power Query (M) Enhancements
To ensure "clean" data, the following transformations were applied in the Power Query Editor:
* **Unpivoting:** Converted monthly target columns into a "Month" and "Target" attribute pair for easier time-series analysis.
* **Data Typing:** Forced currency and date formats to ensure DAX calculations function correctly.
* **Conditional Columns:** Created a `Region Category` column to group territories based on corporate restructuring.

---

## 2. DAX Measures (Calculated Logic)
The following measures were authored to provide dynamic insights that standard aggregations cannot achieve.

### Total Revenue YTD
Calculates cumulative revenue for the current fiscal year.
$$Total\ Revenue\ YTD = TOTALYTD(SUM(Sales[Amount]), 'Date'[Date])$$

### Variance to Target %
Measures performance against set goals.
$$Variance\ \%\ = DIVIDE([Total\ Revenue] - [Total\ Target], [Total\ Target], 0)$$

---

## 3. Visualization Standards
To maintain high **Data-to-Ink ratios** and accessibility, the following design standards are implemented:

| Visual Type | Usage | Key Feature |
| :--- | :--- | :--- |
| **Slicers** | Date Range, Region | Sync-slicers enabled across all report pages. |
| **Clustered Bar Chart** | Revenue by Product | Tooltips provided to show "Previous Year" comparison on hover. |
| **KPI Cards** | Net Profit, Margin % | Conditional formatting applied (Red for <90% target, Green for >100%). |

---

## 4. Security & Distribution
* **Row-Level Security (RLS):** Implemented roles based on `RegionManager` attributes, ensuring managers only see data for their specific territories.
* **Workspaces:** The report is published to the **Executive Production** workspace with "Viewer" permissions restricted via Active Directory groups.

---

## Maintenance & Troubleshooting

A robust reporting environment requires proactive maintenance. Below are common failure points in the Sales Performance Dashboard and their respective resolutions.

### 1. Scheduled Refresh Failures
If the report fails to update on the Power BI Service, verify the following:

| Symptom | Cause | Resolution |
| :--- | :--- | :--- |
| **Credential Error** | Password expiry or PAT change. | Navigate to **Dataset Settings > Data Source Credentials** and re-authenticate the SQL or SharePoint connection. |
| **Gateway Offline** | Local server hosting the On-Premises Gateway is down. | Restart the Gateway service on the host machine and ensure it is updated to the latest version. |
| **Data Type Mismatch** | A source column changed from "Decimal" to "String." | Open Power Query, identify the "Changed Type" step, and update the schema to match the new source format. |

### 2. DAX Performance Optimization
Large datasets can lead to slow "slicer" response times. To maintain a high-performance UI:
* **Minimize Visuals:** Avoid "Visual Overload" by limiting each page to 5-7 key charts.
* **Filter Context:** Use the **Performance Analyzer** to identify which DAX measures are taking the longest to render.
* **Measure vs. Calculated Column:** Always prefer **Measures** for aggregations to keep the file size small and the data model lean.

### 3. Version Control for .pbix Files
Since Power BI files are binary, standard Git "merging" is not possible. We follow this versioning SOP:
1. **Archive:** Save a copy of the `.pbix` with a date stamp (e.g., `Sales_v2026_02_05.pbix`) before making major schema changes.
2. **Development Workspace:** Always publish to a "Sandbox" workspace for QA before pushing to the "Executive" workspace.
3. **Documentation:** Record all logic changes in the **Change Log** at the end of this document.

---

## Change Log
| Date | Author | Description of Change |
| :--- | :--- | :--- |
| 2026-02-05 | [Your Name] | Initial deployment; implemented RLS for Regional Managers. |
| 2026-02-10 | [Your Name] | Updated `Total Revenue` DAX to account for new fiscal year offset. |