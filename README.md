# data-analyst-rosemaureen
# Modernizing Business License Data Management via AWS

## Project Title:
AWS Data Analytic Platform for the City of Vancouver (Phase 1)


## Objective:
To design and implement a scalable, cost-efficient AWS-based Data Analytics Platform (DAP) for the City of Vancouver to manage and analyze business license data for 2024.

## Dataset:
Business license datasets containing:
- Business categories
- License types
- Geographic information
- Issuance dates and fees

### 🧱 DAP System Architecture

To support the end-to-end data pipeline for business license analysis, a two-layer architecture was designed using AWS services. Below are two system diagrams that illustrate the infrastructure and data flow.

![DAP System Architecture diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20DAP%201-2.png)
![DAP System Architecture diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20DAP%202-2.2.png)
 
## Methodology:

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















1. **Data Ingestion**  
   - Collect raw datasets and store in Amazon S3.
   ![Data Ingestion Diagram](https://raw.githubusercontent.com/avenidorp/data-analyst-rosemaureen/main/PP1%20FIG1.1%20DATA%20INGESTION%20.png)

2. **Data Profiling**  
   - Use AWS Glue DataBrew to detect inconsistencies, missing values, and data structure issues.

3. **Data Cleaning**  
   - Handle duplicates and formatting errors using AWS Glue ETL.

4. **Data Cataloging**  
   - Organize metadata in AWS Glue Data Catalog for easy access via Athena or Redshift.

5. **Data Summarization**  
   - Aggregate key metrics (e.g., licenses issued by type, revenue, region) to extract insights.

## Tools and Technologies:
- AWS S3
- AWS Glue & Glue DataBrew
- Amazon Athena
- Amazon EC2
- Amazon Cloudwatch

## Deliverables:
- Data ingestion and cleaning scripts
- AWS architecture diagram
- Summary visualization
- Final report (uploaded in `/reports/`)
- Cost estimation analysis

## Conclusion:
This Phase 1 implementation showcases how cloud-based analytics infrastructure can empower municipalities to manage business data efficiently, supporting real-time insights and better governance.

## 🔗 GitHub Pages Portfolio:
[Link to Portfolio Site](https://avenidorp.github.io/data-analyst-rosemaureen/)
