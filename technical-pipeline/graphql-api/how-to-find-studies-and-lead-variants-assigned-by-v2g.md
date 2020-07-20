# How to find studies and lead variants assigned by V2G

This example illustrates how you can find all studies from the GWAS Catalog or UK Biobank  e.g. [GCST008413](https://genetics.opentargets.org/study/GCST008413) and [NEALE2\_1687](https://genetics.opentargets.org/study/GCST008413), plus all lead variants assigned to your gene of interest \(ENSG00000158158\) as a result of the [V2G pipeline](https://genetics-docs.opentargets.org/our-approach/data-pipeline).

Use the `studiesAndLeadVariantsForGene`query:

```text
{
  studiesAndLeadVariantsForGene(geneId: "ENSG00000158158") {
    indexVariant {
      id
      rsId
    }
    study {
      studyId
      traitReported
    }
  }
}
```

`Response`

```text
{
  "data": {
    "studiesAndLeadVariantsForGene": [
      {
        "indexVariant": {
          "id": "2_96663115_C_T",
          "rsId": "rs17634791"
        },
        "study": {
          "studyId": "NEALE2_30180_raw",
          "traitReported": "Lymphocyte percentage"
        }
      },
      {
        "indexVariant": {
          "id": "2_96506388_G_A",
          "rsId": "rs1866444"
        },
        "study": {
          "studyId": "GCST008413",
          "traitReported": "Core binding factor acute myeloid leukemia"
        }
      },
      {
        "indexVariant": {
          "id": "2_96535945_G_A",
          "rsId": "rs2579500"
        },
        "study": {
          "studyId": "NEALE2_30210_raw",
          "traitReported": "Eosinophill percentage"
        }
      },
      {
        "indexVariant": {
          "id": "2_96535945_G_A",
          "rsId": "rs2579500"
        },
        "study": {
          "studyId": "GCST004606",
          "traitReported": "Eosinophil counts"
        }
      },
      {
        "indexVariant": {
          "id": "2_96297946_A_G",
          "rsId": "rs772178"
        },
        "study": {
          "studyId": "GCST006258",
          "traitReported": "Diastolic blood pressure"
        }
      },
      {
        "indexVariant": {
          "id": "2_96388214_TTAGA_T",
          "rsId": "rs35205062"
        },
        "study": {
          "studyId": "NEALE2_30150",
          "traitReported": "Eosinophill count"
        }
      },
      {
        "indexVariant": {
          "id": "2_96189503_G_A",
          "rsId": "rs4907230"
        },
        "study": {
          "studyId": "NEALE2_30190_raw",
          "traitReported": "Monocyte percentage"
        }
      },
      {
        "indexVariant": {
          "id": "2_96535945_G_A",
          "rsId": "rs2579500"
        },
        "study": {
          "studyId": "GCST007065",
          "traitReported": "Eosinophil counts"
        }
      },
      {
        "indexVariant": {
          "id": "2_96535945_G_A",
          "rsId": "rs2579500"
        },
        "study": {
          "studyId": "GCST004624",
          "traitReported": "Sum eosinophil basophil counts"
        }
      },
      {
        "indexVariant": {
          "id": "2_96510897_C_T",
          "rsId": "rs2579503"
        },
        "study": {
          "studyId": "GCST007269",
          "traitReported": "Pulse pressure"
        }
      },
      {
        "indexVariant": {
          "id": "2_96535945_G_A",
          "rsId": "rs2579500"
        },
        "study": {
          "studyId": "GCST004600",
          "traitReported": "Eosinophil percentage of white cells"
        }
      },
      {
        "indexVariant": {
          "id": "2_96381261_G_A",
          "rsId": "rs1081707"
        },
        "study": {
          "studyId": "GCST007268",
          "traitReported": "Diastolic blood pressure"
        }
      },
      {
        "indexVariant": {
          "id": "2_96564337_G_A",
          "rsId": "rs2708977"
        },
        "study": {
          "studyId": "GCST004617",
          "traitReported": "Eosinophil percentage of granulocytes"
        }
      },
      {
        "indexVariant": {
          "id": "2_96479597_T_TTG",
          "rsId": "rs113359549"
        },
        "study": {
          "studyId": "GCST004606",
          "traitReported": "Eosinophil counts"
        }
      },
      {
        "indexVariant": {
          "id": "2_96564337_G_A",
          "rsId": "rs2708977"
        },
        "study": {
          "studyId": "GCST004623",
          "traitReported": "Neutrophil percentage of granulocytes"
        }
      },
      {
        "indexVariant": {
          "id": "2_96502225_T_C",
          "rsId": "rs2579505"
        },
        "study": {
          "studyId": "NEALE2_30150",
          "traitReported": "Eosinophill count"
        }
      },
      {
        "indexVariant": {
          "id": "2_96116247_G_C",
          "rsId": "rs3111873"
        },
        "study": {
          "studyId": "NEALE2_4079_raw",
          "traitReported": "Diastolic blood pressure, automated reading"
        }
      },
      {
        "indexVariant": {
          "id": "2_95936694_T_C",
          "rsId": null
        },
        "study": {
          "studyId": "GCST004617",
          "traitReported": "Eosinophil percentage of granulocytes"
        }
      },
      {
        "indexVariant": {
          "id": "2_96009418_T_C",
          "rsId": "rs2579519"
        },
        "study": {
          "studyId": "GCST004280",
          "traitReported": "Diastolic blood pressure"
        }
      },
      {
        "indexVariant": {
          "id": "2_96093689_T_C",
          "rsId": "rs2579547"
        },
        "study": {
          "studyId": "GCST004609",
          "traitReported": "Monocyte percentage of white cells"
        }
      },
      {
        "indexVariant": {
          "id": "2_96377542_G_GT",
          "rsId": "rs561539268"
        },
        "study": {
          "studyId": "NEALE2_1687",
          "traitReported": "Comparative body size at age 10"
        }
      },
      {
        "indexVariant": {
          "id": "2_96259531_T_A",
          "rsId": "rs4907307"
        },
        "study": {
          "studyId": "GCST006568",
          "traitReported": "Highest math class taken (MTAG) [MTAG]"
        }
      },
      {
        "indexVariant": {
          "id": "2_96739703_G_A",
          "rsId": "rs2271893"
        },
        "study": {
          "studyId": "GCST001358",
          "traitReported": "Bipolar disorder"
        }
      },
      {
        "indexVariant": {
          "id": "2_96714492_T_G",
          "rsId": "rs56361249"
        },
        "study": {
          "studyId": "GCST003962",
          "traitReported": "Bipolar disorder"
        }
      },
      {
        "indexVariant": {
          "id": "2_96710670_A_AT",
          "rsId": "rs57195239"
        },
        "study": {
          "studyId": "GCST008103",
          "traitReported": "Bipolar disorder"
        }
      },
      {
        "indexVariant": {
          "id": "2_96739703_G_A",
          "rsId": "rs2271893"
        },
        "study": {
          "studyId": "GCST006585_941",
          "traitReported": "Blood protein levels [LMAN2L]"
        }
      },
      {
        "indexVariant": {
          "id": "2_96686103_A_G",
          "rsId": "rs7599598"
        },
        "study": {
          "studyId": "GCST006193_3",
          "traitReported": "Diastolic blood pressure x smoking status (current vs non-current) interaction (2df test) [EA]"
        }
      },
      {
        "indexVariant": {
          "id": "2_96686103_A_G",
          "rsId": "rs7599598"
        },
        "study": {
          "studyId": "GCST006166_6",
          "traitReported": "Diastolic blood pressure x alcohol consumption interaction (2df test) [Asian, EA]"
        }
      },
      {
        "indexVariant": {
          "id": "2_96686103_A_G",
          "rsId": "rs7599598"
        },
        "study": {
          "studyId": "GCST006190",
          "traitReported": "Diastolic blood pressure x smoking status (ever vs never) interaction (2df test)"
        }
      },
      {
        "indexVariant": {
          "id": "2_96686103_A_G",
          "rsId": "rs7599598"
        },
        "study": {
          "studyId": "GCST006166_8",
          "traitReported": "Diastolic blood pressure x alcohol consumption interaction (2df test) [EA]"
        }
      },
      {
        "indexVariant": {
          "id": "2_96686103_A_G",
          "rsId": "rs7599598"
        },
        "study": {
          "studyId": "GCST006193",
          "traitReported": "Diastolic blood pressure x smoking status (current vs non-current) interaction (2df test)"
        }
      },
      {
        "indexVariant": {
          "id": "2_96686103_A_G",
          "rsId": "rs7599598"
        },
        "study": {
          "studyId": "GCST006190_3",
          "traitReported": "Diastolic blood pressure x smoking status (ever vs never) interaction (2df test) [EA]"
        }
      },
      {
        "indexVariant": {
          "id": "2_96752905_T_G",
          "rsId": "rs189255944"
        },
        "study": {
          "studyId": "NEALE2_20151_raw",
          "traitReported": "Forced vital capacity (fvc), best measure"
        }
      },
      {
        "indexVariant": {
          "id": "2_96617939_T_C",
          "rsId": "rs183743021"
        },
        "study": {
          "studyId": "NEALE2_20015_raw",
          "traitReported": "Sitting height"
        }
      },
      {
        "indexVariant": {
          "id": "2_97716827_T_C",
          "rsId": "rs11683207"
        },
        "study": {
          "studyId": "SAIGE_401_1",
          "traitReported": "Essential hypertension"
        }
      },
      {
        "indexVariant": {
          "id": "2_97716827_T_C",
          "rsId": "rs11683207"
        },
        "study": {
          "studyId": "SAIGE_401",
          "traitReported": "Hypertension"
        }
      },
      {
        "indexVariant": {
          "id": "2_97131943_T_C",
          "rsId": "rs13390019"
        },
        "study": {
          "studyId": "GCST008757",
          "traitReported": "Alcohol consumption"
        }
      },
      {
        "indexVariant": {
          "id": "2_96941334_A_G",
          "rsId": "rs6728642"
        },
        "study": {
          "studyId": "GCST005081",
          "traitReported": "Bipolar disorder lithium response (continuous) or schizophrenia"
        }
      },
      {
        "indexVariant": {
          "id": "2_96062159_C_T",
          "rsId": "rs17119859"
        },
        "study": {
          "studyId": "GCST004623",
          "traitReported": "Neutrophil percentage of granulocytes"
        }
      },
      {
        "indexVariant": {
          "id": "2_95991827_A_G",
          "rsId": "rs62155511"
        },
        "study": {
          "studyId": "GCST007269",
          "traitReported": "Pulse pressure"
        }
      },
      {
        "indexVariant": {
          "id": "2_97658891_G_A",
          "rsId": "rs11692435"
        },
        "study": {
          "studyId": "GCST007328",
          "traitReported": "Alcohol consumption (drinks per week)"
        }
      },
      {
        "indexVariant": {
          "id": "2_97658891_G_A",
          "rsId": "rs11692435"
        },
        "study": {
          "studyId": "GCST007474",
          "traitReported": "Smoking initiation (ever regular vs never regular)"
        }
      },
      {
        "indexVariant": {
          "id": "2_97658891_G_A",
          "rsId": "rs11692435"
        },
        "study": {
          "studyId": "GCST007992",
          "traitReported": "Colorectal cancer"
        }
      },
      {
        "indexVariant": {
          "id": "2_97658891_G_A",
          "rsId": "rs11692435"
        },
        "study": {
          "studyId": "GCST007039",
          "traitReported": "Body mass index"
        }
      },
      {
        "indexVariant": {
          "id": "2_97658891_G_A",
          "rsId": "rs11692435"
        },
        "study": {
          "studyId": "GCST007468",
          "traitReported": "Smoking initiation (ever regular vs never regular) (MTAG)"
        }
      },
      {
        "indexVariant": {
          "id": "2_99329966_C_CA",
          "rsId": "rs70940164"
        },
        "study": {
          "studyId": "NEALE2_23115_raw",
          "traitReported": "Leg fat percentage (left)"
        }
      },
      {
        "indexVariant": {
          "id": "2_97658891_G_A",
          "rsId": "rs11692435"
        },
        "study": {
          "studyId": "GCST007461",
          "traitReported": "Alcohol consumption (drinks per week)"
        }
      },
      {
        "indexVariant": {
          "id": "2_97658891_G_A",
          "rsId": "rs11692435"
        },
        "study": {
          "studyId": "GCST007472",
          "traitReported": "Alcohol consumption (drinks per week) (MTAG)"
        }
      },
      {
        "indexVariant": {
          "id": "2_97658891_G_A",
          "rsId": "rs11692435"
        },
        "study": {
          "studyId": "GCST008522",
          "traitReported": "Bitter alcoholic beverage consumption"
        }
      },
      {
        "indexVariant": {
          "id": "2_96617939_T_C",
          "rsId": "rs183743021"
        },
        "study": {
          "studyId": "NEALE2_3062_raw",
          "traitReported": "Forced vital capacity (fvc)"
        }
      },
      {
        "indexVariant": {
          "id": "2_96617939_T_C",
          "rsId": "rs183743021"
        },
        "study": {
          "studyId": "NEALE2_20153_raw",
          "traitReported": "Forced expiratory volume in 1-second (fev1), predicted"
        }
      },
      {
        "indexVariant": {
          "id": "2_97973620_T_A",
          "rsId": "rs905484"
        },
        "study": {
          "studyId": "NEALE2_30210_raw",
          "traitReported": "Eosinophill percentage"
        }
      },
      {
        "indexVariant": {
          "id": "2_97718216_C_T",
          "rsId": "rs11687510"
        },
        "study": {
          "studyId": "GCST008413",
          "traitReported": "Core binding factor acute myeloid leukemia"
        }
      },
      {
        "indexVariant": {
          "id": "2_97740700_T_C",
          "rsId": "rs4851462"
        },
        "study": {
          "studyId": "GCST006630",
          "traitReported": "Diastolic blood pressure"
        }
      },
      {
        "indexVariant": {
          "id": "2_97774654_G_A",
          "rsId": "rs10191483"
        },
        "study": {
          "studyId": "NEALE2_30200_raw",
          "traitReported": "Neutrophill percentage"
        }
      },
      {
        "indexVariant": {
          "id": "2_97921970_A_G",
          "rsId": "rs1578957"
        },
        "study": {
          "studyId": "GCST006287",
          "traitReported": "Adolescent idiopathic scoliosis"
        }
      },
      {
        "indexVariant": {
          "id": "2_95848679_C_T",
          "rsId": "rs13406335"
        },
        "study": {
          "studyId": "NEALE2_30210_raw",
          "traitReported": "Eosinophill percentage"
        }
      },
      {
        "indexVariant": {
          "id": "2_97032743_A_C",
          "rsId": "rs13005320"
        },
        "study": {
          "studyId": "NEALE2_30150",
          "traitReported": "Eosinophill count"
        }
      },
      {
        "indexVariant": {
          "id": "2_94695807_T_A",
          "rsId": "rs191977771"
        },
        "study": {
          "studyId": "NEALE2_50_raw",
          "traitReported": "Standing height"
        }
      },
      {
        "indexVariant": {
          "id": "2_94717678_C_T",
          "rsId": "rs114519920"
        },
        "study": {
          "studyId": "NEALE2_1697",
          "traitReported": "Comparative height size at age 10"
        }
      },
      {
        "indexVariant": {
          "id": "2_96752905_T_G",
          "rsId": "rs189255944"
        },
        "study": {
          "studyId": "NEALE2_50_raw",
          "traitReported": "Standing height"
        }
      },
      {
        "indexVariant": {
          "id": "2_96835038_A_G",
          "rsId": "rs78381888"
        },
        "study": {
          "studyId": "GCST006568",
          "traitReported": "Highest math class taken (MTAG) [MTAG]"
        }
      },
      {
        "indexVariant": {
          "id": "2_96835038_A_G",
          "rsId": "rs78381888"
        },
        "study": {
          "studyId": "GCST006573",
          "traitReported": "Self-reported math ability"
        }
      },
      {
        "indexVariant": {
          "id": "2_96835038_A_G",
          "rsId": "rs78381888"
        },
        "study": {
          "studyId": "GCST006569",
          "traitReported": "Self-reported math ability (MTAG) [MTAG]"
        }
      },
      {
        "indexVariant": {
          "id": "2_96858148_G_A",
          "rsId": "rs79460537"
        },
        "study": {
          "studyId": "GCST008839",
          "traitReported": "Height"
        }
      },
      {
        "indexVariant": {
          "id": "2_96900314_C_T",
          "rsId": "rs114707893"
        },
        "study": {
          "studyId": "NEALE2_1697",
          "traitReported": "Comparative height size at age 10"
        }
      },
      {
        "indexVariant": {
          "id": "2_96916498_A_T",
          "rsId": "rs13018621"
        },
        "study": {
          "studyId": "NEALE2_6138_1",
          "traitReported": "College or university degree | qualifications"
        }
      },
      {
        "indexVariant": {
          "id": "2_96989603_A_G",
          "rsId": "rs148947061"
        },
        "study": {
          "studyId": "NEALE2_5375_raw",
          "traitReported": "Longest period of unenthusiasm / disinterest"
        }
      }
    ]
  }
}
```

