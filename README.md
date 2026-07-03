# End-to-End Analytics Platform with DuckDB & Metabase & Amazon S3

An end-to-end analytics platform that ingests NYC 311 complaint data, stores it in an Amazon S3 data lake following the **Bronze → Silver → Gold** architecture, performs data cleaning and modelling using **DuckDB**, and shows business-ready dashboards through **Metabase**.

The project separates **storage (Amazon S3)** from **compute (DuckDB)**, for scalable and maintainable data processing.

---

# Architecture

```text
                 NYC 311 API
                      │
                      ▼
               Data Ingestion 
                      │
                      ▼
             Amazon S3 (Bronze Layer)
          Raw Partitioned Parquet Files
                      │
                      ▼
                  DuckDB Engine
      Cleaning • Validation • Deduplication
                      │
                      ▼
             Amazon S3 (Silver Layer)
       Cleaned & Standardized Parquet Files
                      │
                      ▼
                  DuckDB Engine
      Data Modelling • Business Transformations
                      │
                      ▼
              Amazon S3 (Gold Layer)
      Fact Tables • Dimension Tables • Aggregates
                      │
                      ▼
                  Metabase Dashboard
```
---
# Tech Stack 
| Component        | Technology                  |
| ---------------- | --------------------------- |
| Data Source      | NYC Open Data (Socrata API) |
| Language         | Python                      |
| Data Lake        | Amazon S3                   |
| Compute Engine   | DuckDB                      |
| File Format      | Parquet                     |
| BI Tool          | Metabase                    |
| Containerization | Docker                      |
| Automation       | GitHub Actions              |

# Running Jupyter Lab

To setup Jupyter Container 
```
cd ./setup/jupyter_lab

docker build -t jupyter_image .

docker images

docker run -it --entrypoint=bash -p 8888:8888 jupyter_image
```
To Start Jupyter Notebook
```
jupyter lab --ip=0.0.0.0 --allow-root --no-browser
```
To skip Token 
```
jupyter lab --ip=0.0.0.0 --allow-root --no-browser \
--NotebookApp.token='' --NotebookApp.password=''
```

# To Setup Entire Environment 

To Setup Entire Environment Using Docker Image
```
cd ./setup
docker compose up --build
```

To Setup Environment Using Shell Script 
```
Future Scope
```
