# GraphQL API

The [Open Targets Genetics Portal API](https://api.genetics.opentargets.org/) is a GraphQL API that powers the user interface and that supports language-agnostic access to our data.

Compared to a REST API, our GraphQL API offers five key benefits:

1. You can construct a query that returns only the fields that you need
2. You can build graphical queries that traverse a data graph through resolvable entities and this reduces the need for multiple queries
3. You can access the [GraphQL API playground](https://api.genetics.opentargets.org/graphql/browser) with built-in documentation to build your query and run it in real-time 
4. You can view the [schema](https://api.genetics.opentargets.org/graphql/schema) that shows the available fields for each object along with a description and data type attribute 
5. You only have to use `POST` requests with a query string and variables object

{% hint style="info" %}
To access our GraphQL API, please use our endpoint `https://api.genetics.opentargets.org/graphql`
{% endhint %}

Our GraphQL API supports queries for a single variant, gene, study, or study-variant pair. For more systematic queries \(e.g. for multiple variants\), please use [our data downloads](data-download.md) or our Google BigQuery instance - [open-targets-prod](https://console.cloud.google.com/bigquery?project=open-targets-prod).

## Example GraphQL query

Below is an example GraphQL query for the study-locus information for [FINNGEN\_R5\_E4\_DM2 \(Type 2 diabetes\) and 11\_72752390\_G\_A](https://genetics.opentargets.org/study-locus/FINNGEN_R5_E4_DM2/11_72752390_G_A) that you can copy and paste into [our GraphQL playground](https://api.genetics.opentargets.org/graphql/browser).

```graphql
query genePrioritisationUsingL2G {
  studyLocus2GeneTable(studyId: "FINNGEN_R5_E4_DM2", variantId: "11_72752390_G_A") {
    rows {
      gene {
        symbol
        id
      }
      yProbaModel
      yProbaDistance
      yProbaInteraction
      yProbaMolecularQTL
      yProbaPathogenicity
      hasColoc
      distanceToLocus
    }
  }
}
```

Using GraphQL's [query strings](https://graphql.org/learn/queries/) and [variables object](https://graphql.org/graphql-js/passing-arguments/) constructs, you can also access the data using a programming language that supports HTTP `POST` requests. While this is a valid approach, we discourage users from repeatedly querying the GraphQL API one entity at a time. Instead, our comprehensive [datasets available for download](data-download.md) provide a simpler and more performant strategy to achieve the same result.

