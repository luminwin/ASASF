# ASA South Florida Student Data Challenge

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

### Training Data
```r
tmp <- tempfile()
download.file("https://luminwin.github.io/ASASF/train.rds", tmp, mode = "wb")
train <- readRDS(tmp)
```