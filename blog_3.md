# Who Left The Damn Sink On?: Data Leakage in Data Science

---

## Data can leak?? I didn't know my PC came with a sink?
Well, in this context, no data leakage has nothing do to with a leaky sink. Instead data leakage is a problem data scientists may face which would lead to inaccurate model performances and flawed predictions. This blog will explore what causes data leakage and how to prevent it.
<br>
<br>

## Understanding Data Leakage:
Data leakage in data science refers to the scenario where information that should not be available at the time of model training or prediction inadvertently influences the model's performance. It occurs when features or information that are not representative of the real-world scenario are included in the training process, leading to overly optimistic performance metrics or biased predictions.
<br>
<br>

## How could I let this happen D:
There are quite a few moments when data leakage can occur:
- Preprocessing steps: 
    - scaling, normalization, or imputation, should be performed separately for the training and testing data. If these steps are mistakenly applied to the entire dataset before splitting, information from the testing set can "leak" into the training process, leading to biased results.
- Target leakage occurs when information directly related to the target variable is included in the feature set. 
    - For example; including future information that would not be available at the time of prediction can lead to overly optimistic performance.
- Overfitting to validation or test sets: 
    - Iteratively modifying the model based on the evaluation of performance metrics on the validation or test sets can inadvertently lead to overfitting. This occurs when the model learns specific patterns or characteristics of the validation or test data, rather than generalizing well to unseen data.

## Gross my data leaked everywhere, what's my mop n bucket?
Obviously leakage = bad, how can I prevent bad?
- Strict separation of training and testing data: 
    - Ensure a clear separation between the training and testing data before any preprocessing steps or model training. This prevents information from the testing set from inadvertently influencing the model.
- Careful preprocessing and feature engineering: 
    - Apply preprocessing steps, such as scaling or imputation, separately to the training and testing data. This ensures that the preprocessing techniques used are representative of real-world scenarios.
- Feature selection and target leakage avoidance: 
    - Carefully analyze the feature set to ensure that no information related to the target variable is included. Remove features that may cause target leakage, preventing the model from learning based on future information.
- Cross-validation techniques: 
    - Implement robust cross-validation techniques, such as k-fold cross-validation, to evaluate model performance. This helps ensure that the model generalizes well to unseen data and is not overly optimized for specific subsets.
- Regularization and model complexity control:
    - Incorporate regularization techniques, such as L1 or L2 regularization, to prevent overfitting and improve the model's ability to generalize to new data.
- Validation set as a safeguard: 
    - Set aside a validation set from the training data to monitor model performance during training and make informed decisions on model modifications. However, ensure that the validation set is not used in an iterative manner that can lead to overfitting.
<br>
<br>

---


## Wow thats it?
Data leakage in data science can happen easily, and ruin your model's prediction and performance easily too. But by understanding what causes data leakage, and how to prevent data leakage, your model will be protected from such blights~ I hope this blog was helpful in understanding data leakage, and don't forget to turn off that sink from now on ;)