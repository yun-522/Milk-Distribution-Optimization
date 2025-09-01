# Milk Distribution Optimization in NSW

## Overview  
This project was developed as part of an **individual academic project** in *QBUS2310 Management Science* at the University of Sydney. The task was to advise the NSW state government on where to build up to three new **milk distribution centers**.  

The model applies **Mixed Integer Programming (MIP)** in Python with Gurobi to minimize costs and delivery time, while accounting for demand, capacity, and demographic trends.  

The work showcases how **optimization can guide government policy and logistics planning**, particularly for perishable goods like milk.

---

## Objectives  

### Assignment 1 — Base Model (2001 & 2006 Data)  
Formulated and solved the **core milk distribution optimization problem** for NSW.  

- Build a **Mixed Integer Programming (MIP)** model to locate up to **3 distribution centers (DCs)**.  
- Ensure **fairness constraints**:  
  - No single DC serves >50% of NSW demand.  
  - Maximum of 3 DCs total.  
- Objective: **minimize total cost**, including:  
  - Transport cost (distance × demand).  
  - Establishment cost of new DCs (capacity-dependent).  
- Conducted **scenario testing** using **2001 and 2006 datasets**.  

---

### Assignment 2 — Extended Model (2021 Data & Beyond)  
Extended the base model to incorporate **real-world logistics and policy trade-offs**.  

- **Tankers & Capacity:** Decision variables for tanker purchase and allocation.  
- **Delivery Time:** Multi-objective optimization (minimize cost *and* delivery time for freshness).  
- **Population Growth:** Sensitivity analysis with **10% annual growth** over 3 years.  
- **Inflation:** Adjusted costs using **55.6% inflation (2001–2021)**.  
- **2021 Data Application:** Evaluated DC placement with updated demand.  

---

## Tech Stack  
- **Language:** Python  
- **Solver:** Gurobi Optimizer (v10.0.2)  
- **Libraries:** `gurobipy`, `numpy`, `pandas`  
- **Data Sources:** 
- [ABS Regional Population by Age and Sex](https://www.abs.gov.au/statistics/people/population/regional-population-age-and-sex/latest-release#data-downloads)  
- [ABS Census Data by Area](https://www.abs.gov.au/census/find-census-data/search-by-area?opendocument&navpos=220)  
- RDI Calcium Intake Data — provided in QBUS2310 course materials (University of Sydney)  
- Synthetic LGA distance data — generated using Python random number functions for modeling purposes  
- **Population Demand Datasets (2001, 2006, 2021)** — provided in *QBUS2310 Management Science* course materials (University of Sydney).  
  Due to licensing restrictions, the full datasets are available only in PDF format (not included here).  
  To illustrate the structure, sample CSVs (first 5 rows) are provided:  
  - [2001 Sample Dataset (CSV)](./data/sample_population_demand_2001.csv)  
  - [2006 Sample Dataset (CSV)](./data/sample_population_demand_2006.csv)  
  - [2021 Sample Dataset (CSV)](./data/sample_population_demand_2021.csv)  

---

## Repository Structure  
milk-distribution-optimization/  
│── [data/](./data)               # Population, RDI, and synthetic distance datasets (PDFs)  
│── [assignment1(code+report).pdf](./assignment1(code+report).pdf)   # Assignment 1 notebook (code + report)  
│── [assignment2(code+report).pdf](./assignment2(code+report).pdf)   # Assignment 2 notebook (code + report + extensions)  
│── [README.md](./README.md)      # Project description  

---

## Key Results  
### Assignment 1 — Base Model (2001 & 2006 Data)  
- **2001 Model:** Optimal centers at *Port Macquarie-Hastings*, *Sydney*, and *Temora*.  
  - Total cost: **AUD 18,098.71**
- **2006 Model:** Cost rises slightly to **AUD 18,143.84**, still optimal at the same 3 locations
- **2021 Model (without inflation):** **AUD 21,611.41**; with inflation: **AUD 33,627.36**
- **Sensitivity (10% annual population growth):** Costs rise to **AUD 19,908.59 (Year 1)**, **AUD 21,899.44 (Year 2)**, and **AUD 24,089.39 (Year 3)**
- **Tankers + Time Objective:** Optimal build in *Sydney*, *Temora*, *Woollahra* with 33 tankers in total; minimum cost ~**AUD 4.14M**

### Assignment 2 — Extended Model (2021 Data & Beyond)  
- **Tankers + Time Objective (Cost Focus):**  
  - Selected DCs: *Sydney*, *Temora*, *Woollahra*  
  - Tanker allocation:  
    - Sydney: 11 tankers  
    - Temora: 12 tankers  
    - Woollahra: 10 tankers  
  - Minimum cost: **AUD 4,143,722.31**  
- **Tankers + Time Objective (Time Focus):**  
  - Minimum total delivery time: **4,524.68 hours**  

---

## Insights  
- Optimal site selection remained consistent despite growth, showing **robustness**.  
- Inflation had a **major long-term cost impact**, doubling effective costs between 2001–2021.  
- Multi-objective optimization highlighted trade-offs between **efficiency (cost)** and **freshness (time)**.  
- Sensitivity analysis confirmed the model’s adaptability to population increases.  



