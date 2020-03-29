# Supervised Learning

## Dataset partition
1. Collect data
2. Divides dataset in to two parts
  - Training set
  - Test set
3. Use accuracy in test set to predict acutal accuracy in the future(called **generalization** accuracy)

** Predicted accuracy doesn't really match to the real case.

*More complicated case*: dataset divided in to three parts
- Training set(60%)
- Validation set(20%)
- Test set(20%)

Validation set is used to deteremine hyper parameters of the classifier
**Don't use Test set to do anything other than accuracy prediction**

## Errors
We have training set & test set; training set for training error, test error for test set.

We can increase **model complexity** to reduce training error, for example, from 1st order increased to 2nd order. The model complexity is related to **VC-dimension**

### Not all errors are equal
- Influences of COVID-19 test if:
  - Flase positive(given negative, but predict positive)
  - Flase negative(gitven positive, but predict negative): *Dangerous)*
- Other terms(exercise)
  - Precision vs recall
  - Sensitivity vs specificity

## Bias & variance
Bias: A tendency of model, the errors will have more likely tendency in manipulate.
Variance: The accuracy of all values.

- Low-order model may have
  - **High bias** and low variance
  - High training error (**underfitting**) & high test error
- High-order model may have
  - Low bias but **high variance**
  - High test error **overfitting**

We often prefer a simpler model since a simple model have following 
