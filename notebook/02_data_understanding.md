# Step 2 Data Understanding

## Overview of data set
Contains forest fire obervations with weather and fire indices and a binary target inidating whether the burned area exceeds 4%. This includes understanding variable types, distributions, and whether each varible is suitable for modelling. 

Notes:
From file widget, we can confirm that month and day are both correctly set to categorical data.
    Changed area (binary variable) to target
    
From data table, no blank values
    Months and days seem to be inputted correctly
    No obvious impossible values or outliers at first glance
    Rain nearly all 0? Worth eliminating?
    
Area categorical (binary) - more true 292 vs 225
X discrete - spatial coordinate
Y discrete - spatial coordinate
Month categorical - highest freq in aug and sept, also highest recordings , only one value for each. 
Day categorical  - fairly even spread, likely to be irrelevant 
FFMC continuous - negative skew, more fires at a higher moisture content , OUTLIER 18.7 
DMC continuous - slight positive skew, 
DC continuous - 8 zero values (worth noting), negative skew
ISI continuous - positive skew 
Temp continuous - close to normal distribution, slight negative skew, not too high (above 40 would be unrealistic)
RH discrete - all between 16% and 98% so possible, negative skew 
Wind continuous - fairly normal, 4.5-5 most frequent 
Rain continuous, mainly zero (0) values, 1 outlier 6.4 
