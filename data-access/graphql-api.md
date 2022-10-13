# GraphQL API

The [Open Targets Genetics Portal API](https://genetics.opentargets.org/api) is a GraphQL API that powers the user interface and that supports language-agnostic access to our data.

Compared to a REST API, our GraphQL API offers five key benefits:

1. You can construct a query that returns only the fields that you need
2. You can build graphical queries that traverse a data graph through resolvable entities and this reduces the need for multiple queries
3. You can access the [GraphQL API playground](https://api.genetics.opentargets.org/graphql/browser) with built-in documentation to build your query and run it in real-time&#x20;
4. You can view the [schema](https://api.genetics.opentargets.org/graphql/schema) that shows the available fields for each object along with a description and data type attribute&#x20;
5. You only have to use `POST` requests with a query string and variables object

## Available endpoints

The base URL endpoint for the Genetics Portal GraphQL API is:

```
https://api.genetics.opentargets.org/graphql
```

Our GraphQL API supports queries for a single variant, gene, study, or study-variant pair. For more systematic queries (e.g. for multiple variants), please use [our data downloads](data-download.md) or our Google BigQuery instance - [open-targets-prod](https://console.cloud.google.com/bigquery?project=open-targets-prod).

GraphQL's [query strings](https://graphql.org/learn/queries/) and [variables object](https://graphql.org/graphql-js/passing-arguments/) constructs, you can also access the data using any programming language that supports HTTP `POST` requests. While this is a valid approach, we discourage users from repeatedly querying the GraphQL API one entity at a time. Instead, our comprehensive [datasets available for download](data-download.md) provide a simpler and more performant strategy to achieve the same result.

## Sample scripts

Below is a sample script in Python for the same sample query -  [FINNGEN\_R5\_E4\_DM2 (Type 2 diabetes) and 11\_72752390\_G\_A](https://genetics.opentargets.org/study-locus/FINNGEN\_R5\_E4\_DM2/11\_72752390\_G\_A).

{% tabs %}
{% tab title="Python" %}
```python
#!/usr/bin/env python3

# Import relevant libraries for HTTP request and JSON formatting
import requests
import json

# Set study_id and variant_id variables
study_id = "FINNGEN_R5_E4_DM2"
variant_id = "11_72752390_G_A"

# Build query string
query_string = """
  query genePrioritisationUsingL2G($myVariantId: String!, $myStudyId: String! ){
    studyLocus2GeneTable(studyId: $myStudyId, variantId: $myVariantId){
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
"""

# Set variables object of arguments to be passed to endpoint
variables = {"myVariantId": variant_id, "myStudyId": study_id}

# Set base URL of Genetics Portal GraphQL API endpoint
base_url = "https://api.genetics.opentargets.org/graphql"

# Perform POST request and check status code of response
r = requests.post(base_url, json={"query": query_string, "variables": variables})
print(r.status_code)

# Transform API response into JSON 
api_response_as_json = json.loads(r.text)

# Print first element of JSON response data
print(api_response_as_json["data"]["studyLocus2GeneTable"]["rows"][0])
```
{% endtab %}

{% tab title="R" %}
```r
# Install relevant library for HTTP requests
library(httr)

# Set study_id and variant_id variables
study_id <- "FINNGEN_R5_E4_DM2"
variant_id <- "11_72752390_G_A"

# Build query string
query_string = "
  query genePrioritisationUsingL2G($myVariantId: String!, $myStudyId: String! ){
    studyLocus2GeneTable(studyId: $myStudyId, variantId: $myVariantId){
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
"

# Set base URL of Genetics Portal GraphQL API endpoint
base_url <- "https://api.genetics.opentargets.org/graphql"

# Set variables object of arguments to be passed to endpoint
variables <- list("myStudyId" = study_id, "myVariantId" = variant_id)

# Construct POST request body object with query string and variables
post_body <- list(query = query_string, variables = variables)

# Perform POST request
r <- POST(url=base_url, body=post_body, encode='json')

# Print first entry of L2G data to RStudio console
head(content(r)$data$studyLocus2GeneTable$rows, 1)
```
{% endtab %}
{% endtabs %}

## Tutorials and how-to guides

For more information on how to use the GraphQL API and example queries based on actual use cases and research questions, check out the [Open Targets Community](https://community.opentargets.org/).
