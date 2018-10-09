# What Technologies Do We Use?

![Diagram outlining technologies used for Open Targets Genetics](../.gitbook/assets/genetics_portal_technical_diagram.png)

Phase 1 of the pipeline is to prepare the input data \(V2D, V2G and summary statistics tables\) in a standardised way. Workflows are written in Python and run using Snakemake workflow management system to ensure analyses are reproducible and portable. Workflows are run on on a Google Compute instance, or the Sanger Institute cluster, and the output is stored on Google Cloud Storage \(GCS\).

Phase 2 of the pipeline processes and merges the input data to produce evidence linking traits to variants to genes. This merging pipeline is written in Scala and Spark running on a Google Dataproc cluster, which automatically scales to accommodate the quantity of the data.

The output tables are saved in JSON files on GCS before being loaded into a ClickHouse database running on a Google Compute instance. The API, which serves the data to the front-end, is written in Scala with Play framework using a GraphQL schema. The API runs on a Google App Engine to allow automatic scalability.

The front-end is written using the React javascript library and is hosted on Netlify.

