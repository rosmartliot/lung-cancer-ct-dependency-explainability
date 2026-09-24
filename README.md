# Code for: Multi-Level Assessment of Deep Learning for Lung Cancer CT Classification: Data Dependency and Explainability Consistency

This repository contains the code used to produce the results reported in the manuscript.

## Files

- `training_architecture.ipynb`: trains the four evaluated architectures (ResNet-18, ResNet-50, EfficientNet-B1, DenseNet-169) on the IQ-OTH/NCCD dataset.

- `testing_internal_dataset.ipynb`: evaluates the trained model on the IQ-OTH/NCCD test set. Computes the confusion matrix, per-class precision/recall/F1-score, Wilson confidence intervals, explainability consistency metrics (Dice, soft IoU, Coverage Ratio) between Grad-CAM++ and Occlusion over the full test set, and computational efficiency metrics (parameters, FLOPs, inference time).

- `preprocess_NLST_dicom_to_jpg.ipynb`: converts NLST DICOM series to JPG images for external validation, selecting a central subset of slices per patient. Requires prior authorized access to NLST data, which is not redistributed in this repository.

- `testing_external_dataset.ipynb`: evaluates the trained model on the NLST external validation cohort. Computes the confusion matrix, AUC using the continuous malignant-class probability, patient-level aggregated performance, and breakdown by scanner manufacturer.

- `continuity_dependency_analysis.ipynb`: exploratory image-dependency analysis grouping images by continuity, in the absence of patient-level identifiers. The notebook defaults to the Benign class; change `CLASS_FOLDER` to `M` or `N` to repeat the analysis for the Malignant or Normal classes.

## Execution order

1. `training_architecture.ipynb`
2. `testing_internal_dataset.ipynb`
3. `preprocess_NLST_dicom_to_jpg.ipynb`
4. `testing_external_dataset.ipynb`
5. `continuity_dependency_analysis.ipynb`

## Requirements

Python 3.11, fastai, PyTorch, Comet ML, pydicom, OpenCV, scikit-learn, Captum, torchcam.

## Data availability

- IQ-OTH/NCCD dataset: publicly available on Mendeley Data (https://data.mendeley.com/datasets/bhmdr45bh2/3).
- NLST dataset: available through the National Cancer Institute upon authorized request (DOI: 10.7937/TCIA.HMQ8-J677).

## Associated publication

Martínez-Licort, R. et al. "Multi-Level Assessment of Deep Learning for Lung Cancer CT Classification: Data Dependency and Explainability Consistency" (manuscript under review). This section will be updated with the DOI upon publication.