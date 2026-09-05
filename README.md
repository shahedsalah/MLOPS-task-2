# MLOPS-task-2

# 📦 E-Commerce Delivery Delay Intelligence & MLOps Pipeline

An end-to-end Machine Learning and MLOps production pipeline designed to predict late shipments (`is_late`) in e-commerce fulfillment. This repository implements strict reproducibility guidelines, robust data integrity checks, and a structured, modular workflow from raw data ingestion to artifact persistence and threshold-tuned inference[cite: 1].

---

## 🏗️ Architectural Workflow & Notebook Pipeline

The project lifecycle is decoupled into six sequential, well-documented stages to ensure strict separation of concerns and eliminate data leakage:

1. **Notebook 1 — Data Ingestion & Relational Merging**
   * Aggregates and joins raw relational tables (Orders, Items, Payments) to establish a granular, order-level unified dataset[cite: 1].

2. **Notebook 2 — Target Engineering & Class Imbalance Assessment**
   * Derives the binary target label (`is_late`) by comparing actual delivery timestamps against estimated deadlines, quantifying the inherent class distribution skew.

3. **Notebook 3 — Rigorous Data Splitting (Train, Validation, Test)**
   * Partitions datasets prior to exploratory analysis or transformation to protect validation/test boundaries, preserving class distributions across splits.

4. **Notebook 4 — Exploratory Data Analysis & Feature Diagnostics (EDA)**
   * Conducts comprehensive statistical profiling exclusively on the training partition—evaluating missingness topologies, feature distributions, cardinalities, and temporal/geospatial correlations.

5. **Notebook 5 — Feature Engineering & Stateful Preprocessing**
   * Implements domain-driven feature extraction, handles missing values, and executes stateful transformations (Scaling, Encoding) fitted **strictly** on training subsets and serialized safely via modular artifacts.

6. **Notebook 6 — Model Training, Hyperparameter Tuning & Evaluation**
   * Establishes robust baseline metrics, trains predictive models utilizing class-weight optimization, and applies decision threshold tuning to maximize recall for minority-class detection without compromising reliability.

---

## 🛠️ Tech Stack & Tooling

* **Language:** Python[cite: 1]
* **Data Processing:** Pandas, NumPy[cite: 1]
* **Machine Learning:** Scikit-Learn[cite: 1]
* **Serialization:** Joblib (Artifact management)[cite: 1]



---
*Designed with enterprise MLOps principles to ensure zero data leakage, artifact reproducibility, and robust generalization.*
