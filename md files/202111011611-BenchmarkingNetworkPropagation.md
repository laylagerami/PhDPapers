#### Benchmarking network propagation methods for disease gene identification
By: Sergio Picart-Armada et al
https://doi.org/10.1371/journal.pcbi.1007276

- In-silico identification of potential target genes for disease
- Benchmarked 12 network propagation algorithms to identify genes that have been targeted by any drug
- Two networks, 6 metrics and 2 types of input gene-disease association scores
- Impact of design factors quantified through additive explanatory models
- Network propagation algorithms start from set of known nodes with a property of interest, and connections are leveraged from the biological network to make predictions
- Algorithms range in complexity
	- First-neighbour approaches: Direct neighbours of a gene of interst are assumed to be implicated in similar processes
	- ML
- Network propagation approaches 
- Test set of disease genes = genes for which the relationship with a disease was sufficiently clear to justify the start of a drug development programme
- Input
	- Network and list of genes with prior disease-association scores

![[Screenshot 2021-01-11 at 16.10.56.png]]

- Methods
	- Classical network propagation
		- ppr, raw, gm, mc and z
		- Differ on directedness of propagation, input weights + statistical normalisation
	- Semi-supervised methods
		- knn and wsld
	- Supervised methods
		- COSNet, bagsvm, rf and svm
	- Baseline
		- EGAD (neighbour voting) as baseline
	- Input-naive baselines
		- pr and randomraw (biased by network topology) and random (purely random)
- Three cross-validation schemes
	- Two take into account protein complexes
	- Some of the prior disease-association scores are hidden
- Desired output = new ranking of genes in terms of association scores to a disease
	- Ranking compared to known target genes in validation fold
- Explanatory additive models used
	- Regression models explained performance metrics (dependent variable), as a function of the prediction method, cross-validation scheme, network and disease (regressors)
- Two metrics
	- AUROC and top 20 hits
- Two input types
	- Known drug target genes and genetically associated genes


Performance using known drug targets as input:
![[Screenshot 2021-01-11 at 16.11.49.png]]
- Figure shows the additive models for AUROC and top 20 hits, using known drug targets as input
- Note that the disease was included as a regressor in the models for further discussion
	- Methods had to predict whether a gene has been targeted by any drug for a particular disease, implying that metrics are available at the disease-level

![[Screenshot 2021-01-11 at 16.17.45.png]]
- Figure shows their predictions for each method, network and cross-validation scheme with 95% confidence intervals, averaged over diseases
- For interpretability, top 20 hits is regarded as reference metric in main body

Comparing cross-validation schemes
- Whether protein complexes were taken into account when performing cross-validation stood out as key influence on quality of predictions
	- Dramatic reduction in performance for most methods when using a complex-aware cross-validation strategy
	- Rf applied on the STRING network dropped from 12 to 4.5
	- Random cross validation leads to overly optimising performances when predicting new regulatory contexts, requiring to control for the distinction between training and test data
- Performance drop when choosing the appropriate validation strategy is comparable to performance gap of competitive methods vs a simple neighbour-voting strategy like EGAD
	- Highlights importance of carefully controlling for this bias when estimating the performance of target gene prediction using network propagation

Comparing networks
- STRING as opposed to OmniPath improved overall performance of disease gene prediction models
	- Models for top 20 hits quantified this effect as noticeable but less important than that of the cross-validation strategy

Comparing methods
- Network topology alone had a slight predictive power
	- pr or PageRank which ignores input gene scores showed better performance than random baseline under all metrics
	- Inherent network topology-related bias among target genes that benefits diffusion-based methods
- Basic GBA approach had advantage over input-naive baselines
- Most diffusion-based and ML-based methods outperformed EGAD
- Tukey's multiple comparison test on model coefficients showed that rf, raw, bagsvm, z and svm should be used in that order

![[Screenshot 2021-01-11 at 16.27.44.png]]
![[Screenshot 2021-01-11 at 16.28.46.png]]
#Fleeting #PhD #Transcriptomics #Bioinformatics #Transcriptomics #MoA 