# Enhanced Filter Selection (EFS) - Hybrid Feature Selection Algorithm

This project introduces a novel, performance-driven approach to feature selection. It optimizes machine learning models by systematically evaluating ranked feature subsets using an early-stopping grid search, bridging the gap between fast filter methods and high-accuracy wrapper methods.

**Academic Research & Implementation | Published 2025**

> This algorithm and the accompanying research paper were developed and published during my **2nd year of undergraduate studies**, representing an early-career contribution to the field of Computational Intelligence and Data Preprocessing.

## Overview
Traditional filter-based feature selection methods often rely on arbitrary thresholds and lack feedback from the learning algorithm. This project implements the **Enhanced Filter Selection (EFS)** algorithm, which addresses these gaps. By incorporating a performance-driven feedback loop and a "patience" parameter (early stopping), EFS identifies the optimal feature subset that maximizes model accuracy while significantly reducing computational overhead.

The system was tested against benchmark datasets (Lung Cancer, Ionosphere, and Sonar), demonstrating superior performance in dimensionality reduction compared to standard Chi-Square and Mutual Information methods.

## Features
- **Early-Stopping Logic:** Implements a "patience" parameter to prevent exhaustive searching once accuracy stabilizes.
- **Hybrid Scorer Method:** Integrates traditional statistical ranking (Chi2, MIC) with machine learning model feedback.
- **Dynamic Subset Selection:** Automatically determines the optimal number of features ($k$) instead of using fixed thresholds.
- **Multi-Metric Support:** Compatible with various ranking methods including Chi-Square, Mutual Information (MIC), and Variance.
- **Optimized Performance:** Reduces "Feature Fatigue" in models, improving both training speed and interpretability.

## How It Works
- **Ranking Phase:** Input features are ranked using a statistical filter method (e.g., Mutual Information).
- **Iterative Evaluation:** The algorithm adds features one-by-one based on their rank.
- **Model Feedback:** At each step, a Random Forest (or specified model) evaluates the current subset's accuracy.
- **Global Optima Tracking:** The system keeps track of the highest accuracy ($a^*$) and the corresponding feature set ($F^*$).
- **Early Termination:** If accuracy does not improve for a set number of steps (the patience $p$), the algorithm stops to save time.
- **Final Selection:** The system returns the smallest, most efficient feature subset that achieved the best result.

## Research Publication
This implementation is based on the paper: 
**"An Enhanced Filter-based approach for Feature Selection"** *Authors: Mohammed Ammar Mohammed & Shereen Fathy El-Feky (2025)*

## Prerequisites
- Python 3.x
- Required libraries: numpy, scikit-learn, pandas
