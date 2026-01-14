---
title: "backup_hiw_dynamo"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/backup_hiw_dynamo.html"
last_updated: "2/9/2024"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS performs DynamoDB backup in the following way:

1. Veeam Backup for AWS uses the [AWS Backup service](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/CreateBackupAWS.html) to create a cloud-native backup of the DynamoDB table, and saves this backup to the specified backup vault in the same AWS Region in which the source table resides.

The backup is assigned AWS tags upon creation. Keys and values of AWS tags contain encrypted metadata that helps Veeam Backup for AWS identify the related table backup.

1. If you configure the DynamoDB backup policy to copy backup files to another AWS Region, Veeam Backup for AWS copies the created backup to the target AWS Region in the same AWS account.

Related Topics

* [Backup Chain](backup_chain_dynamo.md)
* [DynamoDB Backup Retention](retention_backup_dynamo.md)

Page updated 2/9/2024

Page content applies to build 10.0.0.232
