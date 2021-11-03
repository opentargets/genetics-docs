# Overview

![Schematic outlining the data model and main data sources used in Open Targets Genetics](<../.gitbook/assets/Genetic Portal Data Overview Figure (2).png>)

The aim of Open Targets Genetics is to aggregate evidence linking (i) variants to disease, and (ii) variants to genes, so that for a specific disease potential drug targets can be prioritised based on robust genetic information.

Disease association information (![](../.gitbook/assets/S\_30.png)= study) is obtained from genome-wide association studies (GWAS) which link disease status (or other trait measurements) to common genetic variation. Due to how GWAS results are reported, we often only know the lead variant  (![](<../.gitbook/assets/VL\_30 (1).png>)) at each associated locus. However, it cannot be assumed that the lead variant is _causing_ the association, instead, we expand the lead variant to include all tag variants (![](../.gitbook/assets/VT\_30.png)), which make up a more complete set of potentially _causal_ variants. The lead to tag expansions are made using two methods: (i) fine-mapping / credible set analysis, where full summary statistics are available; (ii) linkage-disequilibrium expansion.

Given a set of potentially _causal_ tag variants, we next assign these to genes (![](../.gitbook/assets/G\_30.png)) using our variant-to-gene (V2G) pipeline. The V2G pipeline combines data from four sources:

1. Molecular phenotype quantitative trait loci experiments (e.g. eQTLs and pQTLs)
2. Chromatin interaction experiments (e.g. Promoter Capture Hi-C)
3. _In silico_ functional predictions (e.g. Variant Effect Predictor from Ensembl)
4. Distance from the canonical transcript start site (TSS)

For each variant, the pipeline first assigns functional evidence to variant-gene pairs (V, G) across all sources, then applies a scoring algorithm to produce aggregated V2G scores. Detailed methods can be found [here](data-pipeline.md).

