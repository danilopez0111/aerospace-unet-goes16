# Predicting Lightning Strikes using GOES-16 and U-Net Semantic Segmentation Model

## Motivation

This project is the culmination of my internship with The Aerospace Corporation in the summer of 2021 within the Weather Remote Sensing Systems Office. My task was to develop a dataset to apply a machine learning algorithm to create pixel-based lightning predictions to support the launch of space vehicles at Cape Canaveral. Because severe weather is an important consideration when launching these vehicles, being able to accurately predicting lightning strikes would help improve the safety of missions.

## Data

For this project, I used two primary data sources:

### NASA GOES-16 ABI CONUS Channel 13

Part of the GOES-R series- Geostationary Operation Environmental Satellite operated by NASA and NOAA, providing 16 spectral bands (including visible and infrared) of imagery through the instrument called the Advanced Baseline Imager centered at 75.2 deg W centered on the Americas. Channel 13 is a 10.3 micrometers clean infrared window band, is less sensitive to water vapor, and is available day and night. This will aid in machine learning for the visual characterization of lightning events. Based on a Google Cloud bucket, the training dataset consisted of images between mid 2017 to mid 2020.

### Lightning Occurence Dataset

Dataset is sensitive and will not be discussed. 

## ML Architecture

Because this is a semantic segmentation problem, where we want pixel based probabilities, the U-Net architecture was determined to be a sufficient baseline performance candidate. Originally developed for biomedical applications, the U-Net architecture has shown great success in the application of remote sensing. 

## Results



## Summary

