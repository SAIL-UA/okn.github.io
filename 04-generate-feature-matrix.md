---
layout: default
title: "Generate Feature Matrix"
nav_order: 4
---

# Generate Feature Matrix

## Overview

The `feature_matrix_generator.py` module processes raw sensor data and extracts relevant features to create a structured feature matrix. This matrix is essential for training machine learning models.

## Required Data Structure

Ensure that your sensor data is loaded correctly following the structure outlined in the [Data Load](data-load.md) section.

## Generating a Feature Matrix

To generate a feature matrix, use the `generate_feature_matrix` function:

```python
from leap import generate_feature_matrix

saved_files = generate_feature_matrix(
    parent_path='path/to/data', 
    phase='Walk', 
    increment=600, 
    class1='Left', 
    class0='Right', 
    save_path='path/to/save', 
    frequency_thresholds=[8, 16, 32]
)
```

### Parameters:
- `parent_path` (str): The base directory containing participant data.
- `phase` (str): The movement phase (e.g., 'Walk', 'Jog').
- `increment` (int): Time window increment.
- `class1` (str): Label for class 1 (e.g., "Left").
- `class0` (str): Label for class 0 (e.g., "Right").
- `save_path` (str): Directory where processed feature matrices will be saved.
- `frequency_thresholds` (list): List of frequency thresholds for processing (e.g., [8, 16, 32]).

### Returns:
- A dictionary containing paths to the saved `.npy` feature matrix files.

## Output Files

Each frequency threshold generates two output files:
- `freq_<freq>_<class1>_<class0>_<phase>.npy`: The feature matrix.
- `data_<freq>_<class1>_<class0>_<phase>.npy`: Raw sensor data corresponding to the features.

## Next Steps

After generating the feature matrix, proceed to [Sensor Data Processing](sensor-data-processing.md) for further transformations and feature extraction.






