# Invigilator Assignment Optimization

Multi-objective CP-SAT optimization model for university exam invigilator assignment scheduling.

---

## Overview

This project addresses the **Invigilator Assignment Problem (IAP)** using mathematical optimization techniques.

The goal is to assign invigilators to examination shifts while satisfying operational constraints and optimizing multiple objectives such as:

- workload fairness,
- travel minimization,
- fatigue reduction,
- payroll cost,
- invigilator preferences.

The optimization model is implemented using **Google OR-Tools CP-SAT Solver**.

---

## Problem Description

University examination scheduling is a complex resource-allocation problem involving:

- multiple campuses,
- overlapping time slots,
- different invigilator tiers,
- workload limits,
- operational constraints.

The problem belongs to the class of **Constraint Satisfaction Problems (CSP)** and is NP-hard in nature.

---

## Optimization Objectives

The model minimizes a weighted multi-objective function consisting of:

| Objective | Description |
|---|---|
| Fairness | Balance workload among invigilators |
| Travel | Reduce cross-campus assignments |
| Fatigue | Avoid same-day double shifts and long consecutive work streaks |
| Payroll Cost | Minimize operational payroll cost |
| Preference Satisfaction | Reward preferred assignments |

---

## Mathematical Model

### Decision Variables

| Variable | Meaning |
|---|---|
| x[i,j,r] | 1 if invigilator *i* is assigned to role *r* at shift *j* |
| y[i,d] | 1 if invigilator *i* works on day *d* |
| z[i,d] | 1 if invigilator *i* works multiple shifts on day *d* |
| w[i,d] | 1 if invigilator *i* works 3 consecutive days |

---

### Hard Constraints

- Shift demand satisfaction
- Eligibility constraints
- No overlapping assignments
- One role per shift
- Workload cap per invigilator tier

---

### Soft Constraints

- Minimize cross-campus travel
- Minimize fatigue
- Minimize payroll cost
- Maximize invigilator preference satisfaction

---

## Technologies Used

- Python
- OR-Tools CP-SAT
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook

---

## Project Structure

```text
AS_MM/
│
├── data/
├── figures/
├── outputs/
├── .gitignore
├── invigilator_assignment_optimization.ipynb
├── LICENSE
├── README.md
└── requirements.txt
