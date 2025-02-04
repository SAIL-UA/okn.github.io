---
layout: default
title: "Train Model"
nav_order: 6
---

# Train Model and Save Model

## Overview

The `model_trainer.py` module is responsible for training machine learning models using the generated feature matrix and saving the best-performing model.

## Training a Model

To train a model, use the `train_and_save_model` function:

```python
from leap import train_and_save_model

model_path = train_and_save_model(
    phase='Walk', 
    class1='Left', 
    class0='Right', 
    save_path='path/to/save', 
    frequency_thresholds=[8, 16, 32], 
    classifier_name='KNN'
)
```

### Parameters:
- `phase` (str): The movement phase (e.g., 'Walk', 'Jog').
- `class1` (str): Label for class 1 (e.g., "Left").
- `class0` (str): Label for class 0 (e.g., "Right").
- `save_path` (str): Directory where trained models should be saved.
- `frequency_thresholds` (list): List of frequency thresholds to process (e.g., [8, 16, 32]).
- `classifier_name` (str): Classifier to train and save (e.g., "KNN", "Random Forest").

### Returns:
- A string containing the path of the saved model file.

## Available Classifiers

The following classifiers are available for training:
- Support Vector Machine (SVM)
- Naive Bayes
- Random Forest
- K-Nearest Neighbors (KNN)
- Neural Network (MLP)

## Model Evaluation

The function trains multiple classifiers and evaluates them using:
- Accuracy
- Precision
- Recall
- F1-score

Performance metrics are visualized in plots for comparison.

## Saving the Best Model

After evaluation, the best-performing model is saved as a `.pkl` file:

```
best_knn_model_walk_left_vs_right_8hz.pkl
```

## Next Steps

Once the model is trained, proceed to [Feature Importance Analysis](feature-importance-analysis.md) to interpret the model's decision-making process.
