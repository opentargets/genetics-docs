# Overview

![Schematic outlining the data model and main data sources used in Open Targets Genetics](../.gitbook/assets/genetic-portal-data-overview-figure%20%282%29.png)

The aim of Open Targets Genetics is to aggregate evidence linking \(i\) variants to disease, and \(ii\) variants to genes, so that for a specific disease potential drug targets can be prioritised based on robust genetic information.

Disease information \(![](../.gitbook/assets/s_30.png)= study\) comes from genome-wide association studies \(GWAS\) which link disease status \(or other trait measurements\) to common genetic variation. Due to how GWAS results are reported, we often only know the lead variant  \(![](../.gitbook/assets/vl_30%20%281%29.png)\) at each associated locus. However, it cannot be assumed that the lead variant is _causing_ the association, instead, we expand the lead variant to include all tag variants \( ![](../.gitbook/assets/vt_30.png) \), which make up a more complete set of potentially _causal_ variants. ![](../.gitbook/assets/vl-vt.png) links are made using two methods: \(i\) fine-mapping / credible set analysis, if full summary statistics are available; \(ii\) linkage-disequilibrium expansion.

