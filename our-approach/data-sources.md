# Data Sources

{% hint style="info" %}
 We have designed Open Targets Genetics to be scalable and readily extensible. New data sources will continually be curated, reviewed, incorporated, and documented here and in the changelog.  Please get in touch with any suggestions.  
{% endhint %}

**Variant index**

* [GnomAD v2.1](https://gnomad.broadinstitute.org/)

**Disease-associated loci sources \(V2D\)**

* [GWAS Catalog curated studies](https://www.ebi.ac.uk/gwas/)
* [Neale lab UK Biobank summary statistics](http://www.nealelab.is/uk-biobank/)

**Haplotype reference samples**

* [1000 Genomes Phase 3](http://www.internationalgenome.org/category/phase-3/) - used for LD expansion
* [UK10K \(ALSPAC and TwinsUK\) ](https://www.uk10k.org/studies/cohorts.html)- used for conditional analysis in top-loci detection and fine-mapping of studies with full summary statistics

**Variant-to-Gene annotation sources \(V2G\)**

* _In silico_ functional prediction
  * [Variant-Effect Predictor \(VEP\)](https://www.ncbi.nlm.nih.gov/pubmed/27268795): Most severe transcript consequence\(s\)
* Molecular quantitative trait locus \(QTL\) experiments
  * [eQTL \(GTEx V7\)](https://www.ncbi.nlm.nih.gov/pubmed/29022597): Evidence linking genetic varition to gene expression in each of the 44 GTEx V7 tissues
  * [pQTL \(Sun _et al._, 2018\)](https://www.ncbi.nlm.nih.gov/pubmed/29875488): Evidence linking genetic varition to protein abundance in Sun _et al._ \(2018\) pQTL data
* Interaction / interval based experiments
  * [Promoter Capture Hi-C \(Javierre _et al._, 2016\)](https://www.ncbi.nlm.nih.gov/pubmed/27863249): Evidence linking genetic variation to genes using Promoter Capture Hi-C in each of the 17 human primary hematopoietic cell types
  * [Enhancer-TSS correlation \(Andersson _et al._, 2014\)](https://www.ncbi.nlm.nih.gov/pubmed/24670763): Evidence linking genetic variation to genes using correlation between the transcriptional activity of enhancers and transcription start sites using the FANTOM5 CAGE expression atlas
  * [DHS-promoter correlation \(Thurman _et al._, 2012\)](https://www.ncbi.nlm.nih.gov/pubmed/22955617): Evidence linking genetic variation to genes using correlation of DNase I hypersensitive site and gene promoters across 125 cell and tissue types from ENCODE

Further details on each V2G dataset, including workflows to reproduce them, are located [here](https://github.com/opentargets/v2g_data/).

