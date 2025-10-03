CLASSIFICATION ALGORITHMS COMPARISON REPORT
============================================================
Dataset: IRIS (150 samples, 4 features, 3 classes)
Train/Test Split: 70%/30%
Cross-Validation: 5-fold

DATASET SUMMARY
--------------------
• setosa: 50 samples (33.3%)
• versicolor: 50 samples (33.3%)
• virginica: 50 samples (33.3%)

FEATURE ANALYSIS
------------------
Feature Importance (ANOVA F-Score):
  • petal length (cm): 814.73 (p=0.0000)
  • petal width (cm): 791.35 (p=0.0000)
  • sepal length (cm): 95.76 (p=0.0000)
  • sepal width (cm): 33.06 (p=0.0000)

MODEL PERFORMANCE COMPARISON
--------------------------------
Classifier     | Accuracy | Precision | Recall | F1-Score | CV Score (Mean ± Std) | Train Time (s) | Pred Time (s)
------------------------------------------------------------------------------------------------------------------
k-NN           | 0.9556   | 0.9608    | 0.9556 | 0.9554   | 0.9810 ± 0.0233       | 1.2850         | 0.001727     
Decision Tree  | 0.9333   | 0.9345    | 0.9333 | 0.9333   | 0.9524 ± 0.0301       | 0.1519         | 0.000092     
Neural Network | 0.9111   | 0.9155    | 0.9111 | 0.9107   | 0.9143 ± 0.0555       | 0.5617         | 0.000126     

OPTIMAL HYPERPARAMETERS
--------------------------
k-NN:
  • metric: euclidean
  • n_neighbors: 9
  • weights: uniform

Decision Tree:
  • criterion: gini
  • max_depth: None
  • min_samples_leaf: 1
  • min_samples_split: 5

Neural Network:
  • activation: relu
  • alpha: 0.0001
  • hidden_layer_sizes: (50, 25)
  • learning_rate: constant
  • max_iter: 1000
  • n_iter: 21
  • loss: 0.7015698721526835

STATISTICAL SIGNIFICANCE ANALYSIS
------------------------------------
ANOVA Test: F = 2.9600, p = 0.0902
→ No significant difference between classifiers (p ≥ 0.05)

Pairwise t-test results (p-values):
                |         k-NN | Decision Tree | Neural Network
---------------------------------------------------------------
           k-NN |        -     |     0.0705   |     0.1079  
  Decision Tree |     0.0705   |        -     |     0.3375  
 Neural Network |     0.1079   |     0.3375   |        -    

* p < 0.05, ** p < 0.01

KEY FINDINGS AND RECOMMENDATIONS
------------------------------------
• Best performing classifier: k-NN (Accuracy: 0.9556)
• Most discriminative feature: petal length (cm)
• Fastest training: Decision Tree (0.1519s)
• Most stable (CV): k-NN (0.9810)
