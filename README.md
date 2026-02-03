# ECG_QRS_Cutoff_FirstN

A GUI-driven R pipeline for standardized ECG preprocessing based on QRS interval distribution, enabling objective beat selection and First-N beat averaging across multiple recordings.
This repository contains Script 02 of a 3-step ECG analysis pipeline.

## Key Features
- Automatic QRS cutoff detection using a 2-component Gaussian mixture model
- Multiple cutoff strategies (Comp1 percentile, equal-density, valley, posterior probability)
- Interactive GUI (no command-line arguments required)
- Standardized First-N beat extraction after QRS threshold crossing
- Per-recording numeric summaries (mean values)
- Clean, analysis-ready outputs (CSV + XLSX)
- Robust to Windows / RStudio Tk issues

---

## Overview

1. Pool QRS intervals from all ECG recordings
2. Fit a Gaussian mixture model (G = 2) to separate physiological vs prolonged QRS populations
3. Derive candidate QRS cutoffs objectively
4. Select a cutoff strategy via GUI
5. For each recording:
    - Identify the first beat exceeding the cutoff
    - Extract the next N beats
    - Compute mean values for all numeric ECG features

This approach avoids arbitrary time windows and ensures consistent physiological alignment across samples.
