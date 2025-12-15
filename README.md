# 2026 ASA South Florida Student Data Challenge
## Annoucement: 01/01/2026; Deadline: 02/20/2026

This repository provides the training and test datasets for the American Statistical Association (ASA) South Florida 2026 Student Data Challenge.  
The task is to predict HDL cholesterol from NHANES-based variables or to create visualizations for the high-school division. [html link](https://luminwin.github.io/ASASF/)

---

## Dataset Description

The dataset includes **1,200 individuals** and **97 variables** sampled from the 2024 National Health and Nutrition Examination Survey (NHANES).  
The outcome variable is:

- **LBDHDD_outcome** – a noise-perturbed version of Direct HDL-Cholesterol (mg/dL).  
  This prevents reconstruction of the original NHANES values while preserving realistic structure.

Predictors include:
- Dietary intake from the **24-hour dietary recall interview**  
- Demographics (age, gender, race/ethnicity, income-to-poverty ratio, marital status)  
- Anthropometrics (BMI, waist circumference)  
- Alcohol indicators and diet-behavior variables

**Training:** 1,000 observations  
**Test:** 200 observations  

All variables retain NHANES labels and can be inspected using `attr(x, "label")`.

---

## Downloading the Data in R

```r
### Download Training Data

tmp <- tempfile()
download.file("https://luminwin.github.io/ASASF/train.rds", tmp, mode = "wb")
train <- readRDS(tmp)

### View Variable Labels

lapply(train, attr, "label")

### Download Test Data

download.file("https://luminwin.github.io/ASASF/test.rds", tmp, mode = "wb")
test <- readRDS(tmp)
```

## Competition Tasks

### 1. Prediction Track (Undergraduate and Graduate)

Predict **LBDHDD_outcome** for the test dataset.

## Submission Requirements
- A CSV file named **`pred.csv`**
  - Exactly **one column**, named **`pred`**
  - The number of rows must match the test dataset
  - Predictions must be in the **same order as the test data**

- A PDF report (**maximum 4 pages**) summarizing:
  - Model and preprocessing choices
  - Validation and/or tuning strategy
  - The final model used to generate predictions, including code snippets or a link to the full code repository

**Evaluation:**  
Submissions are ranked by **Root Mean Squared Error (RMSE)** on the test dataset.

---

### 2. Visualization Track (High School)

Submit a **1–4 page PDF** containing:
- At least two clear visualizations based on variables in the training dataset  
- Short explanations describing patterns, trends, or insights  

No modeling is required for this track.

---

## Submission

Submit the following files:
- `pred.csv` (prediction track only)  
- `Name_report.pdf`  
- Optional: source code or notebook files  

Submissions should be uploaded through the designated form or emailed to **asasfchapter@gmail.com**.

---

## Award

- **$200 per winner**, with three winners total: one at the **high school**, **undergraduate**, and **graduate** levels  
- Winners will be recognized and invited to present posters at the **2026 Annual ASA Florida Chapter Meeting**  
- The **top 20%** of participants will receive a certificate of recognition  
- The **top 10%** of participants will receive a waived registration fee for the **2026 Annual ASA Florida Chapter Meeting**

---

## Contact

For questions, please contact Dr Min Lu at **m.lu6@umiami.edu**.


