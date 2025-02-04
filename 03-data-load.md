---
layout: default
title: "Data Load"
nav_order: 3
---

# Data Load

## Overview

The `data_loader.py` module is responsible for loading sensor data from structured directories. The module extracts accelerometer and gyroscope readings from different sensors placed on the body.

## Required Data Structure

Ensure that your data follows the required folder structure:

```
/data
    ├── Participant_001
    │   ├── LeftAnkle
    │   │   ├── Walking
    │   │   │   ├── 60s.csv
    │   │   ├── Jogging
    │   ├── RightAnkle
    │   ├── LeftWrist
    │   ├── RightWrist
    │   ├── Sacrum
    ├── Participant_002
```

Each CSV file should contain at least the following columns:

```
Timestamp, Acc_X, Acc_Y, Acc_Z, Gyro_X, Gyro_Y, Gyro_Z
```

## Loading Data

To load sensor data, use the `load_data` function:

```python
from leap import load_data

data = load_data(base_path='path/to/data', phase='Walking', window='60s')
```

### Parameters:
- `base_path` (str): The base directory where sensor data is stored.
- `phase` (str): The movement phase (e.g., 'Walking', 'Jogging').
- `window` (str): The window size identifier for the file (e.g., '60s').

### Returns:
- A list of NumPy arrays containing accelerometer and gyroscope data from different sensors.

## Error Handling

The function raises `FileNotFoundError` in the following cases:
- If the folder for a required sensor is missing.
- If the folder for the specified phase is missing.
- If the corresponding CSV file is not found.

## Next Steps

Once the data is successfully loaded, proceed to [Generate Feature Matrix](generate-feature-matrix.md) for further processing.
