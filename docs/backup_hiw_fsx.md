---
title: "backup_hiw_fsx"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/backup_hiw_fsx.html"
last_updated: "4/24/2024"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS performs FSx backup in the following way:

1. Veeam Backup for AWS uses the [AWS Backup service](https://docs.aws.amazon.com/aws-backup/latest/devguide/whatisbackup.html) to create a cloud-native backup of the file system, and saves this backup to the specified backup vault in the same AWS Region in which the source file system resides.

The backup is assigned AWS tags upon creation. Keys and values of AWS tags contain encrypted metadata that helps Veeam Backup for AWS identify the related FSx file system backup.

1. If you configure the FSx backup policy to copy backup files to another AWS Region, Veeam Backup for AWS copies the created backup to the target AWS Region in the same AWS account.

Related Topics

* [Backup Chain](backup_chain_fsx.md)
* [FSx Backup Retention](retention_backup_fsx.md)

Page updated 4/24/2024

Page content applies to build 10.0.0.232
