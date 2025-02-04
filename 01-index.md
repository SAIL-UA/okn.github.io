---
layout: default
title: "Home"
nav_order: 1
permalink: /
---

# LEAP Dataset for ACL Reconstruction

## Overview

The Lower Extremity Assessment Protocol (LEAP) is a program to prevent reinjury and promote long-term health by characterizing muscle function, evaluating movement performance, and monitoring patient-reported outcomes (e.g., pain). The purpose of this study is to learn more about the outcomes following orthopaedic surgery after a lower limb injury. This dataset is designed for analyzing and classifying ACL (Anterior Cruciate Ligament) injuries using motion data collected from wearable sensors.  This dataset enables personalized classification of ACL injury conditions based on gait patterns observed during walking and jogging. It provides valuable insights into the biomechanics of injured individuals compared to healthy controls, assisting researchers and clinicians in rehabilitation assessment and injury prevention.

## Background

With the advancement of wearable sensor technology, gait data analysis has emerged as a crucial tool for identifying motion impairments. Traditional methods like video-based motion capture are expensive and require complex setups. The LEAP dataset leverages accelerometer and gyroscope data from body-worn sensors to perform movement classification using machine learning. The dataset contains motion data from **131 participants**, including **109 individuals with ACL injuries**. 

## Access to Dataset

If you would like to have access to the LEAP dataset, please send an email to **jiaqi.gong@ua.edu** stating your purpose and affiliated organization.


## Data Collection

Participants wore **five Shimmer sensors** placed on:
- Left Ankle
- Right Ankle
- Left Wrist
- Right Wrist
- Sacrum

Each participant performed the following activities:
- **Walking** (3 minutes at 3 mph)
- **Jogging** (3 minutes at 6 mph)

The data was originally recorded at a 128Hz sampling rate to effectively capture motion dynamics. During preprocessing, we downsampled it from 128Hz to 60Hz to optimize data handling and analysis.

## Workflow

The LEAP dataset follows a structured pipeline for processing sensor data and generating machine learning-ready features:

1. **Data Preprocessing** - Extracts raw motion sensor data.
2. **Feature Matrix Generation** - Computes time and frequency domain features.
3. **Label Assignment** - Maps ground truth labels based on demographics and injury status.
4. **Model Training & Evaluation** - Trains classifiers to distinguish injured vs. healthy individuals.
5. **Feature Importance Analysis** - Identifies key biomechanical features contributing to classification.
6. **t-SNE Visualization** - Visualizes high-dimensional feature space to observe separability.

## Workflow Overview

The following diagram provides an overview of the LEAP data processing and analysis workflow:

![Workflow Diagram](/media/workflow.png)


## Example Results

The dataset has been used to train multiple machine learning models, including SVM, KNN, Naïve Bayes, Random Forest, and Neural Networks. The figure below illustrates some of the key results, including **model accuracy comparisons, t-SNE embeddings, and recovery duration analysis**.

![Example Results](/media/result.png)

## Getting Started

To start using the LEAP dataset, follow these steps:
1. Install the required dependencies ([Installation Guide](installation.md)).
2. Load sensor data ([Data Load](data-load.md)).
3. Generate the feature matrix ([Generate Feature Matrix](generate-feature-matrix.md)).
4. Assign labels to the dataset ([Get Label](get-label.md)).
5. Train and evaluate models ([Train Model and Save Model](train-model-save-model.md)).
6. Perform feature analysis and visualization ([Feature Importance Analysis](feature-importance-analysis.md) & [t-SNE Visualization](tsne-visualization.md)).


## License

This dataset and associated code are released under the MIT License. See the [LICENSE](LICENSE) file for details.

---

For questions or contributions, visit the [GitHub Repository](https://github.com/SAIL-UA/LEAP).




