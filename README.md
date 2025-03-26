# data-analyst-rosemaureen
# AWS Data Analytic Platform for the City of Vancouver (Phase 1)

## Project Title:
Modernizing Business License Data Management via AWS

## Objective:
To design and implement a scalable, cost-efficient AWS-based Data Analytics Platform (DAP) for the City of Vancouver to manage and analyze business license data for 2024.

## Dataset:
Business license datasets containing:
- Business categories
- License types
- Geographic information
- Issuance dates and fees

## Methodology:

1. **Data Ingestion**  
   - Collect raw datasets and store in Amazon S3.
    ![Data Ingestion Diagram](diagrams/data_ingestion.png)

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
