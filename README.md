# fMRI Analysis: Stop-Signal Task (SST) & Resting State

## Project Overview
This project investigates the neural mechanisms of **response inhibition** using the Stop-Signal Task (SST) and explores intrinsic functional architecture via resting-state fMRI. The analysis utilizes the UCLA Consortium LA5c dataset (OpenfMRI ds000030) to model cognitive control networks.

## Methodology

### 1. Task-Based GLM (Stop-Signal Task)
*   **Objective:** Isolate neural correlates of successful inhibition.
*   **Preprocessing:** Realignment (motion correction), Normalization to MNI space, Smoothing (FWHM 6mm).
*   **First-Level Modeling:**
    *   **Conditions:** `Go_Correct`, `Stop_Success`, `Stop_Failure`.
    *   **Nuisance Regressors:** 24-parameter motion model (HMP) to minimize motion artifacts.
    *   **Contrasts:** 
        *   `Stop_Success > Go_Correct` (Inhibitory Control Network)
        *   `Stop_Success > Stop_Failure` (Error Monitoring)

### 2. Functional Connectivity (Resting State)
*   **Pipeline:** Denoising (CompCor, bandpass filtering) performed in CONN/Python.
*   **Analysis:**
    *   **ROI-to-ROI:** Computed correlation matrices between key nodes (e.g., IFG, Pre-SMA).
    *   **Transformation:** Applied **Fisher's r-to-z transformation** to normalize variance for group-level statistical inference.

## Tools Used
*   **SPM12** (Statistical Parametric Mapping)
*   **CONN Toolbox** (Functional Connectivity)
*   **Python** (Pandas for behavioral logs, Nilearn for plotting)

