# Analyzing effect of different augmentation techniques on Brain Tumor Segmentation 

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

## Dataset used
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

## Model architecture
![image](https://github.com/user-attachments/assets/b84f879a-b31f-4a06-86c1-496cc5821b87)


## Experiments conducted
1. Focal loss parameterss
The α and γ parameters
for focal loss were varied to evaluate their impact on segmentation
performance. These experiments were conducted using
the original dataset, without applying any data augmentation
techniques.
Two sets of parameter combinations were tested:
(i) α=0.25, γ=2.0
(ii) α=2.0, γ=0.75

2. Data augmentation
![image](https://github.com/user-attachments/assets/80a07156-4380-4f9f-9c3a-3dd0be9953a5)


## Uncertainty and boundary analysis

## Results 
![image](https://github.com/user-attachments/assets/f0d6e77a-1d48-44b3-bafc-e3bd8c630e0a)
![image](https://github.com/user-attachments/assets/6d796e80-fef1-45c6-b372-957f1cc0d2e1)
![image](https://github.com/user-attachments/assets/28a3c1c7-10a6-40a1-9f89-95587faa4ad8)



### Training graphs
![image](https://github.com/user-attachments/assets/35517e31-c5a4-4b57-8354-9b02d6aaba70)


### Uncertainty distribution for different augmentations
![image](https://github.com/user-attachments/assets/6b05496f-dc48-4d3f-8ccc-275f6c3037e2)


### Uncertainty visualizations for different augmentations
![image](https://github.com/user-attachments/assets/40279e84-4411-42e9-b9ad-64ffc4efbd32)


### Comparison with SOTA
![image](https://github.com/user-attachments/assets/724f6b73-913e-4b03-aca6-5df670062e80)





