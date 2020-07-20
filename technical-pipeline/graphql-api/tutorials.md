# How to find the Ensembl gene ID for a target

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

