# How to find the Ensembl ID for a gene

You need to know the Ensembl gene ID for your gene \(or target\) of interest to apply the Open Targets Genetics GraphQL API for more complex queries \(e.g. find which studies are associated with a gene based on the locus-to-gene pipeline\).

Use`searchWithSymbol`.

`Query`

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

{% hint style="info" %}
Instead of using the GraphI_i_QL browser, you can use `curl` to retrieve this information instead in the command line:

`curl -X POST https://genetics-api.opentargets.io/graphql -H 'Content-Type: application/json' -d '{ "query": "{ geneInfo(geneId: \"ENSG00000091831\") { symbol }}"}'`
{% endhint %}

{% hint style="warning" %}
For more complex queries, save your query in a separate file in JSON, for example, as illustrated [elsewhere](https://gist.github.com/mirandaio/bc0cac808341b074ab0e2da0cfcc3e42).
{% endhint %}





