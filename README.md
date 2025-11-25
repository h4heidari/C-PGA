# Coupled Physics-Gated Adaptation (C-PGA)

This repository contains the official PyTorch implementation of the paper:

**"Coupled Physics-Gated Adaptation: Gating 3D Visual Features for Physics-Aware Volumetric Prediction"**

*Submitted to Nature Machine Intelligence.*

## 📌 Overview
This project introduces **C-PGA**, a physics-aware deep learning architecture designed to predict volumetric photochemical conversion in 3D-printed lattice structures. By leveraging **Feature-wise Linear Modulation (FiLM)**, the model spatially adapts dense 3D visual features using sparse physical process parameters (e.g., diffusivity, layer height), achieving state-of-the-art predictive fidelity while maintaining mechanistic interpretability.

## 📂 Repository Structure

```text
.
├── C-PGA_Nature.ipynb       # Main Jupyter notebook (Architecture, Training, Analysis)
├── README.md                # This file
├── requirements.txt         # List of dependencies
└── data/                    # Demonstration dataset folder
    ├── demo_dataset.xlsx    # Subset of 15 samples (Numerical parameters & Targets)
    └── images/              # Subset of 15 image stacks (Original & Transformed)