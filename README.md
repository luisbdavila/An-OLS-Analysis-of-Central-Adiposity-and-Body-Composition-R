# The Tape Measure vs. The Scale

## An OLS Analysis of Central Adiposity and Body Composition

This project investigates whether simple anthropometric measurements — specifically abdominal and wrist circumference — provide a better prediction of body fat percentage than the commonly used Body Mass Index (BMI).

Using Ordinary Least Squares (OLS) regression and statistical diagnostics, we evaluate whether BMI remains meaningful when more direct measures of body composition are included.

---

## Motivation

Obesity is a major public health concern linked to cardiovascular disease and diabetes. BMI is widely used as a screening metric, but it cannot distinguish between lean muscle mass and adipose tissue.

Clinical gold-standard techniques for body fat measurement are accurate but costly and impractical for everyday use. This project explores whether low-cost tape measurements can outperform BMI in predicting body fat percentage.

---

## Research Question

> *To what extent do central adiposity (abdominal circumference) and skeletal frame size (wrist circumference) improve the prediction of body fat percentage compared to BMI?*

---

## Dataset

We use a cross-sectional dataset of **250 adult men** containing:

* Body fat percentage (target variable)
* Age
* Weight
* Height
* Abdominal circumference
* Wrist circumference

BMI is computed as:

```
BMI = 703 × Weight(lbs) / Height(inches)^2
```

The dataset originates from a publicly available body fat prediction dataset.

---

## Methodology

We estimate the following OLS regression model:

```
BodyFat = β0 + β1(BMI) + β2(Wrist) + β3(Abdomen)
          + β4(Age) + β5(Abdomen²) + ε
```

### Why this model?

* A quadratic abdominal term captures nonlinear fat accumulation patterns.
* Age controls for metabolic and muscle composition changes.
* Wrist circumference proxies skeletal frame size.

---

## Statistical Diagnostics

To validate model assumptions, we performed:

* Breusch–Pagan test → homoskedasticity
* White’s test → variance consistency
* Ramsey RESET test → functional form verification

All tests support the validity of the OLS model.

---

## Results Summary

Key findings:

* Model explains ~73% of variation in body fat
* Abdominal circumference is a strong predictor
* Wrist circumference significantly contributes
* Age is statistically meaningful
* **BMI becomes statistically insignificant** when circumferences are included

This indicates BMI acts as a coarse proxy and adds little predictive value when more informative anthropometric measures are available.

---

## Conclusion

Simple tape measurements — abdominal and wrist circumference — provide a superior prediction of body fat compared to BMI.

BMI fails to distinguish body composition and becomes redundant when central adiposity and skeletal frame size are considered.

These findings support replacing BMI with more direct anthropometric measures in practical health assessment.

---

## How to Run the Analysis

1. Open the R Markdown script:

```
script_group_44.Rmd
```

2. Ensure required R packages are installed:

```
install.packages(c("tidyverse", "lmtest", "car"))
```

3. Knit the document to reproduce analysis and outputs.

---

## Future Work

* Validate findings across genders and ethnic groups
* Longitudinal tracking of circumference changes
* Alternative nonlinear modeling approaches

---

## Authors

Veronica Mendes

Luis Mendes

---

