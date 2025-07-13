# Glomerulus segmentation from whole-slide images (WSIs)

This repository belongs to the project of Lukas Göbl, Peer Schäfter and Lukas Scheib during the Computer Vision course 2025.

## Introduction
In our project we addressed the tasks of segmenting glomeruli from whole-slide and patch-level kidney biopsy images as part of the MICCAI 2024 Kidney Pathology Image segmentation (KPIs) Challenge on medical image segmentation. The core objective was to accurately identify glomerular structures, which is critical for diagnosing kidney diseases. Given the highly imbalanced nature of the data and the large image sizes, standard segmentation models tend to underperform.

In our work, we implemented and evaluated our VariableUNet architecture to primarily tackle the patch-level segmentation task. Our focus was on improving recall and $F_1$-score rather than accuracy, as the class imbalance rendered the latter misleading. We used a training and evaluation strategy using patch-based inference and a mix of a BCE and dice loss function (BCEDiceLoss). Despite finetuning our hyper parameters we only achieved a dice score of $74\%$, falling behind of the winning submisssions. For the whole-slide segmentation task, we only implemented a strategy to patch the large images, but did not conduct any further experiments.

## Dataset 
The dataset used originates from PAS-stained whole-slide images (WSIs) of mouse kidney tissue, collected from four well-established preclinical rodent models of chronic kidney disease (CKD). These models include Normal (Control), 5/6 Nephrectomy (5/6Nx), Diabetic Nephropathy (DN) and NEP25. It includes 8.866 image patches, split into a training, a validation and testing set. Each patch is sized 2048x2048 pixels and extracted from the WSIs.

The dataset be downloaded from the [KPIs 2024 Challenge dataset](https://www.synapse.org/Synapse:syn54077668/wiki/626475) page.

## Files
- `paper.pdf`: Contains the project report.
- `requirements.txt`: Contains the Python dependencies required to run the code.
- `glomerulus-segmentation.yml`: Contains the configuration file for the project.
- `VariableUNet.ipynb`: Contains the implementation of the VariableUNet architecture and training script.
- `models/`: Contains some notable trained models.

## Papers
- R. Deng, T. Yao, Y. Tang et al., "KPIs 2024 Challenge: Advancing Glomerular Segmentation from Patch- to Slide-Level", 2025, doi: [10.48550/arXiv.2502.07288](https://doi.org/10.48550/arXiv.2502.07288). (Challenge dataset)
- Q. H. Cap, "A General Pipeline for Glomerulus Whole-Slide Image Segmentation", 2025, doi: [10.48550/arXiv.2411.04782](https://doi.org/10.48550/arXiv.2411.04782). (Winning paper)
- B. Cheng, I. Misra, A. G. Schwing, A. Kirillov and R. Girdhar, "Masked-attention Mask Transformer for Universal Image Segmentation," *2022 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)*, New Orleans, LA, USA, 2022, pp. 1280-1289, doi: [10.1109/CVPR52688.2022.00135](https://doi.org/10.1109/CVPR52688.2022.00135). (Model)
- Z. Liu et al., "Swin Transformer: Hierarchical Vision Transformer using Shifted Windows", *2021 IEEE/CVF International Conference on Computer Vision (ICCV)*, Montreal, QC, Canada, 2021, pp. 9992-10002, doi: [10.1109/ICCV48922.2021.00986](https://doi.org/10.1109/ICCV48922.2021.00986). (Swin)
- Xiao, Tete, Yingcheng Liu, Bolei Zhou, Yuning Jiang, and Jian Sun. "Unified perceptual parsing for scene understanding." In Proceedings of the European conference on computer vision (ECCV), pp. 418-434. 2018.
- Moreau, Noémie, Michelle Shabani, Christoph Schell, and Katarzyna Bozek. "GLOMNET: a hover deep learning model for glomerulus instance segmentation." In 2024 IEEE International Symposium on Biomedical Imaging (ISBI), pp. 1-5. IEEE, 2024. (https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=10635729&casa_token=yGNqPEu-R_EAAAAA:ZHhEi1hwFnsZJ8VR2LIfW1mCBFW64QZQn_mKy1jT4PQhDc4vTD1gT9EkZvDOjjH191c9sDCjQ_1w&tag=1)
- LI, Xiang, et al. Deep learning segmentation of glomeruli on kidney donor frozen sections. Journal of Medical Imaging, 2021, 8. Jg., Nr. 6, S. 067501-067501.

