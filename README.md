# Milk Distribution Optimization in NSW

## Overview  
This project was developed as part of an **individual academic project** in *QBUS2310 Management Science* at the University of Sydney. The task was to advise the NSW state government on where to build up to three new **milk distribution centers**.  

The model applies **Mixed Integer Programming (MIP)** in Python with Gurobi to minimize costs and delivery time, while accounting for demand, capacity, and demographic trends.  

The work showcases how **optimization can guide government policy and logistics planning**, particularly for perishable goods like milk.

---

## Objectives  
1. **Minimize distribution costs**  
   - Cost of transporting milk between LGAs based on distance and demand  
   - Cost of establishing new centers (capacity-dependent)  
   - Cost of purchasing tanker trucks  

2. **Ensure fairness & feasibility**  
   - No center >50% of state demand  
   - Maximum of 3 distribution centers  

3. **Extend the model**  
   - Sensitivity analysis for 10% annual population growth  
   - Impact of inflation (55.6% between 2001–2021)  
   - Multi-objective optimization (cost vs. delivery time)  
   - Tanker allocation and spoilage risk  

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
- **Population Demand Datasets (2001, 2006, 2021)** — provided in *QBUS2310 Management Science* course materials (University of Sydney), available in PDF format: 
  - [2001 Population & Demand Dataset (PDF)](./data/population_demand_2001.pdf)  
  - [2006 Population & Demand Dataset (PDF)](./data/population_demand_2006.pdf)  
  - [2021 Population & Demand Dataset (PDF)](./data/population_demand_2021.pdf)  

---

## Repository Structure  
milk-distribution-optimization/  
│── data/               # Population, RDI, and synthetic distance datasets (PDFs)  
│── assignment1/        # HTML notebook for Assignment 1 (code + report)  
│── assignment2/        # HTML notebook for Assignment 2 (code + report + extensions)  
│── README.md           # Project description  


