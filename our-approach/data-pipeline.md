# Data Pipeline

Based on Apache Spark and Python infrastructure, OT Genetics firstly annotates polymorphic variants in the genome with detailed trait association, functional and biological data across many cell types \(see Data Sources\), and assigns all published trait-associated lead variants a set of proxies based on LD, or a study-specific 95% credible set where summary statistics are available \(for phenotypes in the NHGRI-EBI GWAS Catalog summary statistics repository, or UK Biobank phenotypes from the Global Biobank Engine\).  This is the **aggregation stage**.  The subsequent **scoring stage** uses a weighted approach to collapse the complex cell type-specfic annotations for each variant into a single score which summarises the strength of evidence by which a variant implicates a given gene.  Using this score, the list of implicated genes for a given variant can be ranked and prioritised from those most likely to be causal to those of least interest.  Cross-referencing to other Open Targets resources allows the viability of these genes as drug targets to then be assesssed.  

{% hint style="info" %}
GRCh37 \(hg19\) genomic coordinates are used throughout the OT Genetics pipelines
{% endhint %}

Both stages are summarised below:

### Aggregation Stage

### Scoring Stage

Input from Ed, Eliseo, Miguel needed

