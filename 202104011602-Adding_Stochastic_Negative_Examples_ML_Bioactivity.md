#### Adding Stochastic Negative Examples into Machine Learning Improves Molecular Bioactivity Prediction
By: Caceres et al, JCIM, 2020

Public datasets are sparse, imbalanced and approximate. 
![[Screenshot 2021-01-04 at 16.23.20.png]]
Bias in QSAR datasets could be due to publication bias toward well-studied molecules or those with positive binding profiles, These skew the data set and therefore the ML models. Thus the authors explore method that leverages uncertainty in unexplored chemical space to augment incomplete public data for activity prediction. Previous approaches for re-balancing data sets are in [[202104011624-Rebalancing_Data_Sets]].

The process, SNA, adds more molecule-protein pairs to a training set where negative examples are otherwised outnumbered and/or unevenly distributed. Exploits the observation that ligand binding events are comparatively rare, despite the biases in the pharmacological data. SNA is carried out in an online fashion where new negative training examples for molecule-protein pairs are generated at each epoch to achieve a desired ratio of positives:negatives for each target. For baseline SNA, negatives are selected randomly from all unlabeled pairs in the data set. They also tried to restrict SNA by molecular similarity (using similarity ensemble approach to predict likely drug-target binders and removing them from being assigned as negatives), but this did not dramatically improve performance

Two splits - Time Split hold-out (fewer negatives, unrealistic class balance) [[202104011630-Time_Series_Hold_Out]] and Drug Screening use-case (preponderance of negatives), to simulate scenario of use. For the Drug Screening scenario, Drug Matrix (dense matrix, all molecules vs all proteins as in drug screening) was used with all protein-molecule interactions removed from the training set. SNA was also tested where negatives were removed from the training set to explore whether performance can be rescued.  

122% increase in drug-screening benchmark performance and 13% increase in temporal benchmark. Consistent for classification and regression tasks, and outperformed y-randomised controls. They found that SNA with a 1:1 positive:negative ratio improves performance on screening scenarios with minor penalty to temporal benchmarks. In addition, SNA corrected for the absence of true negatives when these were removed from the training set.

![[Screenshot 2021-01-04 at 16.35.29.png]]

#PhD #Permanent #ML #MoA 