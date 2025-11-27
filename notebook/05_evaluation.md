## Stage 5 Evaluation

Evaluate the chosen model and test on unseen data. (20% leftover from data sampler = test data)
Interpret results - does this meet business objective?
Confusion matrix 

Using RF #2
Hyperparameters chosen through controlled experiments
Performed on validation folds

I retrained the final model using 100% of the cleaned training data (the 80% split).
This ensures the final model benefits from all available information before being
evaluated on the held out 20% test set.

# Results

Classification accuracy = 46+45/ 103 = 0.8835

FN = 9
FP = 3

91 correct out of 103

# Insights

1. Best performing models were kNN (distance based - sensitive to feature differences) and Random Forest (tree based - sensitive to thresholds in variables)
if environmental features were weak predictors kNN and RF accuracy would be lower
Logistic regression wouldn't under perform

Predictive power must come from environmental indices as they are the only ones in table - high performance = strong signal

RF builds trees using threshold based splits on the strongest predictors, shallow trees (depth = 5) performed the worst.

= implies that indices are important factors 

2. Outperformed logistical regression implying that fire severity depends on non linear interactions.

3. More false negatives - more likely to not flag a severe fire.

4. CV accuracy and test accuracy are close.