---
layout: default
title: "Get Label"
nav_order: 5
---

# Get Label

## Overview

The `ground_truth_processor.py` module is responsible for assigning ground truth labels to each participant based on demographic data. These labels are crucial for supervised learning tasks.

## Required Data Structure

Ensure that the demographic data file and participant folders are correctly structured:

```
/demographics
    ├── demographic_data.xlsx
/data
    ├── Participant_001
    ├── Participant_002
```

Each row in `demographic_data.xlsx` should include:

```
Patient ID, Involved Limb, Sex
```

## Generating Ground Truth Labels

To generate labels, use the `generate_ground_truth` function:

```python
from leap import generate_ground_truth

ground_truth_stats = generate_ground_truth(
    demographic_file='path/to/demographic_data.xlsx', 
    parent_folder='path/to/data'
)
```

### Parameters:
- `demographic_file` (str): Path to the Excel file containing demographic data.
- `parent_folder` (str): Path to the participant data folder.

### Returns:
- A dictionary summarizing label counts and missing data statistics.

## Output Files

For each participant, a `Ground_Truth.txt` file is created in their respective folder containing:

```
<injury_status> <sex>
```

Example:
```
Left injured Male
```

## Error Handling

- If a participant is not found in the demographic data, they will be listed under `No Match Participants`.
- If certain demographic fields are missing, default values may be assigned.

## Next Steps

Once the labels are assigned, proceed to [Train Model and Save Model](train-model-save-model.md) to utilize the labeled data for machine learning tasks.
