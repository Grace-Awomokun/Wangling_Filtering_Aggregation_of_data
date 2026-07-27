# Understanding Data Wrangling, Filtering, and Aggregation

This project demonstrates how to work with, clean, and query datasets in Python. In this notebook, we focus on extracting meaningful insights from messy data through targeted subsetting, filtering, and aggregation.

## Datasets Included
* **Nigeria Economic Data**
* **Nigeria Nursing Mothers Healthcare Data**
* **Nigeria Unemployment Data**

## Project Overview
We use Python, Pandas, and Google Colab to understand the fundamentals of data wrangling, filtering, and aggregation.

### Key Objectives
1. **Load and inspect datasets** from various sources.
2. **Analyze and query datasets** to find solutions to specific scenarios.
3. **Filter and subset data** to isolate demographic segments of interest.
4. **Visualize results** to explain findings clearly.

---

## 📝 Notebook Walkthrough

### 1. What is Data Wrangling?
Data wrangling is the process of taking messy data and transforming it into an organized format. 
The superpower of data wrangling is **data filtering**, which is essential in machine learning workflows. Filtering allows us to:
* Remove logical impossibilities.
* Extract target slices by selecting only the specific subset of the dataset needed for analysis.

### 2. Scenario 1: Analyzing Nigerian Nursing Mothers
We want to understand the healthcare challenges faced by the **poorest mothers living in rural areas**.

#### Step 2.1: Import Dependencies
First, we import the required libraries.
```python
import pandas as pd
```

#### Step 2.2: Load & Preview the Dataset
We load the healthcare dataset containing records of 10,000 nursing mothers.
```python
# Upload the dataset of interest
health_data = pd.read_csv('/nigeria_nursing_mothers_healthcare.csv')
health_data.head()
```

##### Output Preview:
| | Geopolitical_Zone | Residence | Wealth_Quintile | Education_Level | Skilled_Birth_Attendance | Facility_Delivery | Exclusive_Breastfeeding | Full_Immunization | Distance_to_Facility_km |
|---|---|---|---|---|---|---|---|---|---|
| **0** | North East | Rural | Middle | Primary | 1 | 1 | 1 | 0 | 9.35 |
| **1** | South East | Urban | Richest | Higher | 1 | 1 | 1 | 1 | 1.99 |
| **2** | North Central | Urban | Richer | Primary | 1 | 1 | 0 | 0 | 0.95 |
| **3** | North Central | Rural | Poorest | Primary | 1 | 1 | 0 | 0 | 15.22 |
| **4** | North East | Urban | Richer | Secondary | 1 | 0 | 1 | 0 | 1.10 |

#### Step 2.3: Subsetting & Filtering
We create a targeted subset (`targeted_mothers`) of the data by filtering for mothers where the `Residence` is **Rural** and their `Wealth_Quintile` is **Poorest**.
```python
# Create a new dataset from the existing one (called subsetting)
targeted_mothers = health_data[(health_data['Residence'] == 'Rural') & (health_data['Wealth_Quintile'] == 'Poorest')]
```

#### Step 2.4: Verify Subset Size
We print the length of both dataframes to verify the filtering.
```python
print(f"Original dataset size:", len(health_data))
print(f"New dataset size:", len(targeted_mothers))
```

##### Output:
```text
Original dataset size: 10000
New dataset size: 1866
```

---

## 🛠️ Tools Used
* **Languages:** Python
* **Libraries:** Pandas, Matplotlib
* **Environment:** Google Colab / Jupyter Notebooks

## 👤 Author
**Grace Dolapo Awomokun**
