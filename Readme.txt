# SAR Image Processing Toolkit

## Overview
This toolkit provides advanced processing capabilities for Synthetic Aperture Radar (SAR) imagery, offering two main applications:
1. **SAR Colorization**: Segment and colorize SAR images into land cover classes
2. **SAR to Optical Translation**: Convert SAR imagery to optical-like imagery using deep learning

## Features

### SAR Colorization
- Load pre-trained semantic segmentation models (U-Net, DeepLabV3+, SegNet)
- Process single SAR images with optional ground truth comparison
- Batch process multiple images with metrics calculation
- Visualize results using the ESA WorldCover color scheme
- Export colorized results in various formats

### SAR to Optical Translation
- Translate SAR imagery to optical-like imagery using deep learning
- Segment SAR images into land cover classes
- Generate realistic RGB imagery from single-channel SAR data
- Compare results with ground truth optical imagery (PSNR, SSIM metrics)
- Batch process multiple images

## Hugging Face Deployment

This application is deployed on Hugging Face Spaces, providing an easy-to-use web interface for processing SAR imagery without any installation requirements.

**Access the application here**: [SAR Image Processing on Hugging Face](https://huggingface.co/spaces/VarunRavichander/SAR-image-Colorization-NRSC)

## Dataset Information
The models were trained using data from Google Earth Engine (GEE), specifically focusing on the Hyderabad region of India. The dataset includes:
- SAR imagery from Sentinel-1
- Optical imagery from Sentinel-2
- ESA WorldCover land cover classification data

## Requirements (for local deployment)
- Python 3.7+
- TensorFlow 2.12
- Streamlit
- Rasterio
- OpenCV
- NumPy
- Matplotlib
- PIL
- h5py



## Model Information
The application uses pre-trained models stored in the `models/` directory:
- `unet_model.h5`: U-Net segmentation model
- `deeplabv3plus_model.h5`: DeepLabV3+ segmentation model
- `segnet_model.h5`: SegNet segmentation model
- `final_generator.keras`: Generator model for SAR to optical translation

## Land Cover Classes
The toolkit uses the ESA WorldCover classification scheme with 11 classes:
1. Trees (Dark green)
2. Shrubland (Orange)
3. Grassland (Light green)
4. Cropland (Yellow)
5. Built-up (Red)
6. Bare (Brown)
7. Snow (White)
8. Water (Blue)
9. Wetland (Dark cyan)
10. Mangroves (Bright green)
11. Moss (Light grey)

## Input Data
- Supported formats: GeoTIFF (.tif, .tiff), PNG (.png), JPEG (.jpg, .jpeg)
- Single images or ZIP archives containing multiple images
- Optional ground truth data for comparison and metrics calculation

## Output
- Colorized SAR images with land cover classification
- Optical-like imagery generated from SAR data
- Visualization with original SAR, segmentation, and generated imagery
- Metrics when ground truth is provided (pixel accuracy, PSNR, SSIM)
- Downloadable results in PNG format or ZIP archives for batch processing

## Technical Details
- The SAR Colorization application uses semantic segmentation models to classify each pixel in SAR imagery
- The SAR to Optical Translation application uses a two-stage approach:
  1. Segmentation of SAR imagery into land cover classes
  2. Generation of optical-like imagery using the segmentation as guidance



## Project Guidance
This project was developed under the guidance of Dr. Jaya Saxena (Scientist Engineer-SF,NRSC,ISRO).

## Authors
- Varun & Mokshyagna (NRSC, ISRO)
-varunravichander2007@gmail.com
-reddymokshyagna@gmail.com



## Version
1.0.0