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