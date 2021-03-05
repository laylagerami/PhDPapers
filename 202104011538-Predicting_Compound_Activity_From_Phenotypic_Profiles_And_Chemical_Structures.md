#### Predicting compound activity from phenotypic profiles and chemical structures
By: Becker, Carpenter et al.

Chemical structure-based features augmented with experimental information associated with each small molecule - L1000 and cell image assays.

![[Screenshot 2021-01-04 at 15.45.54.png]]

They ensured the held-out test set was chemically dissimilar to the training set, and achieved a number of assays with AUC > 0.9 ("well predicted"). 

Morphological profiles alone, then chemical structures, then gene expression profiles were best accurately able to predict the highest number of assays (67 of 376, vs. 43 and 23). 

They found a lack of overlap among assays predicted by each modality alone - indicating significant complementarity (each profiling modality captures different biologically relevant information). 

![[Screenshot 2021-01-04 at 15.52.03.png]]

Used chemical structure as a baseline (no experiments needed) and added other modalities to see if prediction was improved. Carried out late data fusion rather than early data fusion [[202104011556-Late_Fusion_Vs_Early_Fusion]].  They found an improvement (see below).

![[Screenshot 2021-01-04 at 15.58.56.png]]

#PhD #Permanent #Bioinformatics #ML #MoA #Transcriptomics #CellMorphology #JanssenProject 