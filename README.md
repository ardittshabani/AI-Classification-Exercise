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
