# SVM Optimization Assignment

## Project Overview

This project implements an optimization of a Support Vector Machine (SVM) model using the NuSVC classifier from scikit-learn. The goal is to optimize the SVM hyperparameters for a multi-class classification task on a dataset from the UCI Machine Learning Repository. The dataset is split into 10 different 70-30 train-test samples, and for each sample, hyperparameter optimization is performed using Optuna over 100 trials. The best parameters and test accuracies are reported, and a convergence graph is plotted for the sample with the highest test accuracy.

## Dataset Description

- **Dataset**: Letter Recognition
- **Source**: UCI Machine Learning Repository
- **Number of Instances**: 20,000
- **Number of Features**: 16 (numerical attributes representing letter image characteristics)
- **Number of Classes**: 26 (corresponding to letters A-Z)
- **Task**: Multi-class classification to predict the letter based on features

## Implementation Details

- **Data Splitting**: The dataset is divided into 70% training and 30% testing sets across 10 different random states (seeds 0-9).
- **SVM Model**: NuSVC (Nu-Support Vector Classification) from scikit-learn is used, suitable for multi-class problems.
- **Hyperparameter Optimization**:
  - **Tool**: Optuna
  - **Parameters Optimized**:
    - `kernel`: Choice between 'linear', 'rbf', and 'poly'
    - `nu`: Float between 0.01 and 1.0
    - `gamma`: Log-uniform between 1e-4 and 1e2 (for 'rbf' and 'poly' kernels)
  - **Objective**: Maximize 5-fold cross-validation accuracy on the training set
  - **Trials**: 100 per sample
- **Evaluation**: After optimization, the best parameters are used to train the NuSVC model on the full training set, and accuracy is evaluated on the test set.
- **Visualization**: A convergence graph plots the best cross-validation accuracy over 100 trials for the sample with the highest test accuracy.

## Results

### Table 1: Comparative Performance of Optimized SVM with Different Samples

| Sample # | Best Accuracy | Best SVM Parameters |
| --- | --- | --- |
| S1 | \[TBD\] | kernel: \[TBD\], Nu: \[TBD\], Gamma: \[TBD\] |
| S2 | \[TBD\] | kernel: \[TBD\], Nu: \[TBD\], Gamma: \[TBD\] |
| ... | ... | ... |
| S10 | \[TBD\] | kernel: \[TBD\], Nu: \[TBD\], Gamma: \[TBD\] |

*Note*: Replace \[TBD\] with actual values after running the notebook.

### Figure 1: Convergence Graph

The graph shows the optimization history for the sample with the highest test accuracy, plotting the best cross-validation accuracy against iteration number.

## Basic Data Analytics

1. **Dataset Shape**: 20,000 rows, 17 columns (16 features + 1 target)
2. **Class Distribution**:
   - Approximately balanced across 26 classes (A-Z), with each letter having around 700-800 instances (exact counts available in the notebook output).

**Feature Statistics**: Numerical features represent image attributes (e.g., x-box, y-box, width, height). Further analysis (e.g., histograms) can be added to explore distributions.

## How to Run

1. **Requirements**: Install dependencies via `pip install pandas numpy scikit-learn optuna matplotlib`.
2. **Execute**: Run the Python notebook (`svm_optimization_notebook.py`) to generate results, table, and graph.
3. **Output**: Results are printed to the console, and the convergence graph is saved as `convergence_graph.png`.

## License

This project is for educational purposes and uses a publicly available dataset from UCI.
