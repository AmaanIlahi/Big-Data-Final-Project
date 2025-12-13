# Distributed Transaction Risk Scoring & Merchant Anomaly Profiling  
*A Real-Time Big Data Fraud & Risk Analytics Pipeline*

This project implements a full end-to-end **distributed financial risk analytics system** that performs real-time transaction ingestion, risk scoring, merchant anomaly detection, customer behavioral profiling, and network graph analysis using a modern big-data lakehouse architecture.

Built for **CS-GY 6513 (Big Data) – Final Project**  
**Amaan Elahi (ae2950), Srishti Arora (sa9051), Subhan Akhtar (sa8580)**

---

## 1. Project Overview

Financial institutions increasingly face large-scale transaction streams that require **real-time risk scoring**, **fraud monitoring**, and **merchant behavior analysis**.  
This project builds a distributed system capable of:

- **Real-time transaction risk scoring**
- **Merchant anomaly profiling using MLlib clustering**
- **Velocity-based spending analysis**
- **Customer segmentation**
- **Merchant–customer network graph analysis**
- **Unified lakehouse storage using Delta Lake**
- **A dashboard for fraud/risk analytics**

The system combines **streaming + batch** pipelines to simulate a realistic, cloud-ready risk intelligence platform.

---


The pipeline supports both **high-throughput streaming risk detection** and **batch machine learning workloads**.

---

## 2. Technology Stack

### **Data Ingestion**
- Apache Kafka – Real-time streaming transactions

### **Compute**
- Apache Spark Structured Streaming – Real-time scoring  
- Spark SQL / DataFrames – ETL, aggregations  
- MLlib – Clustering & anomaly detection  
- GraphFrames – Merchant–customer network analysis  

### **Storage**
- Delta Lake – ACID, versioned lakehouse storage

### **Dashboard**
- Flask – Exposes risk scores & analytics  
- (HTML/CSS/JS added later)

---

## 3. Core Features

### 🔹 1. Real-Time Transaction Risk Scoring
Each incoming Kafka transaction is assigned a `RiskScore` computed from:
- Rule-based heuristics  
- Merchant anomaly cluster distance  
- Customer velocity (transactions per time window)

### 🔹 2. Merchant Anomaly Profiling
Batch job using MLlib KMeans computes:
- Merchant clusters  
- Anomaly distances  
- Behavioral categories  

Stored in `merchant_profiles` Delta table.

### 🔹 3. Velocity-Based Spending Alerts
Spark Streaming computes rolling windows over customer activity to flag:
- Rapid transaction bursts  
- High-transaction-frequency behavior

### 🔹 4. Customer Segmentation
Batch clustering groups customers by:
- Spending frequency  
- Average amount  
- Category mix  

### 🔹 5. Merchant–Customer Graph Analytics
GraphFrames generates:
- PageRank scores  
- Connected components  
- Community structures  

Useful for identifying coordinated fraud rings.

### 🔹 6. Unified Dashboard
Displays:
- Real-time risk feeds  
- Merchant anomaly profiles  
- Customer segments  
- Network graph outputs  

---
