---
title: "backup_retention"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/backup_retention.html"
last_updated: "12/8/2025"
product_version: "10.0.0.232"
---


In this article

Cloud-native snapshots, snapshot replicas and image-level backups created by backup policies are not kept forever — they are removed according to retention policy settings specified while creating the policies.

Depending on the data protection scenario, retention policy can be specified:

* In restore points — for cloud-native snapshots and snapshot replicas by schedule-based backup policies.

The snapshot chain can contain only the allowed number of restore points. If the number of allowed restore points is exceeded, Veeam Backup for AWS removes the earliest restore point from the snapshot chain. For more information, see [EC2 Backup Retention](retention_backup.md) and [RDS Backup Retention](retention_backup_rds.md).

* In days/months/years — for image-level backups and archived backups, as well as for cloud-native snapshots and snapshot replicas produced by SLA-based backup policies.

Restore points in the backup chain (either standard or archive) can be stored in the backup repository for the allowed period of time. If a restore point is older than the specified time limit, Veeam Backup for AWS removes it from the backup chain. For more information, see sections [EC2 Snapshot Retention](retention_snapshots.md), [EC2 Backup Retention](retention_backup.md), [RDS Backup Retention](retention_backup_rds.md), [Redshift Backup Retention](retention_backup_redshift.md), [DynamoDB Backup Retention](retention_backup_dynamo.md), [EFS Backup Retention](retention_backup_efs.md), [FSx Backup Retention](retention_backup_fsx.md) and [VPC Configuration Backup Retention](retention_backup_vpc.md).

|  |
| --- |
| Note |
| When configuring policy scheduling, consider that Veeam Backup for AWS runs retention sessions at 4:00 AM by default, according to the time zone set on the backup appliance. If you schedule backup policies to execute at 4:00 AM, the backup policies and retention tasks will be queued. |

You can also specify global retention settings for obsolete snapshots and replicas. For more information, see [Configuring Global Retention Settings](retention_settings.md#snapshots).

Related Topics

* [Creating EC2 Backup Policies](add_policy_schedule_retention.md)
* [Creating RDS Backup Policies](add_policy_schedule_retention_rds.md)
* [Creating Redshift Clusters Backup Policies](add_policy_schedule_retention_redshift.md)
* [Creating Redshift Serverless Backup Policies](add_policy_schedule_retention_redshift_serverless.md)
* [Creating DynamoDB Backup Policies](add_policy_schedule_retention_dynamo.md)
* [Creating EFS Backup Policies](add_policy_schedule_retention_efs.md)
* [Creating FSx Backup Policies](add_policy_schedule_retention_fsx.md)
* [Editing VPC Configuration Backup Policy](vpc_policy_retention.md)

Page updated 12/8/2025

Page content applies to build 10.0.0.232
