## Improving Clinical Trust in Bayesian Medical Image Segmentation  
### Uncertainty–Error Alignment for Interpretable Lung Segmentation

**TL;DR**: A Bayesian deep learning–based lung segmentation system that produces both segmentation masks and pixel-wise uncertainty maps, improving clinical interpretability and trust in medical image analysis.

This project focuses on medical image segmentation with explicit uncertainty modeling to identify regions where model predictions are unreliable. By leveraging Bayesian inference techniques, the system highlights ambiguity in segmentation results—an essential requirement for safety-critical clinical applications.

This is a graduate-level Pattern Recognition project completed as part of the Master’s in Artificial Intelligence program at the University at Buffalo.

___

### Project Motivation

Medical image segmentation models often produce confident predictions even when they are incorrect.  
In clinical settings, this lack of uncertainty awareness can lead to overtrust and potential diagnostic risks.

This project explores how **Bayesian deep learning** can be used to:
- Quantify model uncertainty alongside segmentation outputs
- Improve interpretability of automated lung segmentation
- Identify ambiguous or low-confidence regions in medical images
- Support safer decision-making in downstream clinical workflows

___

### Methodology

The project implements a Bayesian segmentation pipeline that combines convolutional neural networks with uncertainty estimation through stochastic inference.

#### Bayesian Segmentation Framework

- Base Architecture: CNN-based lung segmentation model
- Bayesian Approximation: Monte Carlo Dropout
- Inference Strategy:
  - Multiple stochastic forward passes
  - Mean prediction used for final segmentation
  - Prediction variance used to estimate uncertainty

#### Uncertainty Modeling

- Epistemic uncertainty captured via dropout at inference time
- Pixel-wise uncertainty maps generated from variance across predictions
- High-uncertainty regions indicate ambiguous boundaries or low-confidence predictions

#### Training Details

- Framework: PyTorch
- Loss Function: Dice-based segmentation loss
- Optimization: Adam optimizer
- Input: CT lung images
- Output:
  - Binary segmentation mask
  - Corresponding uncertainty heatmap

___

### Dataset

- **Kaggle Lung Segmentation Dataset**
- Source: KaggleHub
- Data Type: Medical CT images with ground-truth lung masks

> The dataset is downloaded programmatically during execution and is **not included** in this repository to comply with dataset licensing and size constraints.

___

### Evaluation & Analysis

- Visual comparison between predicted masks and ground truth
- Qualitative analysis of uncertainty maps
- Observed that:
  - High uncertainty correlates with boundary regions
  - Ambiguous anatomical structures show elevated variance
  - Clear lung regions exhibit low uncertainty

Detailed experimental results, visualizations, and analysis are included in the project report.

___

### Example Capabilities

- Accurate lung region segmentation from CT images
- Pixel-level uncertainty visualization
- Identification of unreliable predictions
- Improved interpretability over deterministic segmentation models

___

### Repository Contents

- `Lung segmentation code.ipynb` — End-to-end implementation of Bayesian lung segmentation and uncertainty estimation
- `Lung segmentation Report.pdf` — Detailed methodology, experiments, results, and discussion

___

### Technology Stack

- Python
- PyTorch
- NumPy
- OpenCV
- Matplotlib
- KaggleHub
- Jupyter Notebook

___

### Future Work

- Extend to 3D volumetric segmentation
- Incorporate aleatoric uncertainty modeling
- Apply uncertainty-aware loss functions (e.g., AvU loss)
- Evaluate on multi-institution clinical datasets
- Integrate with clinical decision-support systems

___

### Authors

**Aishwarya Virigineni**  Master’s in Artificial Intelligence, University at Buffalo

**Kanisha Raja**  Master’s in Artificial Intelligence, University at Buffalo

**Nithya Kaandru**  Master’s in Artificial Intelligence, University at Buffalo

