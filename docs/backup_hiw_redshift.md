---
title: "backup_hiw_redshift"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/backup_hiw_redshift.html"
last_updated: "4/2/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS performs Redshift clusters backup in the following way:

1. Veeam Backup for AWS uses the [AWS Backup service](https://docs.aws.amazon.com/redshift/latest/mgmt/managing-aws-backup.html) to create a cloud-native backup of the Redshift cluster, and saves this backup to the specified backup vault in the same AWS Region in which the source cluster resides.
2. The backup is assigned AWS tags upon creation. Keys and values of AWS tags contain encrypted metadata that helps Veeam Backup for AWS identify the related cluster backup.

Related Topics

* [Backup Chain](backup_chain_redshift.md)
* [Redshift Backup Retention](retention_backup_redshift.md)

Page updated 4/2/2025

Page content applies to build 10.0.0.232
