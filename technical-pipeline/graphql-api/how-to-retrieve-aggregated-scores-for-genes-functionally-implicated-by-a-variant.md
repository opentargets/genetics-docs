# How to retrieve aggregated scores for genes functionally implicated by a variant

Retrieve beta coefficient and p-value for genes that are functionally implicated by a variant.

`Query`

```text
{
  v_11_59864062_C_T: genesForVariant(variantId: "11_59864062_C_T") {
    overallScore
    gene {
      id
      symbol
      chromosome
      start
      end
      tss
    }
    qtls {
      aggregatedScore
      typeId
      sourceId
      tissues {
        tissue {
          id
          name
        }
        quantile
        beta
        pval
      }
    }
  }
}
```

`Response`

```text
{
  "data": {
    "v_11_59864062_C_T": [
      {
        "overallScore": 0.04532967032967032,
        "gene": {
          "id": "ENSG00000254952",
          "symbol": "AP001257.1",
          "chromosome": "11",
          "start": 60159687,
          "end": 60160822,
          "tss": 60160822
        },
        "qtls": []
      },
      {
        "overallScore": 0.03626373626373626,
        "gene": {
          "id": "ENSG00000110077",
          "symbol": "MS4A6A",
          "chromosome": "11",
          "start": 60172014,
          "end": 60184666,
          "tss": 60184666
        },
        "qtls": []
      },
      {
        "overallScore": 0.009065934065934065,
        "gene": {
          "id": "ENSG00000166926",
          "symbol": "MS4A6E",
          "chromosome": "11",
          "start": 60334831,
          "end": 60396596,
          "tss": 60334831
        },
        "qtls": []
      },
      {
        "overallScore": 0.01813186813186813,
        "gene": {
          "id": "ENSG00000172324",
          "symbol": "OR5A2",
          "chromosome": "11",
          "start": 59416969,
          "end": 59426412,
          "tss": 59426412
        },
        "qtls": []
      },
      {
        "overallScore": 0.07252747252747252,
        "gene": {
          "id": "ENSG00000255393",
          "symbol": "OOSP4B",
          "chromosome": "11",
          "start": 59978020,
          "end": 60031077,
          "tss": 59978020
        },
        "qtls": []
      },
      {
        "overallScore": 0.027197802197802195,
        "gene": {
          "id": "ENSG00000214787",
          "symbol": "MS4A4E",
          "chromosome": "11",
          "start": 60200270,
          "end": 60243137,
          "tss": 60243137
        },
        "qtls": []
      },
      {
        "overallScore": 0.0815934065934066,
        "gene": {
          "id": "ENSG00000284873",
          "symbol": "OOSP1",
          "chromosome": "11",
          "start": 59938432,
          "end": 59957480,
          "tss": 59938432
        },
        "qtls": []
      },
      {
        "overallScore": 0.01813186813186813,
        "gene": {
          "id": "ENSG00000172320",
          "symbol": "OR5A1",
          "chromosome": "11",
          "start": 59436469,
          "end": 59451380,
          "tss": 59436469
        },
        "qtls": []
      },
      {
        "overallScore": 0.01813186813186813,
        "gene": {
          "id": "ENSG00000166884",
          "symbol": "OR4D6",
          "chromosome": "11",
          "start": 59456938,
          "end": 59457991,
          "tss": 59456938
        },
        "qtls": []
      },
      {
        "overallScore": 0.027197802197802195,
        "gene": {
          "id": "ENSG00000254466",
          "symbol": "OR4D10",
          "chromosome": "11",
          "start": 59473315,
          "end": 59479361,
          "tss": 59473315
        },
        "qtls": []
      },
      {
        "overallScore": 0.027197802197802195,
        "gene": {
          "id": "ENSG00000172742",
          "symbol": "OR4D9",
          "chromosome": "11",
          "start": 59511368,
          "end": 59520703,
          "tss": 59511368
        },
        "qtls": []
      },
      {
        "overallScore": 0.0815934065934066,
        "gene": {
          "id": "ENSG00000166902",
          "symbol": "MRPL16",
          "chromosome": "11",
          "start": 59806140,
          "end": 59810778,
          "tss": 59810778
        },
        "qtls": []
      },
      {
        "overallScore": 0.05439560439560439,
        "gene": {
          "id": "ENSG00000110048",
          "symbol": "OSBP",
          "chromosome": "11",
          "start": 59574398,
          "end": 59615774,
          "tss": 59615774
        },
        "qtls": []
      },
      {
        "overallScore": 0.07252747252747252,
        "gene": {
          "id": "ENSG00000285010",
          "symbol": "OOSP4A",
          "chromosome": "11",
          "start": 59964033,
          "end": 59970146,
          "tss": 59964033
        },
        "qtls": []
      },
      {
        "overallScore": 0.04532967032967032,
        "gene": {
          "id": "ENSG00000255008",
          "symbol": "AP000442.1",
          "chromosome": "11",
          "start": 59561146,
          "end": 59566074,
          "tss": 59566074
        },
        "qtls": []
      },
      {
        "overallScore": 0.06346153846153844,
        "gene": {
          "id": "ENSG00000149516",
          "symbol": "MS4A3",
          "chromosome": "11",
          "start": 60056587,
          "end": 60071115,
          "tss": 60056587
        },
        "qtls": []
      },
      {
        "overallScore": 0.05439560439560439,
        "gene": {
          "id": "ENSG00000149534",
          "symbol": "MS4A2",
          "chromosome": "11",
          "start": 60088261,
          "end": 60098467,
          "tss": 60088261
        },
        "qtls": []
      },
      {
        "overallScore": 0.06346153846153844,
        "gene": {
          "id": "ENSG00000172289",
          "symbol": "OR10V1",
          "chromosome": "11",
          "start": 59712916,
          "end": 59713845,
          "tss": 59713845
        },
        "qtls": []
      },
      {
        "overallScore": 0.09065934065934064,
        "gene": {
          "id": "ENSG00000134812",
          "symbol": "CBLIF",
          "chromosome": "11",
          "start": 59829273,
          "end": 59845499,
          "tss": 59845499
        },
        "qtls": []
      },
      {
        "overallScore": 0.5802197802197802,
        "gene": {
          "id": "ENSG00000134827",
          "symbol": "TCN1",
          "chromosome": "11",
          "start": 59852800,
          "end": 59866489,
          "tss": 59866489
        },
        "qtls": [
          {
            "aggregatedScore": 0.8,
            "typeId": "eqtl",
            "sourceId": "eqtl",
            "tissues": [
              {
                "tissue": {
                  "id": "CEDAR-NEUTROPHIL_CD15",
                  "name": "Neutrophil cd15 (CEDAR)"
                },
                "quantile": 0.2,
                "beta": -0.340358,
                "pval": 0.00000317354
              },
              {
                "tissue": {
                  "id": "eQTLGen-UBERON_0000178",
                  "name": "Blood (eQTLGen)"
                },
                "quantile": 0.8,
                "beta": -0.46303803943469946,
                "pval": 2.8499e-48
              },
              {
                "tissue": {
                  "id": "Blueprint-NEUTROPHIL",
                  "name": "Neutrophil (Blueprint)"
                },
                "quantile": 0.3,
                "beta": -0.304993,
                "pval": 3.7648200000000005e-7
              }
            ]
          },
          {
            "aggregatedScore": 0.9,
            "typeId": "pqtl",
            "sourceId": "pqtl",
            "tissues": [
              {
                "tissue": {
                  "id": "SUN2018-UBERON_0001969",
                  "name": "Blood plasma (SUN2018)"
                },
                "quantile": 0.9,
                "beta": -0.7109,
                "pval": 4.570881896148752e-30
              }
            ]
          }
        ]
      },
      {
        "overallScore": 0.05439560439560439,
        "gene": {
          "id": "ENSG00000255139",
          "symbol": "AP000442.2",
          "chromosome": "11",
          "start": 59616429,
          "end": 59639861,
          "tss": 59616429
        },
        "qtls": []
      },
      {
        "overallScore": 0.03626373626373626,
        "gene": {
          "id": "ENSG00000110079",
          "symbol": "MS4A4A",
          "chromosome": "11",
          "start": 60185702,
          "end": 60317944,
          "tss": 60185702
        },
        "qtls": []
      },
      {
        "overallScore": 0.06346153846153844,
        "gene": {
          "id": "ENSG00000149507",
          "symbol": "OOSP2",
          "chromosome": "11",
          "start": 60040409,
          "end": 60048044,
          "tss": 60040409
        },
        "qtls": []
      },
      {
        "overallScore": 0.06346153846153844,
        "gene": {
          "id": "ENSG00000166889",
          "symbol": "PATL1",
          "chromosome": "11",
          "start": 59636716,
          "end": 59669037,
          "tss": 59669037
        },
        "qtls": []
      },
      {
        "overallScore": 0.027197802197802195,
        "gene": {
          "id": "ENSG00000176200",
          "symbol": "OR4D11",
          "chromosome": "11",
          "start": 59503576,
          "end": 59504511,
          "tss": 59503576
        },
        "qtls": []
      },
      {
        "overallScore": 0.09065934065934064,
        "gene": {
          "id": "ENSG00000285231",
          "symbol": "OOSP3",
          "chromosome": "11",
          "start": 59878809,
          "end": 59896481,
          "tss": 59878809
        },
        "qtls": []
      },
      {
        "overallScore": 0.06346153846153844,
        "gene": {
          "id": "ENSG00000166900",
          "symbol": "STX3",
          "chromosome": "11",
          "start": 59713456,
          "end": 59805882,
          "tss": 59713456
        },
        "qtls": []
      }
    ]
  }
}
```

