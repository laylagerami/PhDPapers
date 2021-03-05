#### Cross-Validation

Cross-validation is a ML technique which prevents overfitting. The general procedure is:
- Partition data into subsets
- Hold out a set at a time, and train the model on the remaining set
- Test the model on the held-out set
- Repeat

![[Screenshot 2020-12-18 at 13.33.20.png]]

**k-Fold Cross Validation**
This type of Cross-Validation requires a single parameter, k, which indicates the number of groups a data sample should be split into. The value of k is chosen, such that the train/test sets are sufficiently large enough to represent the underlying distribution of the broader dataset. 

![[Screenshot 2020-12-18 at 13.35.26.png]]

*Stratified* k-Fold Cross-Validation simply means that the data splitting process is guided by the proportion of class observations.

![[Screenshot 2020-12-18 at 13.37.36.png]]

**Leave One Out Cross Validation (LOOCV)**
This approach simply leaves out 1 data point from the training data. If there are n data points, then n-1 samples are used to tran the model, and 1 point is used as the validation set. This process is then repeated, such that all data points end up in the validation set once, and the error is averaged across all trials.

![[Screenshot 2020-12-18 at 13.39.12.png]]

#Permanent #PhD #ML