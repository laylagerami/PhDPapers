#### A modular master regulator landscape controlscancer transcriptional identity
By: Evan O. Paull et al

A network-based integrative genomic analysis of 20 The Cancer Genome Atlas cohorts characterises conserved master regulator blocks underlying cancer hallmarks across different tumour types, providing insights into the connection between genetic alterations and tumour transcriptional identity.

![[Screenshot 2021-01-12 at 09.58.44.png]]

The steady-state transcriptional identity of a cancer cell is tightly regulated by complex regulatory mechanisms. These mechanisms pay a key role in a number of important things such as determining non-oncogene dependencies, transcriptional identities compatible with set of somatic/germline variants harbored by each cell, and cancer cell plasticity across molecularly distinct identities.

Some mutations restrict the transcriptional identity accessible to a cancer cell - for example, luminal subtype BC has activating mutations in ESR1, FOXA1 and GATA3. Many however are far less deterministic - for example, in glioblastoma there is only weak association between mutational and transcriptional states.

The molecular logic that determines cancer cell identity as a function of its mutational + exogenous signal landscape remains elusive. The Oncoteture Hypothesis of master regulators [[202112011005-OncotectureHypothesis]] may help to elucidate these mechanisms that implement and maintain the transcriptional identity of cancer cells (as a function of thier mutational landscape), and for plastically reprogramming across distinct identities.

The authors describe MOMA, or multi-omics master regulator analysis. The methodology integrates gene expression and genomic alteration profiles to identify master regulator proteins and modules, the key effectors of a tumour's mutational landscape. They used the method to study MR modulatory and genetic drivers on a sample-by-sample basis for 9,378 samples in TCGA.

![[Screenshot 2021-01-12 at 10.08.43.png]]

Gene expression profiles from 20 TCGA cohorts were transformed to protein activity profiles by using the VIPER algorithm, which finds upstream proteins responsible for the changes in transcriptional activity. Candidate MR proteins identified by Fisher's integration of p-values from:
	- Their VIPER-measured activity
	- Functional genetic alterations in their upstream pathways by Driver-Gene Inference by Genetical-Genomic Information Theory (DIGGIT) analysis
	- Additional structure and literature-based evidence supporting direct PPIs between MRs and proteins harboring geneic alterations, via the Predicting Protein-Protein Interactions (PrePPI) algorithm
Vector of weighted (Log_10 p)^2 (MOMA scores) to weight each MR's contribution in a tumour subtype clustering step. Genomic saturation analysis upstream of top candidate MRs identified those most likely to control the subtype transcriptional identity . Finally, they carried out identification/functional characterisation of MR block sub-modules, termed MR-Blocks (MRB) recurring across multiple subtypes

#PhD #Permanent  #Transcriptomics #Network #Bioinformatics #Cancer