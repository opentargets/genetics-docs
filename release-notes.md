# Release notes

Head to Open Targets blog for all [Genetics-releases](https://blog.opentargets.org/tag/open-targets-genetics/) posts.

#### 12 October 2022

* Integration of sQTLs from GTEx
* Update to GWAS Catalog studies
  * 6,591 new studies from 70 publications, none of which contain summary statistics
* Integration of FinnGen R6
  * The FinnGen R6 data freeze had data from over 260,000 individuals, analysed almost 17 million variants for over 2,800 disease endpoints (phenotypes). This data was made available to the public in January 2022
* Implementation of a Forest Plot in the variant page
* New API page with key example queries

**25 February 2022**

* New pQTL studies
  * 1,658 new pQTL associations from 6 studies in blood plasma: [Folkersen et al. 2017](https://journals.plos.org/plosgenetics/article?id=10.1371/journal.pgen.1006706); [Hillary et al. 2019](https://www.nature.com/articles/s41467-019-11177-x); [Olli et al. 2016](https://www.cell.com/ajhg/fulltext/S0002-9297\(16\)30485-2); [Pietzner et al. 2020](https://rdcu.be/cGGrc); [SCALLOP consortium, 2020](https://rdcu.be/cGGp3); [Suhre et al. 2017](https://www.nature.com/articles/ncomms14357)
* Updated GWAS Catalog studies
  * 1,508 new GWAS studies from 192 publications in the GWAS Catalog. 653 of these have summary statistics
* Fix to the colocalisation pipeline, and other data fixes
* Improvements to the front-end

For more details, see the [release blog post](https://blog.opentargets.org/open-targets-genetics-version-7/) and the [change log](change-log.md) page.

#### 25 Nov 2021

* Updated eQTL catalogue studies
  * 125 total tissue/cell type contexts from 29 studies (including GTEx v8)
  * 3.7 million colocalisation tests recomputed across all GWAS/eQTLs
* Updated GWAS Catalog studies
  * 1,029 new studies with full summary statistics
  * 2,451 new curated studies
* PheWAS plot now limited to p < 0.005 to improve performance
* Updated gene build from Ensembl 96 to Ensembl 104

For more details, see the [release blog post](https://blog.opentargets.org/open-targets-genetics-version-6/) and the [change log](change-log.md) page.

#### 29 June 2021

* FinnGen R5 sumstats - 2,781 endpoints
* Updated PheWAS plot to allow selection of FinnGen, UK Biobank, GWAS catalog
* Updated GWAS Catalog studies
  * 220 new studies with full summary statistics
  * 11,669 new curated studies

For more details, see the [release blog post](https://blog.opentargets.org/open-targets-genetics-version-5/) and the [change log](change-log.md) page.

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

* Fix compute score for distance (canonical tss) dataset where distance was `0`
* Compute a quantile score based on the rank of each variant 2 gene evidence in a (`source_id`, `feature`) window over the raw `*_score`

For more details, check the [change log](https://genetics-docs.opentargets.org/technical-pipeline/change-log) page.

#### 1 April 2019

* New release of GWAS Catalog curated data (r2019-03-01)
* Harmonised effect sizes for curated variant-disease associations
* GWAS Catalog sub-phenotypes ("p-value text" field) automatically split into separate study IDs
* Subset of GWAS Catalog studies undergo additional distance-based clustering (±500kb) to remove redundant top loci
* Distance between variants and each canonical transcript start site (TSS) within 500kb has been added to the variant-to-gene data
* VEP consequences `intron_variant`, `5_prime_UTR_variant`, `3_prime_UTR_variant`, `NMD_transcript_variant` have been given non-zero (0.1) scores in the V2G assignment
* We now use the gnomAD (v2.1) site list as our variant index

For more details, check the [release blog post](https://blog.opentargets.org/2019/04/09/open-targets-genetics-release-is-out/) and the [change log](https://genetics-docs.opentargets.org/technical-pipeline/change-log) page.

#### 18 October 2018

Open Targets Genetics was first released on 18th October 2018 at the American Society of Human Genetics conference in San Diego in October 2018.&#x20;

Head to [ASHG Workshop 2018](https://genetics-docs.opentargets.org/meetings/ashg-workshop-2018) for the training materials presented at that meeting.
