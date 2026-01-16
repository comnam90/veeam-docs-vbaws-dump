---
title: "schedule_weekly_reshift_serverless"
product: "vbaws"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbaws/guide/schedule_weekly_reshift_serverless.html"
last_updated: "9/23/2025"
product_version: "10.0.0.232"
---


In this article

To create a weekly schedule for the backup policy, at the Schedule step of the wizard, do the following:

1. Set the Weekly schedule toggle to On and click Edit Weekly Settings.
2. In the Create weekly schedule section, select weekdays when the backup policy will create namespace backups.
3. Use the Create restore point at drop-down list to schedule a specific time for the backup policy to run.
4. In the Weekly retention section, specify the number of days (or months) for which you want to keep restore points in a backup chain.

If a restore point is older than the specified time limit, Veeam Backup for AWS removes the restore point from the chain. For more information, see [Redshift Serverless Backup Retention](retention_backup_redshift_serverless.md).

1. To save changes made to the backup policy settings, click Apply.

|  |
| --- |
| Tip |
| Veeam Backup for AWS will start applying the configured retention settings as soon as the backup policy produces restore points. Even if you disable the weekly schedule after the restore points are created, the retention policy will still be applied to these restore points. As a workaround, you can modify the configured retention settings. |

[![Creating Redshift Serverless Backup Policy](images/schedule_weekly_redshift_serverless.webp)](images/schedule_weekly_redshift_serverless.webp "Creating Redshift Serverless Backup Policy")

Page updated 9/23/2025

Page content applies to build 10.0.0.232
