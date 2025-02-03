# End to End Football Data Pipeline and Analytics

## Project Overview
This project implements an **end-to-end data pipeline** for extracting, processing, and visualizing data about football stadiums worldwide. The data is **crawled from Wikipedia** using **Apache Airflow**, stored in **Azure Data Lake**, cleaned and transformed using **Azure Data Factory**, queried using **Azure Synapse**, and finally visualized in **Tableau**.

---
## Data Pipeline
![Blank diagram](https://github.com/user-attachments/assets/3daa7f92-3ebb-4ce5-8d13-5bc62bf9811d)


---

## Downstream Tableau Dashboard
<img width="1207" alt="Screenshot 2025-02-02 at 11 09 34 PM" src="https://github.com/user-attachments/assets/f928ef36-e461-46b9-ad3d-726ca1ceb1e7" />
<a href> https://public.tableau.com/app/profile/sabarish.subramaniam3258/viz/FootballDashboardDownstreamDashboardfromEndtoEnddatapipeline/Dashboard2 </a href>

---

## Architecture Workflow
1. **Data Extraction**: Airflow DAG scrapes Wikipedia for a list of football stadiums and stores raw data in **Azure Data Lake**.
2. **Data Cleaning & Transformation**: Azure Data Factory processes and cleans the extracted data.
3. **Storage**: The cleaned data is stored back in **Azure Data Lake**.
4. **Data Processing & Querying**: Azure Synapse is used for querying and manipulation.
5. **Data Visualization**: The cleaned dataset is connected to Tableau for analysis and visualization.

## Requirements
- **Python 3.9+**
- **Docker** (for Airflow setup)
- **PostgreSQL** (for Airflow metadata database)
- **Apache Airflow 2.6+**
- **Azure Data Lake** (for data storage)
- **Azure Data Factory** (for data transformation)
- **Azure Synapse Analytics** (for querying and manipulation)
- **Tableau** (for visualization)

## Running the Project with Docker
1. Start Docker services:
   ```bash
   docker compose up -d
   ```
2. Open **Airflow UI**:
   - URL: `http://localhost:8080`
   - Login: Use default credentials or set up your own.

3. Trigger the **wikipedia_flow** DAG manually or schedule it.

4. The data will be extracted, cleaned, and stored in **Azure Data Lake**.

5. Azure Synapse processes the cleaned data, and the downstream Tableau dashboard connected to Azure Synapse reflects the updated data dynamically or after a refresh

## How It Works
### **1. Data Extraction (Airflow DAG)**
- The DAG `wikipedia_flow` extracts Wikipedia data about football stadiums.
- Uses `BeautifulSoup` for HTML parsing.
- Extracted data is pushed to **Azure Data Lake**.

### **2. Data Cleaning & Processing (Azure Data Factory)**
- Standardizes data formats.
- Resolves missing values and duplicates.
- Adds geographical coordinates for each stadium.
- Stores the cleaned data in **Azure Data Lake**.

### **3. Querying and Analysis (Azure Synapse)**
- Azure Synapse is used to run SQL queries and transform the data further.
- Performs aggregations, joins, and filtering operations for reporting.

### **4. Visualization (Tableau)**
- Tableau connects directly to Azure Synapse.
- Visualizes stadiums by capacity, region, and distribution.
- Enables dynamic exploration of the dataset.

## Industry Use Cases
This project mimics real-world **data engineering workflows** and can be applied in:
- **Sports Analytics**: Analyzing stadium capacities, team distributions, and geographical insights.
Sports organizations, event managers, and football clubs need data-driven insights to optimize stadium usage, enhance fan engagement, and maximize ticket revenue. Understanding stadium capacities, geographical distribution, and historical attendance trends can help in better event planning, sponsorship targeting, and infrastructure investments.

