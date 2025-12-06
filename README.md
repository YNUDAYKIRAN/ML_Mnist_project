# ML_Mnist_project

Project Overview
This project implements a robust, Object-Oriented Machine Learning pipeline designed to classify handwritten digits from the MNIST dataset.
Moving beyond simple scripting, this solution utilizes a modular Class-based architecture to automate the entire lifecycle of a machine learning project: from data ingestion and cleaning to multi-model training, comparative performance analysis (ROC/AUC), and automatic deployment of the best-performing model.

✨ Key Features
Object-Oriented Design (OOP): Encapsulated logic within the MNIST class for modularity, reusability, and error handling.
Automated Data Cleaning: Built-in exception handling to detect and remove NaN/missing values, ensuring pipeline stability.
Comparative Analysis: Simultaneously trains and evaluates 9 different classification algorithms to benchmark performance.
Advanced Metrics: Goes beyond accuracy by calculating Confusion Matrices, Classification Reports, and Micro-Average ROC Curves.
Hyperparameter Optimization: Integrated GridSearchCV capability to fine-tune model parameters.
Model Persistence: Logic to automatically identify the model with the highest AUC score and serialize it (.pkl) for future use.

Algorithms Implemented
The pipeline rigorously tests the following algorithms:
K-Nearest Neighbors (KNN)
Naive Bayes (GaussianNB)
Logistic Regression (LR)
Decision Tree (DT)
Random Forest (RF)
AdaBoost
Gradient Boosting (GB)
XGBoost (Extreme Gradient Boosting)
Support Vector Machine (SVM) - with Probability calibration

Pipeline Architecture
The project is structured around the MNIST class, executing the following workflow:
Initialization (__init__):
Loads dataset dynamically (local path or fallback).
Performs data cleaning and type casting.
Splits data into Training/Testing sets (80/20).
Binarizes labels for multi-class ROC calculation.

Training Phase (training):
Iterates through the model suite.
Fits models using multi-core processing (n_jobs=-1) where applicable.
Evaluation Phase (predictions & roc_auc_curve):
Generates probability distributions for test data.
Computes FPR/TPR for ROC Curves.
Plots a combined comparison graph.
Auto-Selection: Identifies the "Winner" based on the highest AUC score.
Optimization & Export:
Optional GridSearch module for hyperparameter tuning.
Exports the winning model using pickle.

Visualizations & Results
The pipeline generates comprehensive performance visualizations:
Confusion Matrix: To visualize misclassifications per digit.
ROC Curve Comparison: A single plot overlaying the performance of all 9 models to visually determine the superior classifier.
Note: In standard runs, Ensemble methods like XGBoost and Random Forest typically achieve >96% accuracy on this dataset.

Tech Stack
Core: Python
Data Manipulation: Pandas, NumPy
Machine Learning: Scikit-Learn, XGBoost
Visualization: Matplotlib, Seaborn

📄 License
This project is open-source and available under the MIT License.
