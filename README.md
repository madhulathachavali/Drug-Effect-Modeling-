# Pharmacokinetic and Pharmacodynamic (PK/PD) Modeling of Drug Effects Using Emax Model

To analyze and model a drug's pharmacokinetics (PK) and pharmacodynamics (PD) using a dataset of simulated drug effects over time, employing an Emax model to understand drug efficacy and optimize dosing schedules.

---

## Data Description

The dataset contains 700 rows and 15 columns.

## Features

ID: The patient ID.

TIME: The time point for the measurement or dosing event.

NOMTIME: Nominal time (the time point as intended or planned).

TIMEUNIT: Unit of time (e.g., Hours).

AMT: The amount of drug administered (Dose).

LIDV: Drug concentration at the specified time point.

CMT: Compartment number (if more than one compartment model is being used).

NAME: Event type (e.g., PK concentration or dosing).

EVENTU: The unit of measurement for the event (e.g., ng/mL for concentration).

CENS: Censoring flag (0 = not censored, 1 = censored).

EVID: Event ID (1 = dosing event, 0 = measurement event).

WEIGHTB: Patient weight.

SEX: Patient sex.

TRTACT: Treatment information (e.g., drug type, dosage).

DOSE: Dose amount.

### Data source: https://opensource.nibr.com/xgx/PKPD_Datasets.html

---

## Analysis

This dataset contains 100 missing values, which have been excluded from the analysis

## Time vs. Drug effect

The PK concentration vs. time graph shows distinct gender differences. In females, the drug peaks at 60 ng/mL at time 0, declines to 28 ng/ml at 4 hours and 10 ng/mL at 12 hours, and is nearly eliminated after 36 hours. In males, the concentration peaks at 15 ng/mL at 4 hours and decreases slowly around 24 hours.

<img width="814" alt="image" src="https://github.com/user-attachments/assets/21f4f1bc-f62c-4e95-a8eb-fe83953a07d6" />


## PK/PD Modeling

The initial concentration (A = 6.58) indicates that the dose administered resulted in a relatively high drug concentration at the time of dosing.

The elimination rate constant (k = 0.07) indicates that the drug is being eliminated at a moderate rate, suggesting the drug will remain in the system for some time before being completely cleared.

<img width="819" alt="image" src="https://github.com/user-attachments/assets/afad3a54-ab17-4c40-bf87-4a25f9476524" />

## PK/PD Modeling with Emax Model 

PK/PD Modeling with Emax Model is used to quantify the drug effect as a function of drug concentration

The PK/PD simulation using an Emax model demonstrated a rapid onset of drug effect, with the maximum observed effect of 50% occurring at 2.5 hours after initial administration. Fluctuations in the effect were observed during the first 10 hours, likely due to repeated dosing, with subsequent periodic spikes at intervals of approximately 8 hours. The therapeutic effect (>10%) persisted for 15 hours, after which the effect diminished steadily, stabilizing below 5% after 24 hours. The observed pattern suggests a significant decline in drug activity over time, consistent with elimination or reduced receptor interaction

<img width="819" alt="image" src="https://github.com/user-attachments/assets/3a4d6f5e-8187-4ace-9094-b2c2ce712a0f" />


## Validation

Compare observed vs. predicted effects to assess the model's accuracy.

<img width="629" alt="image" src="https://github.com/user-attachments/assets/62473662-573f-4f62-add3-fe65b48afe02" />

Residual Analysis

<img width="632" alt="image" src="https://github.com/user-attachments/assets/29af3dcd-19fe-4cea-9d52-ecf5494dafe3" />


## Model Performance

| Metric                  | Value                         |
|-------------------------|-------------------------------|
| Mean Squared Error (MSE) | 3.1632489831555417e-16        |
| R-Squared               | 1.0                           |
