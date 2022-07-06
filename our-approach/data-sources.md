# Data Sources

{% hint style="info" %}
&#x20;We have designed Open Targets Genetics to be scalable and readily extensible. New data sources will continually be curated, reviewed, incorporated, and documented here and in the release notes.  Please get in touch with any suggestions. &#x20;
{% endhint %}

#### **Variant index**

* [GnomAD v2.1](https://gnomad.broadinstitute.org/)

#### **Disease-associated loci sources (V2D)**

* [GWAS Catalog curated studies](https://www.ebi.ac.uk/gwas/)
* [GWAS Catalog summary statistics](https://www.ebi.ac.uk/gwas/summary-statistics)
* [Neale lab UK Biobank summary statistics](http://www.nealelab.is/uk-biobank/)
* [SAIGE UK Biobank summary statistics](https://www.ncbi.nlm.nih.gov/pubmed/30104761)
* [FinnGen summary statistics](https://r5.finngen.fi/)

#### **Haplotype reference samples**

* [1000 Genomes Phase 3](http://www.internationalgenome.org/category/phase-3/) - used for LD expansion
* [UK Biobank genotypes](https://www.ukbiobank.ac.uk/) - used for conditional analysis in top-loci detection, fine-mapping and colocalisation analyses ([approved application](https://www.ukbiobank.ac.uk/2019/04/using-genetic-data-in-drug-target-discovery-and-validation/)).

#### **Variant-to-Gene (V2G) annotation sources**

* _In silico_ functional prediction
  * [Variant-Effect Predictor (VEP)](https://www.ncbi.nlm.nih.gov/pubmed/27268795): Most severe transcript consequence(s)
* Molecular quantitative trait locus (QTL) experiments
* pQTL: Evidence linking genetic variation to protein abundance in the list of studies below:

&#x20;   \- [Sun et al. 2018](https://pubmed.ncbi.nlm.nih.gov/29875488/)

&#x20;   \- [Folkersen et al. 2017](https://journals.plos.org/plosgenetics/article?id=10.1371/journal.pgen.1006706)

&#x20;   \- [Hillary et al. 2019](https://www.nature.com/articles/s41467-019-11177-x)

&#x20;   \- [Olli et al. 2016](https://www.cell.com/ajhg/fulltext/S0002-9297\(16\)30485-2)&#x20;

&#x20;   \- [Pietzner et al. 2020](https://rdcu.be/cGGrc)

&#x20;   \- [SCALLOP consortium, 2020](https://rdcu.be/cGGp3)

&#x20;   \- [Suhre et al. 2017](https://www.nature.com/articles/ncomms14357)

* eQTL: Evidence linking genetic variation to gene expression. See table below: &#x20;

| Consortium                                              | Tissues/cell types                                                                      |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| [GTEX v7](https://www.ncbi.nlm.nih.gov/pubmed/29022597) | 44 tissues                                                                              |
| ALASOO                                                  | Macrophage naive/IFNG/IFNG Salmonella                                                   |
| BLUEPRINT                                               | Monocyte, neutrophil, T cells                                                           |
| CEDAR                                                   | B cells, Ileum, monocyte, neutrophil, platelet, rectrum, traverse colon, T cell CD4/CD8 |
| FAIRFAX                                                 | Monocyte naive/IFN24/LPS2/LPS24, neutrophil, T cells, B cells                           |
| GENCORD                                                 | Fibroblast, LCL, T cells                                                                |
| GEUVADIS                                                | LCL                                                                                     |
| HIPSCI                                                  | iPSC                                                                                    |
| NARANBHAI                                               | Neutrophil CD16                                                                         |
| NEDELEC                                                 | Macrophage naive/Listeria/Salmonella                                                    |
| QUACH                                                   | Monocyte IAV/LPS/naive/PAM3CSK4/R848                                                    |
| SCHWAYZENTRUBER\_2018                                   | Sensory neuron                                                                          |
| TWINSUK                                                 | Skin, fat, LCL                                                                          |
| VAN\_DE\_BUNT\_2015                                     | Pancreatic islet                                                                        |
| eQTLGen                                                 | Blood                                                                                   |

* Interaction / interval based experiments
  * [Promoter Capture Hi-C (Javierre _et al._, 2016)](https://www.ncbi.nlm.nih.gov/pubmed/27863249): Evidence linking genetic variation to genes using Promoter Capture Hi-C in each of the 17 human primary hematopoietic cell types
  * [Enhancer-TSS correlation (Andersson _et al._, 2014)](https://www.ncbi.nlm.nih.gov/pubmed/24670763): Evidence linking genetic variation to genes using correlation between the transcriptional activity of enhancers and transcription start sites using the FANTOM5 CAGE expression atlas
  * [DHS-promoter correlation (Thurman _et al._, 2012)](https://www.ncbi.nlm.nih.gov/pubmed/22955617): Evidence linking genetic variation to genes using correlation of DNase I hypersensitive site and gene promoters across 125 cell and tissue types from ENCODE

Further details on each V2G dataset, including workflows to reproduce them, are located [here](https://github.com/opentargets/v2g\_data/).
