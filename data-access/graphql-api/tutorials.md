# How to find the Ensembl ID for a gene

You need to know the Ensembl gene ID for your gene of interest e.g. [PCSK9](https://genetics.opentargets.org/gene/ENSG00000169174) before using the Open Targets Genetics GraphQL API for more complex queries.

Use the`searchWithSymbol`query:

```
{  
  searchWithSymbol: search(queryString: "PCSK9") {
    genes {
      id
      symbol
 }
}
}
```

`Response`

```text
{
  "data": {
    "searchWithSymbol": {
      "genes": [
        {
          "id": "ENSG00000169174",
          "symbol": "PCSK9"
        }
      ]
    }
  }
}
```

![Finding the Ensembl Gene ID for PCSK9 using the GraphiQL browser](../../.gitbook/assets/screen-shot-2020-07-30-at-12.53.10.png)

{% hint style="info" %}
As an alternative to using the GraphI_i_QL browser, you can use `curl` instead to retrieve this information in the command line:

`curl -X POST https://genetics-api.opentargets.io/graphql -H 'Content-Type: application/json' -d '{ "query": "{ geneInfo(geneId: \"ENSG00000091831\") { symbol }}"}'`

For more complex queries, save your query in a separate file in JSON, for example, as illustrated [elsewhere](https://gist.github.com/mirandaio/bc0cac808341b074ab0e2da0cfcc3e42).
{% endhint %}
