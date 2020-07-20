# Tutorials

## **How to find the Ensembl gene ID for your gene of interest**

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

