# 🚚 Delhivery Logistics Data Analysis & Feature Engineering

![Python](https://img.shields.io/badge/Python-Data%20Analysis-blue) ![Pandas](https://img.shields.io/badge/Pandas-Data%20Manipulation-purple) ![Feature Engineering](https://img.shields.io/badge/Feature%20Engineering-Analytics-orange) ![Status](https://img.shields.io/badge/Project-Completed-success)

## 📊 Project Overview

An end-to-end **logistics data analysis and feature-engineering case study** based on Delhivery trip-level operational data.

The project focuses on transforming raw logistics and routing data into structured analytical features that can support **delivery-performance analysis and downstream data-science / forecasting use cases**.

**Raw Operational Data → Data Cleaning → Aggregation → Feature Engineering → Operational Analysis → Data-Science Readiness**

## 🎯 Business Problem

The objective is to understand and process data generated through logistics data pipelines and convert raw operational fields into useful analytical features.

The analysis focuses on:
- Understanding the correct analytical grain
- Cleaning and structuring operational data
- Consolidating records belonging to the same trip
- Extracting geographic information from source and destination fields
- Creating time-based features from timestamps
- Comparing actual operational performance with routing-system estimates
- Preparing useful features for downstream forecasting or machine-learning work

## 📁 Dataset

The dataset contains trip-level logistics information covering trip creation timestamps, route schedules, trip identifiers, source and destination centres, route type, operational timestamps, actual distance/time, OSRM-estimated distance/time and segment-level operational metrics.

### Core Fields

| Field | Purpose |
|---|---|
| trip_creation_time | Trip creation timestamp |
| route_schedule_uuid | Route-schedule identifier |
| route_type | Transportation / route type |
| trip_uuid | Unique trip identifier |
| source_center / source_name | Source information |
| destination_center / destination_name | Destination information |
| od_start_time / od_end_time | Origin-destination timestamps |
| start_scan_to_end_scan | Scan-to-scan duration |
| actual_distance_to_destination | Actual distance |
| actual_time | Actual operational time |
| osrm_time / osrm_distance | Routing-engine estimates |
| segment_actual_time | Segment-level actual time |
| segment_osrm_time / segment_osrm_distance | Segment-level routing estimates |

## 🧩 Analytical Grain

A key part of the project is distinguishing **raw operational records from the complete trip**. Multiple records can belong to the same trip, so trip-level aggregation is required before deriving final operational metrics.

This helps avoid duplicate trip counts, inflated distance/time metrics, incorrect averages and misleading route comparisons.

## 🧹 Data Preparation

- Dataset profiling and structure review
- Data-type and timestamp handling
- Missing-value handling where appropriate
- Operational consistency checks
- Trip-level aggregation

## 🛠️ Feature Engineering

### 📍 Geographic Features

Source and destination location strings are parsed into usable dimensions such as **city, place code and state/region**.

### 🕒 Time Features

Timestamp fields are transformed into features such as **year, month, day and trip duration**.

### ⏱️ Delivery Duration

A duration feature is derived from origin-destination start and end timestamps and compared with the existing scan-to-scan duration for operational validation.

### 🛣️ Actual vs Routing Performance

The project compares:
- Actual distance vs OSRM distance
- Actual time vs OSRM time
- Segment actual time vs segment OSRM time

This creates a foundation for analysing the gap between **estimated routing performance and observed operational performance**.

## 📈 Business Analysis Opportunities

**Logistics:** delivery duration, route performance, distance and actual-vs-estimated time.

**Geography:** source-region performance, destination-region performance, city/state patterns and route comparisons.

**Route:** Carting vs FTL, route schedules and trip-level performance.

**Data Science:** time, geographic, distance, route and actual-vs-estimated performance features suitable for downstream modelling.

## 🔬 Analytical Framework

**Raw Logistics Data → Data Profiling → Data Cleaning → Trip-Level Aggregation → Feature Engineering → Actual vs Estimated Analysis → Model-Ready Dataset**

## 🧠 Skills Demonstrated

Python • Pandas • NumPy • Datetime Manipulation • Data Cleaning • Aggregation • Grain Control • Feature Engineering • Logistics Analytics • Route Analysis • Operational KPI Thinking • Model-Ready Data Preparation

## ⚠️ Analytical Considerations

1. Raw operational records should not automatically be treated as independent trips.
2. Trip-level identifiers are important for correct analytical grain.
3. Actual and OSRM metrics represent different concepts and should be interpreted accordingly.
4. Routing estimates should not automatically be treated as operational targets.
5. Geographic fields derived from semi-structured strings should be validated before business use.

## 📂 Repository Structure

    Delhivery-Business-Case-Study---Feature-Engineering/
    ├── README.md
    ├── Analysis Notebook
    ├── Dataset / Reference Files
    └── Supporting Analysis

## 🛠️ Technology Stack

| Tool | Purpose |
|---|---|
| Python | Data analysis and feature engineering |
| Pandas | Data manipulation and transformation |
| NumPy | Numerical operations |
| Jupyter / Google Colab | Analysis environment |
| GitHub | Version control and portfolio documentation |

## 👤 Author

**Vijay Kumar**  
Data Analytics | Python | Pandas | Feature Engineering | Business Analytics

## ⭐ Project Summary

This project demonstrates how raw logistics data can be transformed into a structured analytical dataset through **data cleaning, grain control, aggregation and feature engineering**.

**Understand → Clean → Aggregate → Engineer → Validate → Analyse**
