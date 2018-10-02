# Assigning Traits to Loci

### Lead Variant Annotation

OT Genetics is based on human genome 37 \(GRCh37, hg19\) as defined by Ensembl.  Lead variants \(V&lt;sub&gt;L&lt;/sub&gt;\) implicated in a phenotype by hypothesis-free approaches \(GWAS\) are initially annotated with their associated trait\(s\) as described below:

{% hint style="info" %}
The trait entity in OT Genetics is assigned in the format `Reported Trait (Author, Year)`.   Multiple studies assessing the same trait are _not_ collapsed into a single annotation.  
{% endhint %}

#### Published Variants

Reported variant-phenotype associations in literature were identified _via_ the NHGRI-EBI GWAS Catalog, a manually-curated database of published variants meeting certain inclusion criteria, which will be familiar to most geneticists.  On an ongoing basis, GWAS Catalog extracts and records detailed variant and study-level data for variants reported to be associated with any phenotype at a significance level of p&lt;=5E-05, and which fall within the inclusion criteria detailed here.

#### UK Biobank Phenotypes

Recent efforts to rapidly and systematically apply established GWAS methods to all available data fields in UKB have made available large repositories of summary statistics.  To leverage these data for variant annotation, we downloaded the full set of summary statistics produced by the Global Biobank Engine Round I \(Neale and colleagues\).  These analyses applied GWAS \(implemented in HAIL\) to all possible data fields in UKB's Interim Genotyping Release \(May 2015\), containing up to ~150,000 participants with intersecting genotyping and phenotype data.  

For the puposes of OT Genetics, independent loci were defined on the basis of proximity, using a 1mB window centred on each lead variant \(p&lt;=5E-08\).  Where two genome-wide significant \(GWS\) variants were located &lt;500kB apart, the variant with the higher p-value was subsumed into the locus defined by the more significant variant.  Conditional and joint analyses \(GCTA-COJO\) were subsequently applied to every identified locus to highlight secondary signals which retained GWS after conditioning the locus for the effect of the lead variant.  LD reference data for these analyses was taken from UK10K Europeans.   

### Locus Definition

By default, all lead variants were expanded on the basis of LD \(1000G Phase III Europeans, r2&gt;0.7\) to identify the corresponding set of tag variants \(Vt\) through which the identified phenotype signal might plausibly exert a biological effect.  For variant-phenotype combination with full summary statistics available \(currently UKB phenotypes from GBE\), a subset of these proxies corresponding to the 95% credible set at the locus for the phenotype were prioritised using a custom fine-mapping approach:

#### Custom Fine-Mapping

@Ed - to fill in details      

{% hint style="info" %}
Due to a legacy pipeline mismatch, different European LD reference panels are used for conditional-joint analyses vs. the locus definition stage.  LD sources will be unified and updated in later releases of the portal.
{% endhint %}

     

