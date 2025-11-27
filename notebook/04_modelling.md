## Stage 4 Modelling

Notes
Build orange workflow: cleaned data - select columns - remove day (irrelevant data as previously identified) - data sampler (80%, 20% to be future test set) - test and score - logistic regression - kNN - random forest.

Set test and score to 5 folds

# Logistic regression

- Linear baseline for skewed numbers
- Moderately collinear (L2)
- Small ish data set, less likely to have overfitting problems

Model	Hyperparameters	        Why test this	             What to expect	           CA 
LR #1	L2 penalty, C = 1.0	    Baseline	                 Good generalisation	0.634
LR #2	L2 penalty, C = 0.1	    Stronger regularisation	     Performs worse	        0.613
LR #3	L1 penalty, C = 1.0	    Sparsity/ feature selection	 Drop less important features	0.632
LR #4	L2 penalty, C = 0.5	    Moderate	Reduce noise from weak features	        0.620

# kNN

Experiment	K	Metric	    Weights	 Expected	         CA
kNN #1	    3	Euclidean	uniform	 Noisy	            0.823
kNN #2	    5	Euclidean	uniform	 Likely to be good	0.811
kNN #3	    7	Euclidean	Distance Good for skew	    0.828
kNN #4	    9	Manhattan	uniform	 Might resist outliers	0.821
kNN #5	    11	Euclidean	uniform	Stable, underfitting?	0.799

Potential issues with kNN:
- Number ranges vary greatly
- DC will dominate distance calculations unless scaled
- However, orange will automatically normalise if not scale

# Random forest

- Non linear and robust
- Extension of decision tree work from practical 4
- Able to handle skewed distributions
- insensitive to scaling
- Nonlinear relationships (useful given frequency of normal distributions?)

Experiment	Trees	Max depth	Split	Expected	                CA
RF #1	     100	None	     2	    Strong baseline	            0.867
RF #2	     100	10	         2	    Usually best generalisation	0.867
RF #3	     200	10	         2	    Improves stability	        0.855
RF #4	      50	5	         2	    Shallow tree	            0.814
RF #5	     200	None	     2	    Might overfit data	        0.862

# Results

# Logistic regression

- Low accuracy (0.61-0.63)
- Struggles as fire behaviour is non linear
- L2 better than L1
- Linear models not ideal for environmental data

# kNN

- kNN #3 performs best
- CA around 0.828, strong performance bit not as good as Random forest
- Either too noisy or too smoothing
- Indicating moderate non-linearity and the importance of weighting closer neighbours more strongly.

# Random forest

- Best results from RF #1 and #2.
- Depth reduction to 10 did not affect performance
- 50 trees underfit
- Handles interactions, non-linearity, skewed environmental variables, good for small data sets.

# The best model - random forest #2

- Shallower trees, therefore less overfitting
- Same accuracy as unlimted depth model


