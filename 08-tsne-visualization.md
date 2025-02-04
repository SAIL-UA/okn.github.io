---
layout: default
title: "t-SNE Visualization"
nav_order: 8
---


# t-SNE Visualization

## Overview

The `tsne_visualizer.py` module provides tools to visualize high-dimensional feature matrices using t-SNE (t-Distributed Stochastic Neighbor Embedding). This helps in understanding the clustering and separability of different classes in the dataset.

## Generating a t-SNE Plot

To generate a t-SNE plot, use the `plot_tsne` function:

```python
from leap import plot_tsne

plot_tsne(
    feature_matrix='path/to/feature_matrix.npy',
    model_path='path/to/trained_model.pkl',
    label_description={0: 'Class 0', 1: 'Class 1'},
    perplexity=30
)
```

### Parameters:
- `feature_matrix` (str or pd.DataFrame): Path to the feature matrix file or a DataFrame.
- `model_path` (str): Path to the trained model file.
- `label_description` (dict): A dictionary mapping class labels to meaningful names.
- `perplexity` (int): t-SNE perplexity parameter (default: 30).

### Returns:
- Two t-SNE scatter plots:
  - One colored by actual class labels.
  - One colored by the model’s prediction confidence.

## Why Use t-SNE?
- Helps visualize high-dimensional data.
- Provides insights into class separability.
- Assists in detecting misclassified samples.


## Example Result

The following figure showed the example T-sne result comparison with label-colored vs model-confidence-colored:

![T-sne](/media/tsne.png)


## Next Steps

After visualizing the feature space, you can refine feature selection, adjust model parameters, or further investigate class distributions.
