# Glomerulus segmentation from whole-slide images (WSIs)

This repository belongs to the project of Group 9 (Lukas Göbl, Peer Schäfter and Lukas Scheib) during the Computer Vision course 2025.

## Introduction
In our project we addressed the tasks of segmenting glomeruli from whole-slide and patch-level kidney biopsy images as part of the MICCAI 2024 Kidney Pathology Image segmentation (KPIs) Challenge on medical image segmentation. The core objective was to accurately identify glomerular structures, which is critical for diagnosing kidney diseases. Given the highly imbalanced nature of the data and the large image sizes, standard segmentation models tend to underperform.

In our work, we implemented and evaluated our VariableUNet architecture to primarily tackle the patch-level segmentation task. Our focus was on improving recall and $F_1$-score rather than accuracy, as the class imbalance rendered the latter misleading. We used a training and evaluation strategy using patch-based inference and a mix of a BCE and dice loss function (BCEDiceLoss). Despite finetuning our hyper parameters we only achieved a dice score of $74\%$, falling behind of the winning submisssions. For the whole-slide segmentation task, we only implemented a strategy to patch the large images, but did not conduct any further experiments.

## Dataset 
The dataset used originates from PAS-stained whole-slide images (WSIs) of mouse kidney tissue, collected from four well-established preclinical rodent models of chronic kidney disease (CKD). These models include Normal (Control), 5/6 Nephrectomy (5/6Nx), Diabetic Nephropathy (DN) and NEP25. It includes 8.866 image patches, split into a training, a validation and testing set. Each patch is sized 2048x2048 pixels and extracted from the WSIs.

The dataset be downloaded from the [KPIs 2024 Challenge dataset](https://www.synapse.org/Synapse:syn54077668/wiki/626475) page.

## Files
- `Computer Vision, Project Report, Group 9, Göbl, Schäfer, Scheib.pdf`: Contains the project report.
- `requirements.txt`: Contains the Python dependencies required to run the code.
- `glomerulus-segmentation.yml`: Contains the configuration file for the project.
- `VariableUNet.ipynb`: Contains the implementation of the VariableUNet architecture and training script.
- `WSI_Patching.ipynb`: Contains the implementation of the WSI level patching logic to create datasets using custom patch_size and overlap. 
- `Experiments1-5/` and `ExperimentPanNuke/`: Contain the results of the different experiments as JSON files. We also included the most notable models for Experiment 4 and 5.
- `Journal Club/`: Contains our journal club presentation.
