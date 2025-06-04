# Glomerulus segmentation from whole-slide images (WSIs)

This repository belongs to the project of Lukas Göbl, Peer Schäfter and Lukas Scheib during the Computer Vision course 2025.

## Papers
- R. Deng, T. Yao, Y. Tang et al., "KPIs 2024 Challenge: Advancing Glomerular Segmentation from Patch- to Slide-Level", 2025, doi: [10.48550/arXiv.2502.07288](https://doi.org/10.48550/arXiv.2502.07288). (Challenge dataset)
- Q. H. Cap, "A General Pipeline for Glomerulus Whole-Slide Image Segmentation", 2025, doi: [10.48550/arXiv.2411.04782](https://doi.org/10.48550/arXiv.2411.04782). (Winning paper)
- B. Cheng, I. Misra, A. G. Schwing, A. Kirillov and R. Girdhar, "Masked-attention Mask Transformer for Universal Image Segmentation," *2022 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)*, New Orleans, LA, USA, 2022, pp. 1280-1289, doi: [10.1109/CVPR52688.2022.00135](https://doi.org/10.1109/CVPR52688.2022.00135). (Model)
- Z. Liu et al., "Swin Transformer: Hierarchical Vision Transformer using Shifted Windows", *2021 IEEE/CVF International Conference on Computer Vision (ICCV)*, Montreal, QC, Canada, 2021, pp. 9992-10002, doi: [10.1109/ICCV48922.2021.00986](https://doi.org/10.1109/ICCV48922.2021.00986). (Swin)

## Dataset 
- KPIs 2024 challenge dataset for task 2 (WSI level)
- Question: Do we have to use the entire dataset for training/validation/testing or can we select a portion of pictures to save time?
  
## Hyperparameters
- Patch size (challenge was done with 2048x2048)
- Overlap size (our main focus)

## Model(s) 
- Mask2Former (winner of WSI contest)
- UPerNet (?)

## Planned approach
- Cropping logic (with variable patch / overlap size)
- Training of the selected model(s) (sequential vs. parallel training with transfer learning)
- Stitching logic (patch coordinates in file name as in winning paper)
