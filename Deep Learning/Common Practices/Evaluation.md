data to be annotate by multiple humans to avoid human error and take a mean or majority vote


all performance measures have a thrushold
 ROC - evaluate classifiers for all thrushold


K - Fold cross validation
for fewer datasets we can use k fold 
where we split the data k times, use k-1 fold as training and k for testing and repeat k times  
variance of the results are undersetimated, because trainig runs are not independent


we can use t-test to see if  the difference of the results is significantly different 

Bonferroni Correction:
if we train multiple model on the same data - we have to correct the sigificance computation
if we compare multiple classifiers we need to adjust alpha (significance) such that alpha' = alpha / n