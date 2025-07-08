# Hyperparameter tuning

Visual analysis of the predicted masks compared to ground-truth masks on the first five pictures of the validation set.

## First run

We did a first run on subsets of our training and validation data. We used 700 random images from the training set and 50 random images from the validation set. 

Fixed parameters:
| Page size | Patch overlap | Epochs | Batch size | Learning rate |
| --- | --- | --- | --- | --- |
| 2048 | 0 | 5 | 16 | 0.0001 |

Parameters to investigate:
| Hyperparameter | Tested initializations |
| --- | --- |
| bce_weight | 0.0, 0.2, 0.4, 0.6, 0.8, 1.0 |
| dice_smooths | 1e-4, 1e-5, 1e-6 |
| pos_weights | 1, 5, 10, 25 |

We see very few true positive pixels on pictures 4 and 5 but even more false positive pixels on pict. 4 for:
| bce_weight | dice_smooth | pos_weight |
| --- | --- | --- |
| 1 | 1e-6 | 1 |

We see a few true positive pixels on pictures 4 and 5 but also a few false positive pixels on pict. 4 for:
| bce_weight | dice_smooth | pos_weight |
| --- | --- | --- |
| **0.4** |	**1e-4** | **25** |
| **0.4** | **1e-6** | **25** |
| 0.6 | 1e-4 | 10 |
| 0.6 | 1e-6 | 5 |

We see a few true positive pixels on pictures 4 and 5 but also a few false positive pixels on pict. 1 and 4 for:
| bce_weight | dice_smooth | pos_weight |
| --- | --- | --- |
| **0.6** | **1e-6** | **1** |

We see a few true positive pixels on pictures 2, 3, 4, 5 but also a few false positive pixels on pict. 4 for:
| bce_weight | dice_smooth | pos_weight |
| --- | --- | --- |
| 0.8 |	1e-4 | 10 |
| 0.8 | 1e-5 | 10 |
| **0.8** | **1e-5** | **25** |

We see a few true positive pixels on pictures 2, 3, 4, 5 but also a few false positive pixels on pict. 1, 4, 5 for:
| bce_weight | dice_smooth | pos_weight |
| --- | --- | --- |
| 0.6 |	1e-4 | 25 |

We see some true positive pixels on all five pictures but also some false positive pixels on pict. 4 and 5 for:
| bce_weight | dice_smooth | pos_weight |
| --- | --- | --- |
| **0.6** |	**1e-6** | **25** |

All other initialization combinations are either all black (majority baseline) or have predicted a few false positive but no true positive pixels.

The five highlighted rows (bold) in the tables above are the top-5 specifications that give the highest recall after 5 epochs.  
&rarr; *Are these the values for training or validation recall?*  
&rarr; *Fix plot. Currently the caption says f1-score but the recall is shown. Either fix that or show f1-score instead.* 

## Second run

For the second run we again used only subsets of our training and validation data. We used 700 random images from the training set and 50 random images from the validation set. 

Fixed parameters:
| Page size | Patch overlap | Epochs | Batch size | Learning rate | dice_smooth |
| --- | --- | --- | --- | --- | --- |
| 2048 | 0 | 5 | 16 | 0.0001 | 1e-6 |

Parameters to investigate:
| Hyperparameter | Tested initializations |
| --- | --- |
| bce_weight | 0.55, 0.6, 0.65 |
| pos_weights | 13, 17, 21, 25 |