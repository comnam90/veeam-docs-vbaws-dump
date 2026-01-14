---
title: "cbt"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/cbt.html"
last_updated: "12/8/2025"
product_version: "10.0.0.232"
---


In this article

The changed block tracking (CBT) mechanism allows Veeam Backup for AWS to reduce the amount of data read from processed EBS volumes, and to increase the speed and efficiency of incremental backups:

* During a full backup session, Veeam Backup for AWS reads only written data blocks, while unallocated data blocks are filtered out.
* During an incremental backup session, Veeam Backup for AWS reads only those data blocks that have changed since the previous backup session.

To detect unallocated and changed data blocks, CBT relies on [EBS Direct APIs](https://docs.aws.amazon.com/ebs/latest/APIReference/Welcome.html).

1. During the first (full) backup session, Veeam Backup for AWS [creates a cloud-native snapshot](backup_hiw_ec2.md#step1) of an EC2 instance. To do that, Veeam Backup for AWS sends API requests to access the content of the snapshot and to detect unallocated data blocks.
2. During subsequent sessions, new cloud-native snapshots are created. Veeam Backup for AWS sends API requests to access and to compare the content of the snapshot created during the previous backup session and the snapshot created during the current backup session. This allows Veeam Backup for AWS to detect data blocks that have changed since the previous backup session.

|  |
| --- |
| Note |
| The CBT mechanism is optional for SLA-based backup policies. However, to increase the speed and efficiency of incremental backups, it is recommended that you enable CBT in SLA templates. For more information, see [CBT Impact on Snapshot Retention](cbt_retention.md). |

Limitations for Changed Block Tracking

Veeam Backup for AWS cannot use CBT for EC2 instances that reside in AWS Regions where EBS Direct APIs are not available.

If CBT cannot be used, Veeam Backup for AWS reads the whole content of processed EBS volumes and compares it with backed-up data that already exists in the backup repository. In this case, the completion time of incremental backups may occur to grow.

Related Topics

[CBT Impact on Snapshot Retention](cbt_retention.md)

Page updated 12/8/2025

Page content applies to build 10.0.0.232
