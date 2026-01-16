---
title: "retention_backup_vpc"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/retention_backup_vpc.html"
last_updated: "5/21/2025"
product_version: "10.0.0.232"
---


In this article

For VPC configuration backups, Veeam Backup for AWS retains restore points for the period of time specified in [backup retention settings](vpc_policy_retention.md).

During every successful backup session, Veeam Backup for AWS creates a restore point and saves the date, time and the applied retention settings in the restore point metadata. If Veeam Backup for AWS detects that the period of time for which the restore point was stored exceeds the period specified in the retention settings, it automatically removes the restore point from the VPC configuration backup chain. You can also remove unnecessary VPC configuration backups manually as described in section [Removing VPC Configuration Backups](backups_remove_vpc.md).

|  |
| --- |
| Note |
| Veeam Backup for AWS applies the retention settings configured for the [VPC Configuration Backup policy](vpc_policy_retention.md) both to VPC configuration backups stored in the Veeam Backup for AWS database and to VPC configuration backups stored in the backup repository selected for the policy. For VPC configuration backups stored in backup repositories that are not specified in the VPC Configuration Backup policy settings, Veeam Backup for AWS applies retention settings saved in the backup metadata. |

[![VPC Backup Retention](images/vpc_backups_retention.webp)](images/vpc_backups_retention.webp "VPC Backup Retention")

Page updated 5/21/2025

Page content applies to build 10.0.0.232
