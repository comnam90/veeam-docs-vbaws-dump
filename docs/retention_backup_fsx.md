---
title: "retention_backup_fsx"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/retention_backup_fsx.html"
last_updated: "8/6/2024"
product_version: "10.0.0.232"
---


In this article

For FSx file system backups, Veeam Backup for AWS retains restore points for the period of time specified in [backup scheduling settings](add_policy_schedule_retention_fsx.md).

During every successful backup session, Veeam Backup for AWS creates a restore point and saves the date, time and applied retention settings in the restore point metadata. If Veeam Backup for AWS detects that the period of time for which the restore point was stored exceeds the period specified in the retention settings, it automatically removes the restore point from the FSx backup chain. You can also remove unnecessary FSx backups manually as described in section [Removing FSx Backups](backups_remove_fsx.md).

[![FSx Backup Retention](images/fsx_backups_retention.PNG)](images/fsx_backups_retention.PNG "FSx Backup Retention")

|  |
| --- |
| Note |
| Veeam Backup for AWS does not apply retention policy to FSx backups created manually. To learn how to remove them, see [Removing FSx Backups Created Manually](backups_remove_individual_fsx.md). |

Page updated 8/6/2024

Page content applies to build 10.0.0.232
