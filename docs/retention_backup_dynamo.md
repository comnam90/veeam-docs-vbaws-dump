---
title: "retention_backup_dynamo"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/retention_backup_dynamo.html"
last_updated: "8/6/2024"
product_version: "10.0.0.232"
---


In this article

For DynamoDB backups, Veeam Backup for AWS retains restore points for the period of time specified in [backup scheduling settings](add_policy_schedule_retention_dynamo.md).

During every successful backup session, Veeam Backup for AWS creates a restore point and saves the date, time and applied retention settings in the restore point metadata. If Veeam Backup for AWS detects that the period of time for which the restore point was stored exceeds the period specified in the retention settings, it automatically removes the restore point from the DynamoDB chain. You can also remove unnecessary DynamoDB backups manually as described in section [Removing DynamoDB Backups](backups_remove_dynamo.md).

[![DynamoDB Backup Retention](images/dynamo_backup_retention.webp)](images/dynamo_backup_retention.webp "DynamoDB Backup Retention")

|  |
| --- |
| Note |
| Veeam Backup for AWS does not apply retention policy to DynamoDB backups created manually. To learn how to remove them, see [Removing DynamoDB Backups Created Manually](backups_remove_individual_dynamo.md). |

Page updated 8/6/2024

Page content applies to build 10.0.0.232
