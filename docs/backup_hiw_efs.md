---
title: "backup_hiw_efs"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/backup_hiw_efs.html"
last_updated: "9/6/2024"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS performs EFS backup in the following way:

1. Veeam Backup for AWS uses the [AWS Backup service](https://docs.aws.amazon.com/efs/latest/ug/awsbackup.html) to create a cloud-native backup of the file system, and saves this backup to the specified backup vault in the same AWS Region in which the source file system resides.

The backup is assigned AWS tags upon creation. Keys and values of AWS tags contain encrypted metadata that helps Veeam Backup for AWS identify the related EFS file system backup.

1. If you configure the EFS backup policy to copy backup files to another AWS Region, Veeam Backup for AWS copies the created backup to the target AWS Region in the same AWS account.
2. If you enable EFS indexing in the backup policy settings, Veeam Backup for AWS performs the following operations:

1. Deploys a worker instance in an AWS Region in which the processed file system resides in an AWS account to which the file system belongs — that is, the production AWS account.

By default, Veeam Backup for AWS selects the most appropriate network settings of AWS Regions in production accounts (for example, selects a VPC specified as a mount target for the processed file system). However, you can add specific worker configurations. For more information on worker instances, see [Managing Worker Configurations](worker_settings.md).

1. Mounts the source file system on the worker instance.
2. Reads data from the file system using the worker instance, creates a catalog of files and folders (index) of the system, transfers the index to a backup repository and stores it in the native Veeam format.
3. The EFS index is associated with the cloud-native backup created at step 1 and the backup copy created at step 2. However, if the indexing session does not complete by the time a new backup session starts, a new indexing session is not launched and Veeam Backup for AWS associates the created EFS index with 2 cloud-native backups and backup copies created by 2 backup sessions.

|  |
| --- |
| Note |
| By default, Veeam Backup for AWS compresses data saved to backup repositories. To learn how to encrypt data stored in backup repositories, see [Data Encryption](encryption.md). |

1. When the indexing session completes, removes the worker instance from Amazon EC2.

Related Topics

* [Backup Chain](backup_chain_efs.md)
* [EFS Backup Retention](retention_backup_efs.md)

Page updated 9/6/2024

Page content applies to build 10.0.0.232
