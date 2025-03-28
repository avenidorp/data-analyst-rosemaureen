# Project 1 Title: AWS Data Analytic Platform for the City of Vancouver (Phase 1)

## Introduction

This project outlines the design and implementation of a Data Analytics Platform (DAP) that will allow the City of Vancouver to analyze and manage business license data efficiently. The platform streamlines data ingestion, profiling, cleaning, cataloging, and summarization to deliver real-time, analysis-ready insight. The estimated monthly cost of running this platform on AWS was also computed to ensure financial feasibility and sustainability. 


## Problem Statement

The City of Vancouver needs to migrate to AWS, a scalable, secure, and cost-efficient cloud solution to manage and analyze its growing business license data, replacing outdated systems that limit performance, data quality, and decision-making. Key challenges addressed:

- Scattered data from various business license departments  
- Lack of visibility for trends, compliance, and economic reporting  
- Need for governance-ready, secure, and scalable infrastructure

## Objective:
To design and implement a scalable, cost-efficient AWS-based Data Analytics Platform (DAP) for the City of Vancouver to manage and analyze business license data for 2024.

## Tools and Technologies:

Key AWS services and tools used in this implementation:

- Amazon S3 – Scalable object storage for raw, curated, and transformed datasets
- AWS Glue – Code-based service for building and automating complex ETL workflows
- AWS Glue DataBrew – Visual, no-code tool for quick data profiling and preparation   
- Amazon EC2 – Virtual compute environment for running ingestion scripts and custom tasks
- AWS Elastic Beanstalk – Hosting for frontend log and data visualization apps  

## Dataset:
Business license 2024 datasets containing:
- Business categories
- License types
- Geographic information
- Issuance dates and fees
 
## Methodology:

1. **Data Ingestion** - Collect raw datasets and store in Amazon S3.
   
2. **Data Profiling** - Use AWS Glue DataBrew to detect inconsistencies, missing values, and data structure issues.

3. **Data Cleaning** - Handle duplicates and formatting errors using AWS Glue ETL.

4. **Data Cataloging** -Store and manage metadata in AWS Glue Data Catalog to enable easy data discovery and organization.

5. **Data Summarization** - Consolidate key metrics (e.g., licenses issued by type, revenue, region) to derive meaningful insights.
  
---

## Project Deliverables

### 🧱 DAP (Data Analytic Platform) Design 

To support end-to-end business license data analysis, a two-layer architecture was designed using AWS services. The following system diagrams illustrate the cloud infrastructure and data flow across the entire analytics pipeline.

![DAP System Architecture diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20DAP%201-2.png)
![DAP System Architecture diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20DAP%202-2.2.png)

Integrated view of data ingestion, enrichment, and transformation processes, with detailed insights into cost analysis and dataset quality

![DAP System Architecture diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%200%20DAP%20PIC3.png)
![DAP System Architecture diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%200%20DAP%20PIC4.png)
![DAP System Architecture diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%200%20DAP%20PIC5.png)

## Step by Step Implementation:

### 1. Data Ingestion

- Initiated the AWS analytics pipeline with structured data ingestion.
- Uploaded raw business license datasets into **Amazon S3**.
- Ensured centralized, secure, and scalable data storage.
- Enabled easy access for downstream processes such as:
  - Data profiling
  - Data cleaning
  - Querying and analysis

1.1 AWS CLI commands within PowerShell to upload the datasets directly to S3 buckets.

![Data Ingestion Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG1.3%20DATA%20INGESTION%20.png)

---

1.2 Successful upload of `business-list.csv` to the S3 bucket.

![Data Ingestion Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG1.1%20DATA%20INGESTION%20.png)

---

1.3 Displays the `license-list.csv` upload to a similar S3 directory. 

![Data Ingestion Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG1.2%20DATA%20INGESTION%20.png)

---

### 2. Data Profiling

- Utilized **AWS Glue DataBrew** to examine the structure and quality of ingested datasets.
- Analyzed three datasets: business list, license list, and location list.
- Key profiling outputs:
  - Total rows, columns, and data types
  - Percentage of missing and duplicate cells
  - Correlation matrices showing variable relationships
- Identified early data issues to guide the cleaning phase and ensure reliable analytics.

2.1 List of created DataBrew projects, each linked to a dataset and recipe.

![Data Profiling Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG2.1%20DATA%20PROFILING%20.png) 

---

2.2 Successful execution of AWS Glue DataBrew profile jobs for Business Licenses 2024 datasets (bus-lst, lic-lst, and loc-lst).

![Data Profiling Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG2.2%20DATA%20PROFILING%20.png)

---

2.3 Profiling summary of the business list dataset with correlations and column stats. 

![Data Profiling Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG2.3%20DATA%20PROFILING%20.png)

---
2.4 Profile overview of the license dataset showing missing values and variable relationships. 
![Data Profiling Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG2.4%20DATA%20PROFILING%20.png)

