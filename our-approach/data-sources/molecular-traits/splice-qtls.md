---
description: >-
  Splice QTLs (sQTLs) are variants which regulate the splicing behaviour of a
  given gene(s). sQTLs tend to be independent from eQTLs, and do not necessarily
  correlate with the expression of the affected
---

# Splice QTLs

### Ingestion and Integration

We integrated the results from the GTEx v8 sQTL datasets, which employed the [leafcutter](https://www.nature.com/articles/s41588-017-0004-9) method, this method does not rely on existing isoform annotations to identify sQTLs, instead, an intron usage focused approach is used. Split reads which map across multiple exons are used to identify alternative splicing events. Splice isoforms which share intron excision are grouped into splice clusters (denoted by a cluster ID). The intron usage is then summarised and sQTLs which are associated with intron excision levels are identified using a linear model.

In summary, there can be multiple splice clusters for each gene. Within each cluster, there are also multiple splice junctions (denoted by chr:start:end - and refers to the position of the relevant intron) and each junction contains its own set of summary statistics. Due to the complexity and abundance of the data, we have decided to only ingest summary statistics from the junction with the best p-value in each cluster.

These new sQTL summary statistics have been processed through the same pipelines as the existing QTLs. This means that there are credible sets and GWAS-molecular trait colocalisation results for sQTLs. In addition, sQTL predictive features have been added to the V2G and L2G gene prioritisation pipelines.

