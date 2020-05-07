# Release Notes

#### Head to Open Targets blog for all [Genetics-releases](http://blog.opentargets.org/tag/genetics-releases/) posts. 

#### 02 March 2020

* New locus-to-gene pipeline
* New repository of gold-standard GWAS loci
* Additional 637 GWAS studies from the GWAS Catalog
* New Promoter Capture Hi-C data

For more details, check the [release blog post](https://blog.opentargets.org/2020/03/06/open-targets-genetics-new-release-is-out/) and the [change log](https://genetics-docs.opentargets.org/technical-pipeline/change-log) page.

#### 13 June 2019

* Disease-molecular trait co-localisation analysis
* Integration of new molecular QTL datasets, including the upcoming Open Targets-European Bioinformatics Institute eQTL database
* Integration of GWAS Catalog summary statistic database, meaning more fine-mapping, colocalisation and PheWAS

For more details, check the [release blog post](https://blog.opentargets.org/2019/06/17/open-targets-genetics-release-19-06-is-out-2/) and the [change log](https://genetics-docs.opentargets.org/technical-pipeline/change-log) page.

#### 11 April 2019

* Fix compute score for distance \(canonical tss\) dataset where distance was `0`
* Compute a quantile score based on the rank of each variant 2 gene evidence in a \(`source_id`, `feature`\) window over the raw `*_score`

For more details, check the [change log](https://genetics-docs.opentargets.org/technical-pipeline/change-log) page.

#### 1 April 2019

* New release of GWAS Catalog curated data \(r2019-03-01\)
* Harmonised effect sizes for curated variant-disease associations
* GWAS Catalog sub-phenotypes \("p-value text" field\) automatically split into separate study IDs
* Subset of GWAS Catalog studies undergo additional distance-based clustering \(±500kb\) to remove redundant top loci
* Distance between variants and each canonical transcript start site \(TSS\) within 500kb has been added to the variant-to-gene data
* VEP consequences `intron_variant`, `5_prime_UTR_variant`, `3_prime_UTR_variant`, `NMD_transcript_variant` have been given non-zero \(0.1\) scores in the V2G assignment
* We now use the gnomAD \(v2.1\) site list as our variant index

For more details, check the [release blog post](https://blog.opentargets.org/2019/04/09/open-targets-genetics-release-is-out/) and the [change log](https://genetics-docs.opentargets.org/technical-pipeline/change-log) page.

#### 18 October 2018

Version 1 of Open Targets Genetics was released at the American Society of Human Genetics conference in San Diego in October 2018. Head to [ASHG Workshop 2018](https://app.gitbook.com/@opentargets/s/open-targets-genetics-documentation/~/drafts/-M6kKMhrUemGpvPtzD0v/meetings/ashg-workshop-2018) for the training materials presented at that meeting.

Future updates to the portal will be documented here.