---

2.5 Profiling results for the location dataset highlighting missing data and correlations.

![Data Profiling Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG2.5%20DATA%20PROFILING%20.png)

---

### 3. Data Cleaning

- Applied **AWS Glue and AWS Glue DataBrew** to clean and prepare datasets for analysis.
- Performed key cleaning operations:
  - Removed duplicate records
  - Handled missing values using imputation, removal or replacing with nulls
  - Standardized column formats (e.g., dates, text case)
- Ensured consistency and accuracy across business list, license list, and location list datasets.
- Saved the cleaned outputs to Amazon S3 for further processing and cataloging.

3.1 Successful execution of AWS Glue DataBrew recipe jobs for transforming Business Licenses 2024 datasets.

![Data Cleaning Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG3.1%20DATA%20CLEANING%20.png)

---

3.2 S3 lifecycle rules enabled to transition data to Glacier storage, reducing costs while preserving long-term data retention.

![Data Cleaning Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG3.2%20DATA%20CLEANING%20.png)

---

3.3 IIS log file generated on EC2 instance capturing web access activity, useful for monitoring usage patterns and detecting potential security issues.

![Data Cleaning Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG3.3%20DATA%20CLEANING.png)

---

3.4 PowerShell command used to upload the user log file to S3.  

![Data Cleaning Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG3.4%20DATA%20CLEANING%20.png)

---

3.5 Uploaded user log file successfully stored in Amazon S3.

![Data Cleaning Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG3.5%20DATA%20CLEANING%20.png)

---

### 4. Data Cataloging

- Used **AWS Glue Data Catalog** to register and organize cleaned datasets.
- Created metadata tables for business, license, and location datasets.
- Enabled fast data discovery and schema management for querying in Athena.
- Ensured consistent naming and logical partitioning for efficient access.
- Simplified data retrieval across multiple AWS services for analytics.

A Glue Data Catalog showing registered tables, enabling easy data discovery and structured querying for analytics.

![Data Cataloging Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG4.1%20DATA%20CATALOGING%20.png)

---

### 5. Data Summarization

- Aggregated cleaned datasets to generate key insights using **AWS Glue jobs**.
- Created summaries for:
  - Total licenses issued by type and category
  - Business distribution by location
  - Fee-related trends and totals
- Joined datasets to support cross-analysis (e.g., licenses by region and employee count).
- Output stored in Amazon S3 for visualization 
- Supports informed decision-making and performance tracking for city operations.

5.1 Shows output folders created for each business type after summarization in S3.

![Data Summarization Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG5.1%20DATA%20SUMMARIZATION-BSN%20LIST%20.png)

---

5.2 Displays the system-generated summary file from the Glue job execution.  

![Data Summarization Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG5.2%20DATA%20SUMMARIZATION-BSN%20LIST%20.png)

---
5.3 Visual workflow of the Glue job performing extract, filter, aggregate, and load operations.

![Data Summarization Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG5.3%20DATA%20SUMMARIZATION-BSN%20LIST%20.png)

---

5.4 Glue Data Catalog tables were created to organize summarized outputs, allowing structured queries and integration with reporting and analytics platforms.
  
![Data Summarization Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG5.10%20DATA%20SUMMARIZATION-TABLES%20IN%20GLUE%20.png)

---
  
5.5 Application log files from Elastic Beanstalk were stored in S3 to monitor access and usage behavior, supporting ongoing operational analysis.  

![Data Summarization Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG5.11%20DATA%20SUMMARIZATION-BEANSTALK%20.png)

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

Phase 1 successfully delivered a scalable and automated AWS-based data platform for business license analytics. With successful transformation of raw records into structured insights, the City of Vancouver can now track licensing trends and plan services more efficiently. With core infrastructure in place, the next phases is to safeguard data and strengthen system integrity to ensure the platform remains reliable, compliant, and prepared for future growth.

---

# Project 2 Title: AWS Data Analytics Platform for the City of Vancouver (Phase 2)

## Introduction

Phase 2 builds on the foundation of the City of Vancouver’s AWS Data Analytics Platform by adding advanced capabilities in data analysis, security, governance, and monitoring. These improvements make the platform more secure, reliable, and efficient, helping the city manage business license data with greater accuracy, transparency, and speed. The system is now aligned with key AWS Well-Architected principles to support data-driven decisions and long-term performance.

---

## Objective

To strengthen the existing AWS-based platform by adding analytics, encryption, governance, and monitoring features—allowing the City of Vancouver to securely manage and analyze business license data while ensuring data quality, performance, and visibility.

---

## Tools and Technologies Used

