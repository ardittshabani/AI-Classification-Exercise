# Classification Algorithms Comparison Report

## Dataset Overview
- **Dataset**: IRIS Dataset
- **Samples**: 150
- **Features**: 4
- **Classes**: 3
- **Train/Test Split**: 70%/30%
- **Cross-Validation**: 5-fold

## Dataset Summary

| Class | Samples | Percentage |
|-------|---------|------------|
| Setosa | 50 | 33.3% |
| Versicolor | 50 | 33.3% |
| Virginica | 50 | 33.3% |

## Feature Analysis

### Feature Importance (ANOVA F-Score)

| Feature | F-Score | p-value |
|---------|---------|---------|
| petal length (cm) | 814.73 | 0.0000 |
| petal width (cm) | 791.35 | 0.0000 |
| sepal length (cm) | 95.76 | 0.0000 |
| sepal width (cm) | 33.06 | 0.0000 |

## Model Performance Comparison

| Classifier | Accuracy | Precision | Recall | F1-Score | CV Score (Mean ± Std) | Train Time (s) | Pred Time (s) |
|------------|----------|-----------|--------|----------|-----------------------|----------------|---------------|
| k-NN | 0.9556 | 0.9608 | 0.9556 | 0.9554 | 0.9810 ± 0.0233 | 1.2850 | 0.001727 |
| Decision Tree | 0.9333 | 0.9345 | 0.9333 | 0.9333 | 0.9524 ± 0.0301 | 0.1519 | 0.000092 |
| Neural Network | 0.9111 | 0.9155 | 0.9111 | 0.9107 | 0.9143 ± 0.0555 | 0.5617 | 0.000126 |

## Optimal Hyperparameters

### k-NN
```python
{
    'metric': 'euclidean',
    'n_neighbors': 9,
    'weights': 'uniform'
}
```
### Decision Tree
```python
{
    'criterion': 'gini',
    'max_depth': None,
    'min_samples_leaf': 1,
    'min_samples_split': 5
}
```
### Neural Network
```python
{
    'activation': 'relu',
    'alpha': 0.0001,
    'hidden_layer_sizes': (50, 25),
    'learning_rate': 'constant',
    'max_iter': 1000,
    'n_iter': 21,
    'loss': 0.7015698721526835
}
```
### Statistical Significance Analysis
ANOVA Test

F-statistic: 2.9600
p-value: 0.0902
Conclusion: No significant difference between classifiers (p ≥ 0.05)

Pairwise t-test Results (p-values)
k-NNDecision TreeNeural Networkk-NN-0.07050.1079Decision Tree0.0705-0.3375Neural Network0.10790.3375-
Note: * p < 0.05, ** p < 0.01
Key Findings and Recommendations
Performance Metrics

 Best performing classifier: k-NN (Accuracy: 0.9556)
 Most discriminative feature: petal length (cm)
 Fastest training: Decision Tree (0.1519s)
 Most stable (CV): k-NN (0.9810)

