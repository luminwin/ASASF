# 2026 ASA South Florida Student Data Challenge

This repository provides the training and test datasets for the ASA South Florida 2026 Student Data Challenge.  
The task is to predict HDL cholesterol from NHANES-based variables or to create visualizations for the high-school division.

---

## Dataset Description

The data consist of **1,200 individuals** sampled from the 2024 NHANES.  
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

**Submission requirements:**
- A CSV file named **`pred.csv`**
- Exactly **one column**, named **`pred`**
- The number of rows must match the test dataset
- Predictions must be in the **same order as the test data**
- A **2-page PDF report** summarizing:
  - Model and preprocessing choices  
  - Validation or tuning strategy  
  - Final model used for generating predictions  

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

## Contact

For questions, please contact the ASA South Florida Data Challenge Committee at **asasfchapter@gmail.com**.


