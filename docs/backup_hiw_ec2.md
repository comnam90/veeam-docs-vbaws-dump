---
title: "backup_hiw_ec2"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/backup_hiw_ec2.html"
last_updated: "11/25/2025"
product_version: "10.0.0.232"
---


In this article

Veeam Backup for AWS performs EC2 backup in the following way:

1. Veeam Backup for AWS uses the Amazon EC2 service to [create snapshots of EBS volumes](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-snapshots.html) that are attached to the processed EC2 instance.

1. EBS snapshots are assigned AWS tags upon creation. Keys and values of AWS tags contain encrypted metadata that helps Veeam Backup for AWS identify and manage the related EBS snapshots, use them to perform restore operations, and treat them as a single unit — a cloud-native snapshot.

1. If you enable snapshot replication for the backup policy, Veeam Backup for AWS copies cloud-native snapshots to the target AWS Region and AWS account specified in the backup policy settings.

1. If you enable image-level backup for the backup policy, Veeam Backup for AWS performs the following operations:

1. Deploys a worker instance in an AWS Region where the processed EC2 instance resides.

By default, Veeam Backup for AWS deploys worker instances in the backup account to perform image-level backups and uses the default network settings of AWS Regions to deploy them. However, you can also instruct Veeam Backup for AWS to deploy worker instances in production accounts and add specific worker configurations. For more information on worker instances, see [Managing Worker Instances](workers.md).

|  |
| --- |
| Note |
| To protect EC2 instances whose volumes are encrypted with default AWS managed keys, it is required to deploy worker instances in the production account. |

1. Re-creates the EBS volumes from the cloud-native snapshot created at step 1 and attaches them to the worker instance. To increase backup performance, Veeam Backup for AWS can deploy worker instances with specific instance and volume types and the required number of copies of EBS volumes depending on the snapshot size.
2. Reads data from the EBS volumes on the worker instance, transfers the data to a backup repository and stores it in the native Veeam format.

To reduce the amount of data read from EBS volumes, Veeam Backup for AWS uses the changed block tracking (CBT) mechanism: during incremental backup sessions, Veeam Backup for AWS compares the new cloud-native snapshot with the previous one and reads only those data blocks that have changed since the previous backup session. If CBT cannot be used, Veeam Backup for AWS reads all data from the re-created EBS volumes. For more information, see [Changed Block Tracking](cbt.md).

|  |
| --- |
| Note |
| By default, Veeam Backup for AWS compresses data saved to backup repositories. To learn how to encrypt data stored in backup repositories, see [Data Encryption](encryption.md). |

1. Removes the worker instance from Amazon EC2 when the backup session completes.

1. If you enable the [backup archiving mechanism](backup_archiving.md), Veeam Backup for AWS performs the following operations:

1. Deploys a worker instance in the backup account in an AWS Region where a backup repository storing backed-up data resides.
2. Retrieves data from the backup repository and transfers it to the archive backup repository.
3. Removes the worker instance from Amazon EC2 when the archive session completes.

Related Topics

* [Snapshot Chain](snapshot_chain.md)
* [Backup Chain](backup_chain.md)
* [Retention Policies](backup_retention.md)

Page updated 11/25/2025

Page content applies to build 10.0.0.232
