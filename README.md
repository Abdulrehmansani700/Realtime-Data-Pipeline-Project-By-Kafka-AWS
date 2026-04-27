# 📈 Real-Time Stock Market Data Pipeline using Kafka & AWS

`This project demonstrates an end-to-end Real-Time Data Engineering pipeline. It ingests simulated stock market data, processes it via **Apache Kafka** on **AWS EC2**, and stores it in **AWS S3** for downstream analytics using **AWS Glue** and **Athena**.`

---

## 🏗️ Architecture Overview

The pipeline follows a structured flow from data generation to cloud-based analytics:

1.  **Data Source:** A Python-based simulator reads historical stock data from a **CSV File**.
2.  **Producer:** The Python producer sends this data in real-time to an **Apache Kafka** cluster.
3.  **Broker (EC2):** Apache Kafka is hosted on an **AWS EC2 Instance**, managing the data streams.
4.  **Consumer:** A Kafka consumer retrieves the data and writes it directly to an **Amazon S3 Bucket**.
5.  **Data Cataloging:** **AWS Glue Crawler** scans the S3 bucket to infer the schema and update the **AWS Glue Data Catalog**.
6.  **Analytics:** **Amazon Athena** is used to run SQL queries on the data stored in S3 for instant insights.

---

## 🛠️ Tech Stack

* **Language:** Python 🐍
* **Streaming:** Apache Kafka 🚀
* **Cloud Provider:** Amazon Web Services (AWS) ☁️
    * **EC2:** For hosting Kafka & Zookeeper.
    * **S3:** As a Data Lake for storage.
    * **Glue:** For ETL and Data Cataloging.
    * **Athena:** For serverless SQL analytics.

---

## 🚀 Key Features

* **Real-Time Ingestion:** Simulated real-time data flow with low latency.
* **Scalable Infrastructure:** Designed to handle high-throughput data using Kafka.
* **Serverless Analytics:** Leveraging AWS Glue and Athena for cost-effective data exploration.
* **Automated Schema Discovery:** Crawlers automatically manage table schemas.

---

## 📁 Project Structure

```text
├── Data_Source/
│   └── index_data.csv          # Historical stock data
├── Kafka_Scripts/
│   ├── producer.py             # Sends data to Kafka topic
│   └── consumer.py             # Reads data and uploads to S3
├── Architecture_Diagram/
│   └── Stock_Market_Kafka_Architecture.jpg
└── README.md
