# ⏳ Real-Time Data Ingestion Pipeline with Apache Airflow, PostgreSQL, and API Integration

## 📌 Overview
This project implements a **real-time data ingestion pipeline** using **Apache Airflow**. The pipeline extracts user data from an API, processes it into a structured format, and loads it into a **PostgreSQL** database. Additionally, weather data is retrieved from another API and integrated into the database. The entire process is **automated with Airflow**, and **DBWeaver** is used for database visualization.


### 🔹 Components
- **🌐 API Data Source**: REST APIs providing user and weather data in JSON format.
- **⚡ Apache Airflow**: Orchestrates the entire ETL (Extract, Transform, Load) process.
- **🗄 PostgreSQL**: Stores the structured user and weather data.
- **📊 DBWeaver**: Used for managing and visualizing PostgreSQL data.
- **🐳 Docker**: Containerizes the Airflow environment for seamless deployment.

---

## 🔄 Workflow

### **1️⃣ Extract User Data**
- The **SimpleHttpOperator** in Airflow fetches user data from an external API.
- The API response is parsed and stored as an **XCom variable**.

### **2️⃣ Extract Weather Data**
- Another **SimpleHttpOperator** fetches real-time weather data from an external API.
- The response is stored as an **XCom variable** for further processing.

### **3️⃣ Process Data**
- The extracted JSON data is **transformed** into a structured format using **Pandas**.
- The data is **normalized** and converted into **CSV format** for efficient loading.

### **4️⃣ Store Data**
- A **PostgresHook** is used to load the processed CSV data into a **PostgreSQL database**.
- The **COPY SQL command** ensures efficient data insertion.

---

## 🚀 Getting Started

### 🔧 Prerequisites
Ensure you have the following installed:
- **Docker** 🐳
- **Apache Airflow** ⚡
- **PostgreSQL** 🗄
- **Python (>=3.8)** 🐍
- **DBWeaver** (Optional for visualization) 📊




