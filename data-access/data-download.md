# Data Download

You can get all data from Open Targets Genetics via:

* EMBL-EBI FTP, database [Open Targets Genetics](https://ftp.ebi.ac.uk/pub/databases/opentargets/genetics/)
* Google BigQuery, project [open-targets-genetics:genetics](https://console.cloud.google.com/bigquery?project=open-targets-genetics\&p=open-targets-genetics\&d=genetics\&page=dataset)
* [Google Cloud Storage](https://console.cloud.google.com/storage/browser/open-targets-genetics-releases?project=open-targets-genetics\&folder\&organizationId) (GCS) paywalled public bucket

{% hint style="warning" %}
Please note that if you download this data using Google Cloud Storage, all charges to bucket `open-targets-genetics-releases` will be billed to the requester.&#x20;

Please refer to the [Requester Pays](https://cloud.google.com/storage/docs/requester-pays?hl=en\_US&\_ga=2.173037540.-691607024.1554819113) feature for Google Cloud Storage for more detail.
{% endhint %}

## Data Schema

The list of datasets with each corresponding data schema

{% hint style="info" %}
Please change the URL tags to their corresponding tables, stated above, as required.
{% endhint %}

| Folder name       | Format  | Spark Schema                                                                                                                   | SQL Schema (Clickhouse Dialect)                                                                                           |
| ----------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------- |
| variant-index     | parquet | -                                                                                                                              | -                                                                                                                         |
| v2g               | jsonl   | [schema link](https://github.com/opentargets/genetics-pipe/blob/19.03.10/src/main/scala/ot/geckopipe/index/V2GIndex.scala#L36) | [schema link](https://github.com/opentargets/genetics-backend/blob/19.03.08/loaders/clickhouse/v2g\_log.sql)              |
| v2d               | jsonl   | [schema link](https://github.com/opentargets/genetics-pipe/blob/19.03.10/src/main/scala/ot/geckopipe/index/V2DIndex.scala#L12) | [schema link](https://github.com/opentargets/genetics-backend/blob/19.03.08/loaders/clickhouse/v2d\_log.sql)              |
| d2v2g             | jsonl   | -                                                                                                                              | [schema link](https://github.com/opentargets/genetics-backend/blob/19.03.08/loaders/clickhouse/d2v2g\_log.sql)            |
| lut/genes-index   | jsonl   | -                                                                                                                              | [schema link](https://github.com/opentargets/genetics-backend/blob/19.03.08/loaders/clickhouse/genes.sql)                 |
| lut/overlap-index | jsonl   | -                                                                                                                              | [schema link](https://github.com/opentargets/genetics-backend/blob/19.03.08/loaders/clickhouse/studies\_overlap\_log.sql) |
| lut/study-index   | jsonl   | -                                                                                                                              | [schema link](https://github.com/opentargets/genetics-backend/blob/19.03.08/loaders/clickhouse/studies\_log.sql)          |
| lut/variant-index | jsonl   | -                                                                                                                              | [schema link](https://github.com/opentargets/genetics-backend/blob/19.03.08/loaders/clickhouse/variants\_log.sql)         |

## Some Tips

### Previewing datasets from the GCS bucket

The `gsutil` command can be used to preview datasets prior to downloading:

```bash
gsutil cat 'gs://open-targets-genetics-releases/19.03.04/lut/variant-index/part-*' | head -1 | jq .
{
  "chr_id": "1",
  "position": 55545,
  "ref_allele": "C",
  "alt_allele": "T",
  "rs_id": "rs28396308",
  "most_severe_consequence": "downstream_gene_variant",
  "gene_id_any_distance": 13546,
  "gene_id_any": "ENSG00000186092",
  "gene_id_prot_coding_distance": 13546,
  "gene_id_prot_coding": "ENSG00000186092",
  "raw": 0.028059,
  "phred": 3.065,
  "gnomad_afr": 0.3264216148287779,
  "gnomad_amr": 0.4533582089552239,
  "gnomad_asj": 0.26666666666666666,
  "gnomad_eas": 0.35822021116138764,
  "gnomad_fin": 0.31313131313131315,
  "gnomad_nfe": 0.26266330506532204,
  "gnomad_nfe_est": 0.3397858319604613,
  "gnomad_nfe_nwe": 0.23609443777511005,
  "gnomad_nfe_onf": 0.2256,
  "gnomad_nfe_seu": 0.1,
  "gnomad_oth": 0.27403846153846156
}
```

### Loading data into a ClickHouse instance

There is an [initial bash](https://github.com/opentargets/genetics-backend/blob/19.03.08/loaders/clickhouse/create\_and\_load\_everything\_from\_scratch.sh) script you can use in order to load all data into a ClickHouse instance. In that script, you will find lines like this

```bash
echo create studies tables
clickhouse-client -m -n < studies_log.sql
gsutil cat "${base_path}/lut/study-index/part-*" | clickhouse-client -h 127.0.0.1 --query="insert into ot.studies_log format JSONEachRow "
clickhouse-client -m -n < studies.sql
clickhouse-client -m -n -q "drop table ot.studies_log;"
```
