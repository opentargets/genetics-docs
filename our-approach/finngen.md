# FinnGen

**Current Release in genetics portal: FinnGen R5**

[FinnGen](https://www.finngen.fi/en) is an academia-industry partnership that aims to produce genome variant data for 500,000 Finns, using GWAS genotyping. The genomic data is then combined with phenotype data collected by national health registries, including extensive longitudinal registry data available on all Finns. FinnGen data will be updated in a series of releases over the next 4 years ([https://finngen.gitbook.io/documentation/releases](https://finngen.gitbook.io/documentation/releases)), as the sample size grows.

We include all endpoints which have public summary statistics and fine-mapping results.

### Fine-mapping

Because the Finnish population has been genetically isolated, fine-mapping needs to be done with a suitable reference panel of linkage disequilibrium. The FinnGen study have themselves performed fine-mapping using the "modern" multi-causal variant fine-mapping methods [SuSIE](https://stephenslab.github.io/susieR/index.html) and [FINEMAP](http://www.christianbenner.com), based on a reference panel of whole genome sequencing data from Finns. Their methods are [described here](https://finngen.gitbook.io/documentation/methods/finemapping). These methods differ somewhat from how we have done fine-mapping for other studies in Open Targets Genetics, [described here](assigning-traits-to-loci.md#fine-mapping-expansion).** **Briefly, for all UK Biobank and GWAS Catalog studies, we have done fine-mapping by identifying independent signals with [GCTA-cojo](https://cnsgenomics.com/software/gcta/#COJO), followed by single-causal variant fine-mapping on each independent signal. We treat each independent signal as a "locus" in Open Targets Genetics, meaning that there may be multiple signals, each tagged by a separate lead variant, which are nearby in the genome.

![](<../.gitbook/assets/FinnGen Figure V5.png>)

To integrate the fine-mapping outputs provided by FinnGen, we had to take a different approach. Each "locus" in FinnGen is a genomic region that may contain multiple independent causal variants. SuSIE is run on each entire locus, and where there are likely to be multiple causal variants, the SuSIE output provides the probability for each variant to be in a credible set. (Note that for simplicity we use only the SuSIE results from FinnGen, and not FINEMAP results.) We use these variant probabilities from SuSIE credible sets in downstream applications, such as locus-to-gene scoring. However, for display of associated loci, we chose to represent each locus by the single variant with the lowest p-value. This is necessary because we do not have conditionally independent summary statistics in FinnGen (as we computed manually for other GWAS studies), and our co-localisation procedure would depend upon these for secondary signals at a locus.

(Note that, consistent with our other GWAS, we only include genomic regions from FinnGen where a variant had p < 5e-8, which may be more stringent than the threshold that FinnGen selected for fine-mapping.)

### Colocalisation

Tests of genetic colocalisation treat each FinnGen locus as a single signal (using the full marginal summary statistics), and this is tested against all independent signals in GWAS Catalog, UK Biobank, and molecular QTLs. This therefore means that we perform a colocalisation test with the full summary statistics at a FinnGen locus against the conditionally independent summary statistics in other studies. In general, it is likely that if there is a true colocalisation with another study, then these full summary statistics will show a high colocalisation value for at least one of the independent signals in the second study. This approach balances the use of accurate fine-mapping produced by FinnGen with a conservative approach to fine-mapping in other studies, where we generally do not have a perfectly matched LD reference panel.\
