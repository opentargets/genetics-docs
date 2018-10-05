# Overview

![Schematic outlining the data model and main data sources used in Open Targets Genetics](../.gitbook/assets/genetic-portal-data-overview-figure%20%282%29.png)

The aim of Open Targets Genetics is to aggregate evidence linking \(i\) variants to disease, and \(ii\) variants to genes, so that for a specific disease potential drug targets can be prioritised based on robust genetic information.

Disease association information \(![](../.gitbook/assets/s_30.png)= study\) is obtained from genome-wide association studies \(GWAS\) which link disease status \(or other trait measurements\) to common genetic variation. Due to how GWAS results are reported, we often only know the lead variant  \(![](../.gitbook/assets/vl_30%20%281%29.png)\) at each associated locus. However, it cannot be assumed that the lead variant is _causing_ the association, instead, we expand the lead variant to include all tag variants \(![](../.gitbook/assets/vt_30.png)\), which make up a more complete set of potentially _causal_ variants. The lead to tag expansions are made using two methods: \(i\) fine-mapping / credible set analysis, where full summary statistics are available; \(ii\) linkage-disequilibrium expansion.

Given a set of potentially _causal_ tag variants, we next assign these to genes \(![](../.gitbook/assets/g_30.png)\) using our variant-to-gene \(V2G\) pipeline. The V2G pipeline combines data from three main sources: \(i\) molecular phenotype quantitative trait loci experiments \(e.g. eQTLs and pQTLs\); \(ii\) chromatin interaction experiments \(e.g. Promoter Capture Hi-C\); and \(iii\) _in silico_ functional predictions \(e.g. Variant Effect Predictor from Ensembl\). For each variant, the pipeline first aggregates functional data across all sources, then applies a scoring algorithm \(outlined in TODO\) to produce 'per source' and 'overall' V2G scores.



