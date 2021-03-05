#### The characteristic direction: a geometrical approach to identify differentially expressed genes
By: Clark *et al*

- DEGs usually identified by univariate approaches such as SAM, LIMMA, DESeq and edgeR
- New geometrical multivariate approach to identify DEGs called Characteristic Direction
	- Significantly more sensitive than existing methods for identifying DEG in the context of TF and drug perturbation responses
	- Benchmarked with RNA-Seq and synthetic data
	- Proteins that interact with the drug-targets are differentially expressed and detected by CD


- DEG approaches usually performe gene-by-gene without regarding gene-gene statistical dependencies
- Fold-change doesn't take into account variance arising from biological and experimental sources, so no estimate of confidence
- Significant statistical dependencies between expression levels of most genes, thus multivariate approaches may be more appropriate 
	- E.g. able to find significant differential expression in cases where there is no marginal differential expression for individual genes
![[Screenshot 2021-01-29 at 09.18.45.png]]
- Approach incorporates a regularization scheme to deal with dimensionality, and provides intuitive geometrical picture of differential expression in terms of a single direction
![[Screenshot 2021-01-29 at 09.20.19.png]]

- Classification approaches are inherently multivariate as they use the structure of the transcriptional profiles as a whole to distinguish between biological conditions/classes
- CD scheme uses a linear classification scheme, which defines a separating hyper-plane; the orientation of which can be interpreted to identify DEGs
	- Direction normal to the separating hyper-plane provides a simple geometrical conceptualisation of the differential expression
- Suppose we have gene expression data from a number of samples N, in which the expression of p genes is measured, and then let each expression profile sample form a row of the matrix X (a N x p matrix)
	- For generality, consider case where each of the expression samples comes from one of K classes belonging to the set G
	- In linear discriminant analysis (LDA), the log-ratio of class posteriors P (G|X), is written as follows:
![[Screenshot 2021-01-29 at 09.24.00.png]]
- Where pi(k) is the class mean, and it is assumed that both classes have the same covariance matrix, Epsilon
- The orientation of the separating hyper-plane (between classes k and l) is defined by the normal p-vector, in the third term on the right hand side, that we label b
![[Screenshot 2021-01-29 at 09.25.20.png]]
- Interpret the direction of the p-vector, b, as the direction in expression space that best characterises the differential expression
	- Components of the vector can be used to identify DEGs
- Calculation involves inverse of a very large p x p matrix
	- Expensive to compute
	- Elements must be estimated from a relatively small sample size (p >> N)
		- Matrix is singular and leads to large variance in results, even when using the generalised inverse
	- Issues of singularity and large variance can be tackled with regularisation - the co-variance matrix can be shrunk to the scalar variance:
![[Screenshot 2021-01-29 at 09.27.21.png]]
- Episilon(hat) is the estimated covariance matrix, and sigma^2 is the scalar covariance
	- Inclusion of a constant on the diagonal resolves singularity problem
	- Modulation of the off-diagonal helps to reduce noise arising from estimation of covariance from few samples
- Computational expense overcome with singular-value decomposition
	- Works in subspace spanned by the data, not the full expression space
	- Normalised vector b(hat) contains only information about the direction of the normal to the separating hyper-plane
	- Components of b(hat) are the direction cosines, and their magnitude quantifies the degree of alignment of the direction to axes corresponding to each gene
	- Sign of each component can be interpreted as the sign of the contribution of each gene to the differential expression
![[Screenshot 2021-01-29 at 09.30.28.png]]
- The contribution of each b(hat)^2_1 to this sum can be interpreted as quantifying the relative contribution of each component to the total differential expression, giving the significance of the corresponding gene
	- Quantitative measure of the relative, but not absolute, significance of each gene to the differential expression
	- As such, can be used to rank the genes in order of significance
- We want to identify a shortlist of DEGs
	- Use a L1 regularization scheme in place of that used in the shrinkage equation, such a penality results in automatic feature selection as many components fall to zero
	- Genes corresponding to features retained = DEGs


- Geometrical picture of differential expression as a single direction leads to some extensions
	- Natural distance measure for two direction is the cosine distance, or angle between two directions
	- We can thus picture the similarity between two biological perturbations as the alignment between two directions
![[Screenshot 2021-01-29 at 09.34.09.png]]
- A gene-set defines a subspace within expression space
	- We can use the angle subtended between this subspace, and the direction characterising the differential expression, the first principal angle
		- Quantification of the significance of a pre-defined gene set for the differential expression

Found improvement in identifying TF and drug perturbations, as well as enriched pathways

#PhD #Permanent #Transcriptomics #Bioinformatics #JanssenProject 