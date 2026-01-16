---
title: "backup_hiw_redshift_serverless"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/backup_hiw_redshift_serverless.html"
last_updated: "12/12/2024"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS performs Redshift Serverless backup in the following way:

1. Veeam Backup for AWS uses the [Amazon Redshift Serverless service](https://docs.aws.amazon.com/redshift/latest/mgmt/serverless-snapshots-recovery-points.html) to create a cloud-native backup of the Redshift Serverless namespace, and saves this backup in the same AWS Region in which the source namespace resides.
2. The backup is assigned AWS tags upon creation. Keys and values of AWS tags contain encrypted metadata that helps Veeam Backup for AWS identify the related namespace backup.

Related Topics

* [Backup Chain](backup_chain_redshift_serverless.md)
* [Redshift Serverless Backup Retention](retention_backup_redshift_serverless.md)

Page updated 12/12/2024

Page content applies to build 10.0.0.232
