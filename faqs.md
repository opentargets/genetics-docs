# FAQs

#### **What genome build are data in Genetics based on?**

All data are based on GRCh38 from the [Genome Reference Consortium](https://www.ncbi.nlm.nih.gov/grc).

#### **How is Open Targets Genetics related to the** [**Open Targets Platform**](https://www.targetvalidation.org)**?**

Open Targets Genetics is a variant-centric resource that complements the Open Targets Platform. Users can navigate to the Open Targets Platform from Open Targets Genetics and obtain for example drug information in clinical trials (or already marketed) for any target of interest.

Open Targets Genetics is also one of [data sources](https://docs.targetvalidation.org/data-sources/genetic-associations#open-targets-genetics-portal) that provide evidence for target-disease associations available in the Open Targets Platform.

#### **How do I cite discoveries made using Open Targets Genetics?**

Please cite our latest paper [Open Targets Genetics: systematic identification of trait-associated genes using large-scale genetics and functional genomics](https://academic.oup.com/nar/article/49/D1/D1311/5921290?login=false).

#### **How can I stay informed about new features and developments?**

For updates, please check the [Open Targets blog](https://blog.opentargets.org/) and [Open Targets Community](https://community.opentargets.org/), and follow us on [Twitter](https://twitter.com/OpenTargets) and [LinkedIn](https://www.linkedin.com/company/open-targets/).

**I would like to see a specific dataset or a new feature in Open Targets Genetics. How can I submit a feature request?**

Please post on the Open Targets Community under our [Feature Request category](https://community.opentargets.org/c/feature-requests/16), using the relevant tags. If the request you would like to make has already been posted, please like the post to indicate you would like this to be prioritised. The team will keep track of and update on the progress of these feature requests.

#### **Why are there two variants mapped to the same rsID?**

Many multi-allelic sites can be assigned a single rsID, and some rsIDs can point to different positions in the genome. This means that rsIDs are not unique to a single variant. We have mapped all rsIDs from GWAS Catalog to unique variants. A small minority of rsIDs will map to multiple variant IDs (approximately 0.6% of lead variants). When this occurs, variants will be duplicated in the portal.

#### **What is the difference between lead variant and tag variant?**

Lead variant is the variant at a given associated locus with the most significant (smallest) p-value whereas Tag variant is the variant that is correlated with the lead variant (r2>0.7) or present in the credible set at a GWAS-associated signal.

#### **What is the effect allele?**

The effect allele is the allele whose effects in relation to disease are being studied. In Open Targets Genetics, this is always the alternative allele.&#x20;

The direction of the effect of the alternative allele can be obtained from the PheWAS plot. If the association has a positive beta coefficient, this means the alternative (effect allele) allele increases the risk. If this value is negative, the alternative allele (effect allele) decreases the risk.

#### **Why are betas and odds ratios displayed inconsistently in the portal?**

Effect sizes are derived from summary statistics, where available, otherwise they are taken from GWAS Catalog curated data. All effects have been harmonised to be with respect to the [alternative allele](faqs.md#what-is-the-alternative-allele-why-not-use-the-minor-allele).

An effect size may not be shown in the portal if: (1)  the effect was not curated for that association by GWAS Catalog; (2) the variant is palindromic as it is not possible to accurately infer the strand, and so direction; (3) The reported risk allele is not-concordant with the alleles in our variant index; (4) the rsID to variant ID mapping was ambiguous (not one-to-one).

Sometimes GWAS Catalog data has been curated from multiple tables in a publication, some with betas, others with odds ratios. In these cases a mixture of betas and odds ratios may be displayed for a single study.

#### **What is the difference between beta coefficient and study beta coefficient?**

For every single variant that is independently and significantly associated with one study, we will display individual beta coefficient values with respect to the alternative allele of each of these variants, such as variants 19\_44886339\_G\_A, 19\_44908822\_C\_T, 1\_109274968\_G\_T associated with [LDL cholesterol](https://genetics.opentargets.org/study/GCST002222).

On the other hand, we display the **study beta** coefficient in the colocalisation table of the study locus page e.g. [LDL cholesterol (GCST002222) with locus around 19\_44886339\_G\_A (rs7254892)](https://genetics.opentargets.org/study-locus/GCST002222/19\_44886339\_G\_A). This beta is with respect to the alternative allele of a single variant, the **lead variant** at the top of the study locus page (i.e. rs7254892 for the LDL cholesterol study).

The reason we have decided to display the study beta it to facilitate the comparison of the direction of effect across different colocalising tissues.&#x20;

#### **What is summary statistics?**

Summary statistics is the aggregate p-values and association data for every variant analysed in a genome-wide association study.

#### **Why is there no LD information for my associated-locus of interest?**

Linkage disequilibrium is calculated using the 1000 Genome Phase 3 reference panel. If your variant is not in this panel post-QC (MAF > 1% and max missing rate < 0.05) then we will not provide any LD information for it.

#### **Why is there no credible set information for my associated-locus of interest?**

Fine-mapping can only be conducted for studies that we have full summary statistics for. Currently this consists of a subset of GWAS catalog studies, UK Biobank summary statistics from the Neale lab and credible set derived by FINNGEN. We encourage the scientific community to submit their full summary statistics to the GWAS Catalog.

#### **Why isn't my variant in Open Targets Genetics?**

Our variant index is built from the gnomAD (v2.1) site list, filtered to keep only variants with minor allele frequency > 0.1% in any population ([code](https://github.com/opentargets/genetics-variant-annotation)). If a variant is not in our index, it will not exist in the portal.

#### **Why doesn't my variant report the GTEx QTL?**

We apply a multiple testing correction that is different from the GTEx method. We use a method that is applicable across datasets, and not all datasets conduct a permutation analysis. We use a Bonferroni correction based on the number of variants tested per gene, i.e. p < 0.05 / (number of tests per gene). For example, GTEx assigns rs4734621 ([8\_102432699\_T\_C](https://genetics.opentargets.org/variant/8\_102432699\_T\_C)) to UBR5 whereas our V2G pipeline assigns it to both ODF1 and NCALD. More details on filtering can be found in the [pre-processing](https://genetics-docs.opentargets.org/our-approach/data-pipeline#pre-processing) help page

#### **How do I download the credible set of variants for an association of interest?**

Credible set information is available for all studies that have gone through our fine-mapping pipeline. The full set of variants in the 95% credible set can be downloaded using the **Tag Variant** table on the **Variant** page for the lead-variant at your locus of interest.

#### **What Variant-to-Gene (V2G) score threshold should I use as a "significance" cut-off?**

The V2G scores are intended as a way to rank genes based on all available functional data. We do not provide an [arbitrary cut-off](https://www.bmj.com/content/322/7280/226.1) for V2G scores.

The data used to calculate V2G scores are already pre-filtered to remove associations with low evidence after multiple testing procedures are applied. Therefore, any $$(V,G)$$ pair with a non-zero score has at least one good string of evidence in the data. The higher the V2G score, the more evidence there is for a functional association.

#### **Why are case counts missing for some case-control studies?**

Sample case counts are stored as part of a text string in GWAS Catalog. This makes the information difficult to parse reliably. We have decided not to show case numbers for these studies.

#### **What is the alternative allele? Why not use the minor allele?**

The reference (ref) and alternative (alt) alleles can be determined by looking at the variant ID, which takes the form: _chromosome\_position\_reference\_alternative_

The ref allele refers to the base that is found in the reference genome, currently GRCh38 in the portal. The alt allele refers to any base, other than the reference, that is found at the locus. The alt allele is not necessarily the minor allele.

For example, if we look at [rs2476601 (1\_114377568\_A\_G)](https://genetics.opentargets.org/variant/1\_114377568\_A\_G). _A_ is the ref, and _G_ is the alt. The allele frequencies and effect are with respect to the alt. So the G has frequency of 0.88 in Non-Finnish European, making it the major allele and A the minor allele.

There can be more than 1 alt allele per position in the genome, in which case they will appear as two separate variant IDs in the portal.

Using ref/alt, as opposed to major/minor, keeps things consistent across studies/populations.

#### Why is the number of independently associated loci different in the portal compared to the study's publication?

We report any association that is curated by the GWAS Catalog ([see inclusion criteria](https://www.ebi.ac.uk/gwas/docs/methods/criteria)), except for a [subset of studies](https://github.com/opentargets/genetics-v2d-data/blob/1fb2d604ad5c231bc912220237a2eede79fbcbba/logs/gwas-cat-assocs\_clustering.log#L8) (N=162) for which we apply an additional step of distance based clumping (±500kb).
