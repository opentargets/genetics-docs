# Assigning Variants to Disease \(V2D\)

### Lead Variant Annotation

Open Targets Genetics is based on the human reference genome assembly GRCh38. Lead variants, $$V_L$$, associated with a phenotype by hypothesis-free approaches \(GWAS\) are initially annotated with their associated trait\(s\) as described below:

{% hint style="info" %}
Traits in Open Targets Genetics are assigned in the format **Reported Trait \(Author, Year\).**  Multiple studies assessing the same trait are _not_ collapsed into a single annotation. This preserves the integrity of the published record and will allow users to select study-specific analyses within the portal.  
{% endhint %}

#### Published Associations

Reported variant-phenotype associations in literature were identified _via_ the NHGRI-EBI GWAS Catalog, a manually-curated database of published variants meeting certain inclusion criteria, which will be familiar to most geneticists. On an ongoing basis, GWAS Catalog extracts and records detailed variant and study-level data for variants reported to be associated with any phenotype at a significance level of $$p≤1e−5$$, and fit the inclusion criteria [detailed here](https://www.ebi.ac.uk/gwas/docs/methods/criteria).

In Open Targets Genetics we include GWAS Catalog curated associations with $$p≤5e−8$$. A [subset of studies](https://github.com/opentargets/genetics-v2d-data/blob/1fb2d604ad5c231bc912220237a2eede79fbcbba/logs/gwas-cat-assocs_clustering.log#L8) \(N=162\) then undergo distance based clustering \(±500kb\) to remove redundant associations that are an artefact of the curation process, as opposed to true independent signals. For associations that have a reported risk allele, we harmonised the effects so that all are with respect to the alternative allele.

#### GWAS Catalog summary statistics repository

Data from the [GWAS Catalog summary statistics repository](https://www.ebi.ac.uk/gwas/summary-statistics) has been included in the portal as of June 2019. The initial release has been restricted to datasets derived from samples of predominantly European ancestry \(N=201\) due to the lack of suitable linkage-disequilibrium reference panels for conditional analysis. We are working to include all datasets in a future release of the portal.

#### UK Biobank Phenotypes

Recent efforts to rapidly and systematically apply established GWAS methods to all available data fields in UK Biobank have made available large repositories of summary statistics. To leverage these data disease locus discovery, we used full summary statistics from:

1. The Neale lab [Round 2](http://www.nealelab.is/uk-biobank/) \(N=2139\). These analyses applied GWAS \(implemented in [Hail](https://hail.is/)\) to all data fields using imputed genotypes from HRC as released by UK Biobank in May 2017, consisting of 337,199 individuals post-QC. Full details of the Neale lab GWAS implementation are available [here](http://www.nealelab.is/blog/2017/9/11/details-and-considerations-of-the-uk-biobank-gwas). We have remove all ICD-10 related traits from the Neale data to reduce overlap with the SAIGE results.
2. The University of Michigan [SAIGE analysis](https://www.leelabsg.org/resources) \(N=1281\). The SAIGE analysis uses [PheCode](https://phewascatalog.org/phecodes) derived phenotypes and applies a new method that "provides accurate P values even when case-control ratios are extremely unbalanced". See [Zhou _et al._ \(2018\)](https://www.ncbi.nlm.nih.gov/pubmed/30104761) for further details.

The fine-mapping section below explains how associated-loci were defined using the UK Biobank summary statistics.

## Lead Variant to Tag Variant expansion

Two methods are used to expand lead disease-associated variants into a more complete set of possibly _causal_ tag variants. Linkage-disequilibrium expansion using a reference population is applied to all studies in Open Targets Genetics, and expansion by fine-mapping \(credible set analysis\) is used where full summary statistics are available \(currently UK Biobank traits and those included in the GWAS Catalog summary statistics repository\).

{% hint style="success" %}
Head to our FAQs page for the explanation on the [differences between lead and tag variants](https://genetics-docs.opentargets.org/faqs#what-is-the-difference-between-lead-variant-and-tag-variant).
{% endhint %}

#### Linkage Disequilibrium Expansion

Linkage disequilibrium \(LD\) information is calculated using the 1000 Genomes Phase 3 \(1KG\) haplotype panel as a reference. LD is calculated in the 1KG super-population that most closely matches GWAS study [ancestry information](https://www.ebi.ac.uk/gwas/ancestry) curated by the GWAS Catalog. If the study is conducted in a mixture of populations, a weighted-average \(of Fisher Z-transformed correlation coefficients\) across super-populations is used. If ancestry information is unknown, European ancestry is assumed. See [here](https://github.com/opentargets/v2d_data#ld-table-methods) for full methods.

### Fine-mapping Expansion

![Overview of the fine-mapping pipeline](../.gitbook/assets/finemapping_overview_figure.png)

#### **Summary Statistics Preprocessing**

Summary statistics were harmonised to ensure that the ALT allele is always the effect allele, and were pre-filtered to remove variants with low minor allele counts which would lead to inaccurate effect estimation. Variants located in the MHC region \(6:28,510,120–33,480,577 GRCh38\) are excluded from the fine-mapping pipeline. See [here](https://github.com/opentargets/sumstat_harmoniser) for harmonisation scripts and [here](https://github.com/opentargets/sumstat_data#requirements-when-adding-new-datasets) for "ingestion" scripts and detailed inclusion criteria.

#### **Top loci detection**

Independently associated top loci are detected with GCTA stepwise selection procedure \(cojo-slct\) using unrelated European ancestry UK Biobank genotypes down-sampled to 10K individuals as an LD reference. Lead variants \(the most associated variant at each locus\) are kept if both the conditional and nominal p-values have $$p≤5e^{-8}$$ . 

#### **Per locus conditional analysis**

Where multiple index SNPs are found at the same locus \(within 2Mb of each other\), we perform GCTA single-variant association analysis conditional on other index SNPs at the locus. This produces a set of conditional summary statistics for each independently associated locus.

#### **Credible set analysis**

Credible set analysis is conducted for each associated locus using the above conditional summary statistics. We calculate an approximate Bayes factors \(ABF\) for all variants in a defined region around the index variant \(±500kb\). ABFs are computed using the `approx.bf.p` [method](https://github.com/chr1swallace/coloc/blob/master/R/claudia.R#L67) re-implemented from the [_coloc_](https://journals.plos.org/plosgenetics/article?id=10.1371/journal.pgen.1004383) package. Variants are ordered by their posterior probabilities \(PP\) and sequentially added to the credible set until the cumulative sum is &gt;0.95 \(95% credible set\).

The implementation of our fine-mapping pipeline can be found [here](https://github.com/opentargets/finemapping).

