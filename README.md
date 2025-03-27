Rose Maureen Avenido

## Project Title:
AWS Data Analytic Platform for the City of Vancouver (Phase 1)

## Introduction

This project addresses the challenge of managing and analyzing large volumes of business license data for the City of Vancouver. By leveraging Amazon Web Services (AWS), we designed a scalable and secure Data Analytics Platform (DAP) to improve decision-making, enhance service delivery, and support governance. The platform streamlines data ingestion, profiling, cleaning, cataloging, and summarization to deliver real-time, analysis-ready insights.

## Problem Statement

The City of Vancouver required a cloud-native solution to analyze business license data. Existing tools lacked scalability, real-time insights, and integration across departments. Key challenges addressed:

- Scattered data from various business license departments  
- Manual processes leading to inconsistencies and data delays  
- Lack of visibility for trends, compliance, and economic reporting  
- Need for governance-ready, secure, and scalable infrastructure

## Objective:
To design and implement a scalable, cost-efficient AWS-based Data Analytics Platform (DAP) for the City of Vancouver to manage and analyze business license data for 2024.

## Tools and Technologies:

Key AWS services and tools used in this implementation:

- Amazon S3 – Scalable storage for raw and processed datasets  
- AWS Glue – Data transformation, cleaning, and job orchestration  
- AWS Glue DataBrew – No-code profiling and cleaning  
- Amazon Athena – Serverless SQL querying on S3-stored data  
- Amazon EC2 – Compute environment for workload execution  
- AWS Elastic Beanstal* – Hosting for frontend log and data visualization apps  

## Dataset:
Business license 2024 datasets containing:
- Business categories
- License types
- Geographic information
- Issuance dates and fees
 
## Methodology:

1. **Data Ingestion**  
   - Collect raw datasets and store in Amazon S3.
   
2. **Data Profiling**  
   - Use AWS Glue DataBrew to detect inconsistencies, missing values, and data structure issues.

3. **Data Cleaning**  
   - Handle duplicates and formatting errors using AWS Glue ETL.

4. **Data Cataloging**  
   - Organize metadata in AWS Glue Data Catalog for easy access via Athena or Redshift.

5. **Data Summarization**  
   - Aggregate key metrics (e.g., licenses issued by type, revenue, region) to extract insights.
  
---

## Project Deliverables

### 🧱 DAP (Data Analytic Platform) Design 

To support the end-to-end data pipeline for business license analysis, a two-layer architecture was designed using AWS services. Below are two system diagrams that illustrate the infrastructure and data flow.

![DAP System Architecture diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20DAP%201-2.png)
![DAP System Architecture diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20DAP%202-2.2.png)

### Step by Step Implementation:

## 1. Data Ingestion

- Initiated the AWS analytics pipeline with structured data ingestion.
- Uploaded raw business license datasets into **Amazon S3**.
- Ensured centralized, secure, and scalable data storage.
- Enabled easy access for downstream processes such as:
  - Data profiling
  - Data cleaning
  - Querying and analysis

1.1 Shows the successful upload of `business-list.csv` to the S3 bucket.

![Data Ingestion Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG1.1%20DATA%20INGESTION%20.png)

---

1.4 Displays the `license-list.csv` upload to a similar S3 directory. 

![Data Ingestion Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG1.2%20DATA%20INGESTION%20.png)

----

1.3 Shows the use of AWS CLI commands within PowerShell to upload the datasets directly to S3 buckets.

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG1.3%20DATA%20INGESTION%20.png) 

---

## 2. Data Profiling

- Used **AWS Glue DataBrew** to examine the structure and quality of ingested datasets.
- Analyzed three datasets: business list, license list, and location list.
- Key profiling outputs:
  - Total rows, columns, and data types
  - Percentage of missing and duplicate cells
  - Correlation matrices showing variable relationships
- Identified early data issues to guide the cleaning phase and ensure reliable analytics.

2.1 List of created DataBrew projects, each linked to a dataset and recipe.

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG2.1%20DATA%20PROFILING%20.png) 

---

2.2 Displays completed DataBrew profile jobs showing datasets, status, and timestamps.

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG2.2%20DATA%20PROFILING%20.png)

---

2.3 Profiling summary of the business list dataset with correlations and column stats. 

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG2.3%20DATA%20PROFILING%20.png)

