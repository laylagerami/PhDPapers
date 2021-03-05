#### Towards a global investigation of transcriptomic signatures through co-expression networks and pathway knowledge for the identification of disease mechanisms

By: Rebeca Figueiredo et al.

**Summary:**
This work attempts to address a key question in transcriptomics data analysis: "can we correlate the patterns we observe in transcriptomic datasets to known molecular interactions and pathway knowlege to broaden our understanding of disease pathophysiology?". The analysis uses transcriptomic datasets to construct disease specific co-expression networks alongside a human interactome of PPIs. By looking at the interoperability between the two networks, patterns both common and particular to the diseases on different levels were explored. 

1. At the node-level, the most and least common proteins in the diseases were identified, and evaluated for consistency against the interactome (as a proxy for their prevalence in the scientific literature)
2. At the edge-level, networks are overlayed to analyse common correlations and interactions across diseases
3. On the pathway-level, pathway signatures associated with specific diseases are identified

Finally, a schizophrenia case study is presented.

**Methodology**
![[Screenshot 2021-03-05 at 10.24.35.png]]
- Generate disease-specific co-expression networks from transcriptomic data
- Construct human PPI network
- Carry out analysis

**1. Co-expression network generation
**

Datasets were obtained from ArrayExpress, sharing the same platform (U133 Plus 2.0) to ensure compatibility. Human disease vs control data was obtained only. The disease terms in the dataset titles/metadata were harminsed with the Human Disease Ontology (DOID) and ZOOMA. Next, they grouped similar diseases under a common label using the ontology network structure. They also ensured that all datasets had minimum 50 samples, minimum of 2 datasets per disease, and all samples with label "cancer" were removed.

Per-disease, samples from different datasets were merged and batch correction carried out with ComBat. The co-expression networks were constructed with WGCNA.

**2. PPI network generation
**

The interactome was comprised of interaction from KEGG, Reactome, WikiPathways, BioGrid, IntAct and PathwayCommons. Interaction were harmonised with PathMe.

**3. Analysis**

To investigate the consensus between patterns prseent in each co-expression network and pathway knowledge, each disease-specific co-expression network was superimposed against KEGG pathways and the constructed PPI using two different methods.

Method 1 looks at every pairwise combination of nodes from the set of proteins P for a given pathway from KEGG (Cp), to find the proportion of edges that exist in the disease co-expression network between the node pairs (edge overlap). This gives a similarity between a pathway and a disease co-expression network.

Method 2 takes the interactome I, and generates a subgraph S, containing only those nodes in P. Next, the proportion of edges on the interactome subgraph S that are also found in each disease co-expression network are calculated. This gives a similarity between an interactome and a disease co-expression network.

Finally, ORA was calculated using Fisher's exact test.

**Results**

![[Screenshot 2021-03-05 at 10.36.12.png]]
Merged and clutered co-expression networks.

They were able to obtain a set of consistsently differentially expressed genes in disease vs. normal, find pathway fingerprints per disease, and so on.

**Case Study: In-depth investigation of the long term potentiation pathway in the context of schizophrenia**

To understand the mechanisms that underlie the similarity of a pathway to a given disease, they next investigated the long-term potentiation (LTP) pathway which has yielded high similarity to the Sz co-expression network.

By overlaying the Sz network with the LTP pathway they found 53 unique correlations between LTP proteins, indicating that the vast majority of proteins in the pathway were correlated in the co-expression network.

They then attempted to pinpoint candidate downstream pathways of LTP in the context of Sz by investigating the edges of ATF4 (key regulator of the LTP pathway). ATF4 is strongly correlated with 70 other proteins in the co-expression networks. They conducted a pathway enrichment analysis as a proxy to reveal pathway crosstalks mediated by this protein.

The analysis pinpointed 4 pathways, from which 3 were involved in protein/RNA processing (ubiquitin mediated proteolysis, RNA transport, spliceosome) which have been linked to Sz, and the fourth, cell cycle, has also been associated with the disease. There hence may be crosstalk between the pathways that could be expored in the future.


#PhD #Permanent #Bioinformatics #Transcriptomics #Network #Cancer 