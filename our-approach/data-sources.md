# Annotation Data Sources

## Functional Annotation

The functional public data sources leveraged by OT Genetics to annotate variants broadly fall into one of two categories based on the genomic 'resolution' of the original analyses; \(1\) variant-centric and \(2\) interval-based.  

#### Variant-Centric

Directly annotate variants with functional consequences, and would include, for example, eQTL datasets, in which the Beta and SE of association with gene expression levels are provided variant-by-variant, in a conventional summary statistics-type format.  

#### Interval-Based

Assess the association between a region of the genome, often pre-selected on the basis of a biological or regulatory prior \(e.g. an enhancer\), and other functional elements proximal or distal to it.  As such, association statistics are not immediately available for each separate variant.  Instead, OT Genetics maps the defined genomic regions used as the base unit of analyses to variants falling within these intervals, using standard genomic maps.  Examples include Promoter-Capture Hi-C \(PCHi-C\).

#### Overview of Annotation

An overview of the data sources currently within the OT Genetics Pipeline can be found below, including how to interpret them as evidence for a target assignment in the platform.      

{% tabs %}
{% tab title="eQTL" %}
**Expression QTLs**

**Data Type -**  Variant-centric

Provide an additive, directional indication of the association between a variant and \(tissue-specific\) abundance of a specific target transcript.

| Source | Version | OT Source ID | OT Type ID | Cell Types |
| :--- | :--- | :--- | :--- | :--- |
| **G**enotype-**T**issue **Ex**pression Project | V7 \(2018\) | gtex | eqtl |  |
{% endtab %}

{% tab title="pQTL" %}
**Protein QTLs**

**Data Type -** Variant-centric

Provide an additive indication of the direction and magnitude of the association between a variant and circulating levels of a specific protein.

| Source | OT Source ID | OT Type ID | Tissues |
| :--- | :--- | :--- | :--- |
| [Sun _et al,_ Nature 2018](https://www.nature.com/articles/s41586-018-0175-2) | sun2018 | pqtl | 1 \(Blood\) |
{% endtab %}

{% tab title="FPred" %}
**Functional Prediction**

**Data Type -** Variant-centric

 Provides predicted coding consequences of a single nucleotide variant, according to the sequence ontology \(SO\).

| Source | OT Source ID | OT Type ID | Cell Types |
| :--- | :--- | :--- | :--- |
| **Ensembl** [**V**ariant **E**ffect **P**redictor \(VEP\)](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-016-0974-4) | vep | fpred | Not Applicable |
{% endtab %}

{% tab title="PCHiC" %}
**Promoter-Capture HiC**

**Data Type -** Interval-based

Assesses 3D chromatin conformation to identify regions interacting physically with promoters \(promoter-interacting regions, PIRs\).  These PIRs are interpreted as regulatory elements of their associated promoter.  A variant falling within a PIR implicated for a given promoter will be assigned the target under the control of that promoter.

| Source | OT Type ID | OT Source ID | Cell Types |
| :--- | :--- | :--- | :--- |
| [Javierre _et al_ Cell 2016](https://www.ncbi.nlm.nih.gov/pubmed/27863249) | pchic | javierre2016 | 17   |
{% endtab %}

{% tab title="DHS-Corr" %}
**DNase I Hypersensity Site Correlation**

DNase I hypersensitivity is a measure of chromatin accessibility and a marker of collocated _cis_-regulatory elements.  _A priori-_defined promoters can be assigned to putative regulatory elements by assessing correlation between the promoter DHS and _cis_ non-promoter DHS.  A variant falling within a non-promoter DHS correlated with a given promoter will be assigned the target under the control of that promoter. 

| Source  | OT Source ID | OT Type ID | Cell Types |
| :--- | :--- | :--- | :--- |
| [Thurman _et al_ Nature 2012](https://www.nature.com/articles/nature11232%20) | thurman2012 | dhscor | 125 |
{% endtab %}

{% tab title="Fantom5" %}
**Fantom 5 Enhancers**
{% endtab %}
{% endtabs %}

{% hint style="info" %}
 We have created OT Genetics to be scalable and readily extensible.  New data sources will continually be curated, reviewed, incorporated, and documented here and in the changelog.  Please get in touch with any suggestions.  
{% endhint %}



