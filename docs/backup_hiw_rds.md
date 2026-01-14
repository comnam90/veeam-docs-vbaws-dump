---
title: "backup_hiw_rds"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/backup_hiw_rds.html"
last_updated: "11/28/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS performs RDS backup in the following way:

1. Veeam Backup for AWS uses the Amazon RDS service to [create a storage volume snapshot](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CreateSnapshot.html) of the processed DB instance (that is, a DB snapshot) or of the processed Aurora DB cluster (that is, a DB cluster snapshot).

The snapshot is assigned AWS tags upon creation. Keys and values of AWS tags contain encrypted metadata that helps Veeam Backup for AWS identify the related snapshot. For the Aurora DB cluster metadata saved in AWS tags also contains information on every DB instance launched in the cluster.

1. If you enable snapshot replication for the backup policy, Veeam Backup for AWS copies the snapshot to the target AWS Region and AWS account specified in the backup policy settings.

1. If you enable image-level backup for the backup policy, Veeam Backup for AWS performs the following operations:

1. Deploys a worker instance in an AWS Region in which the processed DB instance resides in an AWS account to which the instance belongs — that is, the production AWS account.

By default, Veeam Backup for AWS selects the most appropriate network settings of AWS Regions in production accounts. However, you can add specific worker configurations. For more information on worker instances, see [Managing Worker Configurations](worker_settings.md).

1. Creates 2 security groups that are associated with the source DB instance and the worker instance to allow direct network traffic between them. The security group associated with the source instance allows inbound traffic through opened on the instance port only from the worker instance, whereas the security group associated with the worker instance allows outbound traffic through opened on the instance port only to the source instance.
2. [Applies only to Microsoft SQL Server DB instances] Uses the Amazon RDS service to [create a native backup of the SQL Server DB instance](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/SQLServer.Procedural.Importing.html), and saves this backup to a temporary Amazon S3 bucket in the same AWS Region in which the source DB instance resides. Then, reads data from the native SQL Server backup, transfers the data to the target backup repository and stores it in the native Veeam format.

1. [Applies only to PostgreSQL DB instances] Uses the worker instance to retrieve dumps, triggers, stored procedures and transfers the retrieved data to the target backup repository and stores the data in the native Veeam format. Then, uses PostgreSQL capabilities to dump out PostgreSQL databases.
2. Removes the worker instance and 2 created security groups from AWS when the backup session completes.
3. [Applies only to Microsoft SQL Server DB instances] Removes the temporary Amazon S3 bucket from AWS if it is not currently used by any data protection operations.

1. If you enable the [backup archiving mechanism](backup_archiving_rds.md), Veeam Backup for AWS performs the following operations:

1. Deploys a worker instance in an AWS Region where a backup repository storing backed-up data resides in the [backup account](worker_options.md).
2. Retrieves data from the backup repository and transfers it to the archive backup repository.
3. Removes the worker instance from Amazon EC2 when the archive session completes.

Related Topics

* [Snapshot Chain](snapshot_chain_rds.md)
* [Backup Chain](backup_chain_rds.md)

Page updated 11/28/2025

Page content applies to build 10.0.0.232
