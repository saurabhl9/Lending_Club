
# Lending_Club

📊 Lending Club Data Engineering Project

This project simulates a real-world data engineering pipeline using Apache Spark (PySpark). The goal is to clean, transform, and prepare lending data for downstream analytics teams. It reflects practical experience working with large-scale datasets, Spark transformations, and performance-optimized ETL workflows.

---

<summary>📁 Project Structure</summary>
```bash
LENDING CLUB/
├── Cleaning/
│ ├── LendingClub_DataCleaning_S1.ipynb
│ ├── LendingClub_DataCleaning_S2.ipynb
│ ├── LendingClub_DataCleaning_S3.ipynb
│ ├── LendingClub_DataCleaning_S4.ipynb
│ └── LendingClub_Intro.ipynb
│
├── Transformation/
│ ├── LendingClub_Transformation_part1.ipynb
│ ├── LendingClub_Transformation_part2.ipynb
│ ├── LendingClub_Transformation_part3.ipynb
│ ├── LendingClub_Transformation_part4.ipynb
│ └── LendingClub_Transformation_part5.ipynb
│
├── tests/
│ ├── conftest.py
│ ├── DataManipulation.py
│ └── test_pipeline.py
│
├── requirements.txt
└── README.md
```



---

## 🚀 Project Overview

Financial institutions like Lending Club (a peer-to-peer lending platform) use borrower data to:

- Assess credit risk  
- Approve/reject loans  
- Analyze repayment behavior  
- Create borrower risk profiles  

This project demonstrates how raw data from Lending Club can be cleaned, transformed, and structured for business insights and reporting.

---

## 🔧 Key Components

### 1. **Data Cleaning** (`Cleaning/`)

- Loaded raw data (`accepted_2007_to_2018Q4.csv`) into Spark DataFrames  
- Created unique identifiers (`emp_id`) using SHA-2 hashing  
- Handled:
  - Null and missing values  
  - Data type inconsistencies  
  - Duplicates  
  - Invalid formats (e.g., non-numeric employment lengths)  
- Enriched columns like `ingest_date`, `loan_purpose`  
- Saved cleaned datasets in CSV and Parquet formats  

### 2. **Data Transformation** (`Transformation/`)

- Converted loan terms from months to years  
- Applied logic to compute **loan scores**:
  - Loan Repayment History: 20%  
  - Loan Defaulters History: 45%  
  - Financial Health: 35%  
- Derived and joined datasets for:
  - Customers  
  - Loans  
  - Repayments  
  - Defaulters  
- Built Hive external tables and views for reporting  
- Flagged and removed bad data (duplicate member IDs)  

---

## 🧠 Business Use-Cases Addressed

- Build a **360° view** of the customer  
- Enable **risk scoring** for loan applications  
- Maintain **master borrower records**  
- Support **batch and real-time analytics** through Hive views  

---

## 🛠 Tech Stack

- Apache Spark (PySpark)  
- Hive Metastore  
- HDFS  
- Python (Jupyter Notebooks)  
- CSV & Parquet formats  
- Logging via Log4j  
- Virtual environments via `pipenv`  
- Unit testing using `pytest`  

---