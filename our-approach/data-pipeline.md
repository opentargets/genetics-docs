# Assigning Variants to Genes \(V2G\)



![Overview of Variant-to-Gene \(V2G\) pipeline aggregation and scoring.](../.gitbook/assets/v2g-scoring-figure-draft-2%20%281%29.png)

All variants in the variant index are annotated using our Variant-to-Gene \(V2G\) pipeline. The pipeline integrates V2G evidence that fall into four main data types:

1. Molecular phenotype quantitative trait loci experiments \(QTLs\), e.g. GTEx eQTLs
2. Chromatin interaction experiments, e.g. Promoter Capture Hi-C \(PCHi-C\)
3. _In silico_ functional predictions, e.g. Variant Effect Predictor \(VEP\) from Ensembl
4. Distance between the variant and each gene's canonical transcription start site \(TSS\)

Within each data type there are multiple sources of information produced by different experimental methods. Some of these sources can further be broken down into separate tissues or cell types \(features\). A full list of data sources used in the V2G pipeline can be seen on the [Data Sources](data-sources.md) page.

### Pre-processing

#### Filtering

Raw datasets are processed to conform to a standardised format and filtered so that they:

* Only contain associations with **strong evidence post-multiple testing correction**
* Only contain cis-regulatory associations

A full list of filters applied to each dataset, and workflows to reproduce the V2G files, can be found on [GitHub](https://github.com/opentargets/v2g_data).

#### Score transformation

Different data sources use different metrics to measure the association between variants \(or genomic intervals\) and a gene. For example QTLs provide a p-value from standard linear regression, whereas PCHi-C provides a [CHiCAGO score](https://www.ncbi.nlm.nih.gov/pubmed/27306882). To harmonise scores across sources, a relevant study-specific metric is extracted followed by quantile transformation using a uniform distribution. If multiple features \(tissues/cell types\) are available, then the transformation is applied at the feature level. Transformed scores are rounded to the nearest decile, so a score of 1.0 is in the top decile, a score of 0.9 is in the 9th decile, and so on.

### Variant-Gene annotation

Next, each variant-gene $$(V, G)$$ pair is annotated with all available functional evidence. _QTL_ and _functional prediction_ data types contain $$(V, G)$$-centric scores and so are simple to combine. Interaction data types link functional genomic regions \(interval A\) to gene positions \(interval B\). Variants that lie within interval A are assigned evidence scores that link it to genes located in interval B. The resulting V2G merge table consists of approximately **1.7 billion evidence strings**.

### Scoring

Given the scale of the data, a scoring system was developed so that for a given variant $$(V)$$ we can get a list of genes $$(G_1... G_N)$$ ranked by either \(i\) the overall V2G score, \(ii\) a per-source V2G score.

**Step 1, Aggregate across features \(tissues or cell types\).** Some data sources \(i.e. GTEx and PCHi-C\) provide associations measured in multiple tissues or cell lines \(features\). Where multiple features exist, we aggregate by taking the maximum score across all features for each $$(V, G)$$ pair. This aggregation gives a per-source V2G score for each $$(V, G)$$ pair.

**Step 2, Aggregate across sources.** The next stage is to combine information across the sources to produce an overall V2G score. Given the heterogenous nature of the data, we may have more confidence in evidence from some sources over others. We therefore down-weight some sources before aggregation. Using _a prior_ knowledge we rank evidence from sources in this order \[ Transcript functional prediction &gt; QTLs &gt; Interaction based data sets \] and apply the following weights:

| Data type | Experiment type | Source | Weighting |
| :--- | :--- | :--- | :--- |
| _In silico_ functional prediction | Transcript consequence | VEP | 1.0 |
| QTL | eQTL | GTEx v7 | 0.66 |
| QTL | pQTL | Sun _et al._ \(Nature, 2018\) | 0.66 |
| Interaction | PCHi-C | Javierre _et al._ \(Cell, 2016\) | 0.33 |
| Interaction | Enhancer-TSS correlation | Andersson _et al._ \(Nature, 2014\) | 0.33 |
| Interaction | DHS-promoter correlation | Thurman _et al._ \(Nature,  2012\) | 0.33 |
| Distance | Canonical TSS |  | 0.33 |

After weighting, sources are aggregated across sources by taking the mean weighted-quantile to give an overall V2G score for each $$(V, G)$$ pair.

#### Scoring pseudocode

```text
## Preprocessing (applied across whole dataset)
- Create a score column
  * QTL datasets: -log10(p-value)
  * Interval datasets: interval score (differs between sources)
  * VEP map to v2g_score column in https://github.com/opentargets/v2g_data/blob/master/configs/vep_consequences.tsv
  * TSS Distance: 1/distance
- Group by (source, tissue), transform into quantiles

## Aggregate across tissues (per source)
- Group by (variant, source, gene)
- Calculate max score across tissues
- This gives a score per gene for each source

## Aggregate across sources (per variant)
- Group by (variant, gene)
- Caluclate weighted mean over sources using source weights (see below)
- This gives a score per gene for a given variant

source_weights = {
    'vep': 1,
    'javierre2016': 0.33,
    'andersson2014': 0.33,
    'thurman2012': 0.33,
    'canonical_tss': 0.33,
    'gtex_v7': 0.66,
    'sun2018': 0.66
}
```



