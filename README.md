# ETL Project dengan Apache Airflow

Project ETL (Extract, Transform, Load) menggunakan Apache Airflow yang dijalankan dengan Docker Compose.

## Struktur Project

```
ETL-1/
├── docker-compose.yml          # Konfigurasi Docker Compose
├── dags/                      # Apache Airflow DAGs
│   └── summary_transaction.py
├── data/                      # Dataset
│   └── retail-dataset.csv
├── temp_pipline/              # Jupyter Notebooks untuk development
│   ├── insert_to_master.ipynb
│   └── kotretan_to_warehouse.ipynb
├── logs/                      # Airflow logs (dibuat otomatis)
└── plugins/                   # Airflow plugins (dibuat otomatis)
```


## Services yang Dijalankan

### 1. PostgreSQL Database
- **Port:** 5434 (host) → 5432 (container)
- **Container:** `postgres`
- **Database:** airflow
- **User:** airflow
- **Password:** airflow

### 2. Airflow Webserver
- **Port:** 8080
- **URL:** http://localhost:8080
- **Container:** `airflow-webserver`

### 3. Airflow Scheduler
- **Port:** 8793
- **Container:** `airflow-scheduler`

### 4. Airflow Init
- **Container:** `airflow-init`
- **Function:** Inisialisasi database dan folder permissions