# 🚚 Delhivery Logistics Data Analysis & Feature Engineering

![Python](https://img.shields.io/badge/Python-Data%20Analysis-blue) ![Pandas](https://img.shields.io/badge/Pandas-Data%20Manipulation-purple) ![Feature Engineering](https://img.shields.io/badge/Feature%20Engineering-Analytics-orange) ![Status](https://img.shields.io/badge/Project-Completed-success)

## 📊 Project Overview

An end-to-end **logistics data analysis and feature-engineering case study** based on Delhivery trip-level operational data.

The project focuses on transforming raw logistics and routing data into structured analytical features for **delivery-performance and operational analysis**.

**Raw Operational Data → Data Cleaning → Grain Control → Trip-Level Aggregation → Feature Engineering → Operational Analysis**

## 🎯 Business Problem

The objective is to understand and process data generated through logistics operations and convert raw operational fields into useful analytical features.

The analysis focuses on:
- Understanding the correct analytical grain
- Cleaning and structuring operational data
- Consolidating records belonging to the same trip
- Extracting geographic information from source and destination fields
- Creating time-based features from timestamps
- Comparing actual operational performance with routing-system estimates
- Preparing a structured dataset for downstream analytics

## 📁 Dataset

The dataset contains **144,867 operational records representing 14,817 unique trips** across approximately **27 days of operations (12 September 2018 to 8 October 2018)**.

The data includes trip creation timestamps, route schedules, trip identifiers, source and destination centres, route type, operational timestamps, actual distance/time, OSRM-estimated distance/time and segment-level operational metrics.

### Core Fields

| Field | Purpose |
|---|---|
| trip_creation_time | Trip creation timestamp |
| route_schedule_uuid | Route-schedule identifier |
| route_type | Transportation / route type |
| trip_uuid | Trip identifier |
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

A key part of the project is distinguishing **raw operational records from the complete trip**.

Multiple operational records can belong to the same trip, so trip-level aggregation is required before deriving final trip-level metrics.

This helps avoid:
- Duplicate trip counts
- Inflated distance/time metrics
- Incorrect averages
- Misleading route comparisons

## 🧹 Data Preparation

The notebook includes:

- Dataset profiling and structure review
- Data-type and timestamp conversion
- Missing-value assessment and handling
- Duplicate-record checks
- Category and numeric field standardisation
- Trip-level aggregation
- Final feature preparation

### Data Quality Findings

- **293 source-name values** were missing.
- **261 destination-name values** were missing.
- Each missing-value category represents **less than 0.3%** of the 144,867 records.
- **No duplicate records** were identified in the analysis.
- After preprocessing, the analytical dataset contains **19 features** with the required fields completed.

## 🛠️ Feature Engineering

### 📍 Geographic Features

Source and destination location strings are parsed into usable dimensions such as **city, place code and state/region**.

The dataset contains more than **1,500 source/destination logistics-centre locations**, providing a broad geographic basis for operational analysis.

### 🕒 Time Features

Timestamp fields are transformed into features such as:
- Year
- Month
- Day
- Trip duration
- Operational time measures

### ⏱️ Delivery / Trip Duration

Duration features are derived from operational timestamps and compared with existing scan-to-scan measures for validation.

### 🛣️ Actual vs Routing Performance

The project compares:
- Actual distance vs OSRM distance
- Actual time vs OSRM time
- Segment actual time vs segment OSRM time

This provides a direct view of the gap between **observed operational performance and routing-system estimates**.

## 📈 Key Analytical Findings

### 1. Actual trip time is substantially higher than OSRM time

- Average actual trip time: **417 minutes**
- Average OSRM estimated time: **214 minutes**

The observed average actual trip time is therefore approximately **1.95× the OSRM estimate**, indicating a material gap between routing estimates and observed operational duration.

**Business implication:** Actual operational time should be evaluated separately from routing estimates when analysing delivery performance and planning operational capacity.

### 2. Actual distance is lower than OSRM estimated distance

- Average actual distance: **234 km**
- Average OSRM estimated distance: **285 km**

The average observed distance is approximately **18% lower** than the OSRM estimated distance.

**Business implication:** Distance estimates and observed operational distance should not be treated as interchangeable measures when analysing route efficiency.

### 3. Large operational footprint

The dataset contains more than **1,500 source/destination logistics-centre locations**, providing a broad base for analysing geographic and route-level operational patterns.

**Business implication:** The dataset can support deeper analysis of source hubs, destination hubs, route schedules and geographic differences in operational performance.

### 4. Data quality is broadly controlled

Missing source and destination names are relatively small compared with the overall dataset, and **no duplicate records were identified**.

**Business implication:** The cleaned dataset provides a stronger basis for downstream operational analysis while still requiring validation of location fields before using them for detailed geographic reporting.

## 📊 Business Analysis Opportunities

**Logistics:** delivery duration, route performance, distance and actual-vs-estimated time.

**Geography:** source-region performance, destination-region performance, city/state patterns and route comparisons.

**Route:** route type, route schedules and trip-level performance.

**Operational KPIs:** actual time, estimated time, actual distance, estimated distance and their respective gaps.

## 🔬 Analytical Framework

**Raw Logistics Data → Data Profiling → Data Cleaning → Grain Control → Trip-Level Aggregation → Feature Engineering → Actual vs Estimated Analysis → Operational Insights**

## 🧠 Skills Demonstrated

Python • Pandas • NumPy • Datetime Manipulation • Data Cleaning • Missing-Value Handling • Duplicate Detection • Aggregation • Grain Control • Feature Engineering • Logistics Analytics • Route Analysis • Operational KPI Analysis

## ⚠️ Analytical Considerations

1. Raw operational records should not automatically be treated as independent trips.
2. Trip-level identifiers are important for maintaining the correct analytical grain.
3. Actual and OSRM metrics represent different concepts and should be interpreted separately.
4. Routing estimates should not automatically be treated as operational targets.
5. Geographic fields derived from semi-structured strings should be validated before detailed business use.
6. The observed time and distance gaps are descriptive findings from this dataset and should not be interpreted as causal evidence.

## 📂 Repository Structure

    Delhivery-Logistics-Data-Analysis-and-Feature-Engineering/
    ├── README.md
    ├── Analysis Notebook
    ├── Dataset

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

This project demonstrates how raw logistics data can be transformed into a structured analytical dataset through **data cleaning, grain control, trip-level aggregation and feature engineering**, followed by comparison of observed operational performance with routing-system estimates.

**Understand → Clean → Aggregate → Engineer → Validate → Analyse**