---
2.4 Profile overview of the license dataset showing missing values and variable relationships. 
![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG2.4%20DATA%20PROFILING%20.png)

---

2.5 Profiling results for the location dataset highlighting missing data and correlations.

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG2.5%20DATA%20PROFILING%20.png)

---

## 3. Data Cleaning

- Used **AWS Glue and AWS Glue DataBrew** to clean and prepare datasets for analysis.
- Performed key cleaning operations:
  - Removed duplicate records
  - Handled missing values using imputation or removal
  - Standardized column formats (e.g., dates, text case)
- Ensured consistency and accuracy across business list, license list, and location list datasets.
- Saved the cleaned outputs to Amazon S3 for further processing and cataloging.

3.1 List of recipe jobs with input data, outputs, and run status.

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG3.1%20DATA%20CLEANING%20.png)

---

3.2 S3 lifecycle rules enabled to transition data to Glacier storage.

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG3.2%20DATA%20CLEANING%20.png)

---

3.3 IIS log file showing recorded user activity on the server. 

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG3.3%20DATA%20CLEANING.png)

---

3.4 PowerShell command used to upload the user log file to S3.  

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG3.4%20DATA%20CLEANING%20.png)

---

3.5 Uploaded user log file successfully stored in Amazon S3.

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG3.5%20DATA%20CLEANING%20.png)

---

## 4. Data Cataloging

- Used **AWS Glue Data Catalog** to register and organize cleaned datasets.
- Created metadata tables for business, license, and location datasets.
- Enabled fast data discovery and schema management for querying in Athena.
- Ensured consistent naming and logical partitioning for efficient access.
- Simplified data retrieval across multiple AWS services for analytics.

A Glue Data Catalog showing registered tables, enabling easy data discovery and structured querying for analytics.

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG4.1%20DATA%20CATALOGING%20.png)

---

## 5. Data Summarization

- Aggregated cleaned datasets to generate key insights using **AWS Glue jobs**.
- Created summaries for:
  - Total licenses issued by type and category
  - Business distribution by location
  - Fee-related trends and totals
- Joined datasets to support cross-analysis (e.g., licenses by region and employee count).
- Output stored in Amazon S3 for visualization or querying via Athena and QuickSight.
- Supports informed decision-making and performance tracking for city operations.

5.1 Shows output folders created for each business type after summarization in S3.

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG5.1%20DATA%20SUMMARIZATION-BSN%20LIST%20.png)

---

5.2 Displays the system-generated summary file from the Glue job execution.  

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG5.2%20DATA%20SUMMARIZATION-BSN%20LIST%20.png)

---
5.3 Visual workflow of the Glue job performing extract, filter, aggregate, and load operations.

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG5.3%20DATA%20SUMMARIZATION-BSN%20LIST%20.png)

---

5.4 Glue Data Catalog tables were created to organize summarized outputs, allowing structured queries and integration with BI tools.
  
![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG5.10%20DATA%20SUMMARIZATION-TABLES%20IN%20GLUE%20.png)

---
  
5.5 Application log files from Elastic Beanstalk were stored in S3 to monitor access and usage behavior, supporting ongoing operational analysis.  

![Data Ingestion Diagram](https://github.com/avenidorp/data-analyst-rosemaureen/blob/main/PP1%20FIG5.11%20DATA%20SUMMARIZATION-BEANSTALK%20.png)

---

## 🚧 Challenges Faced & Solutions

- **Handling complex datasets**  
  → Broke down ingestion and processing into modular stages

- **Data quality issues**  
  → Used DataBrew profiling to flag nulls, duplicates, and type mismatches

- **Monitoring and cost control**  
  → Used S3 lifecycle policies and logging for cleanup and visibility

- **Secure access**  
  → Applied IAM role policies across Glue, S3, and EC2 environments

---

## Conclusion

Phase 1 successfully delivered a scalable and automated AWS-based data platform for business license analytics. By transforming raw records into structured insights, the City of Vancouver can now track licensing trends, improve transparency, and plan services more efficiently. With core infrastructure in place, the next phases can expand into predictive analytics, reporting automation, and broader departmental integration.

---

## 🔗 GitHub Pages Portfolio:
[Link to Portfolio Site](https://avenidorp.github.io/data-analyst-rosemaureen/)
