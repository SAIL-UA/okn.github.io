---
layout: default
title: "Feature Importance Analysis"
nav_order: 7
---

# Feature Importance Analysis

## Overview

The `feature_importance_analyzer.py` module helps interpret trained models by analyzing feature importance. This process identifies the most influential features contributing to the model's predictions.

## Calculating Feature Importance

To compute feature importance using permutation importance, use the `analyze_permutation_importance` function:

```python
from leap import analyze_permutation_importance

analyze_permutation_importance(
    model_path='path/to/saved_model.pkl',
    feature_matrix='path/to/feature_matrix.npy',
    label='label_column',
    save_csv_path='path/to/save/importance.csv',
    heatmap_title='Feature Importance Heatmap'
)
```

### Parameters:
- `model_path` (str): Path to the trained model file.
- `feature_matrix` (str): Path to the feature matrix file.
- `label` (str): Column name of the target variable.
- `save_csv_path` (str): Path to save feature importance scores.
- `heatmap_title` (str): Title for the importance heatmap.

### Returns:
- A CSV file containing the feature importance scores.
- A heatmap visualization of feature importance.

## Visualizing Feature Importance

After running the analysis, a heatmap is generated using:

```python
from leap import plot_sensor_pair_importance

plot_sensor_pair_importance(
    csv_file='path/to/importance.csv', 
    title='Feature Importance Heatmap'
)
```

## Why Feature Importance Matters

Feature importance analysis helps:
- Understand which features contribute the most to predictions.
- Improve model performance by selecting the most relevant features.
- Provide interpretability for decision-making.

## Example Result

The following figure showed the example pair-wise sensor importance heatmap extracted from trained model:

![Heatmap](/media/heatmap.png)

## Next Steps

Once feature importance is analyzed, you can refine your model by selecting the most influential features or adjusting feature engineering strategies.
