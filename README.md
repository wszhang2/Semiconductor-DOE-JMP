# Semiconductor Etch Process Optimization Using JMP

## Project Overview

This project demonstrates the application of **Design of Experiments
(DOE)** and statistical modeling to optimize a simulated semiconductor
etch process using **JMP**.

A replicated **2³ full-factorial DOE** was used to investigate how three
process parameters affect etch rate:

-   RF Power
-   Chamber Pressure
-   Gas Flow

The project demonstrates the complete DOE workflow, including
experimental design, effect screening, ANOVA, interaction analysis,
model evaluation, prediction profiling, and process optimization.

> **Note:** This project uses synthetic data created for educational and
> portfolio purposes. It does not contain proprietary semiconductor
> manufacturing or employer data.

## Project Objective

The objective of this study was to:

1.  Identify process factors that significantly affect etch rate.
2.  Evaluate interactions between process parameters.
3.  Develop a statistical model for predicting etch rate.
4.  Evaluate the quality of the fitted model.
5.  Determine process settings that maximize the predicted etch rate
    within the experimental design space.

## Experimental Design

  Factor               Low Level   High Level
  ------------------ ----------- ------------
  RF Power                 200 W        300 W
  Chamber Pressure      20 mTorr     40 mTorr
  Gas Flow               40 sccm      60 sccm

A **2³ full-factorial design** produces 8 treatment combinations. Each
treatment was replicated twice, resulting in **16 total observations**.
The response variable was **Etch Rate (nm/min)**.

## Statistical Model

The factorial model included the main effects of RF Power, Pressure, and
Gas Flow, as well as the two-factor interactions RF Power × Pressure, RF
Power × Gas Flow, and Pressure × Gas Flow. The model was analyzed in JMP
using **Standard Least Squares**.

## Effect Screening

  Effect                    P-value Result
  --------------------- ----------- -----------------------------
  RF Power                \< 0.0001 Significant
  Pressure                \< 0.0001 Significant
  Gas Flow                \< 0.0001 Significant
  RF Power × Pressure        0.0108 Significant
  RF Power × Gas Flow        0.0422 Significant
  Pressure × Gas Flow        0.1040 Not significant at α = 0.05

RF Power showed the strongest statistical evidence of an effect on etch
rate.

## Model Performance

  Model Metric            Result
  --------------- --------------
  R²                      0.9895
  Adjusted R²             0.9825
  RMSE              1.797 nm/min
  Mean Response     93.94 nm/min
  Observations                16

The model explained approximately **98.95% of the observed variation in
etch rate**.

## ANOVA Results

Analysis of Variance (ANOVA) showed that the overall factorial model was
statistically significant:

**F = 141.41, p \< 0.0001**

The model accounted for approximately **2739.88 of the total 2768.94 sum
of squares**, while approximately **29.06** remained as unexplained
error.

## Prediction Profiler

JMP's **Prediction Profiler** was used to examine how each process
factor influenced the predicted etch rate.

Within the investigated experimental range:

-   Increasing **RF Power** increased predicted etch rate.
-   Increasing **Pressure** decreased predicted etch rate.
-   Increasing **Gas Flow** increased predicted etch rate.

Because significant interactions were identified between **RF Power ×
Pressure** and **RF Power × Gas Flow**, these parameters should be
interpreted together rather than independently.

## Process Optimization

  Parameter               Optimized Setting
  --------------------- -------------------
  RF Power                            300 W
  Pressure                         20 mTorr
  Gas Flow                          60 sccm
  Predicted Etch Rate       \~118.19 nm/min
  Desirability                      \~0.929

These values represent a **model-predicted optimum within the
investigated design space**, not validated production settings.
Confirmation experiments would be required before applying the settings
to a real process.

## Engineering Conclusions

-   RF Power, Pressure, and Gas Flow significantly affected the
    simulated etch-rate response.
-   RF Power was the strongest factor based on JMP's Effect Summary.
-   RF Power × Pressure and RF Power × Gas Flow interactions were
    statistically significant.
-   The factorial model provided a strong fit to the synthetic dataset
    (R² = 0.9895).
-   Prediction profiling and desirability optimization identified a
    candidate operating condition for maximizing etch rate.

The next engineering step would be to perform **confirmation runs at the
predicted optimum** and compare the measured response with the model
prediction.

## Tools & Methods

**Software:** JMP Pro

**Statistical Methods:** Design of Experiments (DOE), 2³ Full-Factorial
Design, Standard Least Squares, Effect Screening, ANOVA, Interaction
Analysis, Model Diagnostics, Actual by Predicted Analysis, Prediction
Profiler, and Desirability Optimization.

## Files

-   `Semiconductor_DOE_Portfolio.pdf` --- Complete project report
-   `semiconductor_DOE_data.csv` --- Synthetic DOE dataset
-   `README.md` --- Project overview

## Data Disclaimer

The dataset used in this project is **synthetic and intended solely for
educational and portfolio demonstration purposes**. The data do not
represent actual semiconductor production data, proprietary process
conditions, or confidential information from any semiconductor
manufacturer.
