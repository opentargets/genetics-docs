# How to find studies and lead variants assigned by L2G

Finding which studies \(or traits\) and lead variants are ****assigned to a gene as a result of the L2G pipeline.

`Query`

```
  studiesAndLeadVariantsForGeneByL2G(geneId: "ENSG00000158158") {
    variant {
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
    "studiesAndLeadVariantsForGeneByL2G": [
      {
        "variant": {
          "id": "2_97032743_A_C",
          "rsId": "rs13005320"
        },
        "study": {
          "studyId": "NEALE2_30150",
          "traitReported": "Eosinophill count"
        }
      },
      {
        "variant": {
          "id": "2_96535945_G_A",
          "rsId": "rs2579500"
        },
        "study": {
          "studyId": "GCST007065",
          "traitReported": "Eosinophil counts"
        }
      },
      {
        "variant": {
          "id": "2_96989603_A_G",
          "rsId": "rs148947061"
        },
        "study": {
          "studyId": "NEALE2_5375_raw",
          "traitReported": "Longest period of unenthusiasm / disinterest"
        }
      },
      {
        "variant": {
          "id": "2_96941334_A_G",
          "rsId": "rs6728642"
        },
        "study": {
          "studyId": "GCST005081",
          "traitReported": "Bipolar disorder lithium response (continuous) or schizophrenia"
        }
      },
      {
        "variant": {
          "id": "2_96535945_G_A",
          "rsId": "rs2579500"
        },
        "study": {
          "studyId": "NEALE2_30210_raw",
          "traitReported": "Eosinophill percentage"
        }
      },
      {
        "variant": {
          "id": "2_96502225_T_C",
          "rsId": "rs2579505"
        },
        "study": {
          "studyId": "NEALE2_30150",
          "traitReported": "Eosinophill count"
        }
      },
      {
        "variant": {
          "id": "2_96388214_TTAGA_T",
          "rsId": "rs35205062"
        },
        "study": {
          "studyId": "NEALE2_30150",
          "traitReported": "Eosinophill count"
        }
      },
      {
        "variant": {
          "id": "2_96535945_G_A",
          "rsId": "rs2579500"
        },
        "study": {
          "studyId": "GCST004600",
          "traitReported": "Eosinophil percentage of white cells"
        }
      },
      {
        "variant": {
          "id": "2_96535945_G_A",
          "rsId": "rs2579500"
        },
        "study": {
          "studyId": "GCST004606",
          "traitReported": "Eosinophil counts"
        }
      },
      {
        "variant": {
          "id": "2_96916498_A_T",
          "rsId": "rs13018621"
        },
        "study": {
          "studyId": "NEALE2_6138_1",
          "traitReported": "College or university degree | qualifications"
        }
      },
      {
        "variant": {
          "id": "2_96564337_G_A",
          "rsId": "rs2708977"
        },
        "study": {
          "studyId": "GCST004623",
          "traitReported": "Neutrophil percentage of granulocytes"
        }
      },
      {
        "variant": {
          "id": "2_96564337_G_A",
          "rsId": "rs2708977"
        },
        "study": {
          "studyId": "GCST004617",
          "traitReported": "Eosinophil percentage of granulocytes"
        }
      },
      {
        "variant": {
          "id": "2_96535945_G_A",
          "rsId": "rs2579500"
        },
        "study": {
          "studyId": "GCST004624",
          "traitReported": "Sum eosinophil basophil counts"
        }
      },
      {
        "variant": {
          "id": "2_96663115_C_T",
          "rsId": "rs17634791"
        },
        "study": {
          "studyId": "NEALE2_30180_raw",
          "traitReported": "Lymphocyte percentage"
        }
      },
      {
        "variant": {
          "id": "2_96835038_A_G",
          "rsId": "rs78381888"
        },
        "study": {
          "studyId": "GCST006568",
          "traitReported": "Highest math class taken (MTAG) [MTAG]"
        }
      },
      {
        "variant": {
          "id": "2_96835038_A_G",
          "rsId": "rs78381888"
        },
        "study": {
          "studyId": "GCST006569",
          "traitReported": "Self-reported math ability (MTAG) [MTAG]"
        }
      },
      {
        "variant": {
          "id": "2_96835038_A_G",
          "rsId": "rs78381888"
        },
        "study": {
          "studyId": "GCST006573",
          "traitReported": "Self-reported math ability"
        }
      },
      {
        "variant": {
          "id": "2_96297946_A_G",
          "rsId": "rs772178"
        },
        "study": {
          "studyId": "GCST006258",
          "traitReported": "Diastolic blood pressure"
        }
      },
      {
        "variant": {
          "id": "2_96617939_T_C",
          "rsId": "rs183743021"
        },
        "study": {
          "studyId": "NEALE2_3062_raw",
          "traitReported": "Forced vital capacity (fvc)"
        }
      },
      {
        "variant": {
          "id": "2_96479597_T_TTG",
          "rsId": "rs113359549"
        },
        "study": {
          "studyId": "GCST004606",
          "traitReported": "Eosinophil counts"
        }
      },
      {
        "variant": {
          "id": "2_96739703_G_A",
          "rsId": "rs2271893"
        },
        "study": {
          "studyId": "GCST006585_941",
          "traitReported": "Blood protein levels [LMAN2L]"
        }
      },
      {
        "variant": {
          "id": "2_96752905_T_G",
          "rsId": "rs189255944"
        },
        "study": {
          "studyId": "NEALE2_50_raw",
          "traitReported": "Standing height"
        }
      },
      {
        "variant": {
          "id": "2_96686103_A_G",
          "rsId": "rs7599598"
        },
        "study": {
          "studyId": "GCST006166_6",
          "traitReported": "Diastolic blood pressure x alcohol consumption interaction (2df test) [Asian, EA]"
        }
      },
      {
        "variant": {
          "id": "2_96686103_A_G",
          "rsId": "rs7599598"
        },
        "study": {
          "studyId": "GCST006190",
          "traitReported": "Diastolic blood pressure x smoking status (ever vs never) interaction (2df test)"
        }
      },
      {
        "variant": {
          "id": "2_96686103_A_G",
          "rsId": "rs7599598"
        },
        "study": {
          "studyId": "GCST006190_3",
          "traitReported": "Diastolic blood pressure x smoking status (ever vs never) interaction (2df test) [EA]"
        }
      },
      {
        "variant": {
          "id": "2_96686103_A_G",
          "rsId": "rs7599598"
        },
        "study": {
          "studyId": "GCST006193_3",
          "traitReported": "Diastolic blood pressure x smoking status (current vs non-current) interaction (2df test) [EA]"
        }
      },
      {
        "variant": {
          "id": "2_96686103_A_G",
          "rsId": "rs7599598"
        },
        "study": {
          "studyId": "GCST006166_8",
          "traitReported": "Diastolic blood pressure x alcohol consumption interaction (2df test) [EA]"
        }
      },
      {
        "variant": {
          "id": "2_96686103_A_G",
          "rsId": "rs7599598"
        },
        "study": {
          "studyId": "GCST006193",
          "traitReported": "Diastolic blood pressure x smoking status (current vs non-current) interaction (2df test)"
        }
      },
      {
        "variant": {
          "id": "2_97131943_T_C",
          "rsId": "rs13390019"
        },
        "study": {
          "studyId": "GCST008757",
          "traitReported": "Alcohol consumption"
        }
      },
      {
        "variant": {
          "id": "2_96510897_C_T",
          "rsId": "rs2579503"
        },
        "study": {
          "studyId": "GCST007269",
          "traitReported": "Pulse pressure"
        }
      },
      {
        "variant": {
          "id": "2_96377542_G_GT",
          "rsId": "rs561539268"
        },
        "study": {
          "studyId": "NEALE2_1687",
          "traitReported": "Comparative body size at age 10"
        }
      },
      {
        "variant": {
          "id": "2_96381261_G_A",
          "rsId": "rs1081707"
        },
        "study": {
          "studyId": "GCST007268",
          "traitReported": "Diastolic blood pressure"
        }
      },
      {
        "variant": {
          "id": "2_96506388_G_A",
          "rsId": "rs1866444"
        },
        "study": {
          "studyId": "GCST008413",
          "traitReported": "Core binding factor acute myeloid leukemia"
        }
      },
      {
        "variant": {
          "id": "2_96858148_G_A",
          "rsId": "rs79460537"
        },
        "study": {
          "studyId": "GCST008839",
          "traitReported": "Height"
        }
      },
      {
        "variant": {
          "id": "2_96617939_T_C",
          "rsId": "rs183743021"
        },
        "study": {
          "studyId": "NEALE2_20153_raw",
          "traitReported": "Forced expiratory volume in 1-second (fev1), predicted"
        }
      },
      {
        "variant": {
          "id": "2_96617939_T_C",
          "rsId": "rs183743021"
        },
        "study": {
          "studyId": "NEALE2_20015_raw",
          "traitReported": "Sitting height"
        }
      },
      {
        "variant": {
          "id": "2_96752905_T_G",
          "rsId": "rs189255944"
        },
        "study": {
          "studyId": "NEALE2_20151_raw",
          "traitReported": "Forced vital capacity (fvc), best measure"
        }
      },
      {
        "variant": {
          "id": "2_96900314_C_T",
          "rsId": "rs114707893"
        },
        "study": {
          "studyId": "NEALE2_1697",
          "traitReported": "Comparative height size at age 10"
        }
      },
      {
        "variant": {
          "id": "2_96710670_A_AT",
          "rsId": "rs57195239"
        },
        "study": {
          "studyId": "GCST008103",
          "traitReported": "Bipolar disorder"
        }
      },
      {
        "variant": {
          "id": "2_96739703_G_A",
          "rsId": "rs2271893"
        },
        "study": {
          "studyId": "GCST001358",
          "traitReported": "Bipolar disorder"
        }
      },
      {
        "variant": {
          "id": "2_96714492_T_G",
          "rsId": "rs56361249"
        },
        "study": {
          "studyId": "GCST003962",
          "traitReported": "Bipolar disorder"
        }
      }
    ]
  }
}
```

