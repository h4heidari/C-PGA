# Coupled Physics-Gated Adaptation (C-PGA)

This repository contains the official PyTorch implementation of the paper:

**"Coupled Physics-Gated Adaptation: Gating 3D Visual Features for Physics-Aware Volumetric Prediction"**

*Submitted to Nature Machine Intelligence*

## Overview

This project introduces **C-PGA**, a physics-aware deep learning architecture designed to predict volumetric photochemical conversion in 3D-printed lattice structures.

Standard computer vision models often struggle with coupled physical systems where non-visual parameters (such as heat or diffusion) fundamentally alter how visual features should be interpreted. To address this, C-PGA leverages **Feature-wise Linear Modulation (FiLM)** to spatially adapt dense 3D visual features using sparse physical process parameters (e.g., diffusivity, layer height). By conditioning the visual stream on these physical constraints, the model achieves state-of-the-art predictive fidelity while maintaining mechanistic interpretability through spatial attention maps.

## Repository Structure

.
├── C-PGA.ipynb              # Main Jupyter notebook (Architecture, Training, Analysis)
├── README.md                # Project documentation
├── requirements.txt         # List of Python dependencies
└── data/                    # Demonstration dataset folder
    ├── demo_dataset.xlsx    # Subset of 15 samples (Numerical parameters & Targets)
    └── images/              # Subset of 15 image stacks (Original & Transformed)

## Getting Started

### Prerequisites

The code is implemented in Python 3.8+ and relies on PyTorch. We recommend running this code in a virtual environment (conda or venv) to avoid dependency conflicts.

### Installation

1. Clone the repository:
   
   git clone https://github.com/YOUR_USERNAME/C-PGA-Official.git
   cd C-PGA-Official

2. Install dependencies:
   
   pip install -r requirements.txt

   *Note: Ensure you have a CUDA-enabled version of PyTorch installed if you intend to run training on a GPU.*

## Usage

To ensure reproducibility while protecting proprietary manufacturing data, this repository is configured to run in two modes: **Demo Mode** (default) and **Full Training Mode**.

### 1. Running the Demo (Reproducibility Check)

The repository includes a `data/` folder with 15 representative samples. This allows reviewers and users to verify the model architecture, training loop, and interpretability code without requiring external data.

1. Launch Jupyter Lab or Notebook:
   
   jupyter lab C-PGA.ipynb

2. Ensure the configuration flag in **Step 1** of the notebook is set to `True`:

   # Configuration: Set to True for Demo (15 samples), False for Full Training
   DEMO_MODE = True

3. **Run All Cells**:
   * The notebook will automatically load the sample data from the local `./data` directory.
   * It will initialize the C-PGA architecture and perform a complete training run on the subset.
   * It will generate interpretability visualizations (Saliency Maps and Occlusion Tests) based on these samples.

### 2. Running with Full/Custom Data

Due to intellectual property constraints, the full dataset (648 samples) is not hosted in this public repository. Researchers with access to the full dataset (or their own proprietary data) should follow these steps:

1. Place your full Excel dataset and image directory on your local machine.
2. In **Step 1** of `C-PGA.ipynb`, change the configuration flag:
   
   DEMO_MODE = False

3. Update the path variables in the `else` block to point to your local data:

   else:
       excel_path = '/path/to/your/full_dataset.xlsx'
       image_dir = '/path/to/your/full_images_directory'

4. Run the notebook to train on the full dataset.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For questions regarding the code or requests for data access, please contact the corresponding author as listed in the manuscript.