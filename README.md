# Coresets
This project leverages the concept of coresets to improve the efficiency and accuracy of machine learning models on large datasets. The project involves building and utilizing coresets from the Covertype dataset to train and update logistic regression models. By using coresets, we aim to significantly reduce the amount of data required for training without compromising the model's performance.

## Explanation of Coresets
Coresets are small, weighted subsets of a larger dataset that approximate the original dataset's properties. They are particularly useful for large-scale data problems, enabling faster and more efficient training of machine learning models. The main idea is to select a representative subset of the data that retains the essential characteristics and distribution of the full dataset. This reduces computational overhead and storage requirements while maintaining model accuracy.

## Project Workflow
1. Data Preparation:
- Load the Covertype dataset and split it into training and test sets.
- Further split the training set into two parts: train_1 and train_2.

2. Build Initial Coreset:
- Create a CoresetTreeServiceLG object to handle the coreset operations.
- Build the initial coreset using the train_1 dataset and save it to the local file system.
  
3. Train Models:
- Train a logistic regression model on the coreset.
- Train a logistic regression model on the full train_1 dataset for comparison.
- Evaluate both models using the test dataset and compare their AUC scores.
  
4. Partial Build and Updating Coreset:
- Partially build the coreset tree using the train_2 dataset.
- Select important samples for cleaning and perform updates to targets and features.
- Remove specific samples from the coreset tree.
  
5. Retrain and Evaluate:
- Retrain the logistic regression model on the updated coreset.
- Retrain the model on the full updated dataset.
- Evaluate the performance of the updated models using the test dataset.
  
## Results
The project demonstrates the efficiency of coresets in maintaining high model performance with significantly fewer data points. The logistic regression model trained on the coreset achieved comparable AUC scores to the model trained on the full dataset, highlighting the effectiveness of using coresets for large-scale data problems.

