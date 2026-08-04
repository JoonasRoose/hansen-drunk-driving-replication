# Hansen (2015) Replication and Machine Learning Extension

## Authors

- Joonas Roose
- Talbot Carrie

## Course

EC 410K / EC 610I: Machine Learning in Economics

## Paper

Benjamin Hansen. 2015. *Punishment and Deterrence: Evidence from Drunk Driving.* American Economic Review, 105(4), 1581–1617.

https://doi.org/10.1257/aer.20130189

---

# Project Overview

This repository contains both:

1. A replication of selected results from Hansen (2015).
2. A machine learning extension that applies causal forests to investigate treatment-effect heterogeneity around the legal BAC threshold.

The project was completed as part of the Machine Learning in Economics course.

---

# Replication

The replication reproduces a reduced version of Hansen's Table 2:

> "Regression Discontinuity Estimates for the Effect of Exceeding BAC Thresholds on Predetermined Characteristics."

The analysis estimates local linear regression discontinuity models at the two legal blood alcohol concentration (BAC) thresholds:

- BAC = 0.08
- BAC = 0.15

The replicated predetermined characteristics are:

- Age
- Male
- White
- Accident involvement

Prior BAC history and portable breath-test (PBT) variables included in Hansen (2015) are unavailable in the modified dataset supplied for this assignment.

---

# Machine Learning Extension

The extension builds on the original regression discontinuity design by estimating heterogeneous treatment effects using honest causal forests implemented through the `CausalForestDML` estimator from Microsoft's EconML package.

The extension examines whether the deterrence effect varies according to:

- Age
- Gender
- Race
- Accident involvement
- Year

Additional analyses include:

- Single-characteristic causal forests
- Nested causal-forest specifications
- Treatment-effect profile estimation
- Bandwidth sensitivity analysis
- Statistical comparison with Hansen's published estimates

---

# Research Design

The conventional regression discontinuity specification estimates

\[
Y_i=\alpha+\beta D_i+\gamma(BAC_i-c)+\delta D_i(BAC_i-c)+\varepsilon_i
\]

where

- \(Y_i\) is the outcome variable,
- \(D_i\) equals one if BAC exceeds the legal threshold,
- \(c\) is either 0.08 or 0.15,
- \(\beta\) measures the treatment effect at the threshold.

The machine learning extension preserves the regression discontinuity design while allowing treatment effects to vary across observed characteristics using causal forests.

---

# Repository Structure

```text
hansen-drunk-driving-replication/
│
├── README.md
│
├── code/
│   ├── Hansen_extension.ipynb
│   ├── Replication_and_Causal_ML_Extension.ipynb
│   └── Replication_assignment (1).ipynb
│
├── data/
│   └── modified_hansen_data.csv
│
├── output/
│   ├── figures/
│   └── tables/
│       ├── reduced_table2_replication.csv
│       └── tables.zip
│
└── report/
    ├── Machine_Learning_Final_Project.pdf
    └── ML_Replication_Project.pdf
```

---

# Running the Code

## Replication

Open

```
code/Replication_assignment (1).ipynb
```

and run all cells.

This notebook reproduces the reduced version of Hansen's Table 2.

---

## Machine Learning Extension

Open

```
code/Hansen_extension.ipynb
```

(or alternatively `Replication_and_Causal_ML_Extension.ipynb` if you wish to reproduce the complete workflow.)

Run all notebook cells from top to bottom.

The notebook produces:

- replication tables
- causal forest estimates
- treatment-effect profiles
- bandwidth sensitivity analyses
- comparison tables
- publication-ready figures

Outputs are automatically written to the `output/` directory.

---

# Software

The project was developed in Python using:

- pandas
- numpy
- matplotlib
- scipy
- statsmodels
- EconML
- scikit-learn

---

# Reports

The final research report is located in

```
report/Machine_Learning_Final_Project.pdf
```

and documents the replication, machine learning extension, empirical findings, and policy interpretation.

---

# License

This repository is intended solely for educational purposes as part of the Machine Learning in Economics course.
