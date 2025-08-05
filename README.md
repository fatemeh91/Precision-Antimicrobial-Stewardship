# Precision-Antimicrobial-Stewardship
This project uses AI and machine learning to predict antibiotic resistance patterns from EHR data. By analyzing clinical, demographic, and socioeconomic information, the model accurately predicts resistance during culture collection, improving antibiotic prescribing and supporting antimicrobial stewardship efforts.

## Data Preprocessing
The data used in this project is available at https://doi.org/10.5061/dryad.jq2bvq8kp.
Data preprocessing is provided in the following notebooks:

Inpatient Data Preprocessing: DataPrepration_Inpatient_AllAbx.ipynb

Outpatient Data Preprocessing: DataPrepration_Outpatient_AllAbx.ipynb

## Approach 1:
For each antibiotic, we developed a model to predict patient susceptibility using available EHR data at the time of culture order, including:

  . Clinical vitals from the last 48 hours

  . Lab measurements from the last 14 days

  .  Demographics, prior procedures, and medications from the past 6 months


### Model Development: 

For inpatients we used XGv=boost classifier trained and test on inpatients.
Please Consider:
1. Filter Antibiotics by Prevalence

Include only antibiotics with resistance prevalence ≥ 5% or ≤ 95%.

2. Minimum Sample Size (Exclude antibiotics with fewer than 1,000 records).

3. Deployment Consideration:

Exclude respiratory cultures for real-time model deployment.


#### Outpatient Antimicrobial Susceptibility Model Development: 

Notebook: Aim_1b_ModelDevelopment_Outpatients.ipynb

This notebook contains code for developing machine learning models to predict antimicrobial susceptibility for outpatient data.

Notes and Guidelines

Outpatient susceptibility prediction is more challenging due to data sparsity and lower resistance prevalence. 

Please Consider:

1. Filter Antibiotics by Prevalence

Include only antibiotics with resistance prevalence ≥ 5% or ≤ 95%.

2. Minimum Sample Size (Exclude antibiotics with fewer than 1,000 records).

3. Model Selection

Compare XGBoost and LightGBM models.

Use the model with higher performance for evaluation.

In most cases, performance differences are minimal.

4. Handling Low-Performance or Sparse Antibiotics:

For antibiotics with low model performance or high missingness:

Train on a combined dataset (inpatient + outpatient).

Evaluate performance only on outpatient data.

5. Deployment Consideration:

Exclude respiratory cultures for real-time model deployment.
