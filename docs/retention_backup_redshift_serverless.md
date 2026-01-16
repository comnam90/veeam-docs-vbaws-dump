---
title: "retention_backup_redshift_serverless"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/retention_backup_redshift_serverless.html"
last_updated: "10/15/2024"
product_version: "10.0.0.232"
---


In this article

For Redshift Serverless backups, Veeam Backup for AWS retains restore points for the period of time specified in [backup scheduling settings](add_policy_schedule_retention_redshift_serverless.md).

During every successful backup session, Veeam Backup for AWS creates a restore point and saves the date, time and applied retention settings in the restore point metadata. If Veeam Backup for AWS detects that the period of time for which the restore point was stored exceeds the period specified in the retention settings, it automatically removes the restore point from the Redshift Serverless chain. You can also remove unnecessary Redshift Serverless backups manually as described in section [Removing Redshift Serverless Backups](backups_remove_redshift_serverless.md).

[![Redshift Backup Retention](images/redshift_backup_retention.webp)](images/redshift_backup_retention.webp "Redshift Backup Retention")

|  |
| --- |
| Note |
| Veeam Backup for AWS does not apply retention policy to Redshift Serverless backups created manually. For learn how to remove them, see [Removing Redshift Serverless Backups Created Manually](backups_remove_individual_redshift_serverless.md). |

Page updated 10/15/2024

Page content applies to build 10.0.0.232
