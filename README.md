**BS902 Directed Research | Boston University | Spring 2026**  
**Advisor: Dr. Yorghos Tripodis**

## Overview

This repository contains the preliminary report for a systematic 
study of residual temporal autocorrelation in continuous glucose 
monitoring (CGM) forecasting. Two major model families are evaluated 
on identical data: XGBoost with Fourier features and the Temporal 
Fusion Transformer (TFT), trained on 700 subjects from the Framingham 
Heart Study CGM dataset across ten forecast horizons (30 to 480 minutes).

## Key Finding

Both models produce residual lag-1 ACF of 0.86 to 0.98 and 
Durbin-Watson statistics of 0.06 to 0.27 across all horizons, 
all glycaemic zones, and all subjects. This convergence of two 
architecturally opposite models on the same failure pattern 
implicates the temporally local nature of both training objectives 
as the dominant cause, not model capacity or hyperparameter choice.

Low MSE is insufficient for clinical CGM forecasting. Correlated 
residuals indicate systematic predictability in the errors, 
invalidate standard prediction intervals, and compound across 
multi-step forecast horizons in a clinical setting where reliability 
directly affects insulin dosing decisions.

## Contents

| File | Description |
|---|---|
| `BS902_Full_Report.pdf` | Complete directed research report |
| `figures/` | All diagnostic figures (ACF decay, spectral, zones, time-varying) |

## Motivation for ACF-Penalised Training

These findings motivated a companion theoretical project (MA752, 
Graduate Course, BU) introducing an ACF-regularised training loss 
and analysing it under the Neural Tangent Kernel framework. That 
project provides the theoretical foundation for the ACF-penalised 
training approach proposed here as the principled remedy.

## Data

Framingham Heart Study CGM data (n=700 subjects). Data access 
governed by Framingham Heart Study data use agreement. Raw data 
not included in this repository.

## Citation

If you use or reference this report, please cite:

> Sultana, N. (2026). Systematic evaluation of residual temporal 
> correlation in CGM forecasting: XGBoost vs Temporal Fusion 
> Transformer on 700 Framingham Heart Study subjects. 
> BS902 Directed Research Report, Boston University. 
> Available at: https://github.com/nsultana/cgm-acf-forecasting

## Contact

Naznin Sultana  
PhD Student, Department of Biostatistics  
Boston University  
nsultana@bu.edu
