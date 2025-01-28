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

