# Actividad 1: HDFS, Spark SQL y MLlib

## Overview

This activity consists of analyzing flight delay data using distributed storage (HDFS) and distributed processing with Apache Spark on Google Cloud Dataproc.

**Note:** The notebook (`actividad_1.ipynb`) is written in Spanish, as it is the vehicular language of the course.

## Technologies Used

- **Google Cloud Dataproc** - Managed Hadoop/Spark cluster
- **HDFS** - Distributed file storage
- **PySpark** - Data processing and ML
- **JupyterLab** - Interactive notebook environment

## Setup & Execution

1. A **Google Cloud Dataproc cluster** was created with JupyterLab, Zookeeper and Kafka components
2. The dataset `flights.csv` was uploaded to **HDFS** at `/alexr/flights.csv`
3. The notebook `actividad_1.ipynb` was executed in JupyterLab
4. All data processing (cleaning, analysis, and ML) was done using PySpark

## Summary of Tasks

- Data cleaning (removing NA values and casting columns to correct types)
- Analysis of distinct airports and routes
- Average delay calculation per destination airport
- Binary classification model using DecisionTreeClassifier to predict flight delays (>15 min)

## Results

- **Model accuracy:** ~85.3%
- **Most delayed airports:** BOI (64.75 min), HDN (46.8 min), SFO (41.19 min)

## Author

Alex Rubiño Fernández