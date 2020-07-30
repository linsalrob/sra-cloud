# sra-cloud

These are use contributed ways to search and access SRA data in the cloud. To contribute to this repository, fork it using the fork button above, make some changes, add your name, and then submit a PR for those changes.

Be sure to add your name so you can get credit. If you want to provide more information or help, email [Rob Edwards](https://edwards.sdsu.edu/research/)

# Big Table Queries

Use the [Google-NCBI BigTable Query Creator](https://console.cloud.google.com/bigquery) to try out your queries and run them

## More documentation

- [The BigQuery Metadata Table](https://www.ncbi.nlm.nih.gov/sra/docs/sra-bigquery-metadata-table/) column definitions


## Commonly used field mappings

Field | Contents | Abbreviation
--- | --- | ---
`acc` | Run | SRR######
`sample_acc` | Sample Accession | SRS########
`biosample` | BioSample ID | SAMN######## 
`sra_study` | Study Accession | SRP########
`bioproject` | BioProject Accession | PRJNA########


## Counting all runs associated with a study accession
Submitted by: Rob Edwards

Run accession: [SRP216273](https://trace.ncbi.nlm.nih.gov/Traces/study/?acc=SRP216273&o=acc_s%3Aa)

```
select count(acc) from `nih-sra-datastore.sra.metadata` where sra_study = 'SRP216273';
```
