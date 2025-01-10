# CS412 Machine Learning Course Project

## Overview of the Repository
This repository contains the notebooks for each round and documentation related to the project. Below is an overview of the key components:

### Notebooks
- **`project_round1.ipynb`**: Jupyter Notebook for Round 1 of the project.
- **`project_round2.ipynb`**: Jupyter Notebook for Round 2 of the project.
- **`project_round3.ipynb`**: Jupyter Notebook for Round 3 of the project.

## Methodology
This section provides a high-level explanation of the methodology used in the project in each round:

1. **Round 1**:
    - We didn't apply any change regarding the logic implemented in the notebook provided by the instructor.
    - Our only proper change was to fix an error in regression part.
    - The reasoning behind it was to provide a base for us to compare our results in next rounds.
    - We obtained 0.67 training set accuracy, and 0.57 validation set accuracy in classification task, and 1.227 log MSE in regression task.
    - Note: You can discard the last code cell of this notebook, as its' error is irrelevant.

2. **Round 2**:
    - In classification part, we applied a random forest classifier.
    - Using grid search with 5 fold cross-validation, we observed that best hyperparameters for this classifier, are max_features = 'sqrt', min_samples_split = 50.
    - We obtained 0.88 training set accuracy, and 0.56 validation set accuracy.

    - In regression part, we also decided to apply a random forest regressor.
    - Due to the need to use extensive GPU, we didn't use grid search, and through trial and error, 
    we obtained n_estimators=50 and min_samples_split=400 as the best hyperparameters, in regards to
    both performance and resource issue.
    - We obtained 0.39 training set accuracy, and 0.40 validation set accuracy.
    - Note 1: In regression part, we thought that comment_counts could be a good indicator
    to estimate like_counts, therefore we used that as well.
    - Note 2: We couldn't make a change in time of round 2 submission due to our tight exam schedule therefore it was the same as round 1, however the changed and complete code is available now.

3. **Round 3**:
    - In classification part, we applied a XGBoost classifier.
    - We used label encoder to encode categories.
    - Again, through trial and error, we obtained n_estimators=200, max_depth=2, learning_rate=0.1, reg_alpha=0.6, gamma = 0.3 and early_stopping_rounds = 10.
    - We obtained 0.90 training set accuracy, and 0.65 validation set accuracy.

    - In regression part, we also decided to apply a XGBoost regressor.
    - Again, through trial and error, we obtained n_estimators=200, learning_rate=0.05, early_stopping_rounds = 10, objective="reg:squarederror".
    - We obtained 0.62 training set accuracy, and 0.53 validation set accuracy.

    - Note: In both parts, we included comment_counts, follower_count, following_count, is_business_account, is_private, is_verified in our dataframes.

## Results
Overfitting and managing GPU usage was our main issues in this project. Due to the number of features in comparison to the number of data available, the dataset was prone to overfitting. We managed to reduce overfitting by finding best possible hyperparameters, but only to an extend.

- **Obtained Accuracies**:
    - Naive Bayes Classifier:
        - Training Accuracy: 67%
        - Validation Accuracy: 57%
    - Random Forest Classifier:
        - Training Accuracy: 88%
        - Validation Accuracy: 56%
    - Random Forest Regressor:
        - Training Accuracy: 39%
        - Validation Accuracy: 40%
    - XGBoost Classifier:
        - Training Accuracy: 90%
        - Validation Accuracy: 65%
    - XGBoost Regressor:
        - Training Accuracy: 62%
        - Validation Accuracy: 53%


## Team Contributions

- **Ali Murat Ergül**:
    - Contributions: Responsible for implementing Random Forest Classifier and data preprocessing in Part 2, and XGBoost Regressor in Part 3. Also responsible for managing the Github repo.

- **Parla Güven**:
    - Contributions: Responsible for implementing Random Forest Regressor and data preprocessing in Part 2, and XGBoost Classifier and data preprocessing in Part 3.

---

For any questions or clarifications, feel free to reach out via the repository issues page or contact the team.
