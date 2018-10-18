# FAQs

**What genome build are data in the Genetics Portal based on?**

All data are based on GRCh37/hg19 from the [Genome Reference Consortium](https://www.ncbi.nlm.nih.gov/grc).

**How is the Genetics Portal related to the** [**Open Targets Platform**](https://www.targetvalidation.org)**?**

The Genetics Portal is a variant-centric resource that complements the Open Targets Platform. Users can navigate to the Open Targets Platform from our Genetics portal and drug information in clinical trials \(or already marketed\) for any target of interest.

**How do I cite discoveries made using Open Targets Genetics?**

Please cite our Open Targets paper, ["Open Targets: a platform for therapeutic target identification and validation"](https://academic.oup.com/nar/article/45/D1/D985/2605745).

**How can I stay informed about new features and developments?**

For updates, please subscribe to our [newsletter](https://opentargets.us17.list-manage.com/subscribe?u=d11d0467053c1d4b918eb8738&id=f084c7a7c2). Questions and feedback can be directed to us via [email](mailto:geneticsportal@opentargets.org).

**Why are there two variants mapped to the same rsID?**

RsIDs are not unique to a single variant. Many multi-allelic sites are assigned a single rsID, and some rsIDs can point to different positions in the genome. We have mapped all rsIDs from GWAS Catalog to unique variants. A small minority of rsIDs will map to multiple variant IDs \(approximately 0.6% of lead variants\). When this occurs, variants will be duplicated in the portal.

**Why are there no lead variant effect sizes in the portal?**

We currently don't show effect sizes for lead variants in the portal. We initially took this decision as we can't consistently harmonise effect directions given only an rsID and risk-allele \(from the curated GWAS Catalog data\). In a future release, we plan to provide effect sizes for non-palindromic and non-ambiguously mapped variants \(see above\).

**Why is there no LD information for my associated-locus of interest?**

Linkage disequilibrium is calculated using the 1000 Genome Phase 3 reference panel. If your variant is not in this panel post-QC \(MAF &gt; 1% and max missing rate &lt; 0.05\) then we will not provide any LD information for it.

**Why is there no credible set information for my associated-locus of interest?**

Fine-mapping can only be conduct for studies that we have full summary statistics for. Currently this only consists of UK Biobank summary statistics from the Neale lab. We are currently working with the GWAS Catalog to create a summary statistic repository, which will then be included in the Open Targetes Genetics. We encourage the scientific community to submit their full summary statistics to the GWAS Catalog.

**Why isn't my variant in the portal?**

We use the [Ensembl Variation version 92 VCF](ftp://ftp.ensembl.org/pub/grch37/update/variation/vcf/homo_sapiens/) as a variant index. All ~350 million variants in the index should be included in the portal. However, there are some examples of variants that are missing from the index. If you find a variant that you think should be in the portal but isn't, please [email us](mailto:geneticsportal@opentargets.org) the details of the variants and we will investigate this further.

**How do I download the credible set of variants for an association of interest?**

Credible set information is available for all studies that have gone through our fine-mapping pipeline. The full set of variants in the 95% credible set can be downloaded using the **Tag Variant** table on the **Variant** page for the lead-variant at your locus of interest.

**What Variant-to-Gene \(V2G\) score threshold should I use as a "significance" cut-off?**

The V2G scores are intended as a way to rank genes based on all available functional data. We do not provide an [arbitrary cut-off](https://www.bmj.com/content/322/7280/226.1) for V2G scores.

The data used to calculate V2G scores are already pre-filtered to remove associations with low evidence after multiple testing procedures are applied. Therefore, any $$(V,G)$$ pair with a non-zero score has at least one good string of evidence in the data. The higher the V2G score, the more evidence there is for a functional association.

**Why are case counts missing for some case-control studies?**

Sample case counts are stored as part of a text string in GWAS Catalog. This makes the information difficult to parse reliably. We have decided not to show case numbers for these studies.

