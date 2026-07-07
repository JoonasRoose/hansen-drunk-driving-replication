# Replication Assignment: Hansen (2015) Table 2

## Authors

- Joonas Roose  
- Talbot Carrie  

## Course

EC 410K / EC 610I: Machine Learning in Economics

## Paper

Benjamin Hansen. 2015. “Punishment and Deterrence: Evidence from Drunk Driving.” *American Economic Review*, 105(4): 1581–1617.  
https://doi.org/10.1257/aer.20130189

## Replicated Result

This project replicates a reduced version of Table 2 from Hansen (2015), titled:

> “Regression Discontinuity Estimates for the Effect of Exceeding BAC Thresholds on Predetermined Characteristics.”

The original table tests whether drivers immediately below and above Washington State’s legal blood alcohol content (BAC) thresholds are similar in predetermined characteristics. This is an important validity test for the paper’s regression discontinuity design.

The replication estimates local linear regression discontinuity models at:

- BAC = 0.08: the standard DUI threshold
- BAC = 0.15: the aggravated DUI threshold

The replicated outcomes are:

- Male
- White
- Age
- Accident involvement

The original paper also includes prior BAC-test history and portable breath-test (PBT) results. Those variables are not available in the modified dataset provided for this assignment. Therefore, this project is a reduced replication of Table 2.

## Research Design

The analysis estimates whether predetermined driver characteristics change discontinuously when BAC crosses a legal threshold.

For each outcome variable, the regression is:

Yᵢ = α + βDᵢ + γ(BACᵢ − c) + δ[Dᵢ(BACᵢ − c)] + εᵢ

where:

- Yᵢ is a predetermined driver characteristic, such as sex, race, age, or accident involvement.
- Dᵢ equals 1 when BAC is at or above the relevant legal threshold.
- BACᵢ − c is BAC centered at the threshold.
- c equals 0.08 or 0.15.
- β measures the discontinuity at the legal BAC threshold.

The analysis uses a bandwidth of 0.05 BAC units around each threshold and clusters standard errors by BAC values measured to 0.001


## How to run code
1. Download or clone this repository.
2. Confirm that `modified_hansen_data.csv` is in the `data/` folder.
3. Open `code/Replication_assignment (1).ipynb`.
4. Run all cells from top to bottom.
5. The output table will be saved to `output/tables/reduced_table2_replication.csv`.
## Repository Structure

```text
replication-assignment/
│
├── README.md
├── requirements.txt
├── AI_DISCLOSURE.md
│
├── code/
│   └── replication_table2.ipynb
│
├── data/
│   └── README.md
│
├── output/
│   └── tables/
│       └── reduced_table2_replication.csv
│
└── report/
    └── Roose_Carrie_ReplicationReport.pdf# hansen-drunk-driving-replication
