# ArtificialVision_PreliminaryResults

Here we find the preliminary results for the Artificial Vision Subject. It involves a research for 1D datasets about Power Quality Disturbances / Faults, the generation of a 2D dataset using wavelet transform, and the training and validation of a CNN.

# Visualizing the Grid: Power Quality Classification via Time-Frequency Spectrograms

## Problem Description
The stability of modern electrical power systems is increasingly threatened by Power Quality Disturbances (PQDs) such as voltage sags, swells, harmonics, and high-frequency oscillatory transients. 

## Solution Statement
This project transforms 1D electrical time-series signals into 2D time-frequency spectrograms utilizing the Continuous Wavelet Transform (CWT). A Convolutional Neural Network (CNN) is then deployed to treat the signal analysis as a computer vision problem, extracting spatial features to successfully classify six distinct types of simple and complex grid disturbances.

## Preliminary Advances
A comprehensive dataset of 18,000 synthetic PQD signals (across 6 classes) was mathematically generated based on IEEE 1159 parameters and successfully transformed into 2D CWT spectrograms. Subsequently, a custom CNN architecture was developed, compiled, and validated on the image dataset, effectively resolving the feature overlap and proving the viability of the deep learning approach. As the results seemed to be too good to be true, the following step was to use an existing dataset. Then a 1D-dataset  with 17 classes was used for generating a 2D dataset. Then the same steps for the sinthetic data was implemented to see a more realistic result.

## Final Results
For the final part of the Artificial Vision project some improvements were accomplished, as well as some more experiments. In the following the list of improvements and experiments are shown.
- Improvements for the CNN
  1. SpecAugment (Time and Frequency Masking)
  2. CLAHE (Contrast Limited Adaptive Histogram Equalization)
  3. Grayscale Conversion vs. Colormaps
- Training amd Validating a CRNN
- Training amd Validating a MobileNetV2
- Training and validating an SVM
- Final comparison between all models and approaches


## File Structure
```text
/
├── 1stExperiments_SyntheticData.ipynb        # Generates 1D PQ signals and saves them as 2D CWT PNG images
                                              # Defines and trains the Deep Learning CNN architecture
├── ExistentDataset_CNN_Classifier.ipynb      # Process the 1D signals to get a 2D dataset
                                              # Defines and trains the Deep Learning CNN architecture
├── ExistentDataset_CNN_Classifier_Additional_Preprocessing.ipynb      # Adds the preprocessing improvements proposed to the CNN
                                              # Defines and trains the Deep Learning CNN modified/enhanced architecture
                                              # Defines and trains the Deep Learning CRNN architecture
                                              # Defines and trains the MobileNetV2 architecture
                                              # Final Performance Comparison
├── Non_DL_SVM.ipynb                          # Performs a complete feature extraction process for the SVM
                                              # Defines and trains the SVM                                              
                                              # Final Performance Comparison
├── /pq_complex_spectrograms/ # Directory containing the generated image dataset (excluded from repo)
│   ├── /Complex
│   ├── /Harmonics
│   ├── /Normal
│   ├── /Sag
│   ├── /Swell
│   └── /Transient
├── /SEED_CVS_DATA/ # Directory containing the existing dataset
│   ├── /Pure_Sinusoidal
│   ├── /Sag
│   ├── /Swell
│   ├── /Interruption
│   ├── /Transient
│   ├── /Oscillatory_Transient
│   ├── /Harmonics
│   ├── /Harmonics_with_Sag
│   ├── /Harmonics_with_Swell
│   ├── /Flicker
│   ├── /Flicker_with_Sag
│   ├── /Flicker_with_Swell
│   ├── /Sag_with_Oscillatory_Transient
│   ├── /Swell_with_Oscillatory_Transient
│   ├── /Sag_with_Harmonics
│   ├── /Swell_with_Harmonics
│   ├── /Notch
└── README.md                 # Project documentation
