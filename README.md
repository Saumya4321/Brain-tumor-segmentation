# Uncertainty Analysis of Augmentation Techniques in Brain Tumor Segmentation

## Motivation
This project was done as a part of the '*AI for Medical Image Analysis - DS261*' course @ CDS, IISc.

## Overview
This study proposes a modified U-Net incorporating focal loss to address
class imbalance and Monte Carlo Dropout for uncertainty
estimation, providing interpretable predictions. The model
was evaluated on MRI data, with experiments focusing on
focal loss parameter tuning and studying the impact of three
data augmentation techniques: Horizontal Flip, Rotation,
and Scaling. 

## Contents of Repository

+ ```augmentation_experiments\```\
This directory contains the notebooks for all three data augmentation experiments done and their uncertainty analysis. The different data augmentation techniques are labeled as follows:\
DA1 - Horizontal flip\
DA2 - Rotation\
DA3 - Random scaling

+ ```model_weights\``` \
This directory contains a readme file with the link to download the best performing model weights.

+ ```Brain_Tumor_Segmentation_best.ipynb```\
Notebook containing the best performing segmentation model

+ ```Inference_notebook_for_grading.ipynb```\
This notebook loads the weights of the best performing model and runs inference on the provided test data provided in the zip file. Before running this notebook, download the weights from [link](https://drive.google.com/file/d/1YChnisdNceJbb9c4KcS6WbjdLOr4_B1K/view?usp=sharing) , the test data from ```test_data.zip``` and unzip them.

+ ```test_data.zip```\
This zip file includes 6 images and masks in their respective directories. To be used for evaluation.


## Dataset used

![image](https://github.com/user-attachments/assets/297eaae0-7606-4f4d-a15c-b8d1a2bc2fd6)

For this study, a brain tumor dataset containing 3064 T1-
weighted contrast-enhanced MRI images was used. The data
was collected from Nanfang Hospital and Tianjing Medical
University, China, from 2005 to 2010, by Jun Cheng, who
who had
uploaded the entire dataset with its metadata to Figshare. The
dataset consists of T1-weighted contrast-enhanced MRI scans
from 233 patients, and has three kinds of brain tumors - 708
cases of Meningiomas, 1426 gliomas and 930 cases of pituitary
tumors. The tumor border was manually delineated
by three experienced radiologists. A copy of this dataset was
taken from Kaggle, where the scans and corresponding binary
masks were uploaded as 256x256 pixel images.
## Preprocessing workflow
![image](https://github.com/user-attachments/assets/e9bb6d5d-3397-4dde-8e77-542b10a5553a)


## Model architecture
![image](https://github.com/user-attachments/assets/b84f879a-b31f-4a06-86c1-496cc5821b87)



## Experiments conducted
#### Focal loss parameterss
The α and γ parameters
for focal loss were varied to evaluate their impact on segmentation
performance. These experiments were conducted using
the original dataset, without applying any data augmentation
techniques.
Two sets of parameter combinations were tested:
(i) α=0.25, γ=2.0
(ii) α=2.0, γ=0.75

#### Data augmentation
![image](https://github.com/user-attachments/assets/80a07156-4380-4f9f-9c3a-3dd0be9953a5)



## Results 
#### Results of focal loss parameters experiments
![image](https://github.com/user-attachments/assets/f0d6e77a-1d48-44b3-bafc-e3bd8c630e0a)
 In the first case, the
configuration prioritized hard-to-classify examples, particularly tumor boundaries, resulting in better performance. In
the second case, the configuration emphasized the minor class
(tumor regions) more but focused less on boundary details,
leading to weaker performance in challenging regions.

#### Results of data augmentation experiments
![image](https://github.com/user-attachments/assets/6d796e80-fef1-45c6-b372-957f1cc0d2e1)

<br>
Horizontal flip consistently improved performance across
all metrics, making it the most effective augmentation technique. Rotation improved the Dice coefficient and IoU, indicating its effectiveness. Scaling, however, showed negligible
or no improvement in segmentation performance

<br/>

<br>
![image](https://github.com/user-attachments/assets/28a3c1c7-10a6-40a1-9f89-95587faa4ad8)

<br>
Boundary-specific metrics—including
mean boundary uncertainty and maximum boundary uncertainty—
highlighted that applying augmentations like Horizontal
Flip and Rotation decreased uncertainty at tumor boundaries.

#### Training graphs
![image](https://github.com/user-attachments/assets/35517e31-c5a4-4b57-8354-9b02d6aaba70)

As seen from the training graphs, horizontal flip and rotation helps in achieving a lower
final loss when compared to the baseline model. Horizontal
flip has a more positive effect and can be seen to help in
achieving faster convergence and lower final loss.

#### Uncertainty visualizations for different augmentations
![image](https://github.com/user-attachments/assets/40279e84-4411-42e9-b9ad-64ffc4efbd32)

From the above images, it can be seen that the data augmentations decrease uncertainty at tumor boundaries to different extents. This indicates that these techniques not only
improve segmentation accuracy but also enhance the model’s
confidence in its predictions.

#### Comparison with SOTA
![image](https://github.com/user-attachments/assets/724f6b73-913e-4b03-aca6-5df670062e80)

## Citation

If you find this work useful, please cite:
```
Saumya4321, "Uncertainty Analysis of Augmentation Techniques in Brain Tumor Segmentation," 2025.
GitHub repository - https://github.com/Saumya4321/ds261-project
```





