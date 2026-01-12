# 2026 ASA South Florida Student Data Challenge
## Deadline: 11:59pm EST, 02/20/2026

[Competition Website](https://luminwin.github.io/ASASF/)
&nbsp;&nbsp;&nbsp;
[Announcement (PDF)](https://luminwin.github.io/ASASF/ASA_South_Florida_Student_Data_Challenge_2026_Call.pdf)
&nbsp;&nbsp;&nbsp;
[Teacher Call – High School](https://luminwin.github.io/ASASF/2026_ASA_South_Florida_High_School_Data_Challenge--teacher-facing.pdf)
&nbsp;&nbsp;&nbsp;
[Flyer – High School](https://luminwin.github.io/ASASF/Flyer-highschool.pdf)
&nbsp;&nbsp;&nbsp;
[Flyer – University](https://luminwin.github.io/ASASF/Flyer-university.pdf)
&nbsp;&nbsp;&nbsp;
[Flyer – All Levels](https://luminwin.github.io/ASASF/Flyer-all.pdf)


This repository provides the training and test datasets for the American Statistical Association (ASA) South Florida 2026 Student Data Challenge.  
The task is to predict HDL cholesterol from NHANES-based variables or to create visualizations for the high-school division. 

Students at the high school, undergraduate, and graduate levels may participate and will be evaluated within their respective academic levels, with two award categories for high school students (prediction and visualization).

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

**Downloading the Data in R**

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

---

## Eligibility

- Any student is eligible to participate, including **high school**, **undergraduate**, and **graduate** students, with no geographic restrictions (not limited to Florida or South Florida).
- Submissions may be made by an **individual** or a **team of up to 4 members**.
- Each participant or team is allowed **one submission**.
- For team submissions, the competition level is determined by the **highest academic level among all team members**. Mixed-level teams will be evaluated in the category corresponding to that highest level.

---

## Competition Tasks

### 1. Prediction Track (High School, Undergraduate, and Graduate)

Predict **LBDHDD_outcome** for the test dataset.

**Submission Requirements**
- A CSV file named **`pred.csv`**
  - Exactly **one column**, named **`pred`**
  - The number of rows must match the test dataset
  - Predictions must be in the **same order as the test data**

- A report (**maximum 4 pages**) named **`<participant_or_team_name>.pdf`**, summarizing:
  - Model and preprocessing choices
  - Validation and/or tuning strategy
  - The final model used to generate predictions, including code snippets or a link to the full code repository

**Allowed Software:**
Participants may use **any software, programming language, or computational tools** to generate their submissions.

**Evaluation Process**

- For the prediction task, submissions will first be ranked based on **Root Mean Squared Error (RMSE)** evaluated on the test dataset.
- The **top 30%** of participants within each competition level (high school, undergraduate, graduate) will advance to the **final evaluation stage**.
- In the final stage, submissions will be reviewed by judges and ranked based on the **quality, clarity, and rigor of the submitted reports**.

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
- `participant_or_team_name.pdf`  
- Optional: source code or notebook files  

Submissions should be uploaded through the [designated form](https://forms.gle/XAuuDYiU4RPqMEyJ7) (File uploads require Google login; this is a Google Forms requirement).

---

## Award

- **$300 per winner**, with four winners total: <br> 
–- High School (Prediction Track) <br> 
–- High School (Visualization Track) <br> 
–- Undergraduate (Prediction Track) <br> 
–- Graduate (Prediction Track) <br> 
- Winners will be recognized and invited to present posters at the **2026 Annual ASA Florida Chapter Meeting**  
- The **top 20%** of participants will receive a certificate of recognition  
- The **top 10%** of participants will receive a waived registration fee for the **2026 Annual ASA Florida Chapter Meeting**

---

## Contact

For questions, please contact Dr Min Lu at **m.lu6@umiami.edu** or **asasfchapter@gmail.com**.


