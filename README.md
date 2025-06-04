# cv25-glom-segmentation-from-wsis

# Paper
- https://doi.org/10.48550/arXiv.2411.04782 (winning paper)
- https://openaccess.thecvf.com/content/CVPR2022/papers/Cheng_Masked-Attention_Mask_Transformer_for_Universal_Image_Segmentation_CVPR_2022_paper.pdf (model)
- https://openaccess.thecvf.com/content/ICCV2021/papers/Liu_Swin_Transformer_Hierarchical_Vision_Transformer_Using_Shifted_Windows_ICCV_2021_paper.pdf (SWIN)
 
# Dataset 
- Do we have to use the entire dataset for training/validation/testing or can we select a portion of pictures to save time?
  
# Hyperparameters
- Patch size (challenge was done with 2048x2048)
- Overlap size (main focus)

# Model 
- Mask2Former (winner of WSI contest)
- UPerNet (?)

# Planned approach
- Segmentation logic (with variable patch / overlap size)
- Training of the selected models (sequential vs parallel training with transfer learning)
- Stitching logic (patch coordinates in file name as in winning paper)