- **Amazon S3** – Tiered data storage for raw, cleaned, and summarized datasets  
- **AWS Glue & DataBrew** – ETL pipeline creation, cleaning logic, and profiling  
- **Amazon Athena** – Serverless querying of structured data  
- **AWS CloudWatch** – Real-time performance monitoring and alerting  
- **AWS CloudTrail** – User activity and audit logging  
- **AWS KMS** – Managed encryption key service for S3 and metadata  
- **AWS IAM** – Secure access management and policy enforcement  

---

## Phase 2 – Methodology

1. **Data Analysis** – Use AWS Glue DataBrew to clean and standardize datasets, then execute SQL queries in Amazon Athena to uncover trends (e.g., employee count, business types, monthly growth).

2. **Data Security** – Apply AWS KMS encryption for all data stored in Amazon S3, enable bucket versioning, and manage access using IAM policies to ensure confidentiality and resilience.

3. **Data Governance** – Implement AWS Glue ETL checkpoints to validate data quality (completeness, uniqueness, freshness) and organize validated data into structured tables via AWS Glue Data Catalog.

4. **Data Monitoring** – Deploy Amazon CloudWatch dashboards and alarms to track system performance. Enable CloudTrail logging for user activity, ensuring visibility and accountability.

---

## Project Deliverables ##

### 🧱 DAP Architecture – Phase 2 Enhancement

The diagram below illustrates the updated Data Analytics Platform with integrated analysis, encryption, governance, and monitoring features. It shows how AWS services interact to support secure, reliable, and governed data workflows.

---

## Step by Step Implementation ##

### 6. Data Analysis

- Cleaned and structured the 2024 business license data using **DataBrew** recipes.
- Executed multiple SQL queries in **Amazon Athena** to uncover:
  - Total and average number of employees per business type
  - Top business sectors by license count
  - Trends in new license issuances over time
- Provided aggregated views that support compliance reporting, operational planning, and economic assessments.

---

### 7. Data Security

- Activated **KMS encryption** for all S3 buckets storing raw and transformed data.
- Enforced **S3 bucket versioning** to preserve data history and recovery options.
- Established **IAM roles and permissions** for secure access between Glue jobs, Athena, and user groups.
- Created security controls to prevent unauthorized data manipulation, ensuring public trust.

---

### 8. Data Governance

- Implemented ETL checkpoints that filter and route high-quality data to “Passed” zones in S3.
- Used **AWS Glue** to validate data types, null counts, uniqueness, and freshness.
- Created dynamic **partitioned tables** in AWS Glue Data Catalog for query optimization.
- Ensured repeatability and transparency in data validation for audit-readiness and compliance.

---

### 9. Data Monitoring

- Deployed **CloudWatch dashboards** to monitor Glue job metrics and S3 activity.
- Configured **CloudWatch Alarms** with SNS to alert stakeholders of resource thresholds (e.g., storage spikes, job failures).
- Enabled **AWS CloudTrail** for full visibility into user interactions and access events.
- Supported continuous performance tuning and early detection of operational issues.

---

## 📊 DAP Architecture Alignment (Phase 1 & 2 Combined)

| Phase   | Focus Areas                                  | AWS Services                           | Aligned Pillars                                   |
|---------|----------------------------------------------|----------------------------------------|--------------------------------------------------|
| Phase 1 | Ingestion, Profiling, Cleaning, Cataloging, Summarization | EC2, S3, Glue, DataBrew, Athena        | Operational Excellence, Cost Optimization        |
| Phase 2 | Analysis, Security, Governance, Monitoring   | KMS, IAM, CloudTrail, CloudWatch       | Security, Reliability, Performance Efficiency     |

---

## 🔍 Evaluation Highlights

## ✅ Key Accomplishments

- Delivered deeper analytical insights using Athena and DataBrew
- Strengthened data protection with encryption and access controls
- Established data quality checkpoints and routing logic
- Enabled real-time monitoring with alerting for proactive issue management  

## ⚠️ Areas for improvement:
- Refine IAM policies for more granular access control  
- Implement schema evolution and disaster recovery playbooks  
- Add documentation for Glue transformations and job parameters  

---

## Conclusion

Phase 2 significantly enhances the City of Vancouver’s AWS Data Analytics Platform by introducing intelligence, automation, and governance. These upgrades not only ensure data is trustworthy and secure but also enable real-time visibility and performance tracking. The resulting architecture is agile, policy-driven, and optimized for growth—empowering the city to make informed decisions and uphold transparency in managing business license operations.

---

## Course Completion Badge

🎖️ Earned the **AWS Academy Cloud Foundations** badge, demonstrating foundational knowledge in AWS Cloud, Architecture, Core Services, Pricing, and Support.  
Issued by AWS Academy on March 26, 2025.

![Course Completion Badge Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/AWS%20BADGE%20WITH%20SKILLS.png)


## 🔗 GitHub Pages Portfolio:
[Link to Portfolio Site](https://avenidorp.github.io/data-analyst-rosemaureen/)
