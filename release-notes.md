# Release Notes

#### Head to Open Targets blog for all [Genetics-releases](http://blog.opentargets.org/tag/genetics-releases/) posts. 

#### 11 April 2019

* Fix compute score for distance \(canonical tss\) dataset where distance was `0`
* Compute a quantile score based on the rank of each variant 2 gene evidence in a \(`source_id`, `feature`\) window over the raw `*_score`

#### 1 April 2019

* New release of GWAS Catalog curated data \(r2019-03-01\)
* Harmonised effect sizes for curated variant-disease associations
* GWAS Catalog sub-phenotypes \("p-value text" field\) automatically split into separate study IDs
* Subset of GWAS Catalog studies undergo additional distance-based clustering \(±500kb\) to remove redundant top loci
* Distance between variants and each canonical transcript start site \(TSS\) within 500kb has been added to the variant-to-gene data
* VEP consequences `intron_variant`, `5_prime_UTR_variant`, `3_prime_UTR_variant`, `NMD_transcript_variant` have been given non-zero \(0.1\) scores in the V2G assignment
* We now use the gnomAD \(v2.1\) site list as our variant index

#### 18 October 2018

Version 1 of Open Targets Genetics was released at the American Society of Human Genetics conference in San Diego in October 2018. Future updates to the portal will be documented here.

