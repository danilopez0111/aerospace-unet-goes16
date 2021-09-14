# Predicting Lightning Strikes using GOES-16 and U-Net Semantic Segmentation Model

## Motivation

This project is the culmination of my internship with The Aerospace Corporation in the summer of 2021 within the Weather Remote Sensing Systems Office. My task was to develop a dataset to apply a machine learning algorithm to create pixel-based lightning predictions at 5, 15, and 30 minute intervals to support the launch of space vehicles at Cape Canaveral. Because severe weather is an important consideration when launching these vehicles, being able to accurately predicting lightning strikes would help improve the safety of missions.

## Data

For this project, we used two data sources:

### NASA GOES-16 ABI CONUS Channel 13

<p align="center">
  <img src="https://github.com/danilopez0111/aerospace-unet-goes16/blob/main/images/goes16.jpg?raw=true">
</p>

Part of the GOES-R series- Geostationary Operation Environmental Satellite operated by NASA and NOAA, providing 16 spectral bands (including visible and infrared) of imagery through the instrument called the Advanced Baseline Imager centered at 75.2 deg W centered on the Americas. Channel 13 is a 10.3 micrometers clean infrared window band, is less sensitive to water vapor, and is available day and night. This will aid in machine learning for the visual characterization of lightning events. Based on a Google Cloud bucket, the training dataset consisted of images between mid 2017 to mid 2020.

### Lightning Occurence Dataset

Dataset is sensitive and will not be discussed. 

## ML Architecture

<p align="center">
  <img src="https://github.com/danilopez0111/aerospace-unet-goes16/blob/main/images/u-net-architecture.png?raw=true">
</p>

Because this is a semantic segmentation problem, where we want pixel based probabilities, the U-Net architecture was determined to be a sufficient baseline performance candidate. Originally developed for biomedical applications, the U-Net architecture has shown great success in the application of remote sensing. 

## Results

### Sample 1

<p align="center">
  <img src="https://github.com/danilopez0111/aerospace-unet-goes16/blob/main/images/Picture1_auto_x2.jpg?raw=true">
</p>

### Sample 2

<p align="center">
  <img src="https://github.com/danilopez0111/aerospace-unet-goes16/blob/main/images/Picture2_auto_x2.jpg?raw=true">
</p>

### Sample 3

<p align="center">
  <img src="https://github.com/danilopez0111/aerospace-unet-goes16/blob/main/images/Picture3_auto_x2.jpg?raw=true">
</p>

## Evaluation

Two methods of accuracy we evaluated for the results are the IOU score and the F1 score- two widely accepted methods for evaluation for semantic segmentation.

### 5 Minute Model

IOU: 73%
F1: 40%

### 15 Minute Model

IOU: 75%
F1: 48%

### 30 Minute Model

IOU: 77%
F1: 50%

# Summary

The great success of this project include being able to accurately predict the relative location of lightning occurences, being able to characterize the shape of lightning hotspots, and being a proof of concept as a success for machine learning to be applied to remote sensing and atmospheric scicences. 

Though, there are still areas of improvement. The model lacks fidelity and precision for lightning strikes, but is currently expected as exact lightning locations are very hard to characterize! Also, the model still misclassified some areas, which may be recitified through the input of more traning samples. 
