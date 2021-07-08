# GraphQL API tutorials

The Open Targets Genetics Portal GraphQL API — available at [https://api.genetics.opentargets.org/](https://api.genetics.opentargets.org/) — is the robust API that powers the user interface and that supports language-agnostic access to our data, along with other key benefits:

1. You can construct a query that returns only the fields that you need
2. You can build graphical queries that traverse a data graph through resolvable entities and this reduces the need for multiple queries
3. You can access the [GraphQL API playground](https://api.genetics.opentargets.org/graphql/browser) with built-in documentation and schema showing required and optional parameters 
4. You can view the [schema](https://api.genetics.opentargets.org/graphql/schema) that shows the available fields for each object along with a description and data type attribute 
5. You only have to use `POST` requests with a simple query string and variables object

To access the data with your programming language of choice, you will need to use the following GraphQL API endpoint:

{% hint style="info" %}
[**https://api.genetics.opentargets.org/graphql**](https://api.genetics.opentargets.org/graphql)\*\*\*\*
{% endhint %}

Our GraphQL API supports queries for a single variant, gene, study, or study-variant pair. For more systematic queries \(e.g. for multiple variants\), please use [our data downloads](../data-download.md) or our Google BigQuery instance - [open-targets-prod](https://console.cloud.google.com/bigquery?project=open-targets-prod).



