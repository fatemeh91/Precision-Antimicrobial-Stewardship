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

The Recursive Feature Elimination (RFE) approach was used to remove features with low predictive value (validation set was used to select optimal features).

5-fold cross-validation with random search was used to optimize hyperparameters.

The AUC for each antibiotic, with and without the history of prior microbial resistance in the last 6 months, is provided in Figure 1.

Approach 2:
