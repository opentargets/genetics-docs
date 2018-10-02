# Introducing the Locus Plot

Many pages in the portal are centred on a new plot designed to effectively summarise the complexity of the links between numerous genes \(targets\), traits, and lead variants.  We call this the Locus Plot.  

The Locus Plot uses a track-style browser to display a locus which can be centred on a gene, variant, or trait of interest \(each known as an **entity**\).  Connecting traits, variants and genes are **evidence strings** which indicate an association or functional link between the entities.  A link indicates that there is at least one element of functional data in at least one cell by which the two entities are associated.  When navigating to the Locus Plot, certain entities will be pre-selected based on context; filters and selections can be altered at any time by clicking an entity or removing it from the applied filters.  

The example below highlights the main features of the plot and should help you familiarise yourself with its concepts.  In this case, one variant from one study has been selected to identify the targets prioritised as functional at this locus.

### Entity Tracks

![The plot contains four entity tracks - study \(S\), lead variants \(Vl\), tag variants \(Vt\) and genes \(G\) ](../.gitbook/assets/screen-shot-2018-10-02-at-10.35.55.png)

#### Key Features

{% hint style="success" %}
The example above shows one lead selected from one study, functionally implicating four genes via one of a number of LD-defined tag variants in at least one data source and cell type.
{% endhint %}

1. Entities and evidence strings can be coloured grey, red or blue.  
2. Selected entities are indicated on 'chips' at the top of the plot and are highlighted blue.  For any track on which a selection has been applied, the track label will also be illuminated blue
3. Red entities and tracks are those linked to the selected entities by underlying trait or functional annotation, but not actively selected.  They will usually be the main tracks of interest.  
4. Grey entities are those colocated at the locus displayed, but not implicated by OT Genetics.  Grey genes can be hidden from view by using the drop-down at the top of the display
5. Some entities will be pre-selected when the plot is loaded, based on viewing context.  Any combination of entities can then be selected and managed using the 'chip' filters.
6. Selecting multiple entities will display the **intersection** of evidence strings containing the selections
7. Selections dynamically update and restrict the **Evidence Strings Table**, restricting it to those evidence strings currently being displayed
8. V\(T\) in the loci of V\(L\) are defined either on LD, or using finemapping approaches if sumstats are available.  Evidence strings which pass via a V\(T\) in the credible set are distinguished from those acting via LD-defined V\(T\) by the colour of the link \(see key\).  Credible sets are re-calculated for every V\(L\)-study pairing displayed on the plot.  The logic used to define V\(T\) can be restricted to finemapping only using the 'expansion' drop-down, in which case all LD-based V\(T\) are hidden
9. To restrict the credible set finemapping to a single set of summary statistics, the corresponding study must be selected.  Alternatively search the Evidence String Table to identify strings of interest.
10. The locus can be panned and zoomed using the embedded controls \(upper left\)
11. Download a static PNG of the plot for presentation/publication using the 'PNG' link \(upper right\) 

{% hint style="warning" %}
In the current version, links are only shown between entities if there is there is a link between all four entities.  This means that variants can only be viewed in the Locus Plot if it has both a trait and a functional annotation.  The Plot will be updated to allow variants with functional but not trait annotation, for example, to be viewed in the next release.
{% endhint %}

### Evidence String Table

![](../.gitbook/assets/screen-shot-2018-10-02-at-12.14.06.png)



